# Test 2 — `/article-forge`

> Linear pipeline, knowledge processing, 3 composed skills. The first composition test.

**Overall: A-**

---

## Metadata

- **Generated skill:** `/article-forge` (350 lines)
- **Model:** Claude Opus 4.6
- **Path:** FULL (5 sequential phases, no agents)
- **Composition:** 3 skills (`/defuddle`, `/obsidian-markdown`, `/humanizer`)
- **Generation time:** ~4 minutes
- **Date generated:** 2026-03-28

---

## Process compliance

| Phase | Verdict | Notes |
|---|---|---|
| Pre-Phase (invocation parsing) | Pass | Detected 3 skill names from conversation. Set EXPLICITLY_REQUESTED. |
| Phase 0 (classification) | Pass | Correctly identified FULL PATH (enough phases for full architecture). |
| Phase 1 (elicitation) | Pass | Pre-answered from detailed user description. Skipped AskUserQuestion. |
| Phase 1.5 (skills discovery) | Pass | Resolved all 3 composed skills. Read their SKILL.md files for context. |
| Phase 2 (architecture) | Pass | Full spec. Composition properly documented. Category detection designed. |
| Phase 3 (generation) | Pass | 350 lines. Saved to skills folder. Symlinked. |
| Phase 4 (self-critique) | Pass (lenient) | All checks passed. Didn't flag the hardcoded vault path primary. |

---

## 20-principle scoring

| # | Principle | Grade | Notes |
|---|---|---|---|
| 1 | Description as router | A | Multi-line YAML. 3 anti-triggers. `composed_skills` metadata in header (new pattern). |
| 2 | Route before work | A | Phase 0 routes URL/PASTE/BOTH/NEITHER. Clean decision tree. |
| 3 | Modes | A (skip) | Single mode justified: always full processing. Correct. |
| 4 | State | A (skip) | Justified: short runs, no resume needed. |
| 5 | Parallel | N/A | No parallel phases. Linear pipeline. Correct design. |
| 6 | Personas | N/A | No agents. |
| 7 | Files = bus | A | 01-raw.md → 02-reflection.md → 03-applications.md. Sequential chain. |
| 8 | Synthesis | N/A | No parallel work. |
| 9 | Human gate | N/A | No mid-process judgment needed. User reviews output. |
| 10 | Exit = question | A | All 5 phases. Binary. Specific. Phase 2 is best phrased. |
| 11 | Output spec | A+ | Per-section requirements: "8-10 bullets each containing a concrete claim." Honest about when to omit. |
| 12 | Gates = 3 parts | A | 4 gates. Gate 2 is granular: rewrites failing section, not whole file. Gate 3: "If you can't name one, remove the application." Honest. |
| 13 | External storage | A | 350 lines. Appropriate. No need for external files. |
| 14 | Context scope | N/A | No agents. |
| 15 | Progress | A | Status after each phase with stats. |
| 16 | Errors | A | 6-row table. Escalation chain: defuddle → WebFetch → paste. "Heavy AI-slop" row. |
| 17 | Autonomy | A | Category auto-detection. Only asks when genuinely ambiguous. |
| 18 | Path resolution | B+ | Vault path primary is hardcoded to user's machine. Fallback is portable. Acceptable for personal skill but violates the principle. |
| 19 | Composition | A | 3 skills composed. Paths resolved at runtime with fallbacks. `composed_skills` metadata in header. |
| 20 | Output-first | A | All 3 files specified first. Phases are the path. |

**Principles score:** 13 A (including 1 A+), 1 B+, 6 N/A (correct design for linear pipeline) = **A-**.

---

## Key strengths (improvements over Test 1)

1. **Output spec is more detailed per section.** "8-10 bullets each with a concrete claim" is specific enough to evaluate. This is better than Test 1's column-level specs.
2. **Quality gates are more granular.** "Rewrite the failing section, not the whole file." "If you can't name one, remove the application."
3. **Skill composition properly implemented.** 3 skills with runtime path resolution and fallbacks.
4. **`composed_skills` YAML metadata.** New pattern not in the architecture checklist. Useful for discoverability — became the recommended pattern for principle #19 in [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md).
5. **Honest output spec.** "Skip this section entirely if all terms are common knowledge." "If nothing applies to current work: write 'No direct application' — do not force it." This prevents model bloat and became the canonical example for principle #11 in the rubric.

---

## Key weaknesses (risk-ranked)

1. **Hardcoded vault path primary — MEDIUM risk** (B+ on portability). Personal skill, so acceptable in this context, but the self-critique should have flagged it. Skill won't run on someone else's machine without modification.
2. **No validation that composed skills return useful output — MEDIUM risk.** "If `defuddle` fails, try WebFetch" is good, but no check for "`defuddle` returns garbage."
3. **Category auto-detection has no confidence threshold — MEDIUM risk.** "Clearly fits" is subjective. Edge cases will be miscategorized.
4. **`humanizer` check duplicated inline — LOW risk.** Could be a shared step reference. Not a bug, just DRY.
5. **Self-critique again too lenient — process issue.** Didn't flag the hardcoded path. Pattern that recurs across all 4 tests; see [`regression.md`](./regression.md).

---

## What this test stressed

This was the first stress test of:

- **Skill composition** — multiple composed skills, each with a defined phase and output
- **Linear pipeline architecture** — no parallel agents, simple sequential chain
- **Auto-detection logic** — content-based routing without explicit user mode selection

Verdict: composition mechanics are solid. Linear pipeline is correctly identified as the right architecture (the generator didn't over-engineer with unnecessary parallelism). The auto-detection is the weak link — needs confidence thresholds to be production-safe.

---

## Cross-references

- [`methodology.md`](./methodology.md) — Scoring protocol
- [`regression.md`](./regression.md) — How this test compares across the n=4 set
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — Principle definitions; this skill's output spec is the canonical example for #11
