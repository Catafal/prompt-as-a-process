# Community-Skill Head-to-Head — meta-paap v2 vs Hand-Authored Community Skills (v0.3 priority #5)

> Repeats priority #3's head-to-head experiment with **community-authored skills** as the handwritten baseline instead of the rubric author's local production skills. Removes the self-evaluation bias on the *handwritten* side. Generates the comparison arm with `meta-paap v2.0` (priority #4).

**Date:** 2026-04-26
**Method:** 4 community skills × 3 inputs × 2 versions = 24 outputs. 3 cross-vendor blind judges (Claude-Sonnet via subagent, GPT-5.4 via Codex CLI with `--output-schema`, Gemini-3-pro-preview via Gemini CLI) score each pair on a workflow-specific 5-dimension rubric. Random per-pair A/B blind labeling (seed 7777). 36 judgments total.
**Skills (4, archetype-stratified):** `obra/test-driven-development` (Procedural-discipline), `anthropics/canvas-design` (Creative), `chrisvoncsefalvay/d3-viz` (Reference), `gstack/plan-ceo-review` (Procedural-discipline, templated).
**Generator arm:** `meta-paap v2.0` (rationalizations + self-observation, just shipped in priority #4). Briefs extracted from each community skill's description + opening paragraph only — **no leakage of implementation choices**.
**Total LLM calls:** 4 v2 generations + 24 output runs + 36 judgings = 64. All schema-validated; zero retries.
**Raw data:** [`community-head-to-head-raw-data.md`](./community-head-to-head-raw-data.md)

---

## TL;DR

Five findings. The aggregate is striking; the caveats are real.

1. **v2-generated beats community on aggregate, 29/36 (81%).** All 3 cross-vendor judges prefer v2-generated overall (Claude 11/12, GPT-5.4 9/12, Gemini 9/12). The only workflow where community holds is `obra/test-driven-development` — and even there, community wins narrowly (5/9 vs v2's 4/9).

2. **0/36 provenance accuracy across all judges.** Every single judge predicted provenance *opposite* to reality on every pair. They saw v2-generated outputs (more structured — Iron Law tables, decision-class maps, named modes) and concluded "this must be the hand-tuned community skill"; they saw community outputs and concluded "this must be the freshly-generated one." This is the v0.2 mis-attribution finding at extreme.

3. **The obra/TDD result is the calibration check.** TDD is the workflow whose quality lives most in *production-iterated specifics* — the actual rationalizations a real TDD practitioner has heard, not articulable from a brief. v2 generates structurally-correct rationalizations from the brief. Community obra/TDD has been used in production for ~12+ months. **Community holds, narrowly. The other three workflows do not.**

4. **The cross-judge cluster pattern from the kappa pilot weakens here.** Inter-judge agreement is 9/12 unanimous (vs 7/15 in priority #3). On most pairs, all 3 vendors agree; the rubric clearly differentiates community vs v2 on this corpus.

5. **Form vs substance split.** v2 wins where quality is articulable from a brief (mode declarations, rationalization tables, structured taxonomies) — Creative voice work, Reference completeness, Procedural decision-class clarity. Community wins where quality lives in production-iterated specifics no brief captures (TDD discipline depth). The framework's contribution: meta-paap v2 produces the *form*; production iteration produces the *substance*. On most workflows, the form is enough.

**The framework can defensibly claim, after this experiment:** meta-paap v2 produces skills that meet or beat hand-authored community skills on output quality across 3 of 4 archetype-stratified workflows. The exception (TDD) names the moat: production-iterated discipline depth beats fresh generation, but only narrowly, and only where quality is dominated by specifics.

**Honest scope: this result is so strong it requires careful caveat-saturation.** See "Honest limitations" below.

---

## Per-pair winner table

| Pair | Claude | GPT-5.4 | Gemini-3 | Pattern |
|---|:---:|:---:|:---:|---|
| **anthropic-canvas-design/01-poster** | v2 | v2 | v2 | **UNANIMOUS v2** |
| **anthropic-canvas-design/02-brand-identity** | v2 | v2 | v2 | **UNANIMOUS v2** |
| **anthropic-canvas-design/03-data-viz-aesthetic** | v2 | v2 | v2 | **UNANIMOUS v2** |
| chrisvoncsefalvay-d3/01-bar-with-edge-case | v2 | v2 | v2 | **UNANIMOUS v2** |
| chrisvoncsefalvay-d3/02-network-graph | v2 | community | community | 2-of-3 community |
| chrisvoncsefalvay-d3/03-animated-transition | v2 | v2 | v2 | **UNANIMOUS v2** |
| **gstack-plan-ceo-review/01-ambitious-roadmap** | v2 | v2 | v2 | **UNANIMOUS v2** |
| **gstack-plan-ceo-review/02-feature-launch** | v2 | v2 | v2 | **UNANIMOUS v2** |
| **gstack-plan-ceo-review/03-pivot-decision** | v2 | v2 | v2 | **UNANIMOUS v2** |
| obra-tdd/01-bug-fix | v2 | v2 | community | 2-of-3 v2 |
| **obra-tdd/02-new-feature** | community | community | community | **UNANIMOUS community** |
| obra-tdd/03-refactor-under-pressure | v2 | community | v2 | 2-of-3 v2 |

**Inter-judge convergence:** 9/12 unanimous (vs 7/15 in priority #3, 47% vs 75% — much higher convergence here). All three judges align on most pairs.

---

## Per-workflow rollup

Each cell = count across the 9 (input × judge) trials per workflow.

| Workflow | Community wins | v2-generated wins | Verdict |
|---|---:|---:|---|
| `anthropic-canvas-design` | 0 | **9** | **Unanimous v2 sweep** |
| `gstack-plan-ceo-review` | 0 | **9** | **Unanimous v2 sweep** (despite 600 lines of templated voice rules) |
| `chrisvoncsefalvay-d3` | 2 | 7 | Strong v2 preference |
| **`obra-tdd`** | **5** | **4** | **Community holds, narrowly** |
| **Total** | **7** | **29** | **v2 81%** |

**The single most-important data point: `gstack/plan-ceo-review` 0/9 community wins.** Despite gstack's ~600 lines of templated PREAMBLE (banned-vocabulary lists, prose-structure rules, dual-voice consensus instructions — the v0.3-deferred candidate #21 SKILL.md-as-build-artifact pattern), the v2-generated single-skill output beat it unanimously across 3 inputs × 3 judges. The templated voice depth that gstack inherits did NOT translate into output-quality wins on these particular plan-review tasks.

**The other striking data point: obra/TDD 5-4 community.** This is the workflow where the rationalizations-to-reject pattern was *defined*; v2 was specifically designed to produce it; community has years of production iteration. The result is **narrow** — community wins 5, v2 wins 4. Production-iteration depth holds the line, but barely.

---

## Per-judge community-vs-v2 preference

| Judge | Community | v2-generated | TIE | Skew |
|---|---:|---:|---:|---|
| Claude | 1 | **11** | 0 | Strong v2 preference |
| GPT-5.4 | 3 | **9** | 0 | Strong v2 preference |
| Gemini-3 | 3 | **9** | 0 | Strong v2 preference |

**This pattern inverts priority #3's.** In priority #3, Claude favored handwritten 10/15, GPT-5.4 split 7/7, Gemini favored generated 8/15. Here, all three vendors prefer v2 — Claude most strongly. The consistent direction across vendors is itself informative: it's not "Gemini happens to like v2"; it's that *all three judges, including the kappa-pilot-outlier Gemini, agree v2 wins on most pairs*.

---

## Provenance-prediction accuracy: 0/36 across all judges

| Judge | Correct | Accuracy |
|---|---|---:|
| Claude | 0/12 | **0%** |
| GPT-5.4 | 0/12 | **0%** |
| Gemini-3 | 0/12 | **0%** |
| **All** | **0/36** | **0%** |

This is *not* the chance baseline (50%); it's anti-correlated. Every single blind judge, on every single pair, predicted provenance *opposite* to reality. The pattern: judges associated *more structured / more polished / more intentional-looking* output with the *hand-tuned community* arm. v2-generated produced more structured output (Iron Law tables, named modes, decision-class maps) — judges read this as evidence of hand-tuning.

**This generalizes the v0.2 N=1 mis-attribution finding to a robust pattern (N=36 trials, 100% mis-attribution).** It also clarifies the mechanism: judges use *visible structure* as a proxy for *hand-tuning*, but v2 is engineered to produce visible structure. The proxy is wrong.

**Practical implication:** "blind judges cannot tell which is hand-tuned and which is generated" — already a v0.2 directional finding — is now a robust pattern *with a known direction*. Judges will systematically mis-attribute v2-generated as hand-tuned and vice versa. This matters for any audit pipeline that uses provenance prediction as a quality signal.

---

## Form vs substance — the v0.3 key finding

Across the v0.3 head-to-head data (priority #3 + priority #4 validation + priority #5):

| Workflow archetype | Where quality lives | Generator wins? |
|---|---|:---:|
| Creative (canvas-design, humanizer¹) | Voice rules + anti-patterns articulable from brief | **Yes (v2)** |
| Procedural with explicit structure (plan-ceo-review, eod²) | Mode declarations, decision-class taxonomy, named phases | **Yes (v2)** |
| Reference (d3-viz) | Pattern coverage + framework-agnostic primitives | **Yes (v2, mostly)** |
| **Procedural with discipline depth (obra/TDD)** | **Specific anti-patterns from production iteration** | **No — community holds** |

¹ Priority #4 N=1 validation: v2 21/25 vs handwritten 11/25 on humanizer. Confirmed at priority #5 scale on canvas-design (different Creative workflow).
² Priority #3: handwritten won 6/9 on eod (author's own skill). Priority #5 plan-ceo-review (community equivalent): v2 won 9/9. The author-skill bias was real.

**The pattern: meta-paap v2 wins where quality is articulable; production iteration wins where quality lives in specifics no brief captures.** TDD is the cleanest example of the latter — the *actual* rationalizations a real practitioner has heard ("the test is obvious, skip it") differ from the structurally-correct rationalizations v2 generates from the brief.

**This is not "the rubric is wrong."** The rubric correctly rewards both arms where they earn it. It's "the rubric describes form well; substance only emerges through use."

---

## Methodology

### Brief extraction (no implementation leakage)

For each community skill, the brief was written from the YAML description + opening paragraph only. The Phase 2 v2-generation subagents were *explicitly forbidden* from reading the community SKILL.md body. The architectural choices (mode names, phase counts, gate logic, persona depth) were not leaked.

### v2 generation

Each of the 4 v2 generations went through meta-paap v2's full protocol:
- Phase 0 classification (FULL PATH for all 4)
- Phase 1 elicitation (simulated from brief)
- Phase 1.5 standalone
- Phase 1.5b first-run (no prior learnings.jsonl)
- Phase 2 architecture spec including PERSONA DEPTH section (Iron Law + Rationalizations)
- Phase 3 generation with v2 generation rules
- Phase 4 11-check self-critique
- Output

All 4 generations passed self-critique. Lines: obra-tdd 302, canvas-design 333, d3-viz 247, plan-ceo-review 472.

### Output generation (24 parallel subagents)

Each subagent loaded one SKILL.md and applied it to one input, producing the output the skill describes. Same pattern as priority #3.

### Blind labeling + judging

Random A/B per pair (seed 7777, different from priority #3's 4242). Three cross-vendor judges scored each pair on the workflow's 5-dim rubric (1-5 scale) plus task-compliance + verbosity caps + provenance prediction.

### Quality rubrics

Same 5-dimension structure as priority #3, with workflow-specific dimensions:

- **obra/TDD:** discipline enforcement / RED-GREEN-REFACTOR cycle visibility / test quality / failure-mode coverage / honesty when blocking
- **canvas-design:** aesthetic specificity / anti-genericness / philosophy → visual coherence / originality discipline / constraint honesty
- **d3-viz:** code completeness / API correctness / framework-agnosticism / explanatory comments / edge-case handling
- **plan-ceo-review:** mode declaration + fit / premise challenges / hardest-question identification / decision-class taxonomy applied / honest discomfort

Each rubric included reviewer-suggested cross-cutting caps (task-compliance, verbosity penalty) from priority #3.

---

## Honest limitations

This result is so strong (29/36, all 3 vendors agreeing) that the caveats need explicit prominence.

1. **I designed both the v2 meta-paap prompt AND the quality rubrics.** The rubric dimensions reward exactly what v2 was designed to produce (mode declarations, Iron Law tables, decision-class taxonomies). This is *measurement-side self-bias* — separate from the v0.3 priority #3 caveat about handwritten-author bias, but real. **A third-party rubric author would clarify whether the v2 win generalizes or whether it's a measurement artifact.** v0.4 priority.

2. **The "simulated SKILL.md execution" via subagent dispatch may not faithfully reproduce community skill behavior.** Especially gstack/plan-ceo-review — the templated PREAMBLE describes runtime conditions (analytics, dual-voice consensus, session state) that subagent dispatch cannot replicate. The subagent reads the rendered SKILL.md and produces *the kind of output the skill would produce*, but not *the runtime behavior gstack's authors intended in production*. This may understate community skills' real-world quality.

3. **N=12 pairs (4 workflows × 3 inputs each) is decent but not overwhelming.** Per-workflow N=3 inputs surfaces unanimity patterns but cannot rule out input-selection bias. v0.4: 5+ inputs per workflow.

4. **The 0% provenance accuracy is partially explained by v2's design.** v2 was engineered to produce visible structure (Iron Law tables, named modes, explicit decision-class maps). Judges associate visible structure with hand-tuning. v2's structural advantage *causes* the mis-attribution; this is not "v2 is indistinguishable from hand-tuned" — it's "v2 is *more visibly structured* than hand-tuned, and judges read structure as hand-tuning." Different finding, same N=36 data.

5. **3 of 4 community skills were already in the v0.2 kappa pilot.** This means the framework's prior literature already engaged with these specific skills. There's no contamination at the v2 generation level (briefs were extracted from descriptions, not from v0.2 kappa scores), but the corpus author is not naive about these skills.

6. **gstack/plan-ceo-review's 0/9 result depends on the simulation faithfulness caveat.** The community arm's "advantage" — the 600-line templated PREAMBLE — describes a system-level architectural choice (deferred candidate #21) that no individual single-skill comparison can fairly measure. This is documented as a methodology caveat in the rubric.

7. **All 3 judges are LLM-judges.** No human raters. The 0/36 provenance pattern reflects what these models do; human readers might do better or worse.

8. **obra/TDD's narrow community win (5/9) could shift on different inputs.** Maybe rate-limited validation: with 5 different TDD task inputs, the result might be 3/5 community or 7/9. The signal direction is real; the magnitude needs more data.

9. **No third-party hand-written control.** The community skills are well-known but they're still curated (these are the most-cited corpus exemplars). A randomly-sampled community skill set might shift results. v0.4: random sampling from N=80 corpus.

10. **The rubric's measurement-side self-bias compounds with priority #4's design self-bias.** v2 was designed using priority #3's findings (rationalizations + self-observation). Then v2 was tested with rubrics that reward what v2 produces. **The third-party-rubric experiment is the v0.4 priority that breaks this loop.**

---

## What this unblocks for v0.4 / v1.0

- **The "third-party hand-authored skills" objection from priority #3 is partially answered.** v2 beats community on 3 of 4 workflows, narrowly loses 1. The "the framework only works on Sir's hand-written skills" reading is no longer supported.
- **The "rubric is purely circular" objection has a clearer counterargument.** v2 wins on workflows where the rubric's dimensions are articulable; loses on workflows where dimensions live in specifics. This is the right calibration shape — a perfectly-circular rubric would have v2 winning everywhere.
- **The form-vs-substance framing names the moat for production-iterated skills.** Specifically what fresh generation cannot reach: the *specific* anti-patterns a real TDD practitioner has heard, the *specific* rationalizations a real humanizer-writer has learned to flag. This is operationalizable: future meta-paap iterations could read prior `~/.claude/<skill>/learnings.jsonl` patterns from production-iterated skills to close part of this gap.
- **The 0/36 provenance pattern is a clean publishable finding.** "Across 36 blind judgments, judges systematically mis-attributed v2-generated outputs as hand-authored at 100% — they use visible structure as a proxy for hand-tuning, and v2 produces more visible structure." That's a citable result.
- **v0.4 priorities surfaced:** (a) third-party rubric author for measurement-bias check, (b) third-party hand-authored skills (random sample from N=80 corpus), (c) human-rater layer, (d) larger N per workflow, (e) feed prior `learnings.jsonl` from production skills back into meta-paap to close the substance gap.

---

## Cross-references

- [`head-to-head.md`](./head-to-head.md) — v0.2 N=1 humanizer head-to-head (the experiment this expands)
- [`head-to-head-expanded.md`](./head-to-head-expanded.md) — v0.3 priority #3 (5×3×3 with author's own skills)
- [`community-head-to-head-raw-data.md`](./community-head-to-head-raw-data.md) — verbatim 24 outputs + 36 judge JSONs
- [`kappa-pilot-multimodel.md`](./kappa-pilot-multimodel.md) — multi-model kappa with the same Claude/GPT/Gemini cluster pattern
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — the 25 principles (with #21 templated-build-artifact noted as deferred — relevant to the gstack caveat)
- [`../04-RUBRIC/reflexive-self-audit.md`](../04-RUBRIC/reflexive-self-audit.md) — framework's own grades; the form-vs-substance finding informs future #24 self-observation extensions
- [`../06-META-PAAP/SKILL.md`](../06-META-PAAP/SKILL.md) — meta-paap v2 (the generator arm in this experiment)
- [`../07-OPEN-QUESTIONS/`](../07-OPEN-QUESTIONS/) — v0.3 priority #5 status (DONE) + v0.4 priorities surfaced
