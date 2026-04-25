# Test 4 — `/idea-to-pr`

> Full orchestration pipeline, 10 composed skills, 2 human gates. The most ambitious of the four tests.

**Overall: A-**

---

## Metadata

- **Generated skill:** `/idea-to-pr` (555 lines + 173-line artifact schemas reference)
- **Model:** Claude Opus 4.6
- **Path:** FULL (4 phases + routing, 2 human gates, 10 composed skills)
- **Composition:** 6 mandatory + 4 conditional skills, all runtime-resolved
- **Generation time:** ~10 minutes (plus iterative fixes for non-existent skill references)
- **Date generated:** 2026-03-30

---

## Process compliance

| Phase | Verdict | Notes |
|---|---|---|
| Pre-Phase (invocation parsing) | Pass | Detected 14 skill names from conversation. Set EXPLICITLY_REQUESTED. |
| Phase 0 (classification) | Pass | FULL PATH. 5 phases, 2 human gates, state, 10+ compositions. |
| Phase 1 (elicitation) | Pass | Pre-answered from extensive conversation (idea description, failure modes, output spec). |
| Phase 1.5 (skills discovery) | Pass | Resolved 10 skills. Found 2 not installed (`/cso`, `/plan-design-review`). Handled gracefully. |
| Phase 2 (architecture) | Pass | Full spec presented. User approved with modifications (removed two skills). |
| Phase 3 (generation) | Pass | 555 lines + 173 reference. Saved + symlinked. |
| Phase 4 (self-critique) | Pass (lenient) | Used external core-reviewer. Found 1 issue (missing tools field), fixed it. Missed deeper issues. |

**Process note:** This was the most interactive `meta-paap` run. The user pushed back on over-engineering (original 6-skill + 19-composed design → collapsed to 1 skill + 10 composed). Two non-existent skills were referenced and had to be removed post-generation. This validates the pattern: `meta-paap` generates, user iterates, bugs get caught in conversation.

---

## 20-principle scoring

| # | Principle | Grade | Notes |
|---|---|---|---|
| 1 | Description as router | A | Multi-line YAML, 3 anti-triggers, `tools` field, 10 `composed_skills` with phase + purpose metadata. |
| 2 | Route before work | B+ | Phase 0 routes NEW/RESUME/SKIP-SPEC. But no "is this the right tool?" validation. Goes straight to slug generation without checking if the request is actually a feature idea (vs. bug fix, refactoring). |
| 3 | Modes | A (skip) | Single mode. Correct: you always want the full pipeline for idea-to-PR. |
| 4 | State | A | `meta.json` with all fields. Updated after every phase. Resume protocol with phase-specific artifact re-injection. |
| 5 | Parallel | A (skip) | No direct parallel. `/review-plan` handles its own agents internally. Quality chain is correctly sequential (each skill sees fixes from previous). |
| 6 | Personas | N/A | No direct agent personas. Composed skills bring their own. |
| 7 | Files = bus | A | Clean artifact chain: SPEC.md → OBSERVE.md → PLAN-vN.md → PLAN-final.md → REVIEW.md. All in `.claude/runs/{slug}/`. `meta.json` as state bus. |
| 8 | Synthesis | N/A | No direct parallel burst. |
| 9 | Human gate | A | 2 gates: spec confirmation (Phase 1), plan approval (Phase 3). Both loop until confirmed. Phase 3 has 3 options (approve, revise, reject to DESCRIBE). |
| 10 | Exit = question | B+ | Phases 1-4 have binary questions. Phase 0 has no explicit exit condition, just finishes routing. |
| 11 | Output spec | A | PR description template with 6 sections. 5 artifact schemas in external file. SPEC.md template is excellent: "NOT 'improve X' — instead 'when user does Y, system responds with Z'". |
| 12 | Gates = 3 parts | A | 6 gates, all complete. Gates 4-6 have "max N cycles → STOP and ask user" pattern. |
| 13 | External storage | A | `references/artifact-schemas.md` (173 lines). Fallback to inline format guidance. |
| 14 | Context scope | A | Each phase states which artifacts to read. Resume protocol scopes artifact re-injection per phase. |
| 15 | Progress | A | Print after every phase with key stats. Final completion block with PR URL, skills invoked, quality chain results. |
| 16 | Errors | A+ | 10-row table. Covers GitNexus, missing skills, test failures, critical review issues, spec/plan rejection, branch conflicts, merge conflicts, context window pressure, `/ship` failure. Most comprehensive of any test. |
| 17 | Autonomy | A | Autonomous except at 2 human gates. Only stops for errors requiring human decision. |
| 18 | Path resolution | A | Three-tier: PRIMARY → FALLBACK → SEARCH. No hardcoded absolutes. "If not found: skip, note in progress." |
| 19 | Composition | A+ | 10 skills. 6 mandatory + 4 conditional. Conditional routing based on spec content analysis. Runtime resolution for all. Most complex composition of any test. |
| 20 | Output-first | A | PR is the final output. Artifact chain leads to PR. Schemas specified before phases. |

**Principles score:** 14 A (including 2 A+), 2 B+, 4 N/A or skip = **A-**.

---

## Key strengths (most complex generated skill)

1. **Composition at scale.** 10 skills composed with runtime resolution, conditional activation, and graceful degradation. `composed_skills` YAML metadata gives a complete dependency graph at a glance.

2. **Artifact schemas as a separate reference.** SPEC.md, OBSERVE.md, PLAN-vN.md, REVIEW.md, `meta.json` all have exact templates. The SPEC.md template ("NOT 'improve X' — instead 'when user does Y, system responds with Z'") prevents the #1 failure mode of vague specs.

3. **Conditional skill routing based on content analysis.** Detects auth/PII → `/cso`, big scope → `/plan-eng-review`, backend changes → `/backend-docs-writer`. Auto-detection from spec, not manual flags.

4. **Error handling is the most comprehensive of any test.** 10 rows. Context window pressure handling ("Re-inject only current phase artifacts, summarize OBSERVE.md if too large") shows awareness of real operational constraints.

5. **Plan versioning.** PLAN-v1 → v2 (GitNexus) → v3 (review fixes) → PLAN-final. Each version is a traceable artifact. The user can diff versions to see how the plan evolved.

---

## Key weaknesses (risk-ranked)

1. **`git add -A` in the fallback PR creation — HIGH safety risk.** Line 493 falls back to `git add -A && git commit`. Project conventions explicitly say "prefer adding specific files by name rather than `git add -A` which can accidentally include sensitive files (`.env`, credentials) or large binaries." Should list files from PLAN-final.md instead.

2. **Phase 0 missing "is this the right tool?" validation — MEDIUM risk.** Goes straight to slug generation. If someone types `/idea-to-pr fix the login button` (a bug fix, not a feature), it would proceed instead of redirecting to a direct fix.

3. **Quality chain justification missing — LOW risk.** The sequential quality chain (`/code-quality` → `/code-comments` → `/solid-principles`) is correct (each sees fixes from previous) but the skill doesn't state WHY sequential. A reader might question why they're not parallel.

4. **Non-existent skills referenced in initial generation — process issue.** `/plan-design-review` and `/plan-ceo-review` were referenced but don't exist. Caught by the user post-generation, not by the self-critique. Self-critique checked for "composition paths no hardcoded absolutes" but not "do the named skills actually exist."

5. **Self-critique too lenient (again).** Found only 1 issue (missing `tools` field). Missed: `git add -A` safety violation, missing Phase 0 validation, non-existent skill references, sequential quality chain justification. Pattern persists across all 4 tests; see [`regression.md`](./regression.md).

---

## What this test stressed

This was the first stress test of:

- **Composition at orchestration scale** — 10 composed skills with conditional routing
- **Two human gates with looping recovery** — both spec confirmation and plan approval can iterate
- **Artifact schemas as separate reference** — 5 templates in an external file
- **Plan versioning** — explicit version progression preserved as separate files
- **Context window pressure handling** — explicit guidance for long-running orchestration

Verdict: The most ambitious skill `meta-paap` produced. The architecture is appropriately complex — composition correctly scales with workflow demands. Three new failure modes surfaced that smaller tests didn't reveal: (a) safety-rule violations against project conventions, (b) named-reference validation, (c) the cost of context-window pressure on long pipelines. All three become priority fixes for `meta-paap` v2.

---

## Cross-references

- [`methodology.md`](./methodology.md) — Scoring protocol
- [`regression.md`](./regression.md) — How this test compares across the n=4 set
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — Principle definitions; this skill's `composed_skills` metadata is the canonical example for #19
