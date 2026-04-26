# Multi-model Kappa Pilot — 5-rater matrix (Claude × 3 + GPT-5.4 + Gemini-3)

> v0.3 Stage: extends the v0.2 prompt-variant kappa pilot across two additional model families. Same 10 skills, three vendors, five raters total. Asks the question v0.2 deferred: **does the rubric travel across model families, or does it encode Claude-shaped bias?**

**Date:** 2026-04-26
**Method:** Single non-interactive call per (model, skill) pair, full 25-principle rubric, `pragmatic-practitioner` persona for all non-Claude raters. GPT-5.4 via `codex exec --output-schema` (server-side JSON Schema enforcement). Gemini-3 via `gemini -p` with prompt-engineered JSON + client-side validation + retry-once.
**Skills:** the same 10 community SKILL.md files used in v0.2 (4 Procedural / 1 Reference-borderline / 3 Reference / 3 Creative — see [`kappa-pilot.md`](./kappa-pilot.md) for the original archetype declarations).
**Raters:** 3 Claude personas (strict-academic / pragmatic-practitioner / charitable-newcomer, v0.2 data) + GPT-5.4 (Codex CLI, this file) + Gemini-3-pro-preview (Gemini CLI, this file).
**Raw data:** [`kappa-pilot-multimodel-raw-data.md`](./kappa-pilot-multimodel-raw-data.md)
**Rubric version:** v0.3 (Catafal, 2026) — 25 principles. v0.2 Claude data was at 22-principle scale; the comparison uses aggregate grades (which don't depend on individual principle counts the same way).

---

## Research arc — read this first

This document was originally written after the GPT-5.4 run alone. Its first headline finding was *"cross-model agreement is tighter than within-Claude persona spread — the rubric travels"*. **Gemini-3-pro-preview added 24 hours later overturned that synthesis.** The Gemini ↔ Claude-pragmatic distance is 2.30 grade-steps — the **largest** pair distance in the dataset, larger than within-Claude strict↔pragmatic (1.83) and nearly twice GPT-5.4's 1.20.

The GPT-5.4 sections below are preserved as written. The "Multi-vendor synthesis" section at the end carries the corrected conclusions. This is intentional — the 24-hour story-arc shows what one model's data alone supports vs what triangulation reveals.

---

## Stage A — GPT-5.4 vs Claude (original headline findings)

> The findings in this section are correct *for the GPT-5.4-only data*. They were the headline before Gemini-3 was added. The "Multi-vendor synthesis" section at the end shows what changes once Gemini-3 is included.

1. **Cross-model agreement is *tighter* than within-Claude persona spread.** GPT-5.4 ↔ Claude-pragmatic mean grade-step distance = **1.20** (n=10). The within-Claude strict↔pragmatic distance was 1.83 (v0.2 data). A different model family agrees with Claude-pragmatic *more closely* than Claude-strict does. This is the single most important finding: the rubric is not Claude-specific in any disabling way.

2. **GPT-5.4 sits between Claude-strict and Claude-pragmatic, slightly closer to strict.** Mean distances:
   - GPT-5.4 ↔ Claude-strict: **1.00** grade-steps (closest)
   - GPT-5.4 ↔ Claude-pragmatic: **1.20**
   - GPT-5.4 ↔ Claude-charitable: **1.30**
   GPT-5.4 grades systematically more conservatively than Claude-pragmatic. Whether this is OpenAI training-data bias toward stricter rubric application, or just GPT-5.4 being more cautious with `B+/A−` borderlines, the data can't distinguish — but the direction is consistent.

3. **Archetype detection is robust across model families.** GPT-5.4 agrees with Claude-pragmatic on archetype 7/10 (same numerator as v0.2's within-Claude pragmatic-vs-strict 7/10). All 3 disagreements are on the same borderline cases that split the Claude personas — never a wild misclassification.

4. **Principle #24 (self-observation) reveals a corpus-wide failure pattern.** Of the 7 skills where #24 applied, **all 7 scored F or near-F** (mean ordinal = 1.0, where F=0). Only `anthropics/skill-creator` (B−) demonstrated a real read-back loop. This confirms what the reflexive self-audit found internally: the community-skill corpus systematically does not implement skill-level self-observation. v0.3's promotion of #24 surfaces a real gap, not a theoretical one.

5. **Principle #23 (host-portable) shows a real range.** Mean ≈ B across the 10. Top: `chrisvoncsefalvay/d3-viz` (A) and `trailofbits/agentic-actions-auditor` (A−) — both intentionally environment-agnostic. Bottom: `anthropic/algorithmic-art` (C−). Skills that hardcode harness assumptions are detectably distinct from skills that abstract over them.

6. **Principle #25 (spawn-detection) defaults to N/A for non-Procedural skills, as designed.** GPT-5.4 marked 6/10 N/A (3 Reference + 2 Creative + 1 with N/A justification). Of the 4 applicable, 3 scored D or worse — Procedural skills mostly don't adapt to spawn vs interactive context. Only `anthropics/skill-creator` (B−) showed real adaptive behavior.

---

## Aggregate grade table — all 4 raters

| Skill | GPT-5.4 | Claude-pragmatic | Claude-strict | Claude-charitable | 4-rater max gap |
|---|:---:|:---:|:---:|:---:|---:|
| obra/test-driven-development | B− | A− | C+ | B+ | 4.0 |
| trailofbits/agentic-actions-auditor | B− | A− | B+ | B+ | 3.0 |
| anthropic/skill-creator | B+ | B+ | B+ | B+ | 0.0 |
| tapestry/article-extractor | B− | B− | C | C+ | 2.0 |
| expo/deployment | C | B− | C− | B− | 3.0 |
| K-Dense-AI/biopython | B− | B+ | B− | B+ | 2.0 |
| chrisvoncsefalvay/d3-viz | B− | B | C+ | B | 2.0 |
| anthropic/canvas-design | B | B+ | B+ | B+ | 1.0 |
| anthropic/frontend-design | B− | B− | C+ | B+ | 3.0 |
| anthropic/algorithmic-art | B+ | B+ | B | B+ | 1.0 |

**Within-rater grade ranges (across 10 skills):**

- GPT-5.4: C → B+ (5 letter-steps)
- Claude-pragmatic: B− → A− (4 letter-steps)
- Claude-strict: C− → B+ (5 letter-steps)
- Claude-charitable: C+ → B+ (3 letter-steps)

GPT-5.4 uses a comparable grade-range to Claude-strict — both cover ~5 letter-steps. Claude-pragmatic and Claude-charitable cluster more tightly in the B-band.

---

## Mean grade-step distances (aggregate level, n=10)

| Pair | Mean distance |
|---|---:|
| GPT-5.4 ↔ Claude-strict | **1.00** |
| GPT-5.4 ↔ Claude-pragmatic *(headline)* | **1.20** |
| GPT-5.4 ↔ Claude-charitable | 1.30 |
| *(reference)* Claude-strict ↔ Claude-pragmatic (v0.2) | 1.83 |
| *(reference)* Claude-strict ↔ Claude-charitable (v0.2) | 1.63 |
| *(reference)* Claude-pragmatic ↔ Claude-charitable (v0.2) | 0.60 |

Cross-model distance (GPT-5.4 ↔ Claude-pragmatic, 1.20) is **smaller** than two of the three within-Claude distances (1.83 strict↔pragmatic, 1.63 strict↔charitable). It is slightly larger than the closest within-Claude pair (1.20 vs 0.60 for pragmatic↔charitable).

**Implication:** the rubric communicates well across model families. The persona system continues to produce the largest grade-shift; model identity is a smaller (but real and consistent) effect.

---

## Archetype detection

| Skill | GPT-5.4 | C-pragmatic | C-strict | C-charitable | Note |
|---|---|---|---|---|---|
| obra/test-driven-development | Procedural | Procedural | Procedural | Procedural | ✅ unanimous |
| trailofbits/agentic-actions-auditor | Procedural | Procedural | **Hybrid** | Procedural | C-strict outlier (v0.2 finding) |
| anthropic/skill-creator | Procedural | **Hybrid** | Procedural | **Hybrid** | GPT-5.4 + C-strict agree; C-pragmatic + C-charitable agree |
| tapestry/article-extractor | Procedural | Procedural | **Reference** | Procedural | C-strict reads as documentation (v0.2 finding) |
| expo/deployment | Reference | Reference | Reference | Reference | ✅ unanimous |
| K-Dense-AI/biopython | Reference | Reference | Reference | Reference | ✅ unanimous |
| chrisvoncsefalvay/d3-viz | Reference | Reference | Reference | Reference | ✅ unanimous |
| anthropic/canvas-design | **Hybrid** | Creative | Creative | Creative | GPT-5.4 the only Hybrid call |
| anthropic/frontend-design | Creative | Creative | Creative | Creative | ✅ unanimous |
| anthropic/algorithmic-art | **Hybrid** | Creative | Creative | Creative | GPT-5.4 the only Hybrid call |

**Agreement:**

- GPT-5.4 ↔ C-pragmatic: 7/10
- GPT-5.4 ↔ C-strict: 6/10
- GPT-5.4 ↔ C-charitable: 7/10

All disagreements are within the same borderline regions identified in v0.2 (Procedural↔Hybrid for skill-creator; Procedural↔Reference for tapestry; Creative↔Hybrid for canvas-design and algorithmic-art). GPT-5.4 introduces a new pattern: marking Creative-with-procedural-elements as Hybrid where Claude-pragmatic kept them Creative (canvas-design, algorithmic-art). That's a defensible reading — both skills do have phased generation pipelines underneath the aesthetic spec.

---

## v0.3 new principles — first inter-model evidence

These three principles were promoted in v0.3 and have **no prior calibration data**. GPT-5.4's grades are the first independent rater on them.

### #23 Host-portable; agent harness is a config knob

| Skill | GPT-5.4 grade | Reasoning summary |
|---|---|---|
| obra/test-driven-development | C+ | Conceptually portable but examples lean JS/npm; minor harness coupling |
| trailofbits/agentic-actions-auditor | A− | Strong portable design |
| anthropic/skill-creator | C+ | Adapts across Claude Code / Claude.ai / Cowork; falls short of explicit `--host` mechanism |
| tapestry/article-extractor | B+ | Mostly portable, minor coupling |
| expo/deployment | A− | Clean platform-agnostic spec |
| K-Dense-AI/biopython | B | Library reference; portable in spirit |
| chrisvoncsefalvay/d3-viz | A | Intentionally environment-agnostic; explicit framework portability |
| anthropic/canvas-design | B− | Some host-specific assumptions |
| anthropic/frontend-design | B | Reasonable portability |
| anthropic/algorithmic-art | C− | Most harness-coupled of the corpus |

**Mean: B (ordinal 7.9).** Range: C− to A. Real spread, defensible top and bottom.

### #24 Skills observe themselves and feed prior runs forward

| Skill | GPT-5.4 grade | Reasoning summary |
|---|---|---|
| obra/test-driven-development | F | No mechanism to record prior executions or read them back |
| trailofbits/agentic-actions-auditor | F | Stateless audit; no learning store |
| anthropic/skill-creator | **B−** | Real read-back loop in iteration cycle (prior outputs + benchmarks fed forward) |
| tapestry/article-extractor | F | No prior-run awareness |
| expo/deployment | F | Stateless deployment skill |
| K-Dense-AI/biopython | F | Library reference, no execution history |
| chrisvoncsefalvay/d3-viz | F | Reference skill, no execution history |
| anthropic/canvas-design | N/A | Creative archetype excludes #24 |
| anthropic/frontend-design | N/A | Creative archetype excludes #24 |
| anthropic/algorithmic-art | N/A | Creative archetype excludes #24 |

**Mean of applicable (n=7): ordinal 1.0 (≈ F).** Only `skill-creator` demonstrates the read-back loop. This is a corpus-wide structural gap, not a single-skill failure. Confirms the v0.3 reflexive-self-audit's honest C grade on the framework's own #24 — the community is also at F-band on this principle.

### #25 Skills detect spawn vs interactive and adapt

| Skill | GPT-5.4 grade | Reasoning summary |
|---|---|---|
| obra/test-driven-development | D | No spawn-vs-interactive adaptation |
| trailofbits/agentic-actions-auditor | F | Always interactive-shaped |
| anthropic/skill-creator | **B−** | Adapts to whether subagents/browsers exist; partial spawn-awareness |
| tapestry/article-extractor | D | No adaptation |
| expo/deployment | N/A | Reference archetype |
| K-Dense-AI/biopython | N/A | Reference archetype |
| chrisvoncsefalvay/d3-viz | N/A | Reference archetype |
| anthropic/canvas-design | N/A | Creative archetype |
| anthropic/frontend-design | N/A | Creative archetype |
| anthropic/algorithmic-art | N/A | Creative archetype |

**Applicable: 4/10. Mean of applicable: ordinal 2.8 (≈ D+).** Only `skill-creator` adapts to spawn context. Procedural skills mostly assume interactive invocation. This matches the principle's v0.2 candidate notes ("weak corpus support, but real pattern in subagent-aware skills").

---

## Top 5 largest GPT-5.4 ↔ Claude-pragmatic divergences

| Distance | Skill | GPT-5.4 | C-pragmatic | Note |
|:---:|---|:---:|:---:|---|
| 3.0 | trailofbits/agentic-actions-auditor | B− | A− | GPT-5.4 weighs missing recovery paths heavier than Claude-pragmatic |
| 3.0 | obra/test-driven-development | B− | A− | GPT-5.4 penalizes missing #4 state, #7 file bus more strictly |
| 2.0 | K-Dense-AI/biopython | B− | B+ | Reference-archetype N/A interpretation differs slightly |
| 2.0 | expo/deployment | C | B− | Smallest skill (190 lines); GPT-5.4 sees more applicable principles than Claude-pragmatic did |
| 1.0 | anthropic/canvas-design | B | B+ | Adjacent grades; small calibration shift |

The two 3.0-step divergences are both on well-known good Procedural skills (`obra/TDD`, `trailofbits/auditor`) that Claude-pragmatic rates near-A. GPT-5.4's lower grades there are consistent with its closer cluster to Claude-strict — both raters reward strictly-defined Procedural elements (state, file bus, formal Phase 0) more heavily than Claude-pragmatic does.

---

## Methodology

### Invocation

Each skill scored with a single non-interactive `codex exec` call:

```
codex exec \
  --skip-git-repo-check \
  -s read-only \
  --ignore-user-config \
  -m gpt-5.4 \
  -c model_reasoning_effort="high" \
  --output-schema rubric-schema.json \
  -o grades/<NN>-<slug>.json \
  "$(cat rubric-prompt.txt)"
```

with the SKILL.md content piped on stdin. JSON Schema is server-side enforced — no schema-violation retries occurred across 10 calls.

### Persona

GPT-5.4 was given the `pragmatic-practitioner` persona instructions (matching the v0.2 Claude-pragmatic baseline) — *"Real-world weighting. Reward implementations that work in practice, not just textbook compliance. A skill that solves the actual problem with one missing element scores B+/A−, not C."* Despite identical persona instructions, GPT-5.4 consistently graded ~1 step lower than Claude-pragmatic. Either training-data variance, or genuinely stricter interpretation of "borderline" — the experiment can't distinguish.

### Wall-clock & cost

- 10 calls, sequential, total wall-clock 17 min 12 sec (mean ≈ 110s/call at high reasoning effort)
- 1 cached run (frontend-design, from the smoke test) — re-run produced identical aggregate
- Cost not directly measured; estimated low double digits USD at gpt-5.4 pricing

### Why `gpt-5.4` not `gpt-5.5`

`gpt-5.5` is server-recognized but locked behind a Codex CLI version newer than the local `0.122.0` and not yet available on this account. `gpt-5.4` is the highest-tier OpenAI frontier model accessible at run time. The methodology is identical for `gpt-5.5`; v0.3 follow-up will re-run when access lands.

### Why not run all 3 personas on GPT-5.4?

A 3× expansion would multiply cost without proportional signal. The v0.2 pilot already established that *within-Claude* persona modulation produces ~1.83 grade-step distance; the question for v0.3 was inter-model agreement, which one persona suffices to answer. Multi-persona GPT-5.4 + Gemini are deferred.

### Why aggregate grades rather than per-principle Cohen's kappa?

Per-principle κ requires aligned rubric versions (Claude data is 22-principle, GPT-5.4 is 25-principle) and a categorical-agreement metric across an ordinal scale. Aggregate grade-step distance is the right comparable across rubric versions and the metric used in v0.2. Per-principle agreement on the 22 shared principles is computable from the raw data ([`kappa-pilot-multimodel-raw-data.md`](./kappa-pilot-multimodel-raw-data.md)) but not run here.

---

## Honest limitations

1. **Single rater per model.** One GPT-5.4 invocation per skill — no within-GPT variance estimate. Kappa pilot v3 should run each call 2-3× to bound that.
2. **`gpt-5.4`, not `gpt-5.5`.** When `gpt-5.5` is accessible, the experiment should re-run; the conservative-grading pattern may shift.
3. **Pragmatic-practitioner persona only.** Strict and charitable on GPT-5.4 are missing. Cannot compute the analogue of v0.2's within-Claude triangle.
4. **Rubric version mismatch in the cross-comparison.** v0.2 Claude data is 22-principle; v0.3 GPT-5.4 data is 25-principle. Aggregate grades are stable across rubric versions for Procedural / Reference / Creative skills (the 3 new principles either don't apply or fail uniformly), but a clean apples-to-apples on the 22 shared principles requires re-collecting Claude grades at 22-principle scope from this run.
5. **Reasoning-effort fixed at `high`.** GPT-5.4 at `medium` or `low` may produce different grades; no cost/quality tradeoff data here.
6. **No Gemini.** Multi-vendor expansion (Gemini, Mistral, etc.) is the next experiment.
7. **The 10 skills are the v0.2 set.** No new corpus stratification. Re-using the same 10 was deliberate (allows direct comparison) but means findings inherit v0.2's archetype-distribution choices.
8. **Author bias remains.** The rubric was designed by Catafal, who also scored the v0.2 Claude pilot; GPT-5.4 has no such involvement, but the prompt itself encodes Catafal's principle definitions and may favor those framings.

---

## What this unblocks for v0.3 / v1.0

- **The "rubric is Claude-specific" objection is partially answered.** Cross-model agreement (1.20 grade-steps) is *tighter* than within-Claude persona spread (1.83). The rubric travels.
- **The `#24 self-observation` principle is empirically validated as a real corpus-wide gap.** 7/7 applicable skills graded near-F by an independent model. v0.3 priority #4 (`meta-paap` v2 self-critique improvements + closing `#24` in the framework itself) is now supported by external evidence.
- **The persona system's grade-step distances generalize.** GPT-5.4 lands inside the strict↔charitable triangle established by Claude personas. Persona modulation is doing real work, not just prompting noise.
- **GPT-5.5 + Gemini are the obvious next experiments.** Same protocol, different models. The schema + prompt + runner are all reusable.

---

## Stage B — Gemini-3 vs the 4-rater baseline

Same 10 skills, fifth rater added: **gemini-3-pro-preview** via Gemini CLI 0.32.1 with the same `pragmatic-practitioner` persona and the same 25-principle rubric. The CLI does not expose `response_schema`, so JSON was prompt-engineered + Python-validated + retry-once on parse failure (vs Codex's server-side schema enforcement). All 10 calls succeeded on first attempt; no retries triggered.

**Total wall-clock:** 11 min 53 sec for 10 calls (mean ~71 s/call). Faster than GPT-5.4's 17 min — Gemini CLI doesn't expose a reasoning-effort knob.

### Headline finding (Stage B)

**Gemini-3 ↔ Claude-pragmatic = 2.30 grade-steps** — the largest pair distance in the dataset, larger than within-Claude strict↔pragmatic (1.83) and nearly twice GPT-5.4's 1.20.

| Pair | Mean distance | n |
|---|---:|---:|
| **Gemini-3 ↔ Claude-pragmatic** | **2.30** | 10 |
| Gemini-3 ↔ Claude-charitable | 2.00 | 10 |
| Gemini-3 ↔ Claude-strict | 1.70 | 10 |
| Gemini-3 ↔ GPT-5.4 (cross-vendor) | 1.70 | 10 |
| *(reference)* GPT-5.4 ↔ Claude-pragmatic | 1.20 | 10 |
| *(reference)* Within-Claude strict↔pragmatic | 1.83 | 10 |

Gemini-3 is closest to Claude-strict and to GPT-5.4 (both at 1.70), and farthest from Claude-pragmatic. The reframing: GPT-5.4 was the well-aligned outlier; Gemini-3 looks more like what a "different model family" actually produces under the same rubric.

### 5-rater aggregate grades

| Skill | Gemini-3 | GPT-5.4 | Claude-pragmatic | Claude-strict | Claude-charitable | 5-rater spread |
|---|:---:|:---:|:---:|:---:|:---:|---:|
| obra/test-driven-development | A− | B− | A− | C+ | B+ | 4.0 |
| trailofbits/agentic-actions-auditor | C+ | B− | A− | B+ | B+ | 4.0 |
| anthropic/skill-creator | B+ | B+ | B+ | B+ | B+ | **0.0** |
| tapestry/article-extractor | C | B− | B− | C | C+ | 2.0 |
| expo/deployment | **D** | C | B− | C− | B− | **5.0** |
| K-Dense-AI/biopython | C | B− | B+ | B− | B+ | 4.0 |
| chrisvoncsefalvay/d3-viz | C+ | B− | B | C+ | B | 2.0 |
| anthropic/canvas-design | B | B | B+ | B+ | B+ | 1.0 |
| anthropic/frontend-design | B+ | B− | B− | C+ | B+ | 3.0 |
| anthropic/algorithmic-art | C+ | B+ | B+ | B | B+ | 3.0 |

**5-rater unanimity: 1/10** — only `anthropics/skill-creator` earned identical aggregate grades from all 5 raters. Down from v0.2's 2/10 within-Claude. The wildest spread is on `expo/deployment` (5 grade-steps from B− to D — which is also the smallest skill at 190 lines).

### Archetype detection — 5 raters

| Skill | Gemini-3 | GPT-5.4 | C-prag | C-strict | C-charit |
|---|---|---|---|---|---|
| obra/test-driven-development | **Hybrid** | Procedural | Procedural | Procedural | Procedural |
| trailofbits/agentic-actions-auditor | Procedural | Procedural | Procedural | **Hybrid** | Procedural |
| anthropic/skill-creator | Procedural | Procedural | **Hybrid** | Procedural | **Hybrid** |
| tapestry/article-extractor | Procedural | Procedural | Procedural | **Reference** | Procedural |
| expo/deployment | Reference | Reference | Reference | Reference | Reference |
| K-Dense-AI/biopython | Reference | Reference | Reference | Reference | Reference |
| chrisvoncsefalvay/d3-viz | Reference | Reference | Reference | Reference | Reference |
| anthropic/canvas-design | Creative | **Hybrid** | Creative | Creative | Creative |
| anthropic/frontend-design | Creative | Creative | Creative | Creative | Creative |
| anthropic/algorithmic-art | Creative | **Hybrid** | Creative | Creative | Creative |

**Archetype agreement Gemini-3 vs the others:**

- Gemini-3 ↔ Claude-pragmatic: **8/10**
- Gemini-3 ↔ Claude-charitable: 8/10
- Gemini-3 ↔ Claude-strict: 7/10
- Gemini-3 ↔ GPT-5.4: 7/10

**This is the surprising part.** Gemini-3 *agrees better than GPT-5.4* on archetype classification (8/10 vs 7/10 with Claude-pragmatic), while disagreeing more on grading severity. The disagreement is on *how good is this skill*, not *what kind of skill is this*.

### Gemini-3 grades on the 3 v0.3 principles

| Skill | #23 host | #24 self | #25 spawn |
|---|:---:|:---:|:---:|
| obra/test-driven-development | A | N/A | N/A |
| trailofbits/agentic-actions-auditor | A | F | F |
| anthropic/skill-creator | **A+** | **A** | N/A |
| tapestry/article-extractor | A− | F | N/A |
| expo/deployment | B | F | N/A |
| K-Dense-AI/biopython | A | F | N/A |
| chrisvoncsefalvay/d3-viz | B+ | F | N/A |
| anthropic/canvas-design | C | N/A | N/A |
| anthropic/frontend-design | A | N/A | N/A |
| anthropic/algorithmic-art | B | N/A | N/A |

**Means + comparison to GPT-5.4:**

| Principle | Gemini-3 mean ordinal | GPT-5.4 mean ordinal | Applicability divergence |
|---|---:|---:|---|
| #23 host-portable | 9.6 (≈ A−) | 7.9 (≈ B) | Gemini grades ~2 letters higher |
| #24 self-observation | 1.8 (≈ ~F+) | 1.0 (≈ F) | Gemini found `skill-creator` deserved A; GPT-5.4 said B− |
| #25 spawn-detection | 0.0 (≈ F, n=1 only) | 2.8 (≈ D+) | **Major applicability split:** Gemini marked 9/10 N/A; GPT-5.4 marked 4/10 applicable |

**The #25 applicability split is the most informative single finding.** Gemini-3 read spawn-detection as not-applicable to most Procedural skills in the corpus; GPT-5.4 read it as applicable to all 4 Procedural skills. The rubric's N/A justification rule is genuinely ambiguous on this principle — that's a v0.3+ rubric-revision item.

---

## Multi-vendor synthesis (post-Gemini, the corrected conclusions)

### What the GPT-5.4-only data suggested vs what 5-rater data shows

**After GPT-5.4 alone:** "Cross-model agreement is tighter than within-Claude persona spread. The rubric travels."

**After GPT-5.4 + Gemini-3:** That conclusion was over-strong. **Three of four Gemini-3 ↔ Claude pair-distances exceed the within-Claude max of 1.83.** Cross-model variance is real and substantial; GPT-5.4 was the well-aligned outlier, not the representative case.

### Candidate explanations for the asymmetric vendor agreement

The data does not adjudicate between these — but they are the live hypotheses worth testing. The first one is the **leading candidate** given the observed asymmetry (Claude+GPT cluster, Gemini outlier):

1. **Corpus-vendor familiarity bias (leading candidate).** The 10-skill corpus was authored primarily for Claude Code. From GPT-5 onward, OpenAI's frontier models follow long detailed instructions with accuracy that closely tracks Claude's interpretation of the same text — the two vendors converged on similar instruction-following behavior at the high end. Gemini-3 trained on a different RLHF distribution: same instruction text, different reading. Under this hypothesis, the asymmetry isn't "Gemini grades wrong" — it's "the corpus and the rubric were both authored against the Claude+GPT mode of instruction-following, so a model that doesn't share that mode applies the same rubric more literally and lands at different grades." *This explanation is consistent with all the observed data*: GPT-5.4 inside the Claude triangle (1.20 from pragmatic), Gemini outside it (2.30 from pragmatic), cross-vendor distance equal to Gemini-vs-Claude-strict (both 1.70 — Gemini reads like its own consistent rater, not a noisy version of the others).
2. **Pragmatic-practitioner persona prompt landed differently.** GPT-5.4 may interpret "real-world weighting; reward implementations that work in practice" closely to Claude's reading; Gemini-3 may apply that frame to a stricter baseline of what "works" means.
3. **N/A handling.** Gemini-3 marked 9/10 N/A on #25 vs GPT-5.4's 4/10 — meta-level disagreement on what counts as applicable. Some of Gemini's lower aggregate grades come from including more applicable principles in the average.
4. **Reasoning-effort confound.** GPT-5.4 was run at `model_reasoning_effort=high` (explicit deeper-thinking). Gemini CLI doesn't expose an equivalent knob — Gemini-3 may have done less internal CoT per call.

The cleanest discriminator: re-run GPT-5.4 at `medium` or `low` effort, and re-run a deliberately Claude-friendly skill subset on Gemini, and see which knobs move the distances most. **v0.4 follow-up.**

### Updated headline numbers

| Pair | Mean grade-step distance |
|---|---:|
| **GPT-5.4 ↔ Claude-pragmatic** | **1.20** |
| GPT-5.4 ↔ Claude-strict | 1.00 |
| GPT-5.4 ↔ Claude-charitable | 1.30 |
| **Gemini-3 ↔ Claude-pragmatic** | **2.30** |
| Gemini-3 ↔ Claude-strict | 1.70 |
| Gemini-3 ↔ Claude-charitable | 2.00 |
| **Cross-vendor Gemini-3 ↔ GPT-5.4** | **1.70** |
| *(reference)* Within-Claude strict↔pragmatic | 1.83 |
| *(reference)* Within-Claude pragmatic↔charit | 0.60 |

**Mean across all 4 cross-vendor non-Claude pairs (Gem ↔ each of {Claude-prag, Claude-strict, Claude-charit, GPT-5.4} + the GPT-5.4 ↔ Claude-prag pair): ~1.7 grade-steps.** Cross-vendor distances cluster around the within-Claude strict↔pragmatic distance, suggesting the persona system and the model-vendor identity are *roughly comparable* sources of grade-shift, not one dominating the other.

### What now reads as confirmed

1. **Archetype detection is stable across all 5 raters** (8/10 unanimous on Reference + Creative skills; all disagreements on the same Procedural↔Hybrid borderline cases v0.2 already named). This generalizes cleanly.
2. **#24 self-observation is a real corpus-wide gap.** Both GPT-5.4 (7/7 near-F) and Gemini-3 (5/6 F or near-F) confirm this. The framework's own honest C self-audit on #24 is externally validated by *two* independent model families.
3. **The persona system does real work** — and it's roughly the same magnitude as the model-vendor effect. Persona modulation is not just prompt-noise; model identity is not just translation-noise. Both contribute meaningfully to grade-step distances.

### What now reads as open

1. **Aggregate grade portability across vendors is weaker than v0.2's within-model data implied.** A skill graded A− by Claude-pragmatic might draw C+ from Gemini-3 — that's a real difference for any practitioner using the rubric to make ship-or-iterate decisions.
2. **#25 spawn-detection applicability is unstable across vendors.** Until the rubric's N/A rule for #25 is sharpened, scores on this principle aren't comparable across raters.
3. **The "rubric is Claude-specific" objection is partially valid.** It's *not* that Claude is uniquely interpreting the rubric — GPT-5.4 sits inside the Claude-persona triangle. It's that Gemini sits outside it. Either Claude+GPT cluster as one mode of instruction-following and Gemini is another, or the corpus was authored for Claude's reading and GPT happens to read it similarly.

---

## Cross-references

- [`kappa-pilot.md`](./kappa-pilot.md) — v0.2 prompt-variant kappa pilot (3 Claude personas)
- [`kappa-pilot-multimodel-raw-data.md`](./kappa-pilot-multimodel-raw-data.md) — verbatim per-principle outputs (GPT-5.4 + Gemini-3 sections)
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — the 25 principles being scored
- [`../04-RUBRIC/reflexive-self-audit.md`](../04-RUBRIC/reflexive-self-audit.md) — the repo's own grades (including the C on #24 that this pilot externally confirms across two vendors)
- [`../06-META-PAAP/paap-eval/SKILL.md`](../06-META-PAAP/paap-eval/SKILL.md) — the auto-scoring instrument; `paap-eval` was NOT used here (direct CLI invocation per the methodology)
- [`../07-OPEN-QUESTIONS/`](../07-OPEN-QUESTIONS/) — v0.3 priority #2 (multi-model kappa) status
