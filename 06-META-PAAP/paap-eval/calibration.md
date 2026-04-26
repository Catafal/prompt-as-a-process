# `/paap-eval` Calibration Notes

> Validation of `/paap-eval` against the four manual evaluations in [`05-EVALUATION/`](../../05-EVALUATION/). Where do `/paap-eval` and the manual scorer agree? Where do they diverge? What does that tell us?

**Status:** Placeholder (Stage 1a). Validation runs in Stage 1d after Stages 1b + 1c complete.

---

## Why this file is a placeholder

Once Stage 1b (algorithmic detectors) and Stage 1c (semantic judges) are in, Stage 1d runs `/paap-eval` against the four skills already manually scored:

- [`/skill-audit`](../../05-EVALUATION/test-1-skill-audit.md) — manual grade: B+
- [`/article-forge`](../../05-EVALUATION/test-2-article-forge.md) — manual grade: A-
- [`/review-plan`](../../05-EVALUATION/test-3-review-plan.md) — manual grade: A- / A
- [`/idea-to-pr`](../../05-EVALUATION/test-4-idea-to-pr.md) — manual grade: A-

For each skill, the calibration compares:

- **Aggregate grade** — does `/paap-eval`'s grade match the manual one?
- **Per-principle grades** — which principles agree? Which diverge?
- **Confidence calibration** — when `/paap-eval` says "high confidence," is it actually right?
- **Archetype detection** — does `/paap-eval` classify the skill the same way the manual scorer did?

---

## What this file will contain (after Stage 1d)

A per-skill calibration section with:

- **Aggregate grade comparison** — manual vs `/paap-eval` per persona variant
- **Per-principle agreement table** — which principles match exactly, which differ
- **Divergence analysis** — root cause for each disagreement (detector miss, judge bias, manual scorer bias)
- **Calibration adjustments** — proposed tweaks to detectors/judges based on findings
- **Confidence audit** — for each "high confidence" claim, did it hold?

Plus a cross-skill summary:

- Overall agreement rate (algorithmic vs semantic principles)
- Persona-variant differences (does strict-academic agree more or less with manual scoring?)
- Which principles are most reliably scored by `/paap-eval`
- Which principles still need human judgment despite Stage 1c

---

## Why this matters

Without calibration, `/paap-eval` is a black-box scorer that might reproduce the rubric author's biases at scale (the "self-reinforcement" problem flagged in the v0.1 limitations). Calibration against the four manual evaluations is the cheapest sanity check available — it doesn't validate the skill against ground truth (no ground truth exists for rubric scoring), but it validates that `/paap-eval` makes the same decisions a careful manual scorer makes.

If calibration finds systematic divergence (e.g., `/paap-eval` always scores Reference skills lower than the manual scorer), that's a direct signal to fix Stage 1c's judge prompts before Stage 2 (kappa pilot) runs.

---

## Cross-references

- [`./SKILL.md`](./SKILL.md) — The skill being calibrated
- [`./genesis.md`](./genesis.md) — Architecture spec
- [`../../05-EVALUATION/`](../../05-EVALUATION/) — The four manual evaluations being calibrated against
- [`../../05-EVALUATION/methodology.md`](../../05-EVALUATION/methodology.md) — How the manual evaluations were done
- [`../../07-OPEN-QUESTIONS.md`](../../07-OPEN-QUESTIONS.md) — v0.2 plan including Stage 1d
