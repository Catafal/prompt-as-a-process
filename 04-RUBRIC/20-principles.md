# The 20 Principles

> The architectural rubric for evaluating a SKILL.md. Each principle: definition, why it matters, anti-pattern, and a concrete example.

**Status:** Skeleton — full content lands in Phase 3. The principles are currently referenced by number across the four `meta-paap` evaluations in [`05-EVALUATION/`](../05-EVALUATION/) but not yet defined in one place. This file becomes the canonical reference.

---

## Format for each principle

```
## N. Principle name

**Definition:** [One-sentence statement of what this asserts]

**Why it matters:** [Failure mode it prevents, or quality it enables]

**Anti-pattern:** [The common mistake / what NOT to do]

**Concrete example:** [Pulled from a real skill — pre-call, deep-research, meta-paap, or community survey]

**Related principles:** [Cross-references to other numbered principles]
```

---

## The 20 principles (full list, definitions in Phase 3)

1. **Description as router** — the YAML description is routing logic, not metadata
2. **Route before work** — Phase 0 decides path before any execution
3. **Modes** — explicit alternative paths (auto/manual, quick/full) where they apply
4. **State** — persistent state for runs that need resume, justified skips otherwise
5. **Parallel** — explicit invocation rules ("single message; do NOT launch sequentially")
6. **Personas** — behavioral, not just role-scoped, when agents are used
7. **Files = bus** — numbered file convention as the inter-phase data bus
8. **Synthesis** — explicit priority rules + conflict resolution where parallel work merges
9. **Human gate** — explicit checkpoint design where human judgment is required
10. **Exit = question** — phase exit conditions phrased as binary, answerable questions
11. **Output spec** — format, sections, length, per-section content rules
12. **Gates = 3 parts** — every quality gate has check + failure condition + recovery path
13. **External storage** — agent prompts and references in separate files when SKILL.md exceeds 400 lines
14. **Context scope** — explicit per-agent scoping with stated reasoning
15. **Progress** — status reporting after each phase with key stats
16. **Errors** — error-handling table mapping specific error → specific action
17. **Autonomy** — sensible defaults, mode inference, manual as safe fallback
18. **Path resolution** — runtime resolution with fallbacks; no hardcoded absolute paths
19. **Composition** — composed skills resolved at runtime with fallbacks; metadata in YAML
20. **Output-first** — output spec defined before phases; phases are the path to it

---

## Why 20 (and not 12 or 30)

Brief justification: these are the patterns that distinguished A-grade skills from B-grade skills across n=4 evaluations of `meta-paap`-generated skills, plus the structural patterns observed in mature hand-written skills (`/deep-research`, `/blog-factory`). Some are universal (1, 2, 11, 12). Some apply only when relevant (4, 6, 8, 19). The rubric explicitly accommodates "N/A — justified skip" for principles that don't apply to a given skill's design.

(Full discussion in Phase 3.)

---

## Cross-references

- [`../05-EVALUATION/`](../05-EVALUATION/) — the n=4 regression study where principles are referenced by number
- [`../06-META-PAAP/SKILL.md`](../06-META-PAAP/SKILL.md) — the skill that operationalizes these principles in a checklist
- Reference skills cited in worked examples: `/deep-research`, `/blog-factory`, `/review-plan`, `/idea-to-pr`

---

*Populated in Phase 3.*
