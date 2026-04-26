# `/paap-eval` — User Quick Reference

> A skill that auto-scores any SKILL.md file against the 22-principle PaaP rubric. Archetype-aware. Confidence-rated per principle. Self-disclosed as an LLM-judge.

**Status:** v0 scaffold (Stage 1a). Production-ready after Stages 1b + 1c + 1d complete.

---

## What this is

`/paap-eval` is the operational complement to [`/meta-paap`](../SKILL.md):

| Skill | What it does | When to use |
|---|---|---|
| `/meta-paap` | Generates a SKILL.md from a workflow description | You want to write a skill |
| `/paap-eval` | Scores a SKILL.md against the 22-principle rubric | You want to evaluate a skill (yours or someone else's) |

Together they form the generate → evaluate loop that operationalizes the [PaaP rubric](../../04-RUBRIC/principles.md).

---

## Why this exists

v0.1 of the rubric was *expensive to apply* — the [scoring template](../../04-RUBRIC/scoring-template.md) takes 30-45 minutes per skill manually. `/paap-eval` collapses that to ~1 minute per skill, which makes:

- Multi-scorer reliability studies tractable (3 prompt-variants of one skill = a kappa pilot)
- Corpus-scale evaluation possible (100+ skills in an hour, not 50+ hours)
- Head-to-head experiments practical (50 outputs blind-scored)
- The rubric itself usable in production (skill authors auditing their own work)

See [`../../07-OPEN-QUESTIONS.md`](../../07-OPEN-QUESTIONS.md) for the full v0.2 plan that this skill unlocks.

---

## How to use (after Stages 1b + 1c + 1d ship)

**Basic invocation:**

```
/paap-eval ./path/to/SKILL.md
```

Output goes to `./scored/<skill-slug>-<YYYY-MM-DD>.md` by default.

**With persona variant (relevant for kappa pilot work):**

```
/paap-eval ./path/to/SKILL.md --persona strict-academic
/paap-eval ./path/to/SKILL.md --persona pragmatic-practitioner    # default
/paap-eval ./path/to/SKILL.md --persona charitable-newcomer
```

**With archetype hint (skip auto-detection):**

```
/paap-eval ./path/to/SKILL.md --archetype Reference
```

**Custom output path:**

```
/paap-eval ./path/to/SKILL.md --output ./my-evaluations/foo.md
```

---

## What you get

A scored evaluation file matching the [`scoring-template.md`](../../04-RUBRIC/scoring-template.md) format, plus three additional sections:

- **Confidence map** — per-principle confidence (high/medium/low)
- **What I was uncertain about** — low-confidence principles flagged for human review
- **What needs human judgment** — irreducibly subjective items the eval skill explicitly defers on

Plus a self-disclosure footer making clear this is an LLM-judge, not an objective grade.

---

## What this is NOT

- **Not an objective grade.** It's a structured first-pass LLM-judge. Always review low-confidence principles.
- **Not a replacement for human scoring** when stakes are high. For paper-track or hiring-decision uses, use the manual scoring template + human review.
- **Not a meta-paap competitor.** They're complementary: meta-paap generates, /paap-eval scores.
- **Not yet calibrated.** v0.2 Stage 1d runs validation against the four manual evaluations; persona variants are calibrated empirically in Stage 2.

---

## Status of components

| Component | Status | Stage |
|---|---|---|
| [`SKILL.md`](./SKILL.md) — 7-phase scaffold | ✅ Done | 1a |
| [`genesis.md`](./genesis.md) — elicitation + architecture spec | ✅ Done | 1a |
| [`references/algorithmic-detectors.md`](./references/algorithmic-detectors.md) — Phase 2 logic | ⏸ Placeholder | 1b |
| [`references/semantic-judges.md`](./references/semantic-judges.md) — Phase 3 prompts | ⏸ Placeholder | 1c |
| [`calibration.md`](./calibration.md) — validation against manual scoring | ⏸ Placeholder | 1d |

---

## See also

- [`SKILL.md`](./SKILL.md) — The skill itself (read this for the full architecture)
- [`genesis.md`](./genesis.md) — How this skill was generated (dogfooding audit)
- [`../README.md`](../README.md) — `/meta-paap` user guide (the complementary skill)
- [`../../04-RUBRIC/principles.md`](../../04-RUBRIC/principles.md) — The 22 principles being scored against
- [`../../04-RUBRIC/scoring-template.md`](../../04-RUBRIC/scoring-template.md) — The output format
- [`../../07-OPEN-QUESTIONS.md`](../../07-OPEN-QUESTIONS.md) — v0.2 plan and where this skill fits
