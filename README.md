# Prompt as a Process (PaaP)

> A framework for treating Markdown SOPs as deployable applications, runnable end-to-end by sufficiently reliable language models.

[![License: MIT](https://img.shields.io/badge/code-MIT-blue.svg)](./LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/docs-CC--BY--4.0-lightgrey.svg)](./LICENSE-docs)
[![Status](https://img.shields.io/badge/status-v0.1-orange.svg)](#roadmap)

---

## TL;DR

The third wave of "AI replaces code" doesn't have a clean name yet. **Prompt as a Process** is one. The thesis in three sentences:

1. Mid-2025 models became reliable enough to follow complex SOPs end-to-end. The `.md` file is now the application; the model is the runtime; the deploy is dropping the file in a folder.
2. This repo formalizes that pattern into a framework: **20 architectural principles**, a **scoring rubric**, an **empirical survey of community skills**, **four documented evaluations** of a meta-skill that generates other skills, and a **runnable example**.
3. Use it to write better skills, evaluate existing ones, extend the rubric, or contribute test data.

---

## Why this exists

Prompt engineering treated the prompt as a one-shot query. Orchestration frameworks (LangChain, AutoGen) wrapped prompts in code and most teams ripped them back out. PaaP is what's left when the model is reliable enough that the SOP itself is the orchestration.

Calling it "just a system prompt" misses what's interesting: standardization (a file format with a slash-command invoker, a shareable artifact that forks like code) created an ecosystem. There are 1,200+ community Claude Code skills on GitHub. Garry Tan's `gstack` models an engineering team in 28 slash commands. The pattern is real, the question is what makes it work.

This repo is the answer, organized as a framework.

---

## What's in here

| Chapter | What it is |
|---|---|
| [01 — Concept](./01-CONCEPT.md) | Why PaaP, why now, what changed in mid-2025 |
| [02 — Landscape](./02-LANDSCAPE.md) | Three waves of AI-replaces-code, the framework backlash, gstack case study, empirical survey of 50 community skills |
| [03 — Anatomy](./03-ANATOMY.md) | How to write a working SKILL.md — the canonical authoring guide |
| [04 — Rubric](./04-RUBRIC/) | The 20 architectural principles, scoring template, bottom-up empirical validation |
| [05 — Evaluation](./05-EVALUATION/) | n=4 regression study of `meta-paap` (a skill that generates skills) — methodology, per-test results, cross-test patterns |
| [06 — meta-paap](./06-META-PAAP/) | The skill itself, plus how to use and extend it |
| [07 — Open questions](./07-OPEN-QUESTIONS.md) | What v0.2 and v1.0 will tackle. Where contributions are most useful |
| [examples/](./examples/) | Runnable skills — start with [`pre-call/`](./examples/pre-call/) |

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
1. Read [`04-RUBRIC/20-principles.md`](./04-RUBRIC/20-principles.md).
2. Use [`04-RUBRIC/scoring-template.md`](./04-RUBRIC/scoring-template.md).
3. Score, identify weak principles, iterate.

---

## Status

**v0.1** — Public-ready. Living research repo. Forks and contributions welcome.

This is not a frozen artifact. The rubric will evolve. The evaluation set will grow. Open questions are tracked in [07-OPEN-QUESTIONS.md](./07-OPEN-QUESTIONS.md).

### Roadmap

- **v0.1 (this release)** — Framework, rubric, n=4 evaluations, 50-skill empirical survey, meta-paap skill, runnable example.
- **v0.2** — Head-to-head experiment: hand-written vs `meta-paap`-generated skills on the same tasks, blind-scored outputs. Extending survey to n=100.
- **v1.0** — Conversion to a peer-reviewable paper (likely workshop venue, not arXiv flagship).

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

This repo builds on prior work by the Anthropic Claude Code team (the SKILL.md format), Garry Tan (`gstack`), Andrej Karpathy (the autoresearch pattern), the Octomind team (the documented LangChain-removal case), and the broader Claude Code skills community. Specific citations live in [02-LANDSCAPE.md](./02-LANDSCAPE.md).

---

*Maintained by [Jordi Catafal](https://x.com/jorcagra). Issues and pull requests welcome.*
