# Prompt as a Process (PaaP)

> A framework for treating Markdown SOPs as deployable applications, runnable end-to-end by sufficiently reliable language models.

[![License: MIT](https://img.shields.io/badge/code-MIT-blue.svg)](./LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/docs-CC--BY--4.0-lightgrey.svg)](./LICENSE-docs)
[![Status](https://img.shields.io/badge/status-v0.1-orange.svg)](#roadmap)

---

## TL;DR

The third wave of "AI replaces code" doesn't have a clean name yet. **Prompt as a Process** is one. The thesis in three sentences:

1. Mid-2025 models became reliable enough to follow complex SOPs end-to-end. The `.md` file is now the application; the model is the runtime; the deploy is dropping the file in a folder.
2. This repo formalizes that pattern into a framework: **22 architectural principles** with applicability across **3 skill archetypes** (Procedural / Reference / Creative), a **scoring rubric**, an **empirical survey of 50 community skills** + a deep-dive on **gstack** (50 SKILL.md, ~82k stars), **four documented evaluations** of a meta-skill that generates other skills, and a **runnable example**.
3. Use it to write better skills, evaluate existing ones, extend the rubric, or contribute test data.

---

## What this looks like in practice

A 60-line `pre-call` SKILL.md (the canonical example in [`examples/pre-call/`](./examples/pre-call/)) takes a name and a company, runs phased research with explicit exit conditions and a quality gate that loops back if the talking points aren't grounded in something concrete, and produces:

```
# Pre-Call Brief: Sarah Chen @ Acme Robotics

**Background:** VP of Engineering at Acme since 2024. Previously led
infrastructure at Stripe (2019-2024), shipped their idempotency-keys system.

**Recent work:** Authored "Building reliable agent loops" (Substack, March 2026)
arguing for filesystem-as-memory over vector DB approaches. Spoke at AI
Engineer Summit on the same topic.

**Company context:** Acme builds warehouse robots; Series B closed Jan 2026
($45M, led by a16z). Recent hiring push for ML infra suggests they're
moving from rules-based picking to learned policies.

**Talking points:**
1. Her Substack piece argues against vector DBs — worth asking how Acme's
   robotics planning stack handles long-horizon memory.
2. The Stripe idempotency work suggests she cares about determinism in
   distributed systems — directly relevant to multi-robot coordination.
3. "How are you sequencing the rules → learned-policies migration without
   breaking warehouse SLAs?"
```

That's the artifact. The framework is about how to write more SKILL.md files like that — and how to know when you've written a good one.

---

## Why this exists

Prompt engineering treated the prompt as a one-shot query. Orchestration frameworks (LangChain, AutoGen) wrapped prompts in code and most teams ripped them back out. PaaP is what's left when the model is reliable enough that the SOP itself is the orchestration.

Calling it "just a system prompt" misses what's interesting: standardization (a file format with a slash-command invoker, a shareable artifact that forks like code) created an ecosystem. Anthropic launched the SKILL.md format on October 16, 2025; the spec was opened as a multi-vendor standard on December 18, 2025, adopted by Microsoft, OpenAI, Atlassian, Figma, Cursor, and GitHub. As of this v0.1's ship date, the format is ~6 months old.

There are 1,200+ community skills on GitHub. Garry Tan's `gstack` models an engineering team in 50 SKILL.md files (~82k stars in 6 weeks). The pattern is real; the question is what makes it work.

This repo is the answer, organized as a framework.

### What this adds beyond Anthropic's own docs and `skill-creator`

A fair question: Anthropic ships the SKILL.md format and a 486-line `skill-creator` skill that already implements many of the patterns documented here. What does PaaP add?

Three things, with honest scope:

1. **A vocabulary and a rubric.** Anthropic ships the *format* and *one* canonical generator. PaaP names the *patterns* across the format — 22 principles you can score any skill against, with archetype-aware applicability so reference and creative skills aren't penalized for not being procedural.
2. **An empirical corpus.** A 50-skill survey across 18 community authors plus a deep-dive on `gstack`, comparing observed patterns to the rubric. That cross-corpus evidence does not exist anywhere else as of this writing.
3. **A meta-skill that makes the rubric operational.** [`meta-paap`](./06-META-PAAP/) generates SKILL.md files that score well on the 22 principles. It's downstream of `skill-creator`, not a competitor — different design (heavier elicitation, runtime composition discovery, externalized architecture checklist) optimized for a different question (rubric compliance vs. workflow iteration).

What PaaP does NOT add: a new file format, a new runtime, or a competitor to Claude Code itself.

---

## What's in here

| Chapter | What it is |
|---|---|
| [01 — Concept](./01-CONCEPT.md) | Why PaaP, why now, what changed in mid-2025 |
| [02 — Evidence](./02-EVIDENCE.md) | Three waves of AI-replaces-code, the framework backlash, gstack case study, empirical survey of 50 community skills |
| [03 — Anatomy](./03-ANATOMY.md) | How to write a working SKILL.md — the canonical authoring guide |
| [04 — Rubric](./04-RUBRIC/) | The 22 architectural principles, scoring template, bottom-up empirical validation |
| [05 — Evaluation](./05-EVALUATION/) | n=4 regression study of `meta-paap` (a skill that generates skills) — methodology, per-test results, cross-test patterns |
| [06 — meta-paap](./06-META-PAAP/) | The skill itself, plus how to use and extend it |
| [07 — Open questions](./07-OPEN-QUESTIONS.md) | What v0.2 and v1.0 will tackle. Where contributions are most useful |
| [examples/](./examples/) | Runnable skills — start with [`pre-call/`](./examples/pre-call/) |

---

## The fast path (if you remember nothing else)

The full rubric has 22 principles across 3 archetypes. If you only internalize five, internalize these — they cover ~70% of what separates good Procedural skills from bad ones in the corpus survey:

1. **Description as router (#1).** YAML `description` is routing logic, not metadata. Include explicit anti-triggers ("Do NOT use for..."). Only 6% of community skills do this.
2. **Phase 0 routing (#2).** First phase classifies the request and identifies STOP conditions before any work runs.
3. **Exit conditions as binary questions (#10).** Not "exit when complete" — "exit when you can answer X."
4. **Quality gates with all 3 parts (#12).** Check + failure condition + recovery path. Without the recovery path, the model invents one.
5. **Output spec, defined first (#11, #20).** Format, sections, length, per-section content rules. Define before phases; phases are the path.

The other 17 principles handle composition, state, parallelism, archetypes, voice, error tables, and edge cases. Useful, but these 5 are the ones to start with. Full definitions and the applicability matrix in [`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md).

---

## Quickstart

Three ways to use this repo:

**Author a skill from scratch:**
1. Read [03 — Anatomy](./03-ANATOMY.md).
2. Copy the template from `examples/pre-call/SKILL.md`.
3. Write your phases, exit conditions, and quality gates. Drop in your skills folder. Run.

**Generate a skill with `meta-paap`:**
1. Drop [`06-META-PAAP/SKILL.md`](./06-META-PAAP/SKILL.md) in your skills folder.
2. Type `/meta-paap` in Claude Code.
3. Describe what you want to automate. Answer the five questions. Review the architecture. Generate.

**Evaluate an existing skill:**
1. Read [`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md).
2. Use [`04-RUBRIC/scoring-template.md`](./04-RUBRIC/scoring-template.md).
3. Score, identify weak principles, iterate.

---

## Status

**v0.1** — Public-ready. Living research repo. Forks and contributions welcome.

This is not a frozen artifact. The rubric will evolve. The evaluation set will grow. Open questions are tracked in [07-OPEN-QUESTIONS.md](./07-OPEN-QUESTIONS.md).

### Roadmap

- **v0.1 (this release)** — Framework, rubric, n=4 evaluations, 50-skill empirical survey, meta-paap skill, runnable example.
- **v0.2** — Head-to-head experiment: hand-written vs `meta-paap`-generated skills on the same tasks, blind-scored outputs. Extending survey to n=100.
- **v1.0** — Possibly: conversion to a workshop-paper format if v0.2's empirical work warrants it. Submission readiness depends on hitting multi-scorer kappa, head-to-head outcome data, and N≥100 corpus. v0.1 is explicitly not paper-ready by current academic standards (see [`07-OPEN-QUESTIONS.md`](./07-OPEN-QUESTIONS.md) for the gap list).

---

## Citing

If you use the framework, the rubric, or the methodology in your work, please cite via [CITATION.cff](./CITATION.cff). GitHub renders this into a one-click citation block automatically.

---

## License

- **Code, scripts, and skill artifacts** — [MIT](./LICENSE)
- **Documentation, chapters, research, evaluations** — [CC-BY-4.0](./LICENSE-docs)

The dual-license is deliberate: code should be freely usable in any setting; written content needs attribution to keep the framework's lineage traceable as it spreads.

---

## Contributing

The most valuable contributions:
1. **Skills audited against the rubric** — score one of your skills and submit the evaluation
2. **Principle critiques** — argue for adding, removing, or rewording a principle
3. **New test cases** — workflows the meta-paap evaluation should cover
4. **Bug reports on examples** — if `pre-call/` or any other example fails, file an issue

See [CONTRIBUTING.md](./CONTRIBUTING.md) for specifics.

---

## Acknowledgements

This repo builds on prior work by the Anthropic Claude Code team (the SKILL.md format), Garry Tan (`gstack`), Andrej Karpathy (the autoresearch pattern), the Octomind team (the documented LangChain-removal case), and the broader Claude Code skills community. Specific citations live in [02-EVIDENCE.md](./02-EVIDENCE.md).

---

*Maintained by [Jordi Catafal](https://x.com/jorcagra). Issues and pull requests welcome.*
