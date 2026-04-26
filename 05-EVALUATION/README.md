# 05 — Evaluation

How we test PaaP empirically: methodology, regression suite, inter-rater reliability, and head-to-head provenance test.

## What's in this folder

### Methodology + suite

| File | Purpose |
|---|---|
| [`methodology.md`](./methodology.md) | How we evaluate skills: archetype-aware scoring, gates, anti-slop checks |
| [`regression.md`](./regression.md) | Regression suite — running record across versions |

### Evaluation tests (output-quality probes)

| File | Purpose |
|---|---|
| [`test-1-skill-audit.md`](./test-1-skill-audit.md) | Test 1 — `/meta-paap` audits an existing skill |
| [`test-2-article-forge.md`](./test-2-article-forge.md) | Test 2 — generate skill from a brief |
| [`test-3-review-plan.md`](./test-3-review-plan.md) | Test 3 — review-plan workflow |
| [`test-4-idea-to-pr.md`](./test-4-idea-to-pr.md) | Test 4 — idea-to-PR end-to-end |

### v0.2 evidence layer

| File | Purpose |
|---|---|
| [`kappa-pilot.md`](./kappa-pilot.md) | 3-persona inter-rater reliability pilot (mean 1.83 grade-steps) |
| [`kappa-pilot-raw-data.md`](./kappa-pilot-raw-data.md) | Raw scores per persona × skill |
| [`head-to-head.md`](./head-to-head.md) | Hand-written vs `/meta-paap`-generated, blind judge couldn't distinguish provenance |
| [`corpus-extension-raw-data.md`](./corpus-extension-raw-data.md) | Raw data for the +30 corpus extension (see [`04-RUBRIC/corpus-extension-30-skills.md`](../04-RUBRIC/corpus-extension-30-skills.md) for analysis) |

## How to use

- **Want to reproduce?** Read [`methodology.md`](./methodology.md), then re-run the tests with `/paap-eval`.
- **Want the headline findings?** [`kappa-pilot.md`](./kappa-pilot.md) + [`head-to-head.md`](./head-to-head.md).
- **Want raw numbers?** The `*-raw-data.md` files.

See also: [04-RUBRIC/](../04-RUBRIC/) for what's being scored, [06-META-PAAP/paap-eval/](../06-META-PAAP/paap-eval/) for the auto-scoring instrument.
