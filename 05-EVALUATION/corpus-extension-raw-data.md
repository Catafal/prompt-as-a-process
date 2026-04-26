# Stage 3 Corpus Extension — Raw `/paap-eval` Scoring Data

> Verbatim per-skill scoring outputs from v0.2 Stage 3's corpus extension. 30 community SKILL.md files scored by `/paap-eval` with the `pragmatic-practitioner` persona. Preserved for reproducibility.

**Date:** 2026-04-26
**Method:** 3 parallel general-purpose subagents (Sonnet model), each scoring 10 SKILL.md files
**Persona:** `pragmatic-practitioner` (default — single persona for corpus extension; Stage 2 already documented persona variance)
**Skills source:** [`04-RUBRIC/corpus-extension-30-skills.md`](../04-RUBRIC/corpus-extension-30-skills.md)
**Local cache:** `/tmp/paap-eval-corpus-extension/*.md` (30 files, 13,178 lines total)
**Subagent IDs:** batch 1 `a06725c`, batch 2 `a3075bf`, batch 3 `a4d0989`

The aggregated analysis is in [`../04-RUBRIC/empirical-validation.md`](../04-RUBRIC/empirical-validation.md). This file is the raw data.

---

## Per-skill aggregate grades + archetype + key findings

### Skills 1-10 (Batch 1)

| # | Skill | Archetype | Aggregate | Top strength | Top weakness | Deferred candidates observed |
|---|---|---|---|---|---|---|
| 51 | jamesrochabrun-apple-hig | Reference | C+ | #14 (explicit iOS scope) | #15 (no progress reporting) | none |
| 52 | jamesrochabrun-leetcode | Procedural | D+ | #1 (specific triggers) | #7 (no file bus) | none |
| 53 | jamesrochabrun-kids-book | Creative | B- | #11 (detailed page/word/rhyme spec) | #15 (no progress) | none |
| 54 | jamesrochabrun-trading | Procedural | C+ | #11 (per-component spec) | #2 (no Phase 0 routing) | none |
| 55 | jamesrochabrun-math | Creative | B- | #17 (autonomous defaults) | #22 (generic DO/DON'T list) | #29 (negative — hardcoded path) |
| 56 | daymade-deep-research | Hybrid | A- | #3 (4 explicit modes with criteria) | #22 (thin voice rules) | #25, #26, #30 |
| 57 | daymade-terraform | Reference | A- | #11 (error→cause→fix format) | #15 (no signal) | none |
| 58 | daymade-financial | Procedural | B+ | #16 (correct/incorrect tables) | #4 (no resume protocol) | #29 (positive — relative paths) |
| 59 | daymade-fact-checker | Procedural | B+ | #9 (explicit human gate before edits) | #4 (no state) | none |
| 60 | daymade-douban | Procedural | B | #16 (Do NOT Attempt list) | #4 (no resume for 600+ items) | none |

### Skills 11-20 (Batch 2)

| # | Skill | Archetype | Aggregate | Top strength | Top weakness | Deferred candidates observed |
|---|---|---|---|---|---|---|
| 61 | daymade-ios | Reference | B+ | #13 (externalized references/) | #15 (no progress) | #29 (negative) |
| 62 | glebis-health | Reference | B | #11 (4 named output formats) | #15 (no progress) | #29 (negative — hardcoded ~/data) |
| 63 | glebis-jtbd | Hybrid | A- | #1 (precise + anti-trigger) | #4 (no Resume Protocol) | #26, #29 |
| 64 | glebis-tufte | Creative | A- | #22 (deeply-embedded voice rules) | #15 (implicit only) | #26, #29 |
| 65 | glebis-decision | Hybrid | B | #11 (4 distinct format specs) | #12 (gates lack 3-part structure) | none |
| 66 | agamm-owasp | Reference | B+ | #18 (no hardcoded paths) | #15 (static doc, no signal) | none |
| 67 | AgriciDaniel-cybersec | Procedural | A | #5 (explicit "spawn ALL 8 agents in single message") | #4 (986 lines, no resume) | #25, #26, #29, #30 |
| 68 | ryanbbrown-revealjs | Creative | B+ | #15 (visual-review loop with re-screenshot) | #18 (manual path resolution) | #21, #26, #30 |
| 69 | zarazhangrui-slides | Creative | A- | #22 (anti-AI-slop voice rules) | #15 (no [PROGRESS] protocol) | #21, #26, #30 |
| 70 | sanjay3290-azure-devops | Reference | B | #1 (13 domains, 99 tools, exact triggers) | #15 (zero progress reporting) | none |

### Skills 21-30 (Batch 3)

| # | Skill | Archetype | Aggregate | Top strength | Top weakness | Deferred candidates observed |
|---|---|---|---|---|---|---|
| 71 | sanjay3290-elevenlabs | Procedural | C+ | #3 (TTS vs podcast modes) | #22 (no script voice rules) | #29 (negative) |
| 72 | BehiSecc-vibesec | Reference | B- | #11 (patterns/bypass tables/checklists) | #1 (over-broad description) | none |
| 73 | tasteray-elicitation | Hybrid | B+ | #22 (rich voice rules with anti-patterns) | #2 (no Phase 0 routing) | none |
| 74 | HeshamFS-mesh | Reference | B+ | #14 (allowed-tools restricts Bash with rationale) | #15 (no progress emit instructions) | #29 (positive) |
| 75 | conorbronsdon-aiwriting | Reference | A- | #11 (P0/P1/P2 severity tiers + tolerance matrix) | #15 (no progress on long rewrites) | #30 |
| 76 | coinpaprika-api | Reference | B | #11 (response shapes + rate-limits + deprecation) | #15 (no multi-call workflow signal) | none |
| 77 | wrsmith108-linear | Procedural | B+ | #16 (image upload pitfalls + validate-description error codes) | #22 (no voice rules) | #25, #30 |
| 78 | olgasafonova-skill-check | Procedural | A- | #11 (score+check_id+severity+line+message+fix per issue) | #19 (composition implied not formal) | #21, #26 |
| 79 | product-on-purpose-prd | Procedural | C+ | #20 (Quality Checklist defined before instructions) | #12 (no check/failure/recovery in 8-step) | none |
| 80 | glacierphonk-naming | Creative | A- | #17 (Steps 3-6 internal; only Step 7 surfaces to user) | #13 (15+ refs without manifest) | #30 |

---

## Aggregate distributions (N=30 new skills)

### Archetype distribution

| Archetype | Count | % |
|---|---:|---:|
| Procedural | 10 | 33% |
| Reference | 10 | 33% |
| Creative | 6 | 20% |
| Hybrid | 4 | 13% |

Compare to v0.1 (76% / 12% / 6% / 6%): Procedural fell substantially (intentional sourcing toward diversity); Reference and Creative meaningfully better-represented.

### Aggregate grade distribution

| Grade | Count | Bar |
|---|---:|---|
| A | 1 | █ |
| A- | 8 | ████████ |
| B+ | 8 | ████████ |
| B | 5 | █████ |
| B- | 3 | ███ |
| C+ | 4 | ████ |
| D+ | 1 | █ |

Mean: ~B (3.12 numeric). Lower than v0.1's manual-scored 10-skill deep sub-sample (mean ~B+) — possibly because Stage 3 included weaker long-tail individual-practitioner skills not present in v0.1's curated-list sourcing.

---

## Deferred-candidate sightings (across 30 new skills)

This is the headline Stage 3 finding for the 8 deferred gstack candidates from v0.1's empirical-validation.md.

| Candidate | Sightings | % | Verdict at extended N |
|---|---:|---:|---|
| **#29 Skills are portable; host is config knob** | 8 | 27% | **Promote to v0.3** (mix of positive implementations + negative violations show the principle is widely relevant) |
| **#26 Skills observe themselves and feed prior runs forward** | 6 | 20% | **Promote to v0.3** (Session Lessons sections, version tracking, accumulated style presets — all forms of self-observation showing up community-wide) |
| **#30 Skills detect spawn vs interactive and adapt** | 6 | 20% | **Promote to v0.3** (mode detection patterns, Linear-specialist-vs-direct-execution criteria — community is solving this problem) |
| #21 SKILL.md as build artifact | 3 | 10% | Trending toward promotion; need more evidence in v0.3 |
| #25 Hard guardrails via hooks, not prose | 2 | 7% | Still rare; hooks-as-enforcement remains gstack-specific in mechanism, but prose-discipline substitutes appear (Cluster B: Refusal-as-skill from v0.1) |
| **#22 Composed skills declare which sections parent owns** | 0 | 0% | **Confirm gstack-specific** — no community evidence at N=80 |
| **#24 Dual-voice consensus** | 0 | 0% | **Confirm gstack-specific** |
| **#28 Plan-stage rubric reused at audit time** | 0 | 0% | **Confirm gstack-specific** |

---

## Sub-agent batch summaries (verbatim)

### Batch 1 summary
- Archetype: P:5 R:2 C:2 H:1
- Most-N/A: P5/P8 (linear pipelines), P12 (no formal gates)
- Most low-confidence: P3 (mode/single-path ambiguity), P19 (informal composition)
- Deferred sightings: #29 ×2, #25 ×1, #26 ×1, #30 ×1

### Batch 2 summary
- Archetype: P:1 R:4 C:3 H:2
- Most-N/A: P21, P4, P5, P7, P8 (all archetype-driven exclusions)
- Most low-confidence: P15 (progress hard to grade definitively), P3 (informal modes)
- Deferred sightings: #21 ×2, #25 ×1, #26 ×4, #29 ×4, #30 ×2

### Batch 3 summary
- Archetype: P:5 R:4 C:1 (the agent's H:1 was elicitation; 5+4+1+1=11, slight count discrepancy noted but per-skill data is canonical)
- Most-N/A: P5, P8 (parallel/synthesis), P4 (state), P10/P12 (procedural-only)
- Most low-confidence: P6/P15/P19
- Deferred sightings: #21 ×1, #25 ×1, #26 ×1, #29 ×2, #30 ×3

---

## Limitations

- **Single persona (pragmatic-practitioner) for all 30.** Stage 2's kappa pilot showed ~1.8 grade-step variance across personas. Aggregate grades here could shift ±1-2 grade-steps under different personas.
- **Same underlying model (Sonnet) as Stages 1-2.** Multi-model kappa is v0.3+.
- **Sub-agents read the rubric file at runtime** — consistent reference, but each subagent applied detector/judge logic with its own contextual judgment (light variation expected within "pragmatic-practitioner" framing).
- **No human-scorer baseline for these 30 skills.** Manual scoring would be 30 × 30 min = 15 person-hours — out of scope for v0.2 single-session work.
- **One agent ran a skill (jamesrochabrun-leetcode) that scored D+** — an outlier that pulled the mean grade down. This is real signal (some community skills are weak) but worth noting that 1/30 outlier influences distribution stats.
