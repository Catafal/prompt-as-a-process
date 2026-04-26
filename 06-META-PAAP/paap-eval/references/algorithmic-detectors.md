# Algorithmic Detectors — `/paap-eval` Phase 2 Reference

> Per-principle pattern-match detector logic for the ~12 algorithmic principles in the [PaaP rubric](../../../04-RUBRIC/principles.md). Loaded by [`paap-eval/SKILL.md`](../SKILL.md) Phase 2.

**Status:** Placeholder (Stage 1a). Full detector logic added in Stage 1b of v0.2.

---

## Why this file is a placeholder

The [`paap-eval` SKILL.md](../SKILL.md) v0 scaffold (Stage 1a) wires up Phase 2 to read this file at runtime. The scaffold is *runnable* without this file — it falls back to "manual-detection mode" and asks the user to score the algorithmic principles by hand. But that defeats the purpose of automation.

Stage 1b fills in this file with the actual regex/pattern-match logic for each of the ~12 algorithmic principles. Until then, the skill is a coarse scaffold.

---

## What this file will contain (after Stage 1b)

For each of the 12 algorithmic principles, a section with:

- **Principle reference** — name + number from `04-RUBRIC/principles.md`
- **Detector strategy** — what to grep / regex / parse for
- **Grade-mapping rules** — how detector output maps to A+ → F
- **Persona modulation** — how strict-academic / pragmatic-practitioner / charitable-newcomer adjust thresholds
- **Evidence format** — how to extract line references for the report
- **Known limitations** — what the detector misses (the spirit-vs-letter gap)

The 12 algorithmic principles in scope:

1. #1 Description as router
2. #2 Route before work
3. #4 State
4. #5 Parallel
5. #7 Files = bus
6. #9 Human gate
7. #10 Exit = question
8. #12 Gates = 3 parts
9. #13 External storage
10. #16 Errors
11. #18 Path resolution
12. #19 Composition

---

## Cross-references

- [`../SKILL.md`](../SKILL.md) — The skill that loads this file
- [`../genesis.md`](../genesis.md) — Architecture spec listing all 12 principles
- [`../../../04-RUBRIC/principles.md`](../../../04-RUBRIC/principles.md) — Principle definitions
- [`../../../07-OPEN-QUESTIONS.md`](../../../07-OPEN-QUESTIONS.md) — v0.2 plan including Stage 1b
