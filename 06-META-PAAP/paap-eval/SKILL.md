---
name: paap-eval
description: Score any SKILL.md file against the 22-principle PaaP rubric with archetype-aware applicability and per-principle confidence ratings. Provide a path to a SKILL.md file. Use when you want a structured first-pass evaluation of a skill (your own or someone else's) before publishing, contributing, or comparing across a corpus. Do NOT use for scoring non-SKILL.md files (READMEs, general docs). Do NOT use to claim objective grades — this is an LLM-judge with stated limitations. Do NOT use for promotion or hiring decisions about a skill author. Do NOT use for skills written in languages other than English at v0.2.
tools: [Read, Bash, Write, AskUserQuestion, Task]
composed_skills: []
---

# paap-eval — PaaP Rubric Scoring Skill

> A structured first-pass evaluation of any SKILL.md against the 22-principle [PaaP rubric](../../04-RUBRIC/principles.md). Archetype-aware. Confidence-rated per principle. Self-disclosed as an LLM-judge with stated limitations.

**Status:** v0.2 released. The phase structure, per-principle detector logic (Stage 1b), semantic judge prompts (Stage 1c), calibration pass (Stage 1d), and 3-persona kappa pilot (Stage 2) are complete. See [`genesis.md`](./genesis.md) for the elicitation answers and architecture spec that drove the initial generation.

---

## Pre-Phase — Input Validation

Before any work, verify the input is a SKILL.md file the rubric can evaluate.

```
Read the path provided as input.

If file does not exist:
    STOP. Tell the user: "File not found at <path>. /paap-eval scores SKILL.md
    files only — provide a valid path."

Read the first 30 lines.

If the file does not begin with `---` followed by YAML frontmatter:
    STOP. Tell the user: "This file does not appear to be a SKILL.md
    (no YAML frontmatter detected). /paap-eval scores SKILL.md files only.
    For scoring general docs against the rubric, use the manual scoring
    template at 04-RUBRIC/scoring-template.md."

Parse the YAML frontmatter. Verify it contains `name` and `description` fields.

If either missing:
    STOP. Tell the user: "SKILL.md frontmatter must contain `name` and
    `description` fields per the Anthropic SKILL.md spec. This file is
    missing one or both."
```

Exit condition: Can you answer "is this file a valid SKILL.md with YAML frontmatter containing name + description"? Yes → proceed to Phase 0. No → STOP per above.

---

## Phase 0 — Configuration

Resolve runtime settings before scoring.

```
Parse invocation flags:
    --persona <name>      strict-academic | pragmatic-practitioner (default) | charitable-newcomer
    --output <path>       default: ./scored/<skill-slug>-<YYYY-MM-DD>.md
    --archetype <name>    Procedural | Reference | Creative | Hybrid | auto (default)
    --rubric-version      default: v0.1 (current); future versions selectable

Resolve rubric path (three-tier fallback):
    PRIMARY:  ./04-RUBRIC/principles.md
    FALLBACK: ../04-RUBRIC/principles.md  (if invoked from a sub-directory)
    SEARCH:   find . -name "principles.md" -path "*/04-RUBRIC/*" 2>/dev/null | head -1

If rubric not found:
    STOP. Tell the user: "Could not locate principles.md. /paap-eval requires
    the PaaP rubric file to score against. Either invoke from inside the
    prompt-as-a-process repo, or set --rubric-path explicitly."

Resolve output directory:
    mkdir -p ./scored/  (or the path from --output)

Generate skill-slug from the SKILL.md's `name` field (lowercase, hyphenated).

Compute scratch directory: .paap-eval-scratch/<skill-slug>/
    mkdir -p this directory; phase outputs go here, deleted in Phase 5.

Save 00-config.json:
    {
      "skill_path": "...",
      "skill_slug": "...",
      "persona": "...",
      "output_path": "...",
      "rubric_path": "...",
      "rubric_version": "...",
      "archetype_hint": "...",
      "scratch_dir": "..."
    }
```

Exit condition: Can you answer "what persona, what output path, what rubric version, what archetype hint"? Yes → proceed to Phase 1.

---

## Phase 1 — Archetype Detection

Classify the skill's archetype before scoring. Different archetypes apply different subsets of principles.

```
Read the entire SKILL.md.

Read principles.md "How to read this rubric" section for archetype definitions
and the applicability matrix.

Auto-classify the skill as one of:
    Procedural    — multi-step workflow with ordering, gates, exits
    Reference     — library/API documentation reformatted as SKILL.md
    Creative      — output-spec-and-voice driven; aesthetic judgment dominates
    Hybrid        — doesn't fit cleanly; identify dominant mode

Compute confidence (0.0 - 1.0) based on signals:
    Procedural signals: numbered phases, exit conditions, quality gates,
                        synthesis sections, AskUserQuestion calls
    Reference signals:  description + tool/method index + code examples,
                        no phase structure, no gates
    Creative signals:   strong output spec + voice rules + anti-templates,
                        no procedural enforcement, aesthetic guidance

If --archetype was set explicitly in Phase 0:
    Use that. Skip auto-classification.
    Set confidence = 1.0 (user-asserted).

If confidence >= 0.75:
    Proceed with detected archetype.

If confidence < 0.75 (the human gate):
    Use AskUserQuestion to present top 2 candidate archetypes:
        "I detected this skill as <top1> (confidence X%) or possibly <top2>
        (confidence Y%). Confirm which archetype to score against, or pick
        Hybrid to apply principles from the dominant mode."
    Wait for user reply. Use the user's choice.

Determine the applicable principle set from principles.md applicability matrix:
    Universal principles: always apply
    Procedural-only: apply if archetype includes Procedural component
    Reference-applicable: apply if archetype includes Reference component
    Creative-applicable: apply if archetype includes Creative component
    Conditional: apply if the skill's content triggers them

Save 01-archetype.json:
    {
      "archetype": "...",
      "confidence": 0.XX,
      "user_confirmed": bool,
      "applicable_principles": [list of principle numbers],
      "skipped_principles": [list with one-line N/A justifications]
    }
```

Exit condition: Can you answer "what archetype is this skill, and which principles apply"? Yes → proceed to Phase 2.

---

## Phase 2 — Algorithmic Auto-Score (parallel-burst)

For each algorithmic principle (the ~12 that can be pattern-matched), run its detector. Each detector outputs a grade + confidence + line evidence.

**Load the detector reference file:**

```
Read references/algorithmic-detectors.md

If file not found:
    Note: "references/algorithmic-detectors.md is missing.
    The v0.2 release expects this file to be present. Falling back to manual-
    detection mode: ask user to score these principles manually."
    Set fallback_mode = true; flag in final report.

For each principle in the algorithmic set that's also in applicable_principles:
    Run its detector against SKILL.md content.
    Detector outputs:
        grade: A+ | A | B+ | B | C | D | F
        confidence: high | medium | low
        evidence: list of "L<n>: <quoted line>" references
        notes: optional one-line context
```

**The 12 algorithmic principles (full detector logic in references/algorithmic-detectors.md):**

1. **#1 Description as router** — YAML parse: anti-triggers count, trigger-phrase count
2. **#2 Route before work** — Phase-0-pattern detection (Phase 0, "Routing", "Classification" headings)
3. **#4 State** — keyword search ("state.json", "Resume Protocol", persistent storage mentions)
4. **#5 Parallel** — keyword search ("parallel", "single message", "do NOT launch sequentially")
5. **#7 Files = bus** — numbered file convention detection (01-, 02-, etc.)
6. **#9 Human gate** — AskUserQuestion call count + position
7. **#10 Exit = question** — "Exit condition" + "Can you answer" pattern detection
8. **#12 Gates = 3 parts** — Quality gate structure: check + failure + recovery
9. **#13 External storage** — line count vs 400-line threshold; references/ directory check
10. **#16 Errors** — error table detection (markdown table with Error|Action columns)
11. **#18 Path resolution** — hardcoded absolute path detection (negative signal)
12. **#19 Composition** — composed_skills YAML field + runtime resolution patterns

**Parallel execution:**

Spawn one Task per applicable algorithmic principle in a SINGLE message. Do NOT launch sequentially. Each Task receives:
- The skill content
- The principle definition + detector logic from references/algorithmic-detectors.md
- The persona from 00-config.json (affects strictness)

Save 02-algorithmic-scores.json:

```
{
  "principle_1": {
    "grade": "A",
    "confidence": "high",
    "evidence": ["L3: 'description: ...'", "L5: 'Do NOT use for...'"],
    "notes": "3 anti-triggers, 4 trigger phrases"
  },
  ...
}
```

Exit condition: Can you answer "have I run a detector for every applicable algorithmic principle, and have a grade + confidence + evidence for each"? Yes → proceed to Phase 3.

---

## Phase 3 — Semantic LLM-Judge (parallel-burst)

For each semantic principle (the ~10 requiring judgment), run an LLM-judge prompt. Each judge outputs grade + confidence + reasoning + uncertainty notes.

**Load the judge reference file:**

```
Read references/semantic-judges.md

If file not found:
    Note: "references/semantic-judges.md is missing.
    The v0.2 release expects this file to be present. Falling back to inline
    judging mode using the principle definitions only."
    Set inline_judge_mode = true; flag in final report.
```

**The 10 semantic principles (full judge prompts in references/semantic-judges.md):**

1. **#3 Modes** — Are modes explicit, named, criteria-driven? Or implicit?
2. **#6 Personas / voice** — Behavioral discipline vs generic role assignment?
3. **#8 Synthesis** — Explicit priority rules + conflict resolution? Or hand-wavy?
4. **#11 Output spec** — Format + sections + length + content rules + anti-templates?
5. **#14 Context scope** — Explicit boundaries stated + per-agent scoping reasoning?
6. **#15 Progress** — Status updates with key stats at meaningful checkpoints?
7. **#17 Autonomy** — Sensible defaults + mode inference + manual safe-fallback?
8. **#20 Output-first** — Output spec defined before phases?
9. **#21 Decision class drives gating** — Mechanical / Taste / User Challenge taxonomy applied?
10. **#22 Voice + writing rules** — Tone, banned phrases, prose structure as skill content?

**Parallel execution:**

Spawn one Task per applicable semantic principle in a SINGLE message. Do NOT launch sequentially. Each Task receives:
- The skill content
- The principle definition from principles.md
- The judge prompt from references/semantic-judges.md
- The persona from 00-config.json (affects emphasis):
    - strict-academic: harder grading, higher confidence threshold
    - pragmatic-practitioner: real-world weighting (default)
    - charitable-newcomer: weights "what would a novice find useful?" higher

Each judge MUST output:
- grade: A+ | A | B+ | B | C | D | F
- confidence: high | medium | low
- reasoning: 2-3 sentences explaining the grade
- uncertainty_notes: optional, but required if confidence is low

Save 03-semantic-scores.json (same shape as algorithmic).

Exit condition: Can you answer "have I judged every applicable semantic principle with grade + confidence + reasoning"? Yes → proceed to Phase 4.

---

## Phase 4 — Synthesis

Aggregate algorithmic + semantic into one score table; compute aggregate grade.

```
Read 01-archetype.json, 02-algorithmic-scores.json, 03-semantic-scores.json.

Build the principle-by-principle score table:
    For each of the 22 principles:
        If in applicable_principles: use grade from 02 or 03
        If in skipped_principles: mark N/A with the one-line justification

Compute aggregate grade:
    Convert grades to numeric (A+ = 4.3, A = 4.0, B+ = 3.3, ..., F = 0)
    Average across applicable principles only (exclude N/A)
    Map back to letter grade

Compute confidence summary:
    Count principles with high / medium / low confidence
    Flag any principle with low confidence for the "what I was uncertain
    about" section

Sanity check (Quality Gate 4):
    Aggregate grade should match the per-principle distribution:
        - If aggregate is A but most individual grades are B-, RECOMPUTE
        - If most grades are A but aggregate is C, RECOMPUTE
    Mismatch indicates a bug; re-run the aggregation.

Save 04-synthesis.json with full score table + aggregate + confidence summary.
```

Exit condition: Can you answer "do I have a grade for every applicable principle, with confidence ratings, and a sanity-checked aggregate"? Yes → proceed to Phase 5.

---

## Phase 5 — Report Generation

Write the scored evaluation in `04-RUBRIC/scoring-template.md` format.

```
Read 04-RUBRIC/scoring-template.md to confirm the exact section structure.
Read 04-synthesis.json for the data.

Generate the report file at <output_path> with these sections in order:

1. Metadata block:
   - Skill name (slug)
   - Repo / location (path provided to /paap-eval)
   - Lines (count)
   - Archetype (with confidence + user-confirmed flag)
   - Path: LEAN / FULL / ORCHESTRATION (line-count-derived)
   - Composition (parsed from composed_skills field)
   - Authored by (best-effort from path heuristics; "unknown" if unclear)
   - Date scored
   - Scorer: "/paap-eval v0.2.0 — persona: <persona>"
   - Rubric version (from config)

2. Archetype declaration with one-line justification

3. Principle-by-principle scoring table (22 rows):
   | # | Principle | Grade | Notes / evidence |
   For N/A rows: include the one-line justification in Notes column

4. Confidence map (per-principle, summarized):
   - High confidence: <N> principles
   - Medium confidence: <N> principles
   - Low confidence: <N> principles
   - List the low-confidence principles by number

5. Key strengths (3-5 bullets)
   Generated from the principles scoring A or A+, prioritizing high-confidence ones

6. Key weaknesses (3-5 bullets, risk-ranked HIGH/MEDIUM/LOW)
   Generated from principles scoring C or worse, prioritizing high-confidence ones

7. What I was uncertain about
   List of low-confidence principles with the uncertainty_notes from each judge

8. What needs human judgment
   Principles where the judge explicitly deferred OR where confidence < medium

9. Aggregate grade (computed)

10. Self-disclosure footer (REQUIRED, exact text):
    ---
    *Generated by `/paap-eval` v0.2.0 (PaaP rubric v<X>) on <date>.*
    *This is a structured first-pass LLM-judge evaluation, not an objective grade.
    Confidence ratings are self-reported by the judge model and may be
    miscalibrated. Do not cite this evaluation as definitive without
    independent human review of low-confidence principles. The scoring
    template at `04-RUBRIC/scoring-template.md` documents the methodology;
    `06-META-PAAP/paap-eval/SKILL.md` documents this skill's design.*
```

Exit condition: Can you answer "is the evaluation file complete, formatted correctly, and does it have the self-disclosure footer"? Yes → proceed to cleanup.

**Cleanup:**

```
Delete .paap-eval-scratch/<skill-slug>/ directory.
Print summary to stdout:
    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
    /paap-eval — done
    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
    Skill scored:    /<skill-name>
    Archetype:       <archetype> (confidence: <high|medium|low>)
    Aggregate grade: <grade>
    Output:          <output_path>
    Confidence:      <H>/<M>/<L> (high/medium/low)
    Persona:         <persona>
    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
    Read the report and verify low-confidence principles before relying
    on the grade.
    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Quality Gates

| Gate | Where | Check | Failure | Recovery |
|---|---|---|---|---|
| 1 | After Phase 1 | Archetype confidence ≥ 0.75 OR user-confirmed | Confidence below threshold and no user confirmation | AskUserQuestion; if user can't decide, default to Hybrid + flag in report |
| 2 | After Phase 2 | Every applicable algorithmic principle has grade + evidence | Detector failed for any principle | Re-run failed detectors; if still failing, mark "detector-error" in report and continue |
| 3 | After Phase 3 | Every applicable semantic principle has grade + confidence + reasoning | Judge returned malformed output for any principle | Re-run failed judges with simpler prompt; if still failing, mark "needs-human-judgment" |
| 4 | After Phase 4 | Aggregate grade matches per-principle distribution sanity check | Aggregate too far from individual grades | Recompute; investigate bug |
| 5 | After Phase 5 | Output file exists, all 10 sections present, self-disclosure footer included | Missing section | Regenerate Phase 5 output |

---

## Error Handling

| Situation | Action |
|---|---|
| Input file not a valid SKILL.md | STOP in Pre-Phase with explanation |
| `principles.md` not found | STOP in Phase 0; require user to set `--rubric-path` or invoke from repo |
| Archetype confidence ambiguous | AskUserQuestion in Phase 1 |
| `references/algorithmic-detectors.md` missing | Fall back to manual-detection mode; flag install/repo packaging issue |
| `references/semantic-judges.md` missing | Fall back to inline judging mode; flag install/repo packaging issue |
| Parallel sub-agent fails for one principle | Re-run that principle's detector/judge; if still fails, mark `error` and continue |
| LLM-judge returns malformed grade (not in A+...F) | Retry once with stricter prompt; if still malformed, mark `error` |
| Output directory not writable | STOP with permission error message |
| Skill being scored is `/paap-eval` itself | Allow it (reflexive scoring is interesting); add note to report: "Scoring oneself — recursion noted" |
| Skill being scored is `/meta-paap` | Allow it; add note: "Scoring meta-paap — outputs of this skill are evaluated separately in 05-EVALUATION/" |

---

## Limitations (stated upfront, not buried)

This skill has known limitations that are inherent to its design, not bugs:

1. **It's an LLM-judge.** Inherits position bias, length bias, style bias. Self-reported confidence may be miscalibrated. Use the scoring template at `04-RUBRIC/scoring-template.md` for any high-stakes evaluation that needs human judgment.

2. **The rubric content is v0.1; the evaluation instrument is v0.2.** Stage 2 prompt-variant reliability data is in, but multi-model and human-rater kappa are still v0.3 work. Some principles may have low inter-rater reliability that future versions of this skill will reflect.

3. **Algorithmic detectors are pattern-matching, not parsing.** They can be fooled by skills that follow the spirit of a principle but use unusual surface forms.

4. **Persona variants are calibrated only within one model family.** strict-academic / pragmatic-practitioner / charitable-newcomer were tested in the v0.2 Stage 2 kappa pilot; v0.3 needs cross-model validation.

5. **English-only at v0.2.** Skills in other languages may produce unreliable grades.

6. **Reference and Creative archetypes are scored against a smaller principle set.** That's correct (they shouldn't be penalized for not being procedural), but it also means their aggregate grades are computed from fewer data points and may be noisier.

---

## See also

- [`genesis.md`](./genesis.md) — Elicitation answers + architecture spec that drove this generation
- [`README.md`](./README.md) — User-facing quick-start (added in Stage 1d after validation)
- [`references/algorithmic-detectors.md`](./references/algorithmic-detectors.md) — Detector logic for the 12 algorithmic principles (added in Stage 1b)
- [`references/semantic-judges.md`](./references/semantic-judges.md) — Judge prompts for the 10 semantic principles (added in Stage 1c)
- [`calibration.md`](./calibration.md) — Validation results against the 4 manual evaluations (added in Stage 1d)
- [`../../04-RUBRIC/principles.md`](../../04-RUBRIC/principles.md) — The rubric this skill scores against
- [`../../04-RUBRIC/scoring-template.md`](../../04-RUBRIC/scoring-template.md) — The output format
- [`../../05-EVALUATION/methodology.md`](../../05-EVALUATION/methodology.md) — How rubric-based evaluation works
- [`../../07-OPEN-QUESTIONS/`](../../07-OPEN-QUESTIONS/) — v0.2 plan and where this skill fits
