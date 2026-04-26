# 07 — Open Questions

> What v0.2 and v1.0 will tackle, and where contributions are most useful right now.

**Status as of 2026-04-26:** v0.2 work has begun. The plan below is the active execution plan, not aspirational.

---

## v0.2 — the unifying primitive: `/paap-eval`

The single insight that shapes the v0.2 plan: **the four academic blockers v0.1 leaves open all become tractable once a single new primitive exists** — an evaluation skill that auto-scores any SKILL.md against the rubric.

| v0.1 blocker | Without `/paap-eval` | With `/paap-eval` |
|---|---|---|
| Multi-scorer kappa reliability | Recruit 3-5 humans, weeks of coordination | 3 prompt-variants of the same skill, 30 minutes |
| N=100 corpus extension | 100 × ~30 min manual scoring = 50 hours | 100 evaluations in parallel, ~1 hour |
| Head-to-head outcome experiment | Score 50 outputs by hand | Score 50 outputs via the eval skill + blind preference rating |
| Re-scoring the n=4 against rubric v0.2 | Manual re-do | Re-run automatically |

`/paap-eval` is therefore the v0.2 cornerstone. Build it first; everything else is downstream.

### `/paap-eval` design spec

**Name:** `/paap-eval` (matches `meta-paap` namespace; signals scoring against PaaP rubric specifically).

**Inputs:** A path to a SKILL.md file, plus optional flags for archetype hint and scoring strictness.

**Outputs:** A scored evaluation file (using the existing [`scoring-template.md`](./04-RUBRIC/scoring-template.md) format), plus a confidence-per-principle annotation, plus a "what I was uncertain about" section.

**Phase structure (drafted; subject to Stage 1 elicitation):**

1. **Pre-Phase — Input validation.** Is the input a SKILL.md? If not, stop with explanation.
2. **Phase 1 — Archetype detection + confirmation.** Auto-classify Procedural / Reference / Creative / Hybrid. If confidence < threshold, ask user.
3. **Phase 2 — Algorithmic auto-score.** Pattern-match the ~12 principles that can be (anti-triggers in YAML, exit conditions formatted as questions, gates with 3 parts in detectable structure, error tables, line count, hardcoded paths, composed_skills metadata).
4. **Phase 3 — Semantic LLM-judge.** Per-principle judge prompts for the ~10 semantic principles (output spec quality, persona depth, context-scope reasoning, voice rules). Each scoring includes a confidence rating and an "I'm uncertain because..." escape.
5. **Phase 4 — Synthesis + honest report.** Aggregate per-principle grades, mark N/A for archetype-skipped principles with stated justification, surface low-confidence scores for human review.
6. **Phase 5 — Self-disclosure.** Always frame as "first-pass evaluation following PaaP rubric v0.X" with explicit caveats. Never as "objective grade."

**Four traps to avoid (from first-principles analysis):**

1. **Pretending it's objective.** It's an LLM-judge. Frame as "structured first-pass evaluation," not "objective scoring."
2. **Trying to score everything algorithmically.** Some principles need judgment. The skill should auto-score the algorithmic ones, LLM-judge the semantic ones, and **defer to user** for the irreducibly subjective ones.
3. **Skipping the archetype gate.** Score Procedural-only principles on a Reference skill = punishing legitimate non-procedural artifacts. Archetype declaration is mandatory before scoring.
4. **Becoming the truth.** Self-disclose loudly. Never let `/paap-eval`'s output be cited as definitive.

---

## v0.2 build plan — six stages, ordered by dependency

| Stage | Output | Time | Blocked by |
|---|---|---|---|
| **0** | This document (you're reading it) — v0.2 plan public | Done | — |
| **1** | `/paap-eval` skill exists at `06-META-PAAP/paap-eval/SKILL.md` | 4-6 hrs (3 sub-sessions) | Stage 0 |
| **2** | Kappa pilot results in `05-EVALUATION/kappa-pilot.md` | 2-3 hrs | Stage 1 |
| **3** | N=100 corpus + 8 deferred candidates re-evaluated | 3-4 hrs | Stage 1 |
| **4** | Head-to-head outcome experiment | 4-6 hrs (2 sub-sessions) | Stage 1 |
| **5** | v0.2 release (CITATION bump, CHANGELOG, re-audit, push) | 1-2 hrs | Stages 1-4 |

**Total:** ~15-22 hrs across 7-9 sessions. Pacing rule: no session > 3 hrs.

### Stage 1 — Build `/paap-eval` (sub-stages)

- **1a — Scaffold.** Run `meta-paap` to generate the v0 skeleton from the design spec above.
- **1b — Algorithmic detectors.** Pattern-match logic for ~12 auto-detectable principles.
- **1c — Semantic judge prompts.** Per-principle LLM prompts for ~10 semantic principles.
- **1d — Validation.** Run against the 4 existing manual evaluations; investigate divergences.

### Stage 2 — Kappa pilot

- Pick 10 reference skills from the corpus, stratified.
- Create 3 scorer-persona variants of `/paap-eval`: **strict-academic**, **pragmatic-practitioner**, **charitable-newcomer**.
- Run 3 × 10 = 30 evaluations in parallel.
- Compute Cohen's kappa per principle.
- Principles with kappa < 0.6 → propose rewording or merger.

### Stage 3 — Extend corpus to N=100

- Add 50 more skills, weighted toward under-represented categories: long-tail individual practitioners, non-Procedural archetypes, non-English authors, non-Claude-Code hosts.
- Run `/paap-eval` against all 100 (parallel).
- Re-evaluate the 8 deferred gstack candidates (below) with new evidence.
- Update [`04-RUBRIC/empirical-validation.md`](./04-RUBRIC/empirical-validation.md).

### Stage 4 — Head-to-head outcome experiment

- Pick 5 workflows spanning the 3 archetypes.
- Author each twice: hand-written + via `meta-paap` (10 skills total).
- Define a task battery per workflow (3-5 inputs each).
- Run 50 outputs in parallel.
- Blind-score by `/paap-eval` (structural rubric) + blind preference rating by Sir (output quality).
- Quantify: meta-paap match rate, hand-written advantage axes, authoring-time delta.

### Stage 5 — v0.2 release

- Bump `CITATION.cff` to 0.2.0.
- Add `CHANGELOG.md` documenting v0.1 → v0.2 deltas.
- Update [`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md) with kappa-driven revisions.
- Re-run [`04-RUBRIC/reflexive-self-audit.md`](./04-RUBRIC/reflexive-self-audit.md) against the v0.2 repo.
- Tag and push.

---

## Items to resolve during v0.2 (downstream of `/paap-eval`)

These are the v0.1 open questions that v0.2's stages will answer.

### The 8 deferred gstack candidates

Eight patterns from gstack didn't clear the v0.1 promotion bar against the 50-skill community survey. v0.2's N=100 extension (Stage 3) re-evaluates each:

- SKILL.md as build artifact (template-rendered, CI-enforced)
- Composed skills declare which sections parent owns (section-skip-list composition)
- Dual-voice consensus for verification
- Hard guardrails via hooks, not prose
- Skills observe themselves and feed prior runs forward
- Plan-stage rubric reused at audit time
- Skills are portable; host is a config knob
- Skills detect spawn vs. interactive and adapt

See [`04-RUBRIC/empirical-validation.md`](./04-RUBRIC/empirical-validation.md) for current evidence.

### The 6 bottom-up clusters

The community survey found 6 patterns the rubric only partially captures. v0.2 (after the kappa pilot in Stage 2) decides which (if any) become explicit principles:

1. **Refusal-as-skill** (currently absorbed into #2 Phase 0 routing) — promote to its own principle?
2. **Rationalizations Rejection Table** (currently in #6 Personas, #22 Voice rules) — surface as canonical pattern?
3. **Aesthetic anti-patterns** (currently in #11 Output spec) — own principle for creative skills?
4. **Tool-availability fallback chain** (currently in #12 Gates 3 parts) — surface as canonical example?
5. **Tone-as-instruction** (currently in #6 Personas, #22 Voice rules) — same as #6 or distinct?
6. **Reference-style skill archetype** — addressed in v0.1 via the archetype framing.

### `meta-paap` v2 self-critique improvements

The 4/4 systematic weakness from the [n=4 regression study](./05-EVALUATION/regression.md) becomes a separate v0.3 work item once `/paap-eval` exists (since `/paap-eval` is the natural place to trace execution paths and validate references):

- Add an **execution-trace pass** — data flow from Phase N output → Phase N+1 references
- Add a **reference-validation pass** — do named skills/files actually exist at resolved paths?
- Add a **safety-audit pass** — read project `CLAUDE.md`, check generated skill against it

Re-run the n=4 evaluation to verify the weaknesses closed. Deferred to v0.3.

---

## v1.0 (conditional on v0.2 evidence)

If v0.2 ships with multi-scorer kappa data, head-to-head outcome experiments, and N≥100 corpus extension, the natural next step is conversion to a workshop-paper-format submission. Likely venues: workshops at NeurIPS / ICLR / ACL on agent evaluation, prompting, or developer tools.

This is **conditional, not promised.** v0.1 is explicitly not paper-ready by current academic standards — single-scorer rubric work plus n=4 convenience-sampled evaluation does not clear a workshop bar. Whether the v0.2 work justifies the paper conversion will be obvious from the v0.2 data; if it doesn't, the repo stays as a maintained framework artifact and that is fine.

Citable via [`CITATION.cff`](./CITATION.cff) in the meantime.

---

## Where contributions help most (right now, v0.1)

### High value
1. **Score one of your skills** against the 22 principles using [`04-RUBRIC/scoring-template.md`](./04-RUBRIC/scoring-template.md). Submit as a PR adding a file under `05-EVALUATION/community/`.
2. **Argue for adding/removing/rewording a principle** with concrete evidence from a real skill. Open an issue tagged `[principle]`.
3. **Propose new test workflows** that stress-test the rubric in ways the current 4 don't — particularly skills in archetypes other than Procedural.
4. **Score gstack skills against the rubric** — gstack is already a confirmed exemplar at the corpus level; per-skill scoring against the 22 principles would be a major contribution.

### Medium value
5. **Bug reports on `examples/pre-call/`** if it fails to run as documented (e.g., LinkedIn search behavior changes).
6. **Citations the evidence chapter missed** — papers, blog posts, framework documentation.
7. **Tonal sharpening** — flag any AI-slop, vague claims, or inflated symbolism. The repo's credibility depends on this.

### Low value (don't PR these)
- New `meta-paap` features (happens in the source skill repo, not here)
- Tonal rewrites without substantive change
- README overhauls without thesis change
- Self-promotional skill submissions dressed as evaluations

---

## Things v0.1 deliberately doesn't try to answer

- **Whether PaaP scales to multi-tenant SaaS.** It doesn't, and that's fine. The determinism and cost economics are wrong for SaaS. Personal and team-scale tools are the right scope.
- **Whether the 22 principles generalize beyond Claude Code.** Probably yes for Cursor / Codex / OpenClaw — gstack already runs on 10 hosts via setup config. Not yet tested in this repo.
- **Whether `meta-paap` is the optimal generator design.** Almost certainly not — it's a starting point. Better generators will emerge; the rubric is what they should be measured against.
- **Long-term ecosystem dynamics.** Skill marketplaces, monetization, certification, version-pinning conventions. Speculative. Out of scope until empirical evidence accumulates.
- **The "Tan endorses PaaP" question.** He doesn't use the term. Cite gstack as evidence the architecture works; do not cite Tan as PaaP's author.

---

## Citing this work

If you build on the rubric, the methodology, or the empirical findings, cite via [`CITATION.cff`](./CITATION.cff). GitHub renders this into a one-click citation block. When v1.0 ships as a paper, it will get its own DOI.

Rubric citation format: *"PaaP rubric v0.1 (Catafal, 2026)."* Include the version — the rubric will evolve.
