# Semantic Judges — `/paap-eval` Phase 3 Reference

> Per-principle LLM-judge prompts for the ~10 semantic principles in the [PaaP rubric](../../../04-RUBRIC/principles.md). Loaded by [`paap-eval/SKILL.md`](../SKILL.md) Phase 3.

**Status:** Placeholder (Stage 1a). Full judge prompts added in Stage 1c of v0.2.

---

## Why this file is a placeholder

The [`paap-eval` SKILL.md](../SKILL.md) v0 scaffold (Stage 1a) wires up Phase 3 to read this file at runtime. Without this file, the skill falls back to "inline judging mode" — using the principle definitions from `principles.md` directly without the calibrated judge prompts.

Stage 1c fills in per-principle judge prompts that:
- Frame the judge with persona context (strict-academic / pragmatic-practitioner / charitable-newcomer)
- Force confidence ratings + uncertainty acknowledgment
- Include exemplar cases (here's what an A looks like; here's what a C looks like)
- Defer explicitly to user when the judgment is irreducibly subjective

---

## What this file will contain (after Stage 1c)

For each of the 10 semantic principles, a section with:

- **Principle reference** — name + number from `04-RUBRIC/principles.md`
- **Judge prompt template** — the LLM prompt with placeholder slots for skill content + persona
- **Required output schema** — grade + confidence + reasoning + uncertainty_notes
- **Exemplar cases** — A-grade example, C-grade example, F-grade example, drawn from corpus
- **Persona-specific framing additions** — what changes per persona variant
- **Defer-to-user conditions** — when the judge should abstain rather than guess

The 10 semantic principles in scope:

1. #3 Modes
2. #6 Personas / voice
3. #8 Synthesis
4. #11 Output spec
5. #14 Context scope
6. #15 Progress
7. #17 Autonomy
8. #20 Output-first
9. #21 Decision class drives gating
10. #22 Voice + writing rules

---

## Why these need LLM-judges (not algorithmic detectors)

These principles require *reading* and *judgment*, not pattern matching. Examples:

- **#11 Output spec** — A regex can detect that an "Output" section exists; only judgment can rate whether the spec leaves nothing to interpretation.
- **#6 Personas** — A regex can find "You are an X" framings; only judgment can rate whether the persona is behavioral discipline vs decoration.
- **#21 Decision class** — Identifying Mechanical / Taste / User Challenge classifications requires understanding the decision's nature, not its surface form.

Stage 1c's judge prompts are the calibration instrument that turns LLM judgment into reproducible scoring.

---

## Cross-references

- [`../SKILL.md`](../SKILL.md) — The skill that loads this file
- [`../genesis.md`](../genesis.md) — Architecture spec listing all 10 principles
- [`../../../04-RUBRIC/principles.md`](../../../04-RUBRIC/principles.md) — Principle definitions
- [`../../../07-OPEN-QUESTIONS.md`](../../../07-OPEN-QUESTIONS.md) — v0.2 plan including Stage 1c
