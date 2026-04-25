# meta-paap — The skill that generates skills

> A SKILL.md that builds other SKILL.md files. Drop it in your skills folder, type `/meta-paap`, describe what you want to automate, answer five questions, review the architecture, generate.

**Status:** Skeleton — full content lands in Phase 3.

---

## What it does

Five steps:

1. **Classify** the workflow as simple or complex
2. **Elicit** — five questions about steps, failure modes, output, tool dependencies, frequency
3. **Discover** — scan installed skills and suggest composition candidates
4. **Architect** — design the structure and present it for review before generating
5. **Generate** — write the SKILL.md and red-team it against the 20-principle checklist

---

## Performance characteristics (n=4)

- Simple workflow: ~4 min, lean skill (~350 lines)
- Complex workflow: ~10 min, full skill (~500-700 lines, possibly with reference file)
- Mean grade against the 20 principles: **A-** (range B+ to A)
- Known systematic weaknesses: see [`05-EVALUATION/regression.md`](../05-EVALUATION/regression.md)

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

`meta-paap` produces 80-90% of a production skill on first run. The architecture is consistently right. The remaining 10-20% is execution-path bugs, under-specified implementation for the hardest phase, and self-critique misses (safety violations, non-existent references). One iteration fixes these.

The quality of the generated skill depends more on your input than on the generator. The five questions are the right ones. The more precisely you answer them, the more precise the skill. If you can't answer them, the skill will be vague — that's true whether `meta-paap` writes it or you do.

---

## See also

- [`SKILL.md`](./SKILL.md) — The skill itself
- [`examples.md`](./examples.md) — Sample inputs and outputs
- [`../05-EVALUATION/`](../05-EVALUATION/) — n=4 regression study
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — What it scores against

---

*Populated in Phase 3.*
