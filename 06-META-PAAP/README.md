# meta-paap — The skill that generates skills

> A SKILL.md that builds other SKILL.md files. Drop it in your skills folder, type `/meta-paap`, describe what you want to automate, answer five questions, review the architecture, generate.

## What it does

Seven phases:

1. **Pre-Phase — Invocation parsing.** Detects skills you named in your invocation (e.g., "build me a skill that uses `/deep-research`") and pre-confirms them.
2. **Phase 0 — Classification.** Classifies the workflow as single-step (don't build a skill, write a prompt), lean (2-3 linear phases), or full (parallel agents, human gates, state, etc.).
3. **Phase 1 — Elicitation.** Five questions in one message: workflow steps, failure modes, output spec, tool dependencies, frequency + resumability.
4. **Phase 1.5 — Skills discovery.** Scans installed skills and suggests composition candidates relevant to your workflow.
5. **Phase 2 — Architecture design.** Loads the architecture checklist (`references/architecture-checklist.md`), works through each decision point, presents the spec for review BEFORE generating.
6. **Phase 3 — Generation.** Writes the complete SKILL.md following the 22-principle rubric (see [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md)).
7. **Phase 4 — Self-critique.** Red-teams the generated skill against a structural checklist; fixes critical issues before saving.

---

## Performance characteristics (n=4)

Based on the [n=4 regression study](../05-EVALUATION/):

- **Simple workflow** (linear pipeline, ~3 composed skills): ~4 min, ~350 lines
- **Complex workflow** (parallel agents, dual modes, external references): ~10 min, ~500 lines + 300-line reference file
- **Most complex tested** (full orchestration, 10 composed skills, 2 human gates): ~10 min + iterative fixes, 555 lines + 173-line reference
- **Mean grade against the 20 original principles:** A- (range B+ to A)
- **Known systematic weaknesses (4/4 tests):**
  1. Self-critique is too lenient — validates structure but doesn't trace execution paths or check safety rules
  2. The hardest technical phase is the least specified
  3. Phase 0 sometimes skips the "is this the right tool?" check

Full per-test detail: [test-1](../05-EVALUATION/test-1-skill-audit.md), [test-2](../05-EVALUATION/test-2-article-forge.md), [test-3](../05-EVALUATION/test-3-review-plan.md), [test-4](../05-EVALUATION/test-4-idea-to-pr.md). Cross-test summary: [regression.md](../05-EVALUATION/regression.md).

---

## When to use

- You have a workflow you do manually and want to slash-command-ify it
- You're not sure what shape the SOP should take (lean / full / orchestration)
- You want the rubric enforced for you (exit conditions, quality gates with all 3 parts, anti-triggers)

## When NOT to use

- The workflow is a one-line query (use direct prompting)
- You already know exactly what you want — write the SKILL.md directly using [`03-ANATOMY.md`](../03-ANATOMY.md)
- The workflow involves credentials, payments, or destructive operations (still author by hand and review carefully)

---

## How to use

```
1. Copy ./SKILL.md to your Claude Code skills folder
   (typically ~/.claude/skills/meta-paap/SKILL.md)
2. Restart Claude Code or reload skills
3. Type: /meta-paap [optional: short workflow description]
4. Answer the five elicitation questions
5. Review the architecture spec presented
6. Approve, revise, or reject
7. Get your generated SKILL.md
```

---

## Honest summary

`meta-paap` produces skills that score B+ to A on the 22-principle rubric (mean A- across n=4). The architecture is consistently right; two systematic gaps appear in every test (self-critique misses + hardest-phase under-specification) and require one iteration to close. Whether the generated skills produce better outputs *when run* than hand-written equivalents is the v0.2 head-to-head experiment, not a v0.1 claim.

The quality of the generated skill depends more on your input than on the generator. The five questions are the right ones. The more precisely you answer them, the more precise the skill. If you can't answer them, the skill will be vague — that's true whether `meta-paap` writes it or you do.

---

## See also

- [`SKILL.md`](./SKILL.md) — The skill itself
- [`references/architecture-checklist.md`](./references/architecture-checklist.md) — The decision-point checklist Phase 2 walks through
- [`examples.md`](./examples.md) — Sample invocations and what they produced (4 worked cases)
- [`../05-EVALUATION/`](../05-EVALUATION/) — Full n=4 regression study
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — The 22 principles `meta-paap` enforces (originally 20 at the time of the n=4 study)
- [`../03-ANATOMY.md`](../03-ANATOMY.md) — How to write a SKILL.md by hand if you'd prefer not to use the generator
