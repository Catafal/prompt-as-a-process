# Cross-Test Regression Analysis (n=4)

> What patterns hold across all four `meta-paap` evaluations. The systematic strengths, the systematic weaknesses, and what an honest summary should say.

**Status:** Skeleton — full content migrated from the original n=4 regression study (the "Cross-Test Regression" section) in Phase 3.

---

## Outline

### Summary table — all 4 tests

| Test | Workflow | Lines | Composition | Overall grade |
|---|---|---|---|---|
| 1 | `/skill-audit` (parallel agents, scoring) | 567 | standalone | B+ |
| 2 | `/article-forge` (linear pipeline, composition) | 350 | 3 skills | A- |
| 3 | `/review-plan` (dual-mode, personas) | 508 + 326 | 2 skills | A- / A |
| 4 | `/idea-to-pr` (orchestration, 10 skills) | 555 + 173 | 10 skills | A- |

**Aggregate: mean A-, range B+ to A.**

### Consistently strong (4/4 tests)

(Pull table from regression doc — exit conditions, quality gates, anti-triggers, error handling, progress reporting, Phase 0 routing, output spec.)

### Consistently weak (4/4 tests)

(Pull from regression doc — self-critique too lenient, in 4/4 cases.)

The systematic weakness:
> Self-critique validates structure but never (a) traces execution paths, (b) validates named references exist, (c) checks against project safety rules.

### Improving across tests

(Pull from regression doc — error handling rows count, composition sophistication, state management, external references, artifact schemas.)

### What this means

- `meta-paap` produces 80-90% of a production skill on first run
- The architecture is consistently right
- The remaining 10-20% falls into 3 categories:
  1. Self-critique misses (safety violations, non-existent references)
  2. Execution-path inconsistencies between phases
  3. Under-specified implementation for the hardest technical step
- One iteration fixes all three

### What `meta-paap` could fix in v2 (carries to v0.2 of this repo)

1. **Execution trace pass** in self-critique: follow data from Phase 1 output through every downstream reference
2. **Reference validation**: verify every named skill/file actually exists at the resolved path
3. **Safety audit**: read `CLAUDE.md` and check generated skill for violations

These are concrete, actionable improvements. They're worth their own evaluation cycle (becomes part of v0.2 regression).

---

## Per-test details

- [Test 1 — `/skill-audit`](./test-1-skill-audit.md)
- [Test 2 — `/article-forge`](./test-2-article-forge.md)
- [Test 3 — `/review-plan`](./test-3-review-plan.md)
- [Test 4 — `/idea-to-pr`](./test-4-idea-to-pr.md)

---

## Cross-references

- [`./methodology.md`](./methodology.md) — how these tests were designed and scored
- Per-test detail: [test 1](./test-1-skill-audit.md), [test 2](./test-2-article-forge.md), [test 3](./test-3-review-plan.md), [test 4](./test-4-idea-to-pr.md)

---

*Populated in Phase 3.*
