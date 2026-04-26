# Algorithmic Detectors — `/paap-eval` Phase 2 Reference

> Per-principle pattern-match detector logic for the 13 algorithmic principles in the [PaaP rubric](../../../04-RUBRIC/principles.md). Loaded by [`paap-eval/SKILL.md`](../SKILL.md) Phase 2.

**Status:** v0.3-dev on a v0.2 Stage 1b baseline. Each detector outputs `grade + confidence + evidence + notes`. Persona variants modulate thresholds (see grade-mapping tables per principle). The 12 v0.2 detectors were validated against the Stage 1d 4-skill calibration set; the v0.3 addition (Detector 23 — host-portable) is wired into Phase 2 but has not yet been calibration-tested at 25-principle scale.

---

## How detectors work

Every detector is a deterministic function over the SKILL.md content (plus archetype context from Phase 1):

```
detector(skill_content, archetype, persona) -> {
  grade:      A+ | A | B+ | B | C | D | F | error,
  confidence: high | medium | low,
  evidence:   ["L<n>: <quoted line>", ...],
  notes:      "one-line context"
}
```

**Persona modulation rule of thumb:**
- `strict-academic` raises the bar by ~0.5 grade for borderline cases (B+ → B, A → A-)
- `pragmatic-practitioner` (default) is the calibrated baseline
- `charitable-newcomer` lowers the bar by ~0.5 grade (rewards visible effort)

Persona never moves a clear A to C or vice versa — only borderline calls.

**Evidence format:** `L<line_no>: <quoted snippet>`. Phase 5's report uses these for traceable per-principle scoring.

**Confidence rule:** detectors report `low` whenever the pattern they're matching has known false-positive or false-negative cases that the detector can't disambiguate. Phase 4's synthesis flags low-confidence principles for human review.

---

## Detector 1 — Principle #1: Description as router

**Reference:** [principles.md #1](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** All (Universal)

### Detector strategy

Parse the YAML frontmatter `description` field. Count three signals:

```bash
# Extract description from YAML frontmatter
desc=$(awk '/^---$/{f=!f; next} f && /^description:/{flag=1} flag && /^[a-z_]+:/&&!/^description:/{flag=0} flag' SKILL.md | sed 's/^description: *//')

# Count anti-triggers
anti_triggers=$(echo "$desc" | grep -ciE "do not use|don['']t use|not for[: ]")

# Count trigger phrases (use when ..., when you ...)
triggers=$(echo "$desc" | grep -ciE "use when|when you|provide [a-z]|trigger")

# Description length (in chars; spec caps at 1024)
desc_len=${#desc}
```

### Grade mapping

| Anti-triggers | Triggers | Length | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| ≥2 | ≥2 | 200-1000 | A | A | A+ |
| ≥1 | ≥2 | 200-1000 | B+ | A | A |
| 0 | ≥2 | 200-1000 | C | B | B+ |
| ≥2 | ≥1 | 50-200 | B | B+ | A |
| 0 | 0 | <50 | F | F | D |
| 0 | ≥1 | any | C | C | B |

### Confidence

- **high:** description follows the canonical "<what> Use when X. Do NOT use for Y." pattern
- **medium:** description has triggers OR anti-triggers but not both
- **low:** description is unstructured prose without clear signals

### Evidence format

Quote the description's anti-trigger lines and the first trigger phrase. Example:
```
L3: "description: Generate a brief... Use when scheduled with someone new..."
L3: "...Do NOT use for people you already know..."
```

### Known limitations

- Multi-line YAML descriptions (using `>` block scalar) require careful parsing; fall back to `low` confidence if AWK can't extract cleanly.
- Skills with `description` split across multiple lines without explicit `>` may produce parsing artifacts.
- Anti-triggers in non-English will fail to match; flag as low confidence with note.

---

## Detector 2 — Principle #2: Route before work

**Reference:** [principles.md #2](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Detector strategy

Detect a Phase-0-equivalent section before any other phase. Three positive signals:

```bash
# Look for explicit Phase 0 / Pre-Phase / Routing heading before any other phase
heading_pattern='^##[[:space:]]*(Pre-Phase|Phase 0|Phase 0:|Routing|Classification|Configuration)'
first_routing=$(grep -nE "$heading_pattern" SKILL.md | head -1 | cut -d: -f1)

# Find first content phase (Phase 1, Phase 2, etc.)
first_work=$(grep -nE '^##[[:space:]]*(Phase [1-9]|Step [1-9])' SKILL.md | head -1 | cut -d: -f1)

# STOP-conditions count (early-exit patterns)
stop_count=$(grep -ciE 'STOP\.|STOP:|stop with|do not proceed' SKILL.md)

# Decision-tree presence (if/then patterns or branching)
decision_tree=$(grep -ciE '^- (If|Is) .+\?|→ (yes|no)|→ STOP' SKILL.md)
```

### Grade mapping

A skill earns the highest grade when it has a routing heading before work, ≥1 STOP condition, and a visible decision tree.

| Routing before work? | STOP conditions | Decision tree | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| Yes | ≥2 | Yes | A+ | A+ | A+ |
| Yes | 1 | Yes | A | A | A+ |
| Yes | ≥1 | No | B+ | A- | A |
| Yes | 0 | No | C | B | B+ |
| No | ≥1 | Yes | C | B | B |
| No | 0 | No | F | F | D |

### Confidence

- **high:** explicit Phase 0 heading + STOP conditions + decision tree
- **medium:** at least one signal present, others implicit
- **low:** routing logic embedded in prose without clear structure

### Evidence format

```
L<n>: "## Phase 0 — Classification"
L<n>: "STOP. This doesn't need a skill — it needs a prompt."
L<n>: "Is this a single-step task? → STOP."
```

### Known limitations

- Skills with routing logic in YAML frontmatter or in a "Context" section before Phase 0 are misdetected as missing routing. Flag low confidence.
- Reference and Creative skills are correctly N/A here — Phase 1's archetype detection should mark them skipped before this detector runs.

---

## Detector 4 — Principle #4: State

**Reference:** [principles.md #4](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Detector strategy

Detect persistent state writing patterns and a Resume Protocol:

```bash
# State-file mentions
state_file=$(grep -ciE 'state\.json|factory-state|skill-state|run-state|workspace/iteration' SKILL.md)

# Write/save patterns
state_writes=$(grep -ciE 'save .+\.(json|md)$|write .+\.(json|md)$|update .+\.json' SKILL.md)

# Resume Protocol section
resume_section=$(grep -ciE '^##.*Resume|^###.*Resume|resume protocol|resume from' SKILL.md)

# Skill line count (state may be N/A for short skills)
line_count=$(wc -l < SKILL.md)
```

### Grade mapping

| State writes? | Resume Protocol? | Line count | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| Yes (≥3) | Yes | any | A+ | A+ | A+ |
| Yes (≥3) | No | >400 | C | B | B+ |
| Yes (≥1) | Yes | any | A | A | A |
| 0 | 0 | <100 | A (skip) | A (skip) | A (skip) |
| 0 | 0 | 100-400 | B (skip) | B+ (skip) | A- (skip) |
| 0 | 0 | >400 | C | B | B |

**N/A justification rule:** If line count <100 AND no parallel/iterative phases detected, score this principle N/A with justification "short skill, no resume needed."

### Confidence

- **high:** explicit state file path + multiple writes + Resume Protocol section
- **medium:** state mentioned but Resume Protocol absent
- **low:** state references are vague ("save progress") without concrete file paths

### Evidence format

```
L<n>: "Save 02-algorithmic-scores.json:"
L<n>: "## Resume Protocol"
L<n>: "If state file exists, read it and continue from current_phase."
```

### Known limitations

- Skills using ephemeral state (variables in single-session memory) score F here even when that's appropriate — the rubric prefers durable state. Persona modulation gives charitable-newcomer some leeway.
- State written to non-JSON formats (CSV, plain text) requires extending the regex.

---

## Detector 5 — Principle #5: Parallel

**Reference:** [principles.md #5](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only (conditional — N/A if no parallel work)

### Detector strategy

Detect explicit parallel-invocation patterns:

```bash
# Canonical parallel phrases
canonical=$(grep -ciE 'single message.*do NOT|do not launch sequentially|in parallel|parallel-burst' SKILL.md)

# Task tool / sub-agent mentions
task_mentions=$(grep -ciE 'spawn .+ Task|Task\(|sub-agent' SKILL.md)

# Sequential anti-patterns (negative signal — sequential when parallel would work)
sequential_warn=$(grep -ciE 'one at a time|sequentially|first.*then.*then' SKILL.md)
```

### Grade mapping

A skill earns A only if parallel is invoked AND the canonical "single message; do NOT launch sequentially" phrasing is present.

| Canonical phrase | Task mentions | Sequential warning | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| Yes | ≥1 | 0 | A+ | A+ | A+ |
| Yes | ≥1 | ≥1 | B+ | A- | A |
| No | ≥2 | 0 | B | B+ | A- |
| No | ≥1 | 0 | C | B | B |
| No | 0 | any | A (skip) | A (skip) | A (skip) |

**N/A justification rule:** If `task_mentions == 0` and skill is single-pass, score N/A with justification "no parallel subtasks; sequential design appropriate."

### Confidence

- **high:** canonical phrase + Task invocations
- **medium:** Task invocations without explicit parallel directive
- **low:** parallel implied by phrasing but not enforced

### Evidence format

```
L<n>: "Spawn one Task per applicable principle in a SINGLE message."
L<n>: "Do NOT launch sequentially."
```

### Known limitations

- Skills with one parallel-burst phase mixed with sequential phases may earn lower grades than warranted — the detector aggregates across the whole skill.
- The canonical phrase match is English-locale specific.

---

## Detector 7 — Principle #7: Files = bus

**Reference:** [principles.md #7](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Detector strategy

Detect numbered file conventions (`01-`, `02-`, etc.) used as inter-phase data bus:

```bash
# Numbered file patterns (00-99 prefix)
numbered_files=$(grep -oE '\b[0-9]{2}-[a-z][a-z0-9-]*\.(md|json|yaml|txt)' SKILL.md | sort -u | wc -l)

# Output-to-file mentions
output_files=$(grep -ciE 'save (to|as) .+\.(md|json)|write .+\.(md|json) to' SKILL.md)

# Phase-N → Phase-N+1 file passing
inter_phase=$(grep -ciE 'Phase [0-9].*reads .+\.(md|json)|Phase [0-9].*output: .+\.(md|json)' SKILL.md)
```

### Grade mapping

| Numbered files (unique) | Output-to-file mentions | Inter-phase passing | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| ≥3 | ≥3 | ≥1 | A+ | A+ | A+ |
| ≥3 | ≥1 | 0 | A | A | A |
| 1-2 | ≥1 | 0 | B | B+ | A- |
| 0 | ≥2 | 0 | C | B | B+ |
| 0 | 0 | 0 | F | D | C |

### Confidence

- **high:** ≥3 unique numbered files referenced consistently
- **medium:** numbered files present but used inconsistently
- **low:** files mentioned but not numbered or not used as inter-phase bus

### Evidence format

```
L<n>: "Output: 01-spec.md"
L<n>: "Save 02-algorithmic-scores.json"
L<n>: "Phase 4 reads 02-algorithmic-scores.json + 03-semantic-scores.json"
```

### Known limitations

- Skills using non-numbered conventions (e.g., descriptive names like `spec.md`, `research.md`) without numeric prefix are penalized; this is the rubric's preferred convention but the principle's spirit is met by any consistent file-bus pattern.

---

## Detector 9 — Principle #9: Human gate

**Reference:** [principles.md #9](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Detector strategy

Detect explicit human-gate invocations and their positioning:

```bash
# AskUserQuestion mentions
ask_user=$(grep -ciE 'AskUserQuestion|ask the user|wait for user|user confirmation' SKILL.md)

# Position check: gates should appear after Phase 0 (not at start)
ask_user_first_line=$(grep -niE 'AskUserQuestion|ask the user' SKILL.md | head -1 | cut -d: -f1)
phase_0_line=$(grep -niE '^##.*Phase 0|^##.*Pre-Phase' SKILL.md | head -1 | cut -d: -f1)

# Recovery loop on gate (loop back if user rejects)
gate_loops=$(grep -ciE 'if user (rejects|disagrees|says no).*return to|loop until|wait until confirmed' SKILL.md)
```

### Grade mapping

| AskUserQuestion count | Position OK | Recovery loop | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| ≥2 | Yes | Yes | A+ | A+ | A+ |
| ≥1 | Yes | Yes | A | A | A+ |
| ≥1 | Yes | No | B+ | A- | A |
| ≥1 | No (at start) | any | C | B | B+ |
| 0 | — | — | A (skip) | A (skip) | A (skip) |

**N/A justification rule:** If skill is fully autonomous (no human judgment required mid-process), score N/A.

### Confidence

- **high:** explicit AskUserQuestion calls with stated trigger conditions and recovery paths
- **medium:** human gate present but recovery path implicit
- **low:** human gate is "optional" or vaguely described

### Evidence format

```
L<n>: "If confidence < 0.75, AskUserQuestion with the top 2 candidates."
L<n>: "Wait for user reply. Use the user's choice."
```

### Known limitations

- Skills that use the user's task description as an implicit human gate (rather than mid-process AskUserQuestion) may earn lower grades than warranted.
- Skills with too many AskUserQuestion calls (over-prompting) are not penalized by this detector — Principle #17 (Autonomy) handles that.

---

## Detector 10 — Principle #10: Exit = question

**Reference:** [principles.md #10](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Detector strategy

Detect `Exit condition:` lines and check for binary-question phrasing:

```bash
# Count exit-condition lines
total_exits=$(grep -c "^Exit condition:\|^\*\*Exit condition" SKILL.md)

# Exit conditions phrased as questions ("Can you answer", "Yes → / No →")
question_exits=$(grep -ciE '^Exit condition.*Can you answer|^Exit condition.*\?$' SKILL.md)

# Exit conditions with explicit Yes/No branching
branching_exits=$(grep -ciE '^Exit condition.*Yes →.*No →' SKILL.md)

# Phase count (denominator)
phase_count=$(grep -cE '^##[[:space:]]*Phase [0-9]+' SKILL.md)
```

### Grade mapping

Compute `question_exits / phase_count` ratio.

| Ratio | Branching style | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|
| 1.0 (every phase) | Yes/No → | A+ | A+ | A+ |
| ≥0.8 | Yes/No → | A | A | A+ |
| ≥0.6 | Question form | B+ | A- | A |
| ≥0.4 | Question form | C | B | B+ |
| <0.4 OR no phases | — | F | D | C |

### Confidence

- **high:** every phase has the canonical "Can you answer X? Yes → ... No → ..." form
- **medium:** most phases have question-form exits; some have statement-form
- **low:** mix of question and statement exits

### Evidence format

```
L<n>: "Exit condition: Can you answer 'what is this company focused on right now'? Yes → proceed. No → return to Phase 1."
```

### Known limitations

- Detector counts at the skill level; if some phases are documentation-style and don't need exits, the ratio undercounts.
- Custom phase types (e.g., "Cleanup", "Output") may not trigger the phase-count regex; flag low confidence in those cases.

---

## Detector 12 — Principle #12: Gates = 3 parts

**Reference:** [principles.md #12](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Detector strategy

Detect Quality Gate sections and verify each gate has check + failure + recovery:

```bash
# Find Quality Gates section/table
gates_section_start=$(grep -nE '^##.*Quality Gate|^##.*Quality gates' SKILL.md | head -1 | cut -d: -f1)

# Count gate entries (table rows or list items)
gate_count=$(awk '/^##.*Quality Gate/,/^##[^#]/{if(/^\| [0-9]+|^### Gate|^- \*\*Gate/) c++} END{print c+0}' SKILL.md)

# For each gate, check for all 3 parts (heuristic: "If fails:" or "Failure:" + "return to" or "recovery:")
recovery_phrases=$(awk '/^##.*Quality Gate/,/^##[^#]/' SKILL.md | grep -ciE 'if fails:|failure:|recovery:|return to')

# Inline gates within phases (e.g., "Quality Check" sections)
inline_gates=$(grep -ciE '^### Quality Check|^## Quality Check' SKILL.md)
```

### Grade mapping

| Gates count | Has 3 parts each | Inline gates | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| ≥4 | Yes (all) | ≥1 | A+ | A+ | A+ |
| ≥3 | Yes (all) | 0 | A | A | A |
| ≥2 | Yes (most) | 0 | B+ | A- | A |
| ≥1 | partial (no recovery) | 0 | C | B | B+ |
| 0 | — | ≥1 | C | B | B+ |
| 0 | — | 0 | F | D | C |

### Confidence

- **high:** explicit Quality Gates table/section + every gate has check/failure/recovery
- **medium:** gates present but recovery paths inconsistent
- **low:** gates implied by phase exit conditions but not in dedicated section

### Evidence format

```
L<n>: "Gate 1 (after Phase 1): Archetype confidence ≥ 0.75 OR user-confirmed."
L<n>: "If fails: AskUserQuestion; if user can't decide, default to Hybrid + flag in report."
```

### Known limitations

- Skills that use exit conditions as gates (without a separate Gates section) may be undercounted; partial credit via the inline-gates check.
- The recovery-path heuristic is keyword-based and can miss elaborate recovery descriptions.

---

## Detector 13 — Principle #13: External storage

**Reference:** [principles.md #13](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural + Reference (conditional — N/A if SKILL.md ≤400 lines)

### Detector strategy

Compare line count to threshold; check for `references/` directory references:

```bash
# Total line count
line_count=$(wc -l < SKILL.md)

# Reference file mentions (other markdown files)
ref_files=$(grep -oE '(\./)?references/[a-z-]+\.md|\.\./[a-z-]+/[a-z-]+\.md' SKILL.md | sort -u | wc -l)

# Inline agent prompts (negative signal — should be externalized)
inline_prompts=$(awk '/^```/,/^```$/' SKILL.md | wc -l)
```

### Grade mapping

| Line count | references/ used | Inline prompts | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| ≤400 | — | — | A (skip) | A (skip) | A (skip) |
| 400-700 | ≥2 | <100 lines | A | A | A |
| 400-700 | ≥1 | 100-200 lines | B+ | A- | A |
| 400-700 | 0 | >200 lines | C | B | B+ |
| >700 | ≥2 | <100 lines | A- | A | A |
| >700 | 0 | >200 lines | F | D | C |

**N/A justification rule:** If line count ≤400, score N/A with "skill fits within 400-line guideline; no external storage needed."

### Confidence

- **high:** references/ directory present + multiple reference files cited
- **medium:** large skill with some externalization but inline prompts remain
- **low:** size warrants externalization but mechanism unclear

### Evidence format

```
L<n>: "Read ./references/algorithmic-detectors.md"
Line count: 443 (above 400; externalization recommended)
References cited: 3 (algorithmic-detectors.md, semantic-judges.md, scoring-template.md)
```

### Known limitations

- Code-block line count includes legitimate code examples that aren't agent prompts; the inline-prompts heuristic over-counts.
- Skills that reference external files via paths (not relative `references/`) may be misdetected.

---

## Detector 16 — Principle #16: Errors

**Reference:** [principles.md #16](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural + Creative

### Detector strategy

Detect error-handling tables (markdown tables with Error/Action columns):

```bash
# Find Error Handling section
error_section_start=$(grep -nE '^##.*Error Handling|^##.*Errors' SKILL.md | head -1 | cut -d: -f1)

# Count rows in error tables (markdown table rows starting with `| ` after a header row with Error/Situation)
error_rows=$(awk '
  /^\| (Error|Situation|Failure|Issue) *\| (Action|Response|Recovery|Fix)/{f=1; next}
  f && /^\| ---/{next}
  f && /^\| /{c++; next}
  f && !/^\|/{f=0}
  END{print c+0}
' SKILL.md)

# Inline error mentions outside tables (negative signal if no table exists)
inline_errors=$(grep -ciE 'if .+ (fails|errors)|on error|in case of error' SKILL.md)
```

### Grade mapping

| Error table rows | Inline error handling | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|
| ≥10 | any | A+ | A+ | A+ |
| 6-9 | any | A | A | A |
| 3-5 | ≥2 | B+ | A- | A |
| 1-2 | ≥3 | C | B | B+ |
| 0 | ≥3 | D | C | B |
| 0 | 0 | F | D | C |

### Confidence

- **high:** explicit Error Handling section with multi-row table
- **medium:** error handling exists but distributed across phases as prose
- **low:** errors mentioned only in passing without action mapping

### Evidence format

```
L<n>: "## Error Handling"
L<n>: "| Situation | Action |"
Error table rows: 10
```

### Known limitations

- Skills with error handling embedded inline within phases (not in a table) score poorly even when handling is thorough; persona modulation softens this.
- Two-column tables that aren't error/action (e.g., principle/grade) match the regex falsely; the column-header check mitigates this.

---

## Detector 18 — Principle #18: Path resolution

**Reference:** [principles.md #18](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** All (Conditional — N/A if no external paths referenced)

### Detector strategy

Negative-signal detector: hardcoded absolute paths are a violation. Positive signal: runtime resolution patterns.

```bash
# Hardcoded absolute paths (anti-pattern)
abs_paths=$(grep -ciE '/Users/[a-z]+|/home/[a-z]+|C:\\\\|/var/|/opt/' SKILL.md)

# Runtime resolution patterns (positive)
resolution_patterns=$(grep -ciE 'PRIMARY:|FALLBACK:|three-tier|find .+ 2>/dev/null|if file exists' SKILL.md)

# Generic ~/.claude/skills paths (acceptable, not absolute)
standard_paths=$(grep -ciE '~/\.claude/skills|~/\.codex/skills|\$HOME/' SKILL.md)

# External paths used at all
any_external=$(grep -cE '/' SKILL.md)
```

### Grade mapping

| Absolute paths | Resolution patterns | Standard paths | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| 0 | ≥2 | ≥1 | A+ | A+ | A+ |
| 0 | ≥1 | ≥1 | A | A | A |
| 0 | 0 | ≥1 | B+ | A- | A |
| ≥1 | ≥1 | any | C | B | B+ |
| ≥1 | 0 | any | F | D | C |
| 0 | 0 | 0 | A (skip) | A (skip) | A (skip) |

**N/A justification rule:** If skill makes no external file references, score N/A with "self-contained; no paths to resolve."

### Confidence

- **high:** explicit three-tier resolution pattern + zero absolute paths
- **medium:** some resolution but a few hardcoded paths present
- **low:** path strategy inconsistent or unclear

### Evidence format

```
L<n>: "PRIMARY:  ./04-RUBRIC/principles.md"
L<n>: "FALLBACK: ../04-RUBRIC/principles.md"
L<n>: "SEARCH:   find . -name 'principles.md' ..."
Hardcoded absolute paths: 0
```

### Known limitations

- Paths in code-block examples (not actual logic) may trigger the absolute-path detector falsely; manual review recommended for borderline cases.
- Windows-style paths (`C:\`) are detected but rare in this corpus.

---

## Detector 19 — Principle #19: Composition

**Reference:** [principles.md #19](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural + Reference

### Detector strategy

Parse YAML frontmatter for `composed_skills:` field; check for runtime resolution patterns:

```bash
# Extract composed_skills field
composed_count=$(awk '/^---$/{f=!f; next} f && /^composed_skills:/{flag=1} flag && /^[a-z_]+:/&&!/^composed_skills:/{flag=0} flag && /^[[:space:]]*-/' SKILL.md | wc -l)

# Optional vs mandatory
optional_count=$(awk '/^---$/{f=!f; next} f && /^composed_skills:/{flag=1} flag' SKILL.md | grep -c 'optional: true')

# Runtime resolution for composed paths
runtime_resolution=$(grep -ciE 'composed.*resolve at runtime|find .+SKILL\.md|fallback path' SKILL.md)

# Skill invocation patterns (slash commands invoked from within)
slash_invocations=$(grep -coE '/[a-z][a-z0-9-]+' SKILL.md | head -1)
```

### Grade mapping

| composed_skills field | Runtime resolution | Slash invocations | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|
| ≥3 with metadata | ≥1 | ≥3 | A+ | A+ | A+ |
| ≥1 with metadata | ≥1 | ≥1 | A | A | A |
| ≥1 (just names) | 0 | ≥1 | B | B+ | A- |
| 0 | 0 | ≥1 | C | B | B+ |
| 0 | 0 | 0 | A (skip) | A (skip) | A (skip) |

**N/A justification rule:** If skill is standalone (no other skills invoked), score N/A with "standalone; no composition."

### Confidence

- **high:** YAML composed_skills field with phase + purpose metadata + runtime resolution
- **medium:** composition mentioned but path strategy unclear
- **low:** slash commands invoked without YAML declaration

### Evidence format

```
L<n>: "composed_skills:"
L<n>: "  - name: defuddle"
L<n>: "    phase: 1"
L<n>: "    purpose: extract clean content"
L<n>: "    optional: true"
```

### Known limitations

- Skills that compose via Bash invocation (not the YAML field) score lower than warranted; persona modulation softens this for charitable-newcomer.
- The phase-and-purpose metadata pattern is a v0.1 recommendation, not yet a community-standard convention.

---

## Detector 23 — Principle #23: Host-portable

**Reference:** [principles.md #23](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** All (Universal — promoted v0.3 from deferred candidate #29)

### Detector strategy

Three signals: positive (host-aware mechanisms), positive (portable conventions), negative (hardcoded host assumptions).

```bash
# Positive: explicit host/profile flags or per-host config blocks
host_flags=$(grep -ciE '\-\-host[ =]|\-\-profile[ =]|host:[ ]|hosts:[ ]|harness:[ ]' SKILL.md)

# Positive: allowed-tools restriction in YAML (harness-agnostic spec)
allowed_tools=$(awk '/^---$/{f=!f; next} f && /^allowed.tools:/{flag=1; next} flag && /^[a-z_]+:/{flag=0} flag' SKILL.md | wc -l)
allowed_tools_present=$([ "$allowed_tools" -gt 0 ] && echo 1 || echo 0)

# Positive: relative paths or HOME-anchored standard locations
relative_paths=$(grep -ciE '~/\.[a-z]+/skills|\$HOME/|\./|\.\./' SKILL.md)

# Negative: hardcoded absolute author-machine paths (overlaps #18 but scored separately)
absolute_author_paths=$(grep -ciE '/Users/[a-z]+|/home/[a-z]+|C:\\\\Users\\\\' SKILL.md)

# Negative: harness-specific subprocess invocations buried in prose
harness_specific=$(grep -ciE 'claude-code\b|claude_code\.|codex\.cli|cursor\.cli' SKILL.md)
```

### Grade mapping

Score the skill on host-portability intent (positive signals) minus host-coupling violations (negative signals). #18 grades resolution discipline; #23 grades portability intent — they overlap on absolute-path detection but are scored independently.

| Host flags / per-host config | allowed-tools | Absolute author paths | Harness-specific calls | strict-academic | pragmatic-practitioner | charitable-newcomer |
|---|---|---|---|---|---|---|
| ≥1 | yes | 0 | 0 | A+ | A+ | A+ |
| 0 | yes | 0 | 0 | A | A | A |
| 0 | yes | 0 | ≥1 | B | B+ | A- |
| 0 | no | 0 | 0 | B+ | A- | A |
| 0 | no | ≥1 | any | D | C | B |
| any | any | ≥3 | any | F | D | C |

**N/A justification rule:** A skill can score N/A on #23 only if it explicitly declares itself host-locked by design and explains why. Otherwise the principle applies (it's universal — every shareable SKILL.md should be portable).

### Confidence

- **high:** explicit per-host config block or `--host` flag + `allowed-tools` field present + zero absolute author paths
- **medium:** portable conventions (relative paths, allowed-tools) but no explicit host-aware mechanism
- **low:** mixed signals — some portable, some host-coupled — without a clear strategy

### Evidence format

```
L<n>: "allowed-tools: [Read, Bash, ...]"
L<n>: "--host codex|opencode|cursor"
L<n>: "PRIMARY:  ~/.claude/skills/<name>/SKILL.md"
Absolute author paths: 0
Harness-specific subprocess calls: 0
```

### Known limitations

- The line between #18 (path resolution) and #23 (host portability) is genuine: a skill can have clean path resolution and still hardcode `claude-code` as the only target harness. Both detectors run and grade independently.
- Plugin-format skills that work across hosts implicitly (no explicit `--host` flag, but the format itself is harness-agnostic) tend to score B / B+; raise to A only when explicit portability mechanisms are visible.
- Calibration data for #23 is pending: the v0.2 4-skill calibration set predates this principle. Treat v0.3 grades on #23 as provisional until kappa-tested.

---

## Detector summary

| # | Principle | Strategy | False-positive risk | False-negative risk |
|---|---|---|---|---|
| 1 | Description as router | YAML parse + keyword counts | Low | Medium (multi-line desc) |
| 2 | Route before work | Heading + STOP + decision-tree | Low | Medium (implicit routing) |
| 4 | State | File mentions + Resume Protocol | Low | Medium (ephemeral state) |
| 5 | Parallel | Canonical phrase + Task mentions | Low | Low |
| 7 | Files = bus | Numbered file regex | Medium (false matches) | Medium (descriptive names) |
| 9 | Human gate | AskUserQuestion + position check | Low | Medium (implicit gates) |
| 10 | Exit = question | "Can you answer" + Yes/No branches | Low | Low |
| 12 | Gates = 3 parts | Section detection + recovery keywords | Medium | Medium |
| 13 | External storage | Line count threshold | Low | Low |
| 16 | Errors | Markdown table parse + columns | Low | Medium (inline handling) |
| 18 | Path resolution | Absolute-path negative signal | Medium (code blocks) | Low |
| 19 | Composition | YAML composed_skills + runtime patterns | Low | Medium (Bash composition) |
| 23 | Host-portable | Host-flag + allowed-tools + path-coupling | Medium (overlap with #18) | Medium (implicit portability) |

**Overall calibration:** detectors 5, 10, 13, 18 have high accuracy. Detectors 7, 12, 16, 19 have moderate noise — flag low confidence when borderline. Detector 23 is provisional at v0.3 (calibration pending).

---

## Cross-references

- [`../SKILL.md`](../SKILL.md) — The skill that loads this file (Phase 2)
- [`../genesis.md`](../genesis.md) — Architecture spec listing the 12 v0.2 algorithmic principles (this file adds #23 in v0.3)
- [`./semantic-judges.md`](./semantic-judges.md) — The complementary file for the 12 semantic principles (10 added in Stage 1c; #24 + #25 added in v0.3)
- [`../../../04-RUBRIC/principles.md`](../../../04-RUBRIC/principles.md) — Principle definitions
- [`../calibration.md`](../calibration.md) — Stage 1d will validate these detectors against the 4 manual evaluations
