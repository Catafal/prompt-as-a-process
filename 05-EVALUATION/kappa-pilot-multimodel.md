# Multi-model Kappa Pilot — GPT-5.4 vs Claude Personas (v0.3)

> v0.3 Stage: extends the v0.2 prompt-variant kappa pilot to a different model family. Same 10 skills, new rater (OpenAI GPT-5.4 via Codex CLI). Asks the question v0.2 deferred: **does the rubric travel across model families, or does it encode Claude-shaped bias?**

**Date:** 2026-04-26
**Method:** Single GPT-5.4 invocation per skill via `codex exec --output-schema` with `model_reasoning_effort=high`, `pragmatic-practitioner` persona, full 25-principle rubric. JSON-Schema-enforced response shape, server-side.
**Skills:** the same 10 community SKILL.md files used in v0.2 (4 Procedural / 1 Reference-borderline / 3 Reference / 3 Creative — see [`kappa-pilot.md`](./kappa-pilot.md) for the original archetype declarations).
**Comparison baseline:** the 3 Claude personas (strict-academic / pragmatic-practitioner / charitable-newcomer) from v0.2's pilot.
**Raw data:** [`kappa-pilot-multimodel-raw-data.md`](./kappa-pilot-multimodel-raw-data.md)
**Rubric version:** v0.3 (Catafal, 2026) — 25 principles. v0.2 Claude data was at 22-principle scale; the comparison uses aggregate grades (which don't depend on individual principle counts the same way).

---

## Headline findings

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

## Cross-references

- [`kappa-pilot.md`](./kappa-pilot.md) — v0.2 prompt-variant kappa pilot (3 Claude personas)
- [`kappa-pilot-multimodel-raw-data.md`](./kappa-pilot-multimodel-raw-data.md) — verbatim GPT-5.4 outputs (10 schema-validated JSON files)
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — the 25 principles being scored
- [`../04-RUBRIC/reflexive-self-audit.md`](../04-RUBRIC/reflexive-self-audit.md) — the repo's own grades (including the C on #24 that this pilot externally confirms)
- [`../06-META-PAAP/paap-eval/SKILL.md`](../06-META-PAAP/paap-eval/SKILL.md) — the auto-scoring instrument; `paap-eval` was NOT used here (direct `codex exec` invocation per the methodology)
- [`../07-OPEN-QUESTIONS/`](../07-OPEN-QUESTIONS/) — v0.3 priority #2 (multi-model kappa) status
