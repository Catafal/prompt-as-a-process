# Evaluation Methodology

> How we test, why this rubric, and what an n=4 study can and cannot tell you.

This file documents the protocol used to evaluate `meta-paap` — a skill that generates other skills (see [`../06-META-PAAP/`](../06-META-PAAP/)). The four tests in this directory ([test-1](./test-1-skill-audit.md), [test-2](./test-2-article-forge.md), [test-3](./test-3-review-plan.md), [test-4](./test-4-idea-to-pr.md)) all follow this protocol. The cross-test regression analysis is in [`regression.md`](./regression.md).

---

## What this evaluates

`meta-paap` takes a workflow description, asks five elicitation questions, scans installed skills for composition candidates, designs an architecture, presents it for review, generates the SKILL.md, and red-teams its own output.

The evaluation question:

> **Does meta-paap-generated output reliably meet the rubric principles, across workflow types?**

Not "is the output good in some abstract sense." Specifically: **does the structural rubric hold?** That's a falsifiable question with a defined rubric.

---

## What this does NOT evaluate (yet)

- **Output quality of generated skills when run.** Whether a generated `/skill-audit` actually produces a better audit than a hand-written `/skill-audit`. That's the v0.2 head-to-head experiment.
- **Authoring time savings.** Anecdotal claim only at v0.1; quantified in v0.2.
- **Comparative scoring against hand-written skills.** Also v0.2.

---

## Important note on rubric version

The four tests in this directory were originally scored against the **20 original principles** (rubric v0.0, pre-promotion). Two principles (#21 Decision class drives gating, #22 Voice + writing rules) were promoted from gstack-specific candidates *after* the n=4 evaluation completed, based on corroboration from the 50-skill community survey (see [`../04-RUBRIC/empirical-validation.md`](../04-RUBRIC/empirical-validation.md)).

The grades shown in each test file are the original 20-principle scores. They have not been retroactively adjusted to the 22-principle rubric. v0.2 of this repo will re-score the same four skills against the 22-principle rubric and report any deltas.

This honest non-revision matters: re-scoring after the fact would conflate "what `meta-paap` actually produced" with "what the rubric currently rewards." The grades reported here describe what `meta-paap` did in March 2026 against the 20-principle rubric of that moment.

---

## Test design

**Workflows tested (n=4):**

| Test | Workflow | What it stresses |
|---|---|---|
| 1 | `/skill-audit` (parallel agents, scoring) | Parallel-burst design, scoring formulae |
| 2 | `/article-forge` (linear pipeline, composition) | Linear phase chain, multi-skill composition |
| 3 | `/review-plan` (dual-mode, behavioral personas) | Mode design, behavioral personas, external prompts |
| 4 | `/idea-to-pr` (full orchestration, 10 composed skills) | Composition at scale, conditional routing, 2 human gates |

**Workflows deliberately not tested (yet):**

- **Simple personal workflow (lean path)** — was planned as test 5; deferred to v0.2. The lean path is documented in `meta-paap`'s Phase 0 classification but not yet stress-tested via evaluation.

**Why these four:**

- **Span the complexity spectrum** (567 / 350 / 508+326 / 555+173 lines)
- **Stress different principles** (parallel agents, composition, modes, state, human gates)
- **Realistic** — all four are skills the author actually uses or built for real work, not toy examples constructed for the test

---

## Scoring protocol

Each generated skill scored on:

1. **Process compliance** — did `meta-paap` execute its own protocol correctly across all 7 phases (Pre-Phase invocation parsing, Phase 0 classification, Phase 1 elicitation, Phase 1.5 skills discovery, Phase 2 architecture, Phase 3 generation, Phase 4 self-critique)?
2. **The 20 original principles** — A+/A/B+/B/C/D/F per principle, with notes and evidence references to specific lines in the generated SKILL.md
3. **Key strengths** — 3-5 narrative bullets, what the skill does notably well
4. **Key weaknesses** — 3-5 narrative bullets, risk-ranked HIGH/MEDIUM/LOW for likelihood of failing on first run
5. **Overall grade** — derived from the principle scores plus weight on the most-violated patterns

After all four tests: **cross-test regression analysis** identifying patterns that are:

- Consistently strong (4/4 tests)
- Consistently weak (4/4 tests) — these are the systematic generator weaknesses
- Improving across tests (sometimes between tests, the generator gets better)
- One-off (specific to a single test)

See [`regression.md`](./regression.md) for the full cross-test summary.

---

## Limitations stated honestly

- **N=4** is enough for pattern detection, not statistical claims.
- **Single scorer.** Multi-scorer reliability (Cohen's kappa per principle) is a v0.2 priority to address potential rubric-author bias.
- **Rubric author scoring own rubric.** The author's preferences shape both what the rubric rewards AND what the scoring notices. Self-reinforcement risk.
- **Workflow selection is convenience-sampled** — skills the author wanted to build anyway. Not random.
- **No blinding.** The scorer knew which skills were `meta-paap`-generated.
- **No comparison baseline.** Without a hand-written counterpart for the same workflow, "this skill scored A-" is a one-sided claim. The v0.2 head-to-head experiment is designed to fix this directly.

The cross-test regression in [`regression.md`](./regression.md) mitigates some of this by surfacing patterns *across* tests rather than relying on a single grade. But the limitations are real and are stated upfront so readers can calibrate.

---

## Findings preview

**Headline:** `meta-paap` produces skills scoring B+ to A across the 4 tests (mean A-). Two systematic weaknesses appeared in 4/4 tests:

1. **Self-critique is too lenient** — validates structure but doesn't trace execution paths, validate named references, or check project safety rules.
2. **The hardest technical phase is the least specified** — implementation detail for the riskiest step gets one paragraph where it needs three.

The cross-test analysis also surfaced **improvements across tests** in error-handling sophistication (6 → 6 → 9 → 10 rows) and composition complexity (0 → 3 → 2 → 10 composed skills). The generator gets better at handling more complex workflows; the systematic weaknesses are stable.

See [`regression.md`](./regression.md) for full cross-test analysis and per-test files for individual evaluations.

---

## What this evaluation enables for v0.2

The n=4 study is the floor for what v0.2 will build on:

1. **Re-scoring against the 22-principle rubric** — does the grade distribution shift?
2. **Multi-scorer reliability** — 3-5 independent scorers grade the same 4 skills. Compute kappa per principle.
3. **Head-to-head with hand-written counterparts** — same workflow authored twice (by hand and by `meta-paap`). Outputs scored blind.
4. **Extension to a 5th test (lean path)** — currently the only spec-untested generation path.
5. **Re-evaluation after `meta-paap` v2 fixes** — the systematic weaknesses identified here become specific features in `meta-paap` v2; re-running the tests measures whether the fixes worked.

See [`../07-OPEN-QUESTIONS.md`](../07-OPEN-QUESTIONS.md) for the full v0.2 research agenda.
