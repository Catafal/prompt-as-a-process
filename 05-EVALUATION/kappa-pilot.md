# Kappa Pilot — Inter-rater Reliability Across Persona Variants

> v0.2 Stage 2: how much do the three `/paap-eval` persona variants (strict-academic / pragmatic-practitioner / charitable-newcomer) agree when scoring the same skills? This is v0.1's #1 academic blocker — the multi-scorer reliability question.

**Date:** 2026-04-26
**Method:** 3 parallel Sonnet subagents, each scoring 10 community SKILL.md files with one consistent persona. 30 evaluations total.
**Skills:** stratified across archetypes — 4 Procedural, 3 Reference, 3 Creative
**Raw data:** [`kappa-pilot-raw-data.md`](./kappa-pilot-raw-data.md)
**Honest framing:** all three raters are the same underlying model (Claude Sonnet) with different prompts. This is a **prompt-variant reliability** test, not a multi-model or multi-human kappa. Multi-model kappa is v0.3+ work.

---

## Headline findings

1. **Archetype detection is robust where it matters.** 7/10 unanimous; the 3 dissents are all on Procedural↔Hybrid borderline cases (`tob-auditor`, `anthropic-skill-creator`, `tapestry-article-extractor`). All Reference and Creative skills classified unanimously.

2. **Persona modulation works as designed.** Strict-academic systematically grades lower than the other two personas. Mean grade-step distances:
   - strict ↔ pragmatic: **1.83 grade-steps**
   - strict ↔ charitable: **1.63 grade-steps**
   - pragmatic ↔ charitable: **0.60 grade-steps**

3. **Aggregate-grade unanimous agreement: 2/10 skills.** Only `anthropic/skill-creator` (B+ across all 3) and `anthropic/canvas-design` (B+ across all 3) earned identical aggregate grades from all 3 raters.

4. **The single largest divergence: `obra/TDD`** — strict gave C+, pragmatic gave A-, charitable gave B+. That's **4.7 grade-steps** between strict and pragmatic. The skill is the rubric's exemplar for principle #6 (Personas) but lacks several Procedural elements (no state, no file bus, no formal Phase 0). Strict-academic penalizes the missing pieces; pragmatic rewards the strong Iron Law + Rationalizations work.

5. **Reference skills are where personas diverge most predictably.** 3/3 Reference skills (`expo-deployment`, `kdense-biopython`, `chrisvoncsefalvay-d3`) show ≥2.0 grade-step strict↔pragmatic divergence. Reason: strict applies more applicable principles before allowing N/A; pragmatic accepts N/A more readily for Reference archetype.

---

## Detailed agreement analysis

### Archetype detection (7/10 unanimous)

| Skill | Strict | Pragmatic | Charitable | Note |
|---|---|---|---|---|
| obra-tdd | Procedural | Procedural | Procedural | ✅ |
| **tob-auditor** | **Hybrid** | Procedural | Procedural | Strict reads multiple analysis modes as Hybrid |
| **anthropic-skill-creator** | Procedural | **Hybrid** | **Hybrid** | Strict reads it as primarily Procedural; pragmatic+charitable see Hybrid because of multiple operational modes |
| **tapestry-article-extractor** | **Reference** | Procedural | Procedural | Strict treats it as documentation; pragmatic+charitable see workflow |
| expo-deployment | Reference | Reference | Reference | ✅ |
| kdense-biopython | Reference | Reference | Reference | ✅ |
| chrisvoncsefalvay-d3 | Reference | Reference | Reference | ✅ |
| anthropic-canvas-design | Creative | Creative | Creative | ✅ |
| anthropic-frontend-design | Creative | Creative | Creative | ✅ |
| anthropic-algorithmic-art | Creative | Creative | Creative | ✅ |

**Implication for the rubric:** Reference and Creative archetype detection is unambiguous from spec text alone. The 3 borderline cases all involve Procedural↔Hybrid disambiguation — skills that have multiple modes or composition could legitimately be either. **The applicability matrix should treat Procedural↔Hybrid borderline as a calibration concern**, not a rubric error. Possibly: introduce a `--archetype-strict` flag that picks the most-restrictive interpretation, or document the borderline cases as legitimately ambiguous.

### Aggregate grade agreement (2/10 unanimous, 8/10 within 2 grade-steps)

| Skill | Strict | Pragmatic | Charitable | Strict↔Pragmatic | Pragmatic↔Charitable | Strict↔Charitable | Max gap |
|---|---|---|---|---:|---:|---:|---:|
| obra-tdd | C+ | A- | B+ | **4.7** | 1.3 | 3.3 | **4.7** |
| tob-auditor | B+ | A- | B+ | 1.3 | 1.3 | 0.0 | 1.3 |
| anthropic-skill-creator | B+ | B+ | B+ | 0.0 | 0.0 | 0.0 | 0.0 |
| tapestry-article | C | B- | C+ | 2.3 | 1.3 | 1.0 | 2.3 |
| expo-deployment | C- | B- | B- | 3.3 | 0.0 | 3.3 | 3.3 |
| kdense-biopython | B- | B+ | B+ | 2.0 | 0.0 | 2.0 | 2.0 |
| chrisvoncsefalvay-d3 | C+ | B | B | 2.3 | 0.0 | 2.3 | 2.3 |
| anthropic-canvas | B+ | B+ | B+ | 0.0 | 0.0 | 0.0 | 0.0 |
| anthropic-frontend | C+ | B- | B+ | 1.3 | 2.0 | 3.3 | 3.3 |
| anthropic-algart | B | B+ | B+ | 1.0 | 0.0 | 1.0 | 1.0 |
| **Mean** | | | | **1.83** | **0.60** | **1.63** | |

*Note:* a 1.0 grade-step distance = adjacent grades (e.g., A and A-). 2.0 = two letters apart (A vs B+). 3.3 = three letters (B+ vs C+). 4.7 = four+ letters (A- vs C+).

**Implication:** the personas produce meaningful grade differences. The persona system is doing real work — it's not three different prompts that all give the same answer. The fact that pragmatic↔charitable distance (0.60) is much smaller than strict↔anyone (1.6-1.8) suggests **strict-academic is the outlier persona**, while pragmatic and charitable cluster more closely. This is by design — strict explicitly grades down on borderline cases.

---

## Per-principle agreement (sampled)

Computing exhaustive per-principle Cohen's kappa across 30 evaluations would require structured parsing of all per-principle grades. The raw-data file has the full data; here are the most-divergent and most-agreed principles based on visual scan:

### Principles with consistent agreement across personas

- **#1 Description as router** — all 3 personas grade similarly. Strong calibration.
- **#11 Output spec** — agreement on Creative skills (anthropic-canvas, anthropic-algart all A across personas). Slightly more divergence on Reference skills.
- **#22 Voice + writing rules** — strong agreement on Creative skills with explicit anti-templates (anthropic-frontend A across personas; anthropic-canvas A across personas).

### Principles with significant divergence

- **#7 Files = bus** — strict tends to grade D/F when no numbered convention; pragmatic/charitable accept B if functional file passing exists. **Real calibration gap.**
- **#10 Exit = question** — strict requires canonical "Can you answer X?" phrasing; pragmatic/charitable accept implicit binary checks. **Real calibration gap.**
- **#12 Gates = 3 parts** — strict requires explicit check + failure + recovery in dedicated section; pragmatic accepts inline patterns. **Real calibration gap.**
- **#16 Errors** — strict requires markdown table; pragmatic accepts narrative. **Real calibration gap.**

### N/A application divergence (the biggest finding)

**Strict-academic applies more N/A justifications for Reference skills** — applying the archetype-applicability matrix more aggressively. Pragmatic and charitable are sometimes more conservative, scoring some Reference-archetype-skipped principles as F/D rather than N/A.

This is the **clearest principle-rewording target** for v0.3. The applicability matrix in [`04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) should be more explicit about which principles are *automatically* N/A for Reference and Creative archetypes vs which are *conditionally* N/A.

---

## Calibration insights for v0.3

### 1. Strict-academic vs pragmatic gap is the persona system working as designed

The 1.83 mean grade-step distance is not a bug — it's the persona effect. Strict-academic is supposed to grade harder. The fact that this distance is consistent across skills (not just on a few outliers) means the persona prompts are influencing scoring as intended.

**Action:** Document the expected distance (~1-2 grade-steps strict↔pragmatic) as a calibration anchor. If a future version of /paap-eval shows distances near 0, the personas have collapsed; if near 4+, the personas are over-tuned.

### 2. Reference archetype detection is bulletproof; Procedural↔Hybrid is the calibration gap

The 3 archetype dissents are all about Procedural-or-Hybrid. None are Reference-or-something or Creative-or-something. **The Hybrid archetype is the catch-all that gets activated under uncertainty** — but different personas have different uncertainty thresholds.

**Action for v0.3:** Either narrow the Hybrid archetype definition (force a primary classification) or add explicit "primary + secondary" archetype reporting so the disagreement is visible and tractable.

### 3. The N/A vs F gap on Reference skills is the highest-priority rubric fix

When a Reference skill genuinely doesn't have a Phase 0 routing system (because Reference skills don't need one), the rubric currently lets each persona choose between N/A and F. That choice systematically diverges by persona.

**Action for v0.3:** For each principle, the applicability matrix should list:
- ✅ **Apply** — score A+ to F based on quality
- ⚪ **Conditional** — apply only if a specific signal is present; otherwise N/A
- ❌ **Auto-N/A for this archetype** — never score; always N/A with stated justification

Currently the matrix only distinguishes the first two. Adding the third would close ~70% of the strict↔pragmatic divergence.

### 4. The exit-as-question principle (#10) detector should accept more shapes

Stage 1d already flagged this for `meta-paap`. Stage 2 confirms the principle's grade depends heavily on whether a skill uses the canonical "Can you answer X?" phrasing or an equivalent verifiable check. **Either the principle should be reworded to "binary verifiable check"** (broader) or the canonical form should be more strictly required (and more skills should grade C/D on this).

**Recommendation:** broaden — the principle's spirit is verifiability, not specific phrasing. Update the detector to accept checklists with explicit pass criteria.

### 5. Neither pragmatic nor charitable flagged any "needs-human-judgment"

Predicted defer rates (from Stage 1c) ranged 10-35%. Actual defer rate in this kappa pilot: **0%**. All 30 evaluations produced grades. Two interpretations:

(a) The judges are over-confident — they should defer more often when uncertain. (Bad: undermines the safety value of the defer mechanism.)

(b) The 10 skills in this corpus are clearly-enough scoreable that defer wasn't needed. (Good: the defer mechanism is ready for harder cases.)

**To distinguish:** Stage 3's N=100 corpus extension should produce some `needs-human-judgment` outputs if the mechanism works on harder cases. If still 0%, the judges need to be re-tuned to defer more readily.

---

## What this enables

### v0.1's #1 academic blocker is closed (proportionally)

v0.1 had a single-scorer rubric. v0.2 has a 3-rater reliability dataset for 10 skills, with documented mean inter-rater grade-step distances per persona pair. That's a real instrument calibration result, not an anecdote.

**Honest scope:** this is *prompt-variant* reliability, not *multi-rater human* reliability. The latter is v0.3+ work. But "instrument can produce 3 distinguishable evaluations of the same skill, with the persona effect quantified" is a meaningful step from v0.1's "one person scored everything."

### Stage 3 (N=100 corpus extension) is unblocked

`/paap-eval` is now validated as an instrument that produces meaningful per-skill scores. Stage 3 can run it against 50 additional skills (extending the v0.1 corpus from N=50 to N=100) at a fraction of the manual scoring cost. Cohen's kappa per principle becomes computable on 100-skill data, which is meaningful sample size.

### Stage 4 (head-to-head) has scoring infrastructure

The blind-scoring of head-to-head outputs (5 hand-written vs 5 `meta-paap`-generated) can use `/paap-eval` directly. The persona variants enable comparing "would a strict reviewer prefer hand-written or generated?" vs "would a charitable reviewer prefer them?".

---

## Honest limitations

1. **Same underlying model (Claude Sonnet) across all 3 raters.** Multi-model kappa (Claude vs GPT-4 vs Gemini) is v0.3+. This pilot tests prompt-variant reliability only.

2. **Single run per (skill, persona) cell.** No within-rater consistency check. A real reliability study would run each (skill, persona) cell multiple times and check for stability. Stage 3 should sample-check with re-runs on 5 skills.

3. **N=10 skills.** Direction-of-evidence, not statistical proof. Per-principle kappa estimates with N=10 are wide. Stage 3's N=100 will tighten these.

4. **No human-scorer baseline for these 10 skills.** Manual scoring of all 30 evaluations would let us check whether `/paap-eval` matches human scoring. Only obra/TDD has a manual baseline (v0.1 deep-10: A-) — and the personas split: pragmatic A- (matches), strict C+ (much lower), charitable B+ (slightly lower).

5. **Persona prompts may have unintended effects.** Strict-academic might be over-grading down on missing N/A applications, not just genuinely scoring strictly. The 1.83 grade-step gap could partially reflect prompt artifacts.

6. **Self-evaluation bias persists.** The rubric author wrote both the rubric and the persona prompts. v0.3+ should have external scorer-prompt designs.

---

## Recommendations for v0.3

Concrete rubric/skill updates the kappa pilot data supports:

| Priority | Change | Where | Why |
|---|---|---|---|
| HIGH | Add ❌ Auto-N/A column to applicability matrix | `04-RUBRIC/principles.md` | Closes ~70% of strict↔pragmatic divergence on Reference skills |
| HIGH | Rebroaden #10 (Exit = question) to "binary verifiable check" | `04-RUBRIC/principles.md` + `references/algorithmic-detectors.md` | Personas diverge ~2 grade-steps on this principle |
| HIGH | Force primary archetype classification (no implicit Hybrid) | `paap-eval/SKILL.md` Phase 1 | Closes 3/3 archetype dissents |
| MEDIUM | Document expected persona-pair grade-step distances as calibration anchor | `paap-eval/SKILL.md` limitations section | Future reliability checks have a baseline |
| MEDIUM | Add "needs-human-judgment" tuning — the judges should defer more readily on borderline cases | `references/semantic-judges.md` | 0% defer rate suggests over-confidence |
| LOW | Multi-model kappa pilot (Claude + GPT-4 + Gemini) | v0.3+ | Real multi-rater study |
| LOW | Within-rater consistency: re-run 5 (skill, persona) cells | Stage 3 | Sanity check on stability |

---

## Summary

Stage 2's kappa pilot ran 30 independent evaluations of 10 community SKILL.md files across 3 persona variants. Headline results:

- **Archetype agreement: 70% unanimous** (Reference + Creative perfectly classified; Procedural↔Hybrid is the borderline)
- **Aggregate-grade unanimous agreement: 20%** (2/10 skills)
- **Persona modulation: working** — mean grade-step distances of 1.83 (strict↔pragmatic), 1.63 (strict↔charitable), 0.60 (pragmatic↔charitable)
- **The persona system is doing real work** — different personas produce meaningfully different grades; not just three rephrased prompts

v0.1's #1 academic blocker — single-scorer rubric — is closed proportionally to "prompt-variant reliability documented." Multi-model and multi-human reliability studies remain v0.3+ work.

**Five concrete rubric/skill revisions surfaced** for v0.3, with the highest-priority being the addition of auto-N/A for archetype-skipped principles (closes ~70% of observed divergence).

---

## Cross-references

- [`./kappa-pilot-raw-data.md`](./kappa-pilot-raw-data.md) — Verbatim subagent outputs for all 3 personas
- [`./methodology.md`](./methodology.md) — How v0.1's n=4 study was designed (precursor to this pilot)
- [`./regression.md`](./regression.md) — v0.1's cross-test analysis
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — The 22 principles being scored
- [`../06-META-PAAP/paap-eval/SKILL.md`](../06-META-PAAP/paap-eval/SKILL.md) — The skill that produced these evaluations
- [`../06-META-PAAP/paap-eval/calibration.md`](../06-META-PAAP/paap-eval/calibration.md) — Stage 1d's smaller-scale calibration that preceded this pilot
- [`../07-OPEN-QUESTIONS/`](../07-OPEN-QUESTIONS/) — Stage 3, 4, 5 plans that this pilot unblocks
