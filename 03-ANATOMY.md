# 03 — Anatomy

> How to write a SKILL.md that actually runs. The canonical authoring guide.

**Status:** Skeleton — full content lands in Phase 3, merging Articles 2 (Anatomy) and 3 (Worked Example) of the original PaaP series into one canonical authoring guide.

---

## Outline

### Part 1 — The mental model

- Models interpret instructions **literally at structure points** and **creatively at content points**
- Be explicit about the former, leave room for the latter
- Most first SOPs get this backwards: vague at structure, prescriptive at content. Flip that.

### Part 2 — The two parts of a SKILL.md

**A. YAML header — routing logic, not metadata**
- `name`: the slash command
- `description`: triggers, anti-triggers, alternative pointers
- The `description` is the model's deciding read before invocation
- Anti-triggers stop a 600-line pipeline from loading on a 2-sentence query
- (Optional) `tools`, `composed_skills`, other metadata

**B. Markdown body — the process**
- Phases with explicit exit conditions
- Decision branches at every fork
- Quality gates that trigger loops, not just checks
- Output spec that leaves nothing to interpretation

### Part 3 — The four required components

1. **Phases with explicit exit conditions**
   - Bad: "Research phase"
   - Good: "Retrieve: run parallel searches across these 5 angles. Exit when you have 15+ sources."
   - The exit condition is what makes it a phase rather than a vague instruction

2. **Decision branches at every fork**
   - The model invents missing branches
   - Write them out: "If fewer than 5 sources found, expand search to adjacent topics before continuing"
   - Phase 0 routing is the most important — sets the path before any work

3. **Quality gates with all three parts**
   - Check
   - Failure condition
   - Recovery path (where to loop back)
   - Without recovery path: model invents next step, polished-looking failures

4. **Output spec**
   - Format, sections, file location, length
   - Per-section content rules ("8-10 bullets each containing a concrete claim")
   - Honest omission rules ("Skip this section entirely if all terms are common knowledge")

### Part 4 — Worked example: `pre-call`

A concrete fill-in of the template for "research a person before a call." (Lives in [`examples/pre-call/SKILL.md`](./examples/pre-call/SKILL.md), referenced here.)

Walks through:
- Why each section is worded the way it is
- Anti-trigger that prevents over-invocation ("Do NOT use for people you already know")
- Exit conditions phrased as **questions, not statements**
- Quality gate with explicit recovery path
- One unstated dependency (web search must be enabled)

### Part 5 — Where most people underwrite

- **Description as routing logic** (most people treat as project description)
- **Exit conditions as tests, not statements** (most people write "exit when complete")
- **Recovery paths in quality gates** (most people skip this)
- All three are required for a working skill

### Part 6 — Iteration

- Write the 80-line version first, not the 600-line version
- Each version fixes one observed failure mode
- Read the execution, find the phase that drifted, add the missing gate or branch
- The first version's job is just to close the loop once

### Part 7 — A minimal starting template

(Reproduce the template from `examples/` so the chapter is self-contained.)

---

## Cross-references

- [`04-RUBRIC/20-principles.md`](./04-RUBRIC/20-principles.md) — each anatomy element maps to one or more principles
- [`examples/pre-call/SKILL.md`](./examples/pre-call/SKILL.md) — the runnable worked-example artifact

---

*Populated in Phase 3.*
