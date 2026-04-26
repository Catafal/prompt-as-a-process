# `/paap-eval` — User Quick Reference

> A skill that auto-scores any SKILL.md file against the 25-principle PaaP rubric. Archetype-aware. Confidence-rated per principle. Self-disclosed as an LLM-judge.

**Status:** v0.3-dev on a v0.2 baseline. Stage 1a scaffold, Stage 1b detectors (12 algorithmic + 1 v0.3-added = 13 total), Stage 1c semantic judges (10 + 2 v0.3-added = 12 total), Stage 1d calibration, and Stage 2 kappa pilot are complete. The v0.3 additions (#23 host-portable algorithmic detector + #24 self-observation and #25 spawn-detection semantic judges) are wired in but have not been calibration-tested at 25-principle scale — calibration deferred to v0.4. Multi-model kappa data extending the v0.2 prompt-variant pilot to GPT-5.4 and Gemini-3 is in [`../../05-EVALUATION/kappa-pilot-multimodel.md`](../../05-EVALUATION/kappa-pilot-multimodel.md).

---

## What this is

`/paap-eval` is the operational complement to [`/meta-paap`](../SKILL.md):

| Skill | What it does | When to use |
|---|---|---|
| `/meta-paap` | Generates a SKILL.md from a workflow description | You want to write a skill |
| `/paap-eval` | Scores a SKILL.md against the 25-principle rubric | You want to evaluate a skill (yours or someone else's) |

Together they form the generate → evaluate loop that operationalizes the [PaaP rubric](../../04-RUBRIC/principles.md).

---

## Why this exists

v0.1 of the rubric was *expensive to apply* — the [scoring template](../../04-RUBRIC/scoring-template.md) takes 30-45 minutes per skill manually. `/paap-eval` collapses that to ~1 minute per skill, which makes:

- Multi-scorer reliability studies tractable (3 prompt-variants of one skill = a kappa pilot)
- Corpus-scale evaluation possible (100+ skills in an hour, not 50+ hours)
- Head-to-head experiments practical (50 outputs blind-scored)
- The rubric itself usable in production (skill authors auditing their own work)

See [`../../07-OPEN-QUESTIONS/`](../../07-OPEN-QUESTIONS/) for the v0.3 retrospective and v0.4 priorities (paap-eval re-calibration at 25-principle scale, paap-eval reading prior calibration outputs to update detector thresholds — closes the framework's own #24 self-observation gap).

---

## How to use

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
- **Not fully externally calibrated.** Stage 1d validation, Stage 2 prompt-variant kappa, and v0.3 multi-model kappa (Codex/GPT-5.4 + Gemini-3) are complete. Still needed: re-calibration at 25-principle scale (the v0.3 additions #23/#24/#25 are wired in but uncalibrated), Anthropic-family expansion (Opus / Sonnet / Haiku), and a human-rater layer.

---

## Status of components

| Component | Status | Stage |
|---|---|---|
| [`SKILL.md`](./SKILL.md) — 7-phase scoring workflow (25-principle scale) | ✅ Done | 1a + v0.3 update |
| [`genesis.md`](./genesis.md) — elicitation + architecture spec | ✅ Done | 1a |
| [`references/algorithmic-detectors.md`](./references/algorithmic-detectors.md) — 13 detectors (12 v0.2 + #23 host-portable v0.3) | ✅ Done | 1b + v0.3 |
| [`references/semantic-judges.md`](./references/semantic-judges.md) — 12 judges (10 v0.2 + #24, #25 v0.3) | ✅ Done | 1c + v0.3 |
| [`calibration.md`](./calibration.md) — validation at 22-principle scale; 25-scale re-calibration is v0.4 | ✅ v0.2 / 🟡 v0.4 |
| [`../../05-EVALUATION/kappa-pilot.md`](../../05-EVALUATION/kappa-pilot.md) — 3-persona reliability pilot | ✅ Done | 2 |
| [`../../05-EVALUATION/kappa-pilot-multimodel.md`](../../05-EVALUATION/kappa-pilot-multimodel.md) — 5-rater multi-model kappa (Claude × 3 + GPT-5.4 + Gemini-3) | ✅ Done | v0.3 |

---

## See also

- [`SKILL.md`](./SKILL.md) — The skill itself (read this for the full architecture)
- [`genesis.md`](./genesis.md) — How this skill was generated (dogfooding audit)
- [`../README.md`](../README.md) — `/meta-paap` user guide (the complementary skill)
- [`../../04-RUBRIC/principles.md`](../../04-RUBRIC/principles.md) — The 25 principles being scored against
- [`../../04-RUBRIC/scoring-template.md`](../../04-RUBRIC/scoring-template.md) — The output format
- [`../../05-EVALUATION/kappa-pilot.md`](../../05-EVALUATION/kappa-pilot.md) — Stage 2 reliability results
- [`../../07-OPEN-QUESTIONS/`](../../07-OPEN-QUESTIONS/) — v0.2 retrospective and v0.3 priorities
