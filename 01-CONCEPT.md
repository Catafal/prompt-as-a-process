# 01 — Concept

> Why Prompt as a Process, why now, what changed.

**Status:** Skeleton — full content lands in Phase 3, drawing from the original PaaP article series (Article 1 — Concept), expanded with Phase 2 landscape findings.

---

## Outline

1. **Three waves of "AI replaces code"**
   - Wave 1: prompt engineering (one-shot)
   - Wave 2: orchestration frameworks (LangChain, LlamaIndex, AutoGen)
   - Wave 3: Prompt as a Process (this)

2. **What changed in mid-2025**
   - Sonnet-class models became reliable enough to follow complex SOPs
   - Sub-agent spawning, quality gate loops, multi-phase state without drift
   - The format was always available; reliability is what unlocked it

3. **What PaaP actually is**
   - YAML header + Markdown body with phases, decision trees, quality gates
   - The artifact is a `.md` file. Runtime is the model. Deploy is dropping the file in a folder.
   - Distinction from prompt engineering: process with branches, not one-shot phrasing
   - Distinction from frameworks: orchestration logic is prose, not code

4. **Where it works**
   - Research pipelines (the strongest case)
   - Editorial pipelines, codebase analysis, structured reporting
   - "Where you'd write a brief for a person, you write a SKILL.md instead"

5. **Where it breaks** (honest, not promotional)
   - Debugging — no stack traces, just wrong output
   - Model updates breaking calibration silently
   - Context-limit ceiling on long processes
   - Determinism gone (use code if you need exact reproducibility)
   - Volume kills the economics (full inference cost per run)

6. **What this means**
   - Iteration speed changes what's worth attempting
   - Personal and team-scale tools is a large space
   - Karpathy autoresearch pattern applied to SOPs → self-improving skills
   - The gap from "manual workflow" to "slash command" went from a code project to an afternoon

---

## Cross-references

- [`02-LANDSCAPE.md`](./02-LANDSCAPE.md) — for framework backlash evidence and the broader ecosystem context
- [`04-RUBRIC/`](./04-RUBRIC/) — for how the structural patterns that "work" formalize as principles

---

*Populated in Phase 3.*
