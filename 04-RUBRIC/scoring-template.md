# Scoring Template

> Copy this file to score any SKILL.md against the 20 principles. Use it for self-audit, peer review, or contribution to `05-EVALUATION/community/`.

**Status:** Skeleton — final template lands in Phase 3, generalized from the scoring format used in the original n=4 regression study.

---

## Usage

1. Copy this file to a new location (`05-EVALUATION/community/your-skill-name.md` if you're contributing).
2. Fill in the metadata block.
3. Score each of the 20 principles using the grade scale below.
4. Mark `N/A` with explicit justification for principles that don't apply.
5. Compute the overall grade.
6. List key strengths and weaknesses.

---

## Metadata block

```
**Skill name:** /your-skill-name
**Lines:** N
**Model used:** Claude Sonnet 4.x / Opus 4.x / etc.
**Path:** LEAN / FULL / ORCHESTRATION
**Composition:** standalone / N composed skills (list)
**Authored by:** human / meta-paap / hybrid
**Date scored:** YYYY-MM-DD
**Scorer:** Your name + handle
```

---

## Grade scale

- **A+** — Exemplary; sets the standard for this principle
- **A** — Fully meets the principle as defined
- **B+** — Meets the principle with one minor gap
- **B** — Mostly meets, one structural shortcut
- **C** — Partially meets; visible failure mode if stressed
- **D** — Largely violates the principle
- **F** — Violates outright
- **N/A (skip)** — Doesn't apply to this skill's design; **must include one-sentence justification**

---

## Principle-by-principle scoring

(Phase 3 fills in the table with each principle as a row, each row having: Grade | Notes | Evidence)

| # | Principle | Grade | Notes | Evidence (line ref) |
|---|---|---|---|---|
| 1 | Description as router | | | |
| 2 | Route before work | | | |
| 3 | Modes | | | |
| 4 | State | | | |
| 5 | Parallel | | | |
| 6 | Personas | | | |
| 7 | Files = bus | | | |
| 8 | Synthesis | | | |
| 9 | Human gate | | | |
| 10 | Exit = question | | | |
| 11 | Output spec | | | |
| 12 | Gates = 3 parts | | | |
| 13 | External storage | | | |
| 14 | Context scope | | | |
| 15 | Progress | | | |
| 16 | Errors | | | |
| 17 | Autonomy | | | |
| 18 | Path resolution | | | |
| 19 | Composition | | | |
| 20 | Output-first | | | |

**Overall grade:** [computed]

---

## Required narrative sections

After the table, fill in:

### Key strengths (3-5 bullets)
What this skill does notably well. Specific, with line references.

### Key weaknesses (3-5 bullets)
What's missing or under-specified. Honest. Be willing to flag your own work.

### Risk-ranked failure modes
For each weakness: HIGH / MEDIUM / LOW likelihood of failing on first run.

### What you'd change in v2
One paragraph. The single highest-leverage edit.

---

*Populated in Phase 3.*
