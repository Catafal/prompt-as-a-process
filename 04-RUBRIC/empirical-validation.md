# Empirical Validation of the Rubric

> The 22 principles in [`principles.md`](./principles.md) are top-down hypotheses. This file presents the bottom-up evidence: gstack as a single-author case study, an 80-skill survey across 36 community authors (extended from v0.1's N=50), and an honest assessment of which principles held up, which didn't, and which patterns the rubric still misses.

**Headline finding (v0.2):** 19 of the 20 original principles confirmed cleanly under bottom-up testing, plus 2 candidate principles promoted from gstack-specific patterns. Three original principles (#5 Parallel, #13 External storage, #18 Path resolution) hold up only conditionally — they apply when triggered, not universally. **Of the 8 deferred gstack candidates, 3 now show ≥20% community-corpus prevalence and are promotion-ready for v0.3** (#26 self-observation, #29 host-portable, #30 spawn-detection). **3 confirmed gstack-specific** (0% community sightings: #22 section-skip, #24 dual-voice, #28 plan-rubric-reuse). **2 ambiguous** (#21 build-artifact at 10%, #25 hooks at 7% — keep deferred).

This file documents how those calls were made.

---

## Two corpora, two complementary tests

### Corpus 1 — gstack (single-author case study)

Garry Tan's `gstack` repo (50 SKILL.md files, ~43,000 lines, MIT license, ~82,000 stars in 6 weeks at snapshot time). One author, "twenty years" of shipping experience (his framing), building skills explicitly to maximize personal velocity. **A strong "different person, same conclusion" data point** — Tan converged on PaaP's architecture without using the term, framing it as "twenty-three specialists and eight power tools, all slash commands, all Markdown." A stronger validation would be multi-author independent derivation; v0.2 will pursue this.

This is a depth test: how does the rubric score against a single practitioner who has thought about every principle deeply?

### Corpus 2 — 80 community skills (breadth test)

A stratified sample now spanning 80 SKILL.md files across 36 distinct authors. Built in two phases:

- **v0.1 baseline (N=50, 18 authors):** Curated from `anthropics/skills` (14), `obra/superpowers` and `obra/superpowers-skills` (7), `trailofbits/skills` (7), `michalparkola/tapestry-skills-for-claude-code` (5), `expo/skills` (3), `K-Dense-AI/claude-scientific-skills` (2), and 12 individual practitioner repos (1 each). Full URL list: [`corpus-50-skills.md`](./corpus-50-skills.md).
- **v0.2 extension (N=30, 18 NEW authors):** Sourced specifically to dilute v0.1's 4-author concentration and 76% Procedural bias. New authors include `jamesrochabrun`, `daymade` (Chinese), `glebis` (Russian — Gleb Kalinin), `agamm`, `AgriciDaniel`, `ryanbbrown`, `zarazhangrui` (Chinese), `sanjay3290`, `BehiSecc`, `tasteray`, `HeshamFS` (Egyptian), `conorbronsdon`, `coinpaprika` (Polish), `wrsmith108`, `olgasafonova`, `product-on-purpose`, `glacierphonk`, `Swiftner`. Full URL list and per-skill metadata: [`corpus-extension-30-skills.md`](./corpus-extension-30-skills.md). Per-skill `/paap-eval` scoring: [`../05-EVALUATION/corpus-extension-raw-data.md`](../05-EVALUATION/corpus-extension-raw-data.md).

This is a breadth test: how does the rubric hold up when applied to many authors with different skill levels, different priorities, and different cultural/domain backgrounds?

**Honest scope:** the v0.2 plan targeted N=100 (50 new skills); actual delivery is N=80 (30 new skills) due to time-bounded discovery in a single session. Remaining 20-skill gap is documented as v0.3 work.

---

## How the rubric scored against gstack

19 of 20 confirmed. Of those, 4 were extended (gstack does them more rigorously than the original principle requires). 1 partial.

| Result | Count |
|---|---:|
| Confirmed cleanly | 15 |
| Confirmed and extended | 4 |
| Partial | 1 (#20 Output-first — gstack prefers per-section output specs over a single skill-level contract) |
| Disconfirmed | 0 |

Beyond confirmation, gstack contributed **10 candidate new principles** observed at scale:

1. SKILL.md as build artifact (template-rendered with CI-enforced consistency)
2. Composed skills declare which sections parent owns (section-skip-list composition)
3. Decision class drives gating policy (Mechanical / Taste / User Challenge)
4. Dual-voice consensus for verification (Codex + Claude subagent)
5. Hard guardrails via hooks, not prose
6. Skills observe themselves and feed prior runs forward (telemetry-driven self-improvement)
7. Voice + writing rules as skill content
8. Plan-stage rubric reused at audit time (the "boomerang")
9. Skills are portable; host is a config knob
10. Skills detect spawn vs. interactive and adapt

Of these 10, only the ones that held up against the 50-skill community corpus were promoted to v0.1.

---

## How the rubric scored against the 50-skill community corpus

This is the harder test. Many community skills are written by less-experienced authors, in spare time, for narrower use cases.

### Feature presence across 50 skills

| Feature | Count | % |
|---|---:|---:|
| YAML anti-triggers | 3/50 | 6% |
| Phase 0 routing (any form) | 11/50 | 22% |
| Explicit exit conditions | 13/50 | 26% |
| Quality gates with all 3 parts | 13/50 | 26% |
| Error-handling table | 3/50 | 6% |
| Persona (YAML or behavioral header) | 1/50 | 2% |

**The community ships a lot of skills that don't follow most of the rubric.** Even with conservative heuristics under-detecting some patterns by ~20%, only error-handling tables and YAML anti-triggers might clear 50%.

This is not a failure of the rubric; it's a finding about the rubric. The rubric is **descriptive of best practice, not of average practice.** Skills can be useful without scoring well — the rubric describes what's load-bearing for the most reliable, highest-quality skills, not what's required for a skill to function.

### Most-respected principles (deep 10-skill sub-sample)

| Rank | Principle | A-rate |
|---|---|---:|
| 1 | Context scope | 10/10 |
| 2 | Output spec / Output-first | 8/10 |
| 3 | Description as router | 7/10 |
| 4 | Progress markers | 7/10 |
| 5 | Autonomy | 7/10 |
| 6 | Path resolution | 6/10 |

### Most-violated principles (deep 10-skill sub-sample)

| Rank | Principle | C-or-worse rate |
|---|---|---:|
| 1 | Composition | 9/10 |
| 2 | State | 8/10 |
| 3 | Errors (table form) | 7/10 |
| 4 | Human gate | 7/10 |
| 5 | Exit = question | 7/10 |
| 6 | Gates with all 3 parts | 6/10 |
| 7 | Personas | 7/10 |

Most violations cluster in principles that are genuinely hard or that only matter for specific archetypes. State and Composition, for example, are violated in most skills — but most skills don't need state or composition. The applicability matrix in [`principles.md`](./principles.md) reflects this.

---

## The biggest finding: skill archetypes are real

The single most valuable disconfirmation from the corpus survey: **the original rubric assumed one archetype. The community produces at least three.**

### Archetype distribution (v0.1 N=50 vs v0.2 N=80)

| Archetype | v0.1 N=50 | v0.2 N=80 | Examples |
|---|---:|---:|---|
| Procedural | 76% | **60%** | obra/TDD, tob/agentic-actions-auditor, anthropic/skill-creator, AgriciDaniel/cybersecurity |
| Reference | 12% | **20%** | expo-deployment, kdense-biopython, chrisvoncsefalvay-d3, conorbronsdon/avoid-ai-writing, agamm/owasp |
| Creative | 6% | **11%** | anthropic-canvas-design, anthropic-frontend-design, glebis/tufte-report, glacierphonk/naming, zarazhangrui/frontend-slides |
| Hybrid | 6% | **9%** | various, including daymade/deep-research, glebis/jtbd, tasteray/elicitation |

**The v0.1 76% Procedural number was partly a sourcing artifact.** v0.2's diverse-author extension (30 new skills, 18 new authors) shifted the distribution meaningfully — the actual community ecosystem is closer to **60% Procedural / 20% Reference / 11% Creative / 9% Hybrid**. This is a real finding: rubric-design must accommodate Reference skills more carefully than v0.1 implied (one in five community skills, not one in eight).

Reference skills are *not* failed procedural skills. They're library/API documentation reformatted as SKILL.md, and they appropriately lack gates and exits. Creative skills lean on output spec and voice rather than procedural discipline — and that's correct for the domain.

Treating all skills as procedural would have penalized ~30% of the corpus for following genuinely sensible patterns (up from ~18% in v0.1's smaller sample). The applicability matrix in [`principles.md`](./principles.md) was added explicitly to fix this; the v0.2 evidence makes the matrix's importance even clearer.

---

## Bottom-up clusters (patterns the rubric still partially misses)

Beyond the 22 promoted principles, six patterns recur across the community corpus that the current rubric only partially captures. These are candidates for v0.2 attention.

### Cluster A — Reference-style skill (n≈6)
Already addressed in v0.1 via the archetype framing. Documented here for completeness.

### Cluster B — "Refusal-as-skill" (n=3)
The skill's primary value is *refusing the wrong action* and *demanding a precondition*. Examples: `emaynard/family-history-planning` ("ABSOLUTELY PROHIBITED: do not perform unsolicited web searches"), `obra/test-driven-development`, `trailofbits/agentic-actions-auditor`. Stronger than generic Phase 0 routing — encodes a hard "do not proceed without X" rule.

**v0.2 question:** Promote this as principle 23 (Refusal Gate)? Or leave it as a sub-pattern of Phase 0?

### Cluster C — "Rationalizations Rejection Table" (n=4 explicit, n≈8 weaker)
Pattern: list the 3-6 ways the AI will try to talk itself out of following the rule. Each rejection has a counter. Examples: `obra/test-driven-development`, `trailofbits/agentic-actions-auditor`. Already partially absorbed into principle 6 (Personas / voice) but worth surfacing as the canonical implementation of behavioral discipline.

### Cluster D — "Aesthetic anti-patterns" (n=3 strong)
Creative skills encoding *what NOT to produce* (purple gradients, Inter font, generic AI aesthetics). Already partially absorbed into principle 11 (Output spec) via the "anti-templates" mention, but could be a standalone principle if more evidence accumulates.

### Cluster E — "Tool-availability fallback chain" (n=4)
Numbered priority list: try tool-A; if not installed, try tool-B; if neither, try fallback-C. Examples: `tapestry/article-extractor`, `anthropic-canvas-design`, `anthropic/skill-creator`. The canonical real-world shape of a 3-part gate.

**v0.2 note:** This is the single most concrete shape of principle 12 (Gates = 3 parts) in the wild. Worth surfacing as the canonical example.

### Cluster F — "Tone-as-instruction" (n=5+)
Imperative voice setting behavior: "**don't hold back**", "**iron law**", "**ABSOLUTELY PROHIBITED**". Functionally a persona, encoded as voice rather than identity. Now absorbed into principle 6 (Personas / voice) and principle 22 (Voice + writing rules).

---

## The 8 deferred gstack candidates — v0.2 verdicts

The remaining 8 candidates from the gstack investigation. v0.2 Stage 3 re-evaluated each against the 30-skill extension corpus (a fresh, diverse community sample). Verdict per candidate based on community-wide sighting rate at N=30 extension:

| Candidate | v0.1 sightings | v0.2 ext sightings (N=30) | v0.3 verdict |
|---|:-:|:-:|:-:|
| **#26 Skills observe themselves and feed prior runs forward** | only `skill-creator` | **6/30 (20%)** | **PROMOTE** |
| **#29 Skills are portable; host is config knob** | partial | **8/30 (27%)** | **PROMOTE** |
| **#30 Skills detect spawn vs interactive and adapt** | weak | **6/30 (20%)** | **PROMOTE** |
| #21 SKILL.md as build artifact | 0 | 3/30 (10%) | Keep deferred (trending) |
| #25 Hard guardrails via hooks, not prose | 0 | 2/30 (7%) | Keep deferred |
| **#22 Composed skills declare which sections parent owns** | partial | **0/30 (0%)** | **CONFIRM gstack-specific** |
| **#24 Dual-voice consensus for verification** | 0 | **0/30 (0%)** | **CONFIRM gstack-specific** |
| **#28 Plan-stage rubric reused at audit time** | partial | **0/30 (0%)** | **CONFIRM gstack-specific** |

**Stage 3's biggest finding:** 3 of 8 deferred candidates show ≥20% community-corpus prevalence — they're real emerging patterns, not gstack-specific. v0.3 should promote them. Specific community evidence:

- **#26 (self-observation)** — appeared in `daymade/deep-research` (V6/V6.1 version tracking suggests skill observes prior outputs and feeds them forward), `glebis/jtbd` (Update Mode reads prior run forward), `glebis/tufte-report` (Session Lessons section), `ryanbbrown/revealjs` (Session Lessons), `AgriciDaniel/cybersecurity` (agent validation step catches failures and feeds forward), `olgasafonova/skill-check` (versioned check IDs).

- **#29 (host-portable)** — 8 sightings across new corpus, mix of positive and negative implementations. Negative cases (hardcoded paths) confirm the principle is widely violated; positive cases (relative paths, allowed-tools restrictions) confirm the pattern is adopted by experienced authors.

- **#30 (spawn-detection)** — appeared in `daymade/deep-research` (P0 capability check + degrade to sequential), `AgriciDaniel/cybersecurity` (orchestrator vs agent distinction with --focus flags), `zarazhangrui/frontend-slides` (Phase 0 mode detection), `conorbronsdon/avoid-ai-writing` (detect/rewrite mode distinction), `wrsmith108/linear` (Linear-specialist subagent vs direct execution), `glacierphonk/naming` (loop-back logic).

**3 candidates confirmed gstack-specific** (0/30 sightings at extension): #22 section-skip composition, #24 dual-voice consensus, #28 plan-rubric-reuse-at-audit-time. These remain interesting architectural patterns but should not be promoted to the universal rubric without evidence of community adoption.

The detailed candidate descriptions follow below.

---

### Original deferred candidate descriptions

(Preserved from v0.1 for reference. Verdicts above incorporate v0.2 Stage 3 evidence.)

### 21 (deferred). SKILL.md as build artifact

**Pattern:** SKILL.md files are template-rendered (`SKILL.md.tmpl` + shared blocks like `{{PREAMBLE}}`, `{{QA_METHODOLOGY}}`) at build time, with `git diff --exit-code` enforced in CI.

**Why deferred:** 0/50 community skills do this. Unique to gstack at scale.

**v0.2 watch:** Does this become a pattern as more skill *systems* (vs. individual skills) are open-sourced?

### 22 (deferred). Composed skills declare which sections parent owns

**Pattern:** When `autoplan` loads `plan-ceo-review/SKILL.md`, it explicitly lists the sections to skip (Preamble, AskUserQuestion Format, Telemetry, etc.) and runs only the methodology body.

**Why deferred:** Partial in `obra/writing-skills` and `tapestry/learn-this`, but neither declares ownership formally. Problem is real, gstack solution is specific.

### 24 (deferred). Dual-voice consensus for verification

**Pattern:** Same plan reviewed by Codex AND a fresh Claude subagent in parallel. Results merged into a 6-row consensus table where DISAGREE → Taste, both AGREE → confirmed.

**Why deferred:** 0/50 community skills implement true dual-voice consensus. `anthropic/skill-creator` has *blind comparison* (similar but not consensus).

### 25 (deferred). Hard guardrails via hooks, not prose

**Pattern:** `careful`, `freeze`, `guard`, `investigate` declare `PreToolUse` hooks pointing to bash scripts. The hook physically blocks Bash/Edit/Write tool calls. The skill's prose informs; the hook enforces.

**Why deferred:** 0/50 community skills use hooks. The community substitutes prose-rules-with-rationale (Cluster C in this file). Different mechanism, similar intent.

### 26 (deferred). Skills observe themselves and feed prior runs forward

**Pattern:** Every skill writes start/end events to `~/.gstack/analytics/`. Future runs `gstack-learnings-search` and inject prior learnings into the preamble.

**Why deferred:** Only `anthropic/skill-creator` has anything similar (iteration history). Otherwise community skills are stateless.

### 28 (deferred). Plan-stage rubric reused at audit time (the "boomerang")

**Pattern:** `plan-design-review` rates each design dimension 0-10 with "what a 10 looks like" before code. After implementation, `design-review` re-scores against the same rubric to detect drift.

**Why deferred:** Partial in `anthropic/skill-creator` (eval rubric persists across iterations). Otherwise rare.

### 29 (deferred). Skills are portable; host is a config knob

**Pattern:** `setup --host codex|opencode|cursor|factory|slate|kiro|hermes|gbrain` rewrites paths and skill prefixes per agent. One skill source, 10 host targets.

**Why deferred:** Several community skills ship in plugin format and work across hosts; principle holds, but the specific *mechanism* (a config knob) is gstack-specific.

### 30 (deferred). Skills detect spawn vs. interactive and adapt

**Pattern:** When OpenClaw spawns a Claude Code session, gstack flips behavior: no `AskUserQuestion`, no upgrade prompts. Skills are cleanly callable from another agent, not just from a human.

**Why deferred:** `obra/dispatching-parallel-agents` and `subagent-driven-development` are aware of subagent context, but don't *self-detect*. Weak corpus support.

---

## Three over-elevated principles (kept with caveats)

The 50-skill survey suggested three principles in the original 20 are over-elevated as universal — they apply more narrowly than implied:

- **#5 Parallel** — only relevant in 2-3/50 skills
- **#13 External storage** — most community skills (which average ~300 lines) don't need it
- **#18 Path resolution** — lower stakes than implied; most skills use relative paths fine

**Resolution for v0.1:** Kept as principles with **caveat language** in their definitions. Each can be marked N/A with one-sentence justification. See [`principles.md`](./principles.md) for the caveat wording.

This avoids destabilizing the principle numbering while honestly acknowledging the corpus evidence.

---

## Limitations stated honestly

This file presents direction-of-evidence, not statistical proof.

- **N=50 community + N=1 gstack** is enough for pattern detection, not generalization.
- **Single scorer** with conservative bias toward "N" / "C" when uncertain. Real prevalence of e.g. exit conditions may be 30-35% rather than the reported 26%.
- **Sampling bias toward visible repos.** Curated lists were the seed; obscure skills under-represented.
- **Author concentration:** 4 authors (Anthropic, obra, ToB, michalparkola) = 66% of the 50-skill corpus. Long tail = 1 each.
- **Heuristic detection** ~80% precision, ~60% recall for some features.
- **Rubric author scoring own rubric** — known weakness. The v0.2 multi-scorer reliability test is designed to address this directly.
- **Date freshness:** All sources accessed 2026-04-25; no commit SHAs pinned.

---

## What v0.2 will resolve

See [`../07-OPEN-QUESTIONS.md`](../07-OPEN-QUESTIONS.md) for the full v0.2 scope. Key empirical questions from this validation:

1. **Multi-scorer reliability** — 3-5 independent scorers grade the same 10 skills. Compute Cohen's kappa per principle. Identify principles with low agreement (likely too vague or overlapping).
2. **Extend community survey to N=100** — does the archetype distribution stabilize? Do the 8 deferred candidates gain additional support?
3. **Promote/reject the deferred candidates** based on N=100 evidence.
4. **Test the rubric's predictive validity** — do skills scoring higher actually produce better outputs when run? This is the head-to-head experiment that converts v0.1 from architectural rubric to outcome-validated rubric.

---

## Sources

- gstack repo: https://github.com/garrytan/gstack (accessed 2026-04-25, SHA `23c4d7b` at writing)
- **v0.1 50-skill corpus full URL list:** [`corpus-50-skills.md`](./corpus-50-skills.md)
- **v0.2 30-skill extension full URL list:** [`corpus-extension-30-skills.md`](./corpus-extension-30-skills.md)
- **v0.2 per-skill /paap-eval scoring data:** [`../05-EVALUATION/corpus-extension-raw-data.md`](../05-EVALUATION/corpus-extension-raw-data.md)
- v0.1 collections: `anthropics/skills`, `obra/superpowers`, `trailofbits/skills`, `michalparkola/tapestry-skills-for-claude-code`, `expo/skills`, `K-Dense-AI/claude-scientific-skills`
- v0.2 extension new authors: `jamesrochabrun`, `daymade`, `glebis`, `agamm`, `AgriciDaniel`, `ryanbbrown`, `zarazhangrui`, `sanjay3290`, `BehiSecc`, `tasteray`, `HeshamFS`, `conorbronsdon`, `coinpaprika`, `wrsmith108`, `olgasafonova`, `product-on-purpose`, `glacierphonk`, `Swiftner`
- Curated discovery lists used: `karanb192/awesome-claude-skills`, `travisvn/awesome-claude-skills`, `ComposioHQ/awesome-claude-skills`, `BehiSecc/awesome-claude-skills` (highest yield for v0.2 extension)
