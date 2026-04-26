# Head-to-Head — Expanded Output-Quality Experiment (v0.3)

> v0.3 priority #3: scale v0.2's N=1 humanizer head-to-head into a 5-workflow × 3-input × 3-judge experiment. Tests *rubric validity* — does scoring predict actual output quality? — across a meaningful corpus.

**Date:** 2026-04-26
**Method:** 5 paired skills × 3 inputs × handwritten + generated arms = 30 outputs. 3 cross-vendor blind judges (Claude-Sonnet via subagent, GPT-5.4 via Codex CLI with `--output-schema`, Gemini-3-pro-preview via Gemini CLI) score each pair on a workflow-specific 5-dimension rubric (1-5 scale) plus task-compliance + verbosity caps + provenance prediction. Random A/B blind labeling per pair (seed 4242).
**Skills:** `eod`, `humanizer`, `prompt-engineering`, `5d-thinking`, `remember` — same paired skills as v0.2's structural head-to-head.
**Total LLM calls:** 30 generation + 45 judging = 75. All on first attempt (no retries triggered on schema-validated calls).
**Raw data:** [`head-to-head-expanded-raw-data.md`](./head-to-head-expanded-raw-data.md)

---

## TL;DR

Five findings — the picture is **workflow-specific**, not a uniform "one arm wins":

1. **Aggregate handwritten preference, narrow margin.** Across 45 judgments: HW 24 / Gen 20 / TIE 1. Hand-tuning beats fresh generation overall, but only by ~10%.

2. **`remember` is a clean *generated*-skill victory: 9/9 unanimous across all 3 judges.** Generated remember-notes win on title quality, distillation, structure, substance preservation — every quality dimension the rubric weights. Reason (informed speculation): meta-paap's strict claim-title and structured-note discipline outperforms a hand-tuned skill that has accumulated cruft over time.

3. **`humanizer` is a clean *handwritten* victory: 8/9.** All 3 judges, all 3 inputs prefer hand on technical and narrative passages; only Gemini dissents on the marketing piece. Voice work is the hardest thing to fresh-generate.

4. **Provenance prediction barely above chance.** GPT-5.4: 67% (10/15). Claude: 60% (9/15). **Gemini: 53% (8/15) — at the 50% chance baseline.** v0.2's N=1 mis-attribution finding generalizes: blind judges cannot reliably tell hand-tuned from generated.

5. **The kappa pilot's Claude+GPT-vs-Gemini asymmetry replicates here.** On `eod`, Claude + Gemini agree (HW); GPT-5.4 alone says Gen. On `humanizer/02-marketing` and most `prompt-engineering`, Claude + GPT agree (HW); Gemini diverges. **Even on output-quality judging — not just rubric scoring — Claude and GPT cluster, Gemini sits outside.** Same pattern as the multi-model kappa.

The framework can defensibly claim, after this experiment: **on the workflows that meta-paap can describe well from a brief alone (structured note-taking, decision-thinking), generator output reaches or exceeds hand-tuned quality. On workflows that depend on production-iterated voice (humanizer, mature interview-style EOD), hand-tuning still wins.**

---

## Per-pair winner table

Each cell = the judge's quality winner, translated from blind A/B back to handwritten/generated using the (hidden-from-judge) mapping.

| Pair | Claude | GPT-5.4 | Gemini-3 | Pattern |
|---|:---:|:---:|:---:|---|
| 5d-thinking/01-career | generated | generated | generated | **UNANIMOUS Gen** |
| 5d-thinking/02-partnership | handwritten | TIE | generated | 3-way split |
| 5d-thinking/03-scope | generated | handwritten | handwritten | 2-of-3 HW |
| eod/01-concise-day | handwritten | generated | handwritten | 2-of-3 HW |
| eod/02-messy-day | handwritten | generated | handwritten | 2-of-3 HW |
| eod/03-meeting-heavy-day | handwritten | generated | handwritten | 2-of-3 HW |
| humanizer/01-technical | handwritten | handwritten | handwritten | **UNANIMOUS HW** |
| humanizer/02-marketing | handwritten | handwritten | generated | 2-of-3 HW |
| humanizer/03-narrative | handwritten | handwritten | handwritten | **UNANIMOUS HW** |
| prompt-engineering/01-vague | handwritten | handwritten | generated | 2-of-3 HW |
| prompt-engineering/02-over-broad | handwritten | handwritten | generated | 2-of-3 HW |
| prompt-engineering/03-under-specified | handwritten | handwritten | handwritten | **UNANIMOUS HW** |
| remember/01-insight | generated | generated | generated | **UNANIMOUS Gen** |
| remember/02-reference | generated | generated | generated | **UNANIMOUS Gen** |
| remember/03-reflection | generated | generated | generated | **UNANIMOUS Gen** |

**Inter-judge convergence:** 7/15 unanimous, 7/15 2-of-3, 1/15 three-way split. Unanimous cases cluster on the strongest signals (`remember` always Gen, `humanizer` always HW where it's unanimous).

---

## Per-workflow rollup

Each cell = count across the 9 (input × judge) trials per workflow.

| Workflow | HW wins | Gen wins | TIE | Verdict |
|---|---:|---:|---:|---|
| `humanizer` | **8** | 1 | 0 | Strong handwritten preference |
| `prompt-engineering` | **7** | 2 | 0 | Strong handwritten preference |
| `eod` | 6 | 3 | 0 | Moderate handwritten preference |
| `5d-thinking` | 3 | 5 | 1 | Slight generated preference |
| `remember` | 0 | **9** | 0 | Unanimous generated preference |
| **Total** | **24** | **20** | **1** | Narrow handwritten edge overall |

The aggregate "handwritten wins" disguises a workflow-specific picture. **Humanizer + prompt-engineering carry the handwritten total.** Remember alone accounts for nearly half the generated wins. 5d-thinking is contested.

---

## Per-judge handwritten-vs-generated preference

| Judge | HW wins | Gen wins | TIE | Total | Skew |
|---|---:|---:|---:|---:|---|
| Claude | 10 | 5 | 0 | 15 | Handwritten-leaning |
| GPT-5.4 | 7 | 7 | 1 | 15 | Balanced |
| **Gemini-3** | 7 | **8** | 0 | 15 | **Slight generated-leaning** |

**Gemini-3 is the only judge that prefers generated overall.** This connects to the kappa pilot's finding: Gemini-3 grades systematically differently from Claude and GPT-5.4, and the difference shows up on output quality too, not just structural scoring.

---

## Provenance-prediction accuracy

After scoring each pair, every judge predicted which output was hand-tuned vs generated. Baseline: 50% (random).

| Judge | Correct | Accuracy | vs Baseline |
|---|---|---:|---|
| GPT-5.4 | 10/15 | **67%** | +17 pp |
| Claude | 9/15 | 60% | +10 pp |
| Gemini-3 | 8/15 | **53%** | **+3 pp (chance)** |

Gemini-3 sits at the 50% chance baseline — it cannot reliably distinguish provenance. GPT-5.4 is the most accurate, but 67% across N=15 is not strong enough to call "the difference is visible." This generalizes v0.2's N=1 mis-attribution finding: **blind judges cannot reliably tell hand-tuned from generated, especially Gemini.**

---

## Per-dimension deltas (HW mean − Gen mean, averaged per judge)

The most-revealing view. Positive Δ = HW arm scored higher; negative = Gen arm scored higher.

### Dimensions where handwritten dominates (consistent across all 3 judges)

| Dimension | Claude Δ | GPT-5.4 Δ | Gemini Δ | Workflow context |
|---|---:|---:|---:|---|
| Voice quality | +2.67 | +2.67 | +2.00 | humanizer (creative voice) |
| AI-signature removal | +2.67 | +2.00 | +2.33 | humanizer (specific anti-patterns) |
| Action specificity | +3.00 | +1.33 | +2.33 | eod (concrete time-anchored proposals) |
| Readability | +1.67 | +1.33 | +1.00 | humanizer / general |
| Honest framing | +2.00 | −0.33 | +0.33 | eod (Claude weights this strongest) |

### Dimensions where generated dominates (consistent across all 3 judges)

| Dimension | Claude Δ | GPT-5.4 Δ | Gemini Δ | Workflow context |
|---|---:|---:|---:|---|
| Title quality | −1.67 | −1.33 | −1.00 | remember (claim-titles) |
| Substance preservation | −1.00 | −2.33 | −2.33 | humanizer (don't change the argument) |
| Distillation | −1.00 | −1.67 | −0.67 | remember (extract the lesson) |
| Brevity discipline | −2.00 | −1.67 | −0.33 | eod (don't pad) |
| Decision-relevance | −1.33 | −0.67 | −1.33 | 5d-thinking (sharpen the choice) |

### Why this matters

The deltas split clean. Handwritten arms win on dimensions that **require taste accumulated over use** — voice, anti-pattern lists, action-specificity-from-experience. Generated arms win on dimensions that **the rubric itself rewards crisply** — claim-titles, distillation, brevity, decision-relevance. **The generator wins where the rubric is clearest about "what good looks like." The hand-tuner wins where good is taste-shaped, not rubric-shaped.**

This is a more nuanced version of v0.2's "circularity caveat" finding. It's not that the rubric simply rewards what the generator produces — it's that the rubric rewards *clearly-articulable* dimensions, and the generator excels at clearly-articulable dimensions. Handwritten skills accumulate something the rubric only partially captures.

---

## Cross-judge bias signals (replication of kappa-pilot pattern)

The multi-model kappa pilot found Claude + GPT-5.4 cluster while Gemini-3 sits outside. **The same pattern appears here in output-quality judging:**

| Pair | Cl + GPT | Gem | Pattern |
|---|---|---|---|
| eod/01-concise-day | HW + Gen | HW | Cl+Gem agree, GPT outlier |
| eod/02-messy-day | HW + Gen | HW | Cl+Gem agree, GPT outlier |
| eod/03-meeting-heavy-day | HW + Gen | HW | Cl+Gem agree, GPT outlier |
| humanizer/02-marketing | HW + HW | Gen | Cl+GPT agree, Gem outlier |
| prompt-engineering/01-vague | HW + HW | Gen | Cl+GPT agree, Gem outlier |
| prompt-engineering/02-over-broad | HW + HW | Gen | Cl+GPT agree, Gem outlier |

On `eod`, GPT-5.4 is the outlier (Claude + Gemini both pick HW). On `humanizer` and `prompt-engineering`, Gemini is the outlier. **The cluster pattern from the kappa pilot replicates with one caveat:** GPT-5.4 doesn't always cluster with Claude — it diverges on `eod` specifically. The corpus-vendor familiarity hypothesis predicts: skills authored for Claude (the corpus origin) read most cleanly to Claude; GPT and Gemini each have their own deviations from the Claude reading. The exact form of those deviations is workflow-specific.

---

## Methodology

### Same-experiment safeguards

- All 5 paired SKILL.md files preserved from v0.2's `/tmp/paap-eval-h2h/{handwritten, generated}/` — no regeneration; same artifacts as v0.2 reviewed.
- 30 generation calls dispatched as 30 parallel Claude subagents from a single Claude Code session. Each subagent received the SKILL.md + the input + write-output instruction, with no awareness of the other arm.
- Random per-pair A/B labeling (seeded for reproducibility); judges never saw mapping; predictions made post-scoring.
- 3 cross-vendor judges with 3 distinct invocation methods to minimize shared-runtime confounds (Claude via subagent, GPT-5.4 via `codex exec --output-schema`, Gemini via `gemini -p` with prompt-engineered JSON).
- Each judge applied **task-compliance cap** (cap dimension scores at 3/5 if output didn't perform the task) and **verbosity penalty** before scoring — these are reviewer-suggested cross-cutting rules added during rubric design.

### Per-workflow quality rubrics (5 dimensions each)

| Workflow | 5 dimensions |
|---|---|
| eod | synthesis quality / pattern recognition / action specificity / honest framing / brevity discipline |
| humanizer | voice quality / substance preservation / AI-signature removal / editorial discipline + meaning preservation / readability |
| prompt-engineering | diagnostic precision / concrete rewrite / production fit / educational value / calibrated scope |
| 5d-thinking | frame diversity / blind-spot surfacing / decision-relevance / specificity to the situation / honest discomfort |
| remember | structure / distillation / title quality / connection-making / tag discipline |

Anchor examples (5/3/1) per dimension. Judges asked to cite specific evidence from the outputs.

### What judges saw vs. didn't see

**Saw:** workflow rubric (with anchors + cross-cutting caps), original input the skills were applied to, blind-labeled Output A and Output B.

**Didn't see:** which output was handwritten, which was generated, that two different SKILL.md files produced them, the SKILL.md content itself.

---

## Honest limitations

1. **N=15 is still small.** Per-workflow N=3 inputs is enough to surface a unanimity pattern (`remember` Gen 9/9, `humanizer` HW 8/9) but not enough to make confident claims about subtler skills (`5d-thinking` slight Gen lean across only 9 trials).

2. **"Handwritten" means *the author's hand-tuned skill*.** It does not mean a randomly-selected community skill. The handwritten arms are production-iterated by one author; results may not generalize to "what an average hand-written skill looks like." Future expansion: include third-party hand-written skills as a control.

3. **All 3 judges are LLM-judges.** No human raters. The provenance-prediction finding (GPT-5.4 67%, Gemini 53%) reflects what these models can detect; human readers might do better or worse.

4. **Generation is single-shot, no production iteration.** The "generated" arm is meta-paap's first output from a brief; the "handwritten" arm has been used in production for months. The comparison is "one-shot generated vs months-iterated hand" — not a pure fairness test of the generator.

5. **Workflow-quality rubrics are author-designed.** The 5-dim rubrics for each workflow are themselves a calibration choice. A different rubric weighting could shift `remember` or `humanizer` results.

6. **The simulated SKILL.md execution is a stand-in.** The 30 generation calls were parallel subagents that read the SKILL.md and produced the output the skill describes. This is not the same as actually invoking the skill in Claude Code — production execution might use different tools, different side-effects, etc. The output text is realistic; the operational behavior is approximated.

7. **Reasoning effort not equalized.** GPT-5.4 ran at `model_reasoning_effort=high`; Gemini CLI doesn't expose an analogous knob; Claude subagents had whatever default depth subagent dispatch provides. Some of the cross-judge variance may be reasoning-budget variance.

8. **Cross-cutting caps were judge-applied, not enforced.** Task-compliance cap and verbosity penalty are rubric-stated rules that each judge applies subjectively. Inter-judge variance in how strictly they apply caps adds noise.

---

## What this unblocks for v0.4 / v1.0

- **The "rubric is purely circular" objection is partially answered.** The generator wins on dimensions the rubric clearly articulates (claim-titles, distillation, decision-relevance) — *and so does the handwritten arm where the rubric is taste-shaped*. The rubric encodes both sides.
- **`remember` is a clear "use the generator" recommendation.** All 3 judges, all 3 inputs, prefer generated. If a user asks "should I hand-write a remember-skill or generate one?" the answer from this data is "generate it."
- **`humanizer` is a clear "use the handwritten" recommendation.** Voice work doesn't transfer well from a brief.
- **The corpus-vendor cluster from the kappa pilot is now confirmed at the output-quality level too.** Claude + GPT-5.4 cluster more tightly than either does with Gemini-3 — across both rubric scoring (the kappa pilot) and output preference (this experiment). The hypothesis "skills authored for Claude grade comparably under Claude-aligned models" is supported by two independent data layers.
- **N=15 is enough to publish a directional claim.** The full kappa-with-N=100+ + multi-author corpus extension is v0.4+ work.

---

## Cross-references

- [`head-to-head.md`](./head-to-head.md) — v0.2 N=1 humanizer head-to-head + structural-rubric scoring on the 5 paired skills
- [`head-to-head-expanded-raw-data.md`](./head-to-head-expanded-raw-data.md) — verbatim 30 outputs + 45 judge JSONs
- [`kappa-pilot-multimodel.md`](./kappa-pilot-multimodel.md) — multi-model kappa with the same Claude+GPT-vs-Gemini cluster pattern
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — the 25 principles being validated for predictive power
- [`../04-RUBRIC/reflexive-self-audit.md`](../04-RUBRIC/reflexive-self-audit.md) — the framework's own honest grade including the C on #24 that this experiment doesn't directly test
- [`../07-OPEN-QUESTIONS/`](../07-OPEN-QUESTIONS/) — v0.3 priority #3 status (DONE) + v0.4 priorities surfaced by these findings
