# Semantic Judges — `/paap-eval` Phase 3 Reference

> Per-principle LLM-judge prompts for the 12 semantic principles in the [PaaP rubric](../../../04-RUBRIC/principles.md). Loaded by [`paap-eval/SKILL.md`](../SKILL.md) Phase 3.

**Status:** v0.3-dev on a v0.2 Stage 1c baseline. Each judge is invoked as a parallel sub-agent (one Task per principle), receives the skill content + principle definition + persona context, and returns a structured grade with confidence + reasoning + uncertainty notes. The 10 v0.2 judges were calibrated against the Stage 1d 4-skill set; the v0.3 additions (Judges 24 and 25) are wired into Phase 3 but have NOT been calibration-tested at 25-principle scale — treat their grades as provisional until the v0.3 kappa re-run completes.

---

## How judges work

Every judge is an LLM-call structured as:

```
INPUT:
  skill_content:  full text of the SKILL.md being evaluated
  archetype:      Procedural / Reference / Creative / Hybrid (from Phase 1)
  persona:        strict-academic | pragmatic-practitioner | charitable-newcomer

OUTPUT (required schema):
  grade:             A+ | A | B+ | B | C | D | F | needs-human-judgment
  confidence:        high | medium | low
  reasoning:         2-3 sentences explaining the grade
  uncertainty_notes: required if confidence < high; describes what the judge
                     was uncertain about and why
  evidence:          ["L<n>: <quoted line>", ...] up to 5 supporting refs
```

**Common prompt envelope** wraps every per-principle judge prompt:

```
You are evaluating a SKILL.md against principle #<N> of the PaaP rubric
(v0.1, Catafal 2026). Apply the principle as defined; do not invent
new criteria. Score using the grade scale (A+ through F, plus N/A
with justification, plus needs-human-judgment for irreducibly
subjective cases).

PERSONA: <persona>
- strict-academic: hold to the strictest reading of the principle.
  Reward only explicit, well-implemented patterns. When in doubt,
  grade down.
- pragmatic-practitioner (default): reward patterns that work in
  practice, even if implemented unconventionally. Calibrate to
  "would this skill actually help a working practitioner?"
- charitable-newcomer: reward visible effort and intent, even if
  execution is incomplete. Calibrate to "did the author try to
  follow this principle?"

PRINCIPLE DEFINITION:
<paste from principles.md>

SKILL CONTENT:
<full SKILL.md text>

ARCHETYPE: <archetype from Phase 1>

If this principle is N/A for this archetype per the applicability
matrix, output {grade: "N/A", reasoning: "<one-line justification>"}.

If the principle applies but you cannot judge it from surface
content (requires running the skill, or tasting the output),
output {grade: "needs-human-judgment", uncertainty_notes: "..."}.

Otherwise, output the structured grade per the schema above.
```

**Exemplar cases** ground each judge in concrete A/C/F examples from the corpus. The judge model uses these as calibration anchors — what an A-grade looks like in this principle, what a C-grade looks like, what an F-grade looks like. Without exemplars, LLM-judge grades drift.

**Defer-to-user conditions** make explicit when the judge should output `needs-human-judgment` instead of guessing. Examples: when the principle requires running the skill (output #11), when the judgment is taste-based and persona variants would diverge sharply (#22 voice), when the skill's archetype is itself ambiguous.

---

## Judge 3 — Principle #3: Modes

**Reference:** [principles.md #3](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Conditional — N/A if skill has only one execution path

### Judge prompt

```
Evaluate principle #3 (Modes) for this SKILL.md.

The principle: when a skill has multiple legitimate execution paths
(auto/manual, quick/full, lean/orchestration), modes are explicit,
named, and selected with stated criteria. Implicit modes leak — the
model picks based on context cues you didn't anticipate. Explicit
modes are auditable.

Score this skill on:
1. Are multiple execution paths visible? (count distinct modes)
2. Are they named explicitly?
3. Are mode-selection criteria stated (vs left to model intuition)?
4. Is there a sensible default mode for ambiguous invocations?

If the skill is genuinely single-mode (linear pipeline that always
does the same thing), score N/A with justification "single mode by
design; no alternatives to compare."
```

### Output schema

Standard schema (see top of file). For this principle, `evidence` should cite the mode declarations and selection criteria.

### Exemplar cases

**A+ example:** gstack's `plan-ceo-review` declares 4 modes (`SCOPE EXPANSION`, `SELECTIVE EXPANSION`, `HOLD SCOPE`, `SCOPE REDUCTION`) with context-dependent defaults (greenfield → EXPANSION, hotfix → HOLD). Each mode maps to a different subset of phases. Selection criteria explicit.

**B example:** A skill with `--quick` and `--full` flags but no description of when to use each; user must guess. Modes named, criteria absent.

**C example:** A skill that "adapts to the situation" without naming the modes. The model picks one and the user is left guessing why.

**N/A example:** `pre-call` (linear pipeline, single mode). Justified as "single mode by design."

### Persona modulation

- **strict-academic:** require all 4 elements (multiple paths, named, criteria, default) for A grades. Borderline → grade down.
- **pragmatic-practitioner (default):** A if 3 of 4 elements present.
- **charitable-newcomer:** B+ if modes are visible but criteria are weak.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- Modes appear to exist but are buried in prose (not in a dedicated section)
- The skill claims to be single-mode but uses many flags that look like mode selectors

### Known limitations

- Skills that use hooks or runtime config to switch modes (rather than explicit YAML/header declarations) may be undercounted.
- The "sensible default" check is subjective; reasonable judges may disagree on what's sensible.

---

## Judge 6 — Principle #6: Personas / voice

**Reference:** [principles.md #6](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural + Creative

### Judge prompt

```
Evaluate principle #6 (Personas / voice) for this SKILL.md.

The principle: when a skill uses agents (sub-tasks with distinct
viewpoints) or enforces a behavioral discipline, it does so through
specific persona definitions or voice rules — not generic "you are
an expert in X" framing. Behavioral discipline beats character
framing. The strongest implementations name the rationalizations
to reject.

Score this skill on:
1. Are personas/voice rules present at all?
2. Are they behavioral (specific scope, named rationalizations to
   reject) or generic ("you are a senior engineer")?
3. Do they specify what to focus on AND what to ignore?
4. If multiple agents exist, do they have distinct, non-overlapping
   personas?
```

### Output schema

Standard schema. Evidence should quote the strongest persona definition + the strongest voice rule (e.g., a "Rationalizations to Reject" entry).

### Exemplar cases

**A+ example:** `obra/test-driven-development` defines persona-by-rejection: an "Iron Law" plus a "Rationalizations to Reject" table listing the specific bad arguments the model will make ("just one quick fix without a test", "the test is obvious"). Each rejection has a counter. This IS behavioral discipline encoded as voice.

**A example:** gstack's review skills name agent personas with sharp scope: *"Burned by untested edge cases. Trusts tests more than comments, edge case tests more than happy path tests."*

**B example:** Skill says "act as a careful researcher" — mentions a role, no behavioral specification, no rationalizations.

**C example:** Skill says "you are an expert" — pure decoration; the model already tries to be one.

**F example:** No persona language at all; instructions are written as a generic checklist with no point-of-view.

### Persona modulation

- **strict-academic:** require Rationalizations Rejection table or equivalent for A+. Generic role assignments cap at C.
- **pragmatic-practitioner (default):** behavioral framing earns A; generic role earns C.
- **charitable-newcomer:** any voice/tone discipline earns at least B; generic role earns B-.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- Voice rules are present but their effectiveness depends on running the skill (taste judgment)
- Persona is genre-specific (e.g., security-auditor) and judging quality requires domain expertise

### Known limitations

- Reference skills are correctly N/A here — they describe libraries, not enforce discipline. Phase 1's archetype detection should mark them skipped.
- Voice rules in the YAML header (e.g., `tone: skeptical`) rather than the body may be undercounted.

---

## Judge 8 — Principle #8: Synthesis

**Reference:** [principles.md #8](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Judge prompt

```
Evaluate principle #8 (Synthesis) for this SKILL.md.

The principle: whenever parallel subtasks produce independent
outputs, an explicit synthesis phase merges them with stated
priority rules and conflict resolution. Without priority rules,
the synthesis agent invents arbitration on the fly — same input,
different runs, different outputs.

Score this skill on:
1. Does the skill have parallel subtasks? (if not, N/A)
2. Is there an explicit synthesis phase after the parallel burst?
3. Are priority rules stated (which agent wins which decisions)?
4. Are conflict resolution rules explicit (what to do when agents
   disagree)?
```

### Output schema

Standard schema. Evidence should quote the priority rules and any explicit conflict-resolution language.

### Exemplar cases

**A+ example:** gstack's `autoplan` Phase 1 synthesis with phase-context tiebreakers: *"CEO phase: P1 (completeness) + P2 (boil lakes) dominate. Eng phase: P5 (explicit) + P3 (pragmatic) dominate."* Different phases, different priority weights.

**A example:** `meta-paap`-generated `/skill-audit` synthesis: *"Usage wins tiers, Staleness wins maintenance, Overlap wins merges."* Three named arbitration rules.

**B example:** Skill has parallel agents and a synthesis section, but the synthesis is "merge findings into one report" without arbitration rules.

**C example:** Skill has parallel work but no synthesis phase — outputs are concatenated rather than synthesized.

**N/A example:** `pre-call` (no parallel work). Justified as "linear pipeline; nothing to synthesize."

### Persona modulation

- **strict-academic:** require explicit named priority rules for A. Hand-wavy synthesis caps at B.
- **pragmatic-practitioner (default):** A if priority rules are stated; B if synthesis is structured but rules implicit.
- **charitable-newcomer:** B+ if synthesis exists at all.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- The skill claims to synthesize but the actual logic depends on the model's judgment in a way that's hard to verify from the spec alone

### Known limitations

- Skills using sequential rounds of agents (each consuming the previous) may not need synthesis but score lower than warranted.
- Synthesis quality is hard to assess without running the skill on real inputs.

---

## Judge 11 — Principle #11: Output spec

**Reference:** [principles.md #11](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** All (Universal)

### Judge prompt

```
Evaluate principle #11 (Output spec) for this SKILL.md.

The principle: the output specification leaves nothing to
interpretation — exact format, named sections, length constraints,
per-section content rules, and (where useful) anti-templates.
Vague output specs produce polished-looking but wrong output.

Score this skill on:
1. Is there a dedicated output specification?
2. Are format, sections, length, and per-section content rules
   stated?
3. Are anti-templates included (what NOT to produce) where
   appropriate?
4. Are honest omission rules included ("skip if X")?
```

### Output schema

Standard schema. Evidence should quote the most specific per-section rule + any anti-template.

### Exemplar cases

**A+ example:** `tapestry/article-extractor` per-section content rules: *"8-10 bullets each containing a concrete claim. Skip this section entirely if all terms are common knowledge. If nothing applies to current work: write 'No direct application' — do not force it."* Honest omission rules prevent bloat.

**A example:** A skill with named output sections + length per section + format examples. Solid output contract.

**B example:** Output is named ("a report") with format (markdown) but no per-section rules.

**C example:** Output spec says "produce a comprehensive analysis." How long? What sections? What if a section is empty?

**F example:** No output specification at all; relies on the model to invent a format.

### Persona modulation

- **strict-academic:** require anti-templates AND honest omission rules for A+. Vague specs ("comprehensive") cap at D.
- **pragmatic-practitioner (default):** A if per-section content rules are stated; B if format is named but rules absent.
- **charitable-newcomer:** B+ if output is named with format; A if any per-section guidance.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- Output spec is highly domain-specific and judging completeness requires domain expertise
- Spec is implicit in worked examples rather than explicit in a dedicated section

### Known limitations

- Reference skills' "output" is the documentation itself; judge via section coverage, not action-output rules.
- Creative skills may legitimately leave room for the model to produce variations; over-specification is a failure mode the judge should not penalize.

---

## Judge 14 — Principle #14: Context scope

**Reference:** [principles.md #14](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** All (Universal)

### Judge prompt

```
Evaluate principle #14 (Context scope) for this SKILL.md.

The principle: the skill explicitly states what it is for and what
it is not for. Per-agent scoping (when agents are used) names what
each agent can read AND what they're denied. Scope creep is the
most common skill-decay pattern.

Score this skill on:
1. Are skill-level boundaries explicit (in description, intro, or
   "what this is/is not" sections)?
2. If agents are used, do they have explicit per-agent scoping?
3. Are denied/excluded items stated, with reasoning where
   non-obvious?
4. Does the skill resist scope creep (refuse to expand into
   adjacent territory)?
```

### Output schema

Standard schema. Evidence should quote the most explicit boundary statement + any per-agent scoping with reasoning.

### Exemplar cases

**A+ example:** gstack's review skills explicitly scope each reviewer agent: *"Agent B is denied access to GitNexus data; reasoning: architecture-level data would invite scope creep into design decisions outside this agent's mandate."* Boundary plus reasoning.

**A example:** Skill description includes 2-3 anti-triggers ("Do NOT use for X, Y, Z") and the body refuses to expand.

**B example:** Skill is described positively (what it's for) without explicit anti-triggers.

**C example:** Skill description is broad enough that scope creep is invited; no explicit boundaries.

**F example:** Skill claims to do "everything related to X" — guarantees scope creep.

### Persona modulation

- **strict-academic:** require both skill-level boundaries AND per-agent scoping (when applicable) for A+.
- **pragmatic-practitioner (default):** A if anti-triggers are present and the body stays scoped.
- **charitable-newcomer:** B+ if any explicit boundary language.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- The skill's domain is itself broad enough that "scoped" is hard to assess from spec alone

### Known limitations

- Some skills have implicit scope (via the workflow's nature) without explicit anti-triggers; this judge undercounts those.
- Per-agent scoping is N/A when there are no agents; the judge should not penalize.

---

## Judge 15 — Principle #15: Progress

**Reference:** [principles.md #15](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** All (Universal)

### Judge prompt

```
Evaluate principle #15 (Progress) for this SKILL.md.

The principle: the skill emits status updates at meaningful
checkpoints — phase transitions at minimum, with key stats
("Found 12 sources, 3 scored above threshold, proceeding to
synthesis"). Without progress reporting, debugging is reading
the whole execution and guessing where it drifted.

Score this skill on:
1. Are status updates emitted at phase transitions?
2. Do updates include key stats (counts, intermediate findings)?
3. Is there a final completion summary?
4. Is the format consistent across phases?
```

### Output schema

Standard schema. Evidence should quote the most-detailed progress statement + any final-summary block.

### Exemplar cases

**A+ example:** gstack's `[PROGRESS]` directive: *"During long-running skill sessions, periodically write a brief [PROGRESS] summary (2-3 sentences: what's done, what's next, any surprises)."* Plus phase-transition summaries with stats.

**A example:** Skill has explicit "print after each phase" instructions with example formats showing what stats to include.

**B example:** Skill says "report progress" without specifying when or what.

**C example:** Skill emits no status until the final result; user has no signal whether it's working.

### Persona modulation

- **strict-academic:** require key-stats inclusion for A; phase-only updates cap at B.
- **pragmatic-practitioner (default):** A if updates include any quantitative info per phase.
- **charitable-newcomer:** B+ if any progress reporting at all.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- The skill is short enough (<2 minutes) that progress reporting may be N/A
- The skill is documentation-style and "progress" maps to navigation cues, not runtime updates

### Known limitations

- Reference skills' "progress" maps to navigation breadcrumbs in the document, not execution logs; judge accordingly.
- Skills with progress in code blocks (Bash echo statements) rather than prose may be undercounted.

---

## Judge 17 — Principle #17: Autonomy

**Reference:** [principles.md #17](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural + Creative

### Judge prompt

```
Evaluate principle #17 (Autonomy) for this SKILL.md.

The principle: the skill has sensible defaults, infers mode from
context, treats interactive-prompts as the exception (only when
genuine human judgment is required). Manual mode is the safe
fallback. Skills that ask too many questions become unusable;
skills that ask too few become dangerous.

Score this skill on:
1. Are defaults stated for ambiguous parameters?
2. Is mode/path inference from context rather than asking?
3. Are AskUserQuestion calls reserved for genuine human judgment?
4. Is there a safe-fallback when inference fails?
```

### Output schema

Standard schema. Evidence should quote the default-statement and the safe-fallback clause.

### Exemplar cases

**A+ example:** `meta-paap`'s "If mode unclear: FULL mode." One sentence, sensible default, no prompt. Plus inferred classification before any user interaction.

**A example:** Skill has explicit defaults for every parameter + inference logic for archetype/mode + AskUserQuestion only when confidence < threshold.

**B example:** Skill has defaults but asks user for confirmation on every mode selection (over-prompting).

**C example:** Skill asks user for every parameter (no defaults) — usable but high-friction.

**F example:** Skill makes consequential decisions silently without defaults or documentation; or asks user to confirm trivial choices.

### Persona modulation

- **strict-academic:** require explicit default statements + safe-fallback for A. Implicit defaults cap at B.
- **pragmatic-practitioner (default):** A if defaults are clear and AskUserQuestion is reserved appropriately.
- **charitable-newcomer:** B+ if any defaults are stated.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- The skill's autonomy calibration depends on workflow stakes (high-stakes work warrants more prompting); judge should note this and defer

### Known limitations

- Skills with intentionally low autonomy (e.g., obra/TDD which deliberately removes choice) score F here even when that's the design point. Persona modulation softens this for charitable-newcomer.
- Skills where autonomy varies by mode (auto-mode high, manual-mode low) may earn lower aggregate grades than warranted.

---

## Judge 20 — Principle #20: Output-first

**Reference:** [principles.md #20](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** All (Universal)

### Judge prompt

```
Evaluate principle #20 (Output-first) for this SKILL.md.

The principle: the output specification is defined before the
phases. The phases are the path to the defined output, not the
other way around. Phase-first thinking produces skills that
ramble. Output-first thinking forces clarity about what the
skill is actually for.

Score this skill on:
1. Is the output spec defined before the phases (in document
   order or by clear cross-reference)?
2. Do the phases visibly contribute to the defined output?
3. Is there evidence the author worked output-first (e.g., output
   defined in YAML/intro, phases written to produce it)?
```

### Output schema

Standard schema. Evidence should cite the output-definition location AND the first phase that consumes it.

### Exemplar cases

**A+ example:** `idea-to-pr` defines the PR description template (6 sections, exact format) in Phase 0 before any phase is described. Every subsequent phase is justified by what it contributes to the final output.

**A example:** Output spec is in the YAML description or intro section; phases reference it explicitly.

**B example:** Output spec exists but appears at the end of the file, after the phases.

**C example:** Output spec is implicit in worked examples; not stated as a contract.

**F example:** No clear output spec; output emerges from whatever the phases happen to produce.

### Persona modulation

- **strict-academic:** require output spec literally before phases in document order for A.
- **pragmatic-practitioner (default):** A if output is defined in intro/description even if also restated at end.
- **charitable-newcomer:** B+ if output spec exists anywhere with cross-reference from phases.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- Output is highly procedural (e.g., a side-effect like "creates a PR") and the judge can't easily map phases to output

### Known limitations

- Reference skills with section-level output specs (no skill-level contract) earn lower grades than warranted; this is the v0.1 partial-pass case noted in the rubric.

---

## Judge 21 — Principle #21: Decision class drives gating

**Reference:** [principles.md #21](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only

### Judge prompt

```
Evaluate principle #21 (Decision class drives gating policy)
for this SKILL.md.

The principle: decisions in a skill are classified into three
types — Mechanical (auto-decide silently), Taste (auto-decide
but surface at gate), User Challenge (never auto-decide, always
escalate) — and each class triggers a different gating treatment.
Without this distinction, skills either over-prompt or under-prompt.

Score this skill on:
1. Are decisions in the skill explicitly classified by type?
2. Do different decision classes trigger different gating?
3. Are User Challenge decisions never silently auto-decided?
4. Are Mechanical decisions silent (no over-prompting)?
```

### Output schema

Standard schema. Evidence should cite where decision classes are named or where different gating is applied to different decision types.

### Exemplar cases

**A+ example:** gstack's `autoplan` distinguishes all three classes explicitly: Mechanical decisions auto-decide, Taste decisions auto-decide-but-flag, User Challenge decisions escalate. The taxonomy is named.

**A example:** Skill calibrates gating without naming the taxonomy: e.g., `obra/TDD` is fundamentally Mechanical (no user prompts for the discipline); `emaynard/family-history-planning` is fundamentally User Challenge (every action requires explicit user approval).

**B example:** Skill has appropriate gating for the dominant decision type but doesn't differentiate within the skill.

**C example:** Skill prompts on every decision regardless of class (over-prompting), or auto-decides everything regardless of stakes (under-prompting).

**F example:** Gating is arbitrary or absent; consequential decisions made silently.

### Persona modulation

- **strict-academic:** require named decision-class taxonomy for A+. Implicit calibration caps at B+.
- **pragmatic-practitioner (default):** A if gating is appropriately calibrated to decision stakes.
- **charitable-newcomer:** B+ if gating shows any thought about decision type.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- The skill's domain makes "decision class" hard to assess from spec alone (e.g., security workflows where everything is User Challenge)

### Known limitations

- This principle was promoted from a gstack candidate based on community-corpus evidence; calibration may shift with v0.2 kappa data.
- Reference and Creative skills don't have execution-time decisions to classify; correctly N/A.

---

## Judge 22 — Principle #22: Voice + writing rules as skill content

**Reference:** [principles.md #22](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural + Creative

### Judge prompt

```
Evaluate principle #22 (Voice + writing rules as skill content)
for this SKILL.md.

The principle: tone, banned phrases, prose structure rules, and
anti-AI-vocabulary lists are first-class skill content — written
into the skill body, not externalized as a separate style guide.
When voice rules live outside the skill, they're not enforced.

Score this skill on:
1. Are voice/tone/style rules present in the skill body?
2. Are banned vocabulary lists or prose-structure rules included
   where appropriate?
3. Are anti-templates (what the output should NOT sound like)
   present for skills that produce text?
4. Are voice rules calibrated to the skill's domain (not generic)?
```

### Output schema

Standard schema. Evidence should quote the strongest voice rule + any banned vocabulary or anti-template.

### Exemplar cases

**A+ example:** gstack preambles include 600+ lines of voice rules: banned AI vocabulary lists ("delve", "crucial", "landscape", "tapestry"), required prose structure (D-numbered AskUserQuestion with ELI10 + Stakes + Recommendation + Completeness score + ≥40-char pros/cons + Net line). Voice IS skill content at scale.

**A example:** `anthropic-canvas-design` encodes aesthetic anti-patterns (avoid purple gradients, Inter font, generic AI aesthetics) directly in the skill. `obra/test-driven-development` specifies prose voice ("Iron Law", "Rationalizations to Reject") that shapes how the skill talks to the user.

**B example:** Skill has tone guidance ("write in a clear, professional voice") but no specific banned phrases or anti-templates.

**C example:** Skill produces text but has no voice guidance at all; output defaults to AI-flavored marketing copy.

**N/A example:** Reference skills that don't produce text-with-voice (e.g., a Python library wrapper) — score N/A with justification "skill produces structured output, not voiced text."

### Persona modulation

- **strict-academic:** require named banned vocabulary OR anti-templates for A. Generic tone guidance caps at C.
- **pragmatic-practitioner (default):** A if voice rules are specific to the domain.
- **charitable-newcomer:** B+ if any tone discipline is present.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- Voice quality requires reading sample outputs (taste judgment beyond spec)
- The skill's domain makes "voice" ambiguous (e.g., code-only skills)

### Known limitations

- This principle was promoted from a gstack candidate; calibration shifts with v0.2 kappa data.
- Voice rules in external style guides (referenced but not in the SKILL.md) score lower than warranted; this is the principle's intent (voice should be in the skill).

---

## Judge 24 — Principle #24: Skills observe themselves and feed prior runs forward

**Reference:** [principles.md #24](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural + Reference (promoted v0.3 from deferred candidate #26)

### Judge prompt

```
Evaluate principle #24 (Skills observe themselves and feed prior runs forward)
for this SKILL.md.

The principle: a skill maintains a record of its own previous executions
(analytics events, session lessons, version-tagged learnings, prior-run
output) and reads from that record on subsequent runs to avoid repeating
mistakes or re-doing solved sub-problems. Stateless skills relearn the
same lessons every invocation; self-observing skills carry calibration
forward.

Score this skill on:
1. Does the skill define a persistence mechanism for prior-run data
   (analytics dir, session-lessons file, version-tagged output, learning
   store)? Mere mention of "save state" is not sufficient — there must
   be a named location and a write protocol.
2. Does the skill read from that record on subsequent runs (search,
   inject prior learnings into preamble, version-aware comparison)?
   Writing without reading is not self-observation.
3. Is the observation loop closed — does prior-run data demonstrably
   change behavior on the next run?

Reject pattern-matching on keywords alone. The principle is about
*using* prior runs, not naming a directory called "analytics".
```

### Output schema

Standard schema. Evidence should quote (a) the persistence mechanism, (b) the read-back mechanism, (c) one concrete example of behavior change driven by prior data.

### Exemplar cases

**A+ example:** `gstack` writes start/end events to `~/.gstack/analytics/` on every skill execution; future runs query this store via `gstack-learnings-search` and inject prior learnings into the preamble — full write→read→behavior-change loop.

**A example:** `glebis/jtbd` Update Mode reads the prior run forward; `glebis/tufte-report` and `ryanbbrown/revealjs` ship "Session Lessons" sections that persist across runs and are explicitly consulted before new runs start.

**B example:** `daymade/deep-research` uses version-tagged identifiers (V6, V6.1) so runs can observe which iteration of logic produced each output — observation pattern present but the read-back side is implicit.

**C example:** Skill mentions saving prior runs but has no read-back mechanism, OR reads prior runs but doesn't demonstrably change behavior based on them.

**D/F example:** Stateless skill that runs as if it has never run before — every invocation starts from zero with no provision for learning from history.

**N/A example:** Pure Reference skills that are read-not-executed (library docs reformatted as SKILL.md) can score N/A with justification "skill is documentation, no execution to observe."

### Persona modulation

- **strict-academic:** require all three loop components (persistence + read-back + visible behavior change) for A. Persistence-only without read-back caps at C.
- **pragmatic-practitioner (default):** A if persistence + read-back are present; demonstrable behavior change is preferred but not required at A.
- **charitable-newcomer:** B+ if any prior-run-aware mechanism is visible, even partial.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- The persistence mechanism is described but its read-back is buried in dependent skills not visible in this SKILL.md
- The skill claims to use prior runs but the implementation reads as architectural intent rather than working logic

### Known limitations

- This principle was promoted from deferred candidate #26 in v0.3; calibration data is pending the 25-principle kappa re-run.
- Some skills delegate self-observation to the harness (host-managed analytics) rather than implementing it in the SKILL.md body. The principle accepts harness-mediated implementations as long as the SKILL.md explicitly relies on them.
- Distinguishing "stateful skill" (#4) from "self-observing skill" (#24): #4 is per-run state (resume protocol, ephemeral storage); #24 is cross-run learning (analytics across many runs). A skill can score well on #4 and poorly on #24.

---

## Judge 25 — Principle #25: Skills detect spawn vs. interactive context and adapt

**Reference:** [principles.md #25](../../../04-RUBRIC/principles.md)
**Applicable archetypes:** Procedural-only (Conditional — promoted v0.3 from deferred candidate #30)

### Judge prompt

```
Evaluate principle #25 (Skills detect spawn vs. interactive context and adapt)
for this SKILL.md.

The principle: a skill recognizes whether it was invoked interactively
(human at keyboard) or spawned by another agent (no human present), and
changes behavior — no AskUserQuestion calls when spawned, no upgrade-
prompt UI, sensible non-interactive defaults, machine-readable output
when called from another agent.

Score this skill on:
1. Does the skill detect its invocation context (interactive vs spawned/
   batch/non-interactive)?
2. Does the skill adapt behavior based on that detection — concretely:
   suppress AskUserQuestion when spawned, switch output format for
   subagent consumption, degrade interactive features cleanly?
3. Are the defaults safe for the spawned case (so a parent agent
   doesn't hang on a never-resolved AskUserQuestion call)?

Apply N/A only when the skill clearly cannot be invoked from another
agent (e.g., a pure interactive design tool). Most modern skills can
be spawned; default to applicable.
```

### Output schema

Standard schema. Evidence should quote the detection mechanism (e.g., flag, env var, capability check) AND the adaptive behavior triggered.

### Exemplar cases

**A+ example:** `gstack` flips off `AskUserQuestion` and upgrade prompts when OpenClaw spawns a Claude Code session — same skill source, different runtime behavior, with the detection mechanism explicit in the skill body.

**A example:** `daymade/deep-research` includes a P0 capability check that degrades to sequential execution when parallel-spawn isn't available; `AgriciDaniel/cybersecurity` distinguishes orchestrator vs agent contexts with `--focus` flags.

**B example:** `zarazhangrui/frontend-slides` Phase 0 mode detection adapts output for batch vs interactive runs; the adaptation is real but only covers output format, not the AskUserQuestion / interactive-feature side.

**C example:** Skill mentions it can be called from another agent but provides no detection mechanism — relies on the caller to know not to expect interactive features.

**D/F example:** Skill always calls `AskUserQuestion` regardless of caller, blocking any subagent invocation; OR always emits human-only prose with no machine-readable alternative.

**N/A example:** Pure Creative skills designed for interactive aesthetic judgment (e.g., a design-review skill that fundamentally requires a human looking at output) — score N/A with justification "skill is interactive-only by design; spawned use is not supported and is documented as such."

### Persona modulation

- **strict-academic:** require both detection AND adaptive behavior for A. Detection-only with no adaptation caps at C.
- **pragmatic-practitioner (default):** A if both halves of the loop are present; B+ if adaptation covers the most-likely-to-hang case (AskUserQuestion suppression) but not the full surface.
- **charitable-newcomer:** B if any spawn-awareness is visible, even just an opt-out flag for AskUserQuestion.

### Defer-to-user conditions

Output `needs-human-judgment` if:
- The skill's invocation pattern is unclear from the SKILL.md alone (does the parent harness pass context implicitly?)
- The skill is a Hybrid where Procedural and Reference modes are interleaved, and only one mode supports spawn

### Known limitations

- This principle was promoted from deferred candidate #30 in v0.3; calibration data is pending the 25-principle kappa re-run.
- Skills that are spawn-safe by accident (no AskUserQuestion calls anywhere) score lower than warranted because the principle rewards intent + detection, not just the absence of blocking calls. Persona modulation softens this for charitable-newcomer.
- The `needs-human-judgment` defer rate for this principle is expected to be elevated until v0.3 kappa data calibrates the borderline cases.

---

## Judge summary

| # | Principle | What it judges | Defer rate (estimate) |
|---|---|---|---|
| 3 | Modes | Multiple paths + naming + criteria + default | Low (15%) |
| 6 | Personas / voice | Behavioral discipline vs decoration | Medium (25%) |
| 8 | Synthesis | Priority rules + conflict resolution | Low (10%) |
| 11 | Output spec | Format + sections + length + content rules + anti-templates | Medium (20%) |
| 14 | Context scope | Boundaries + per-agent scoping + reasoning | Low (15%) |
| 15 | Progress | Status updates + key stats + completion summary | Low (10%) |
| 17 | Autonomy | Defaults + inference + appropriate AskUserQuestion | Medium (20%) |
| 20 | Output-first | Output defined before phases | Low (15%) |
| 21 | Decision class | Mechanical / Taste / User Challenge taxonomy | High (35%) |
| 22 | Voice + writing | Voice rules as skill content + banned vocab + anti-templates | Medium (25%) |
| 24 | Self-observation | Persistence + read-back + behavior change loop | High (provisional, v0.3) |
| 25 | Spawn-detection | Context detection + adaptive behavior | High (provisional, v0.3) |

**Defer rate** = expected % of evaluations where the judge outputs `needs-human-judgment` rather than a grade. Higher defer rates flag principles that may not be well-calibrated as LLM-judges and may need human scoring in the kappa pilot.

**Highest-risk judges:** #21 (decision class) — concept is new, taxonomy may be ambiguous; #6 (personas/voice) and #22 (voice rules) — taste judgments. The v0.3 additions (#24 self-observation, #25 spawn-detection) are also expected to be high-defer until kappa-calibrated.

**Lowest-risk judges:** #8 (synthesis) and #15 (progress) — concrete patterns to detect; less subjective.

---

## Cross-references

- [`../SKILL.md`](../SKILL.md) — The skill that loads this file (Phase 3)
- [`../genesis.md`](../genesis.md) — Architecture spec listing the 10 v0.2 semantic principles (this file adds #24 and #25 in v0.3)
- [`./algorithmic-detectors.md`](./algorithmic-detectors.md) — The complementary file for the 13 algorithmic principles (12 added in Stage 1b; #23 added in v0.3)
- [`../../../04-RUBRIC/principles.md`](../../../04-RUBRIC/principles.md) — Principle definitions (the source of truth)
- [`../../../04-RUBRIC/empirical-validation.md`](../../../04-RUBRIC/empirical-validation.md) — Where the exemplar cases come from
- [`../calibration.md`](../calibration.md) — Stage 1d will validate these judges against the 4 manual evaluations
