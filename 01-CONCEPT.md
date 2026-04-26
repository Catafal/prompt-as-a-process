# 01 — Concept

> Why Prompt as a Process, why now, what changed.

There have been three waves of "AI replaces code" thinking. The third wave doesn't have a clean name yet. **Prompt as a Process** is one. This chapter explains the lineage, what changed in mid-2025, what the framework actually is, where it works, where it breaks, and what it means.

---

## Three waves

**Wave 1 — Prompt engineering (~2020-2023).** The unit of work was a one-shot query. Few-shot, chain-of-thought (Wei et al. 2022), zero-shot CoT. ReAct (Yao et al. 2022, [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)) introduced the canonical loop — *"reasoning traces and task-specific actions in an interleaved manner... reasoning traces help the model induce, track, and update action plans as well as handle exceptions, while actions allow it to interface with external sources."* Reflexion (Shinn et al. 2023, [arXiv:2303.11366](https://arxiv.org/abs/2303.11366)) added *"verbal reinforcement"* — agents critiquing their own outputs and storing the critique as episodic memory. The prompt was still a module *inside* a code system, not the system itself.

**Wave 2 — Orchestration frameworks (~2023-2024).** LangChain, LlamaIndex, AutoGen, CrewAI, DSPy. The premise: chain prompts with code to enforce structure. The trade-off: as much complexity created as removed. The most-cited backlash post is Octomind's June 2024 piece, *"Why we no longer use LangChain for building our AI agents,"* which states bluntly: *"All LangChain has achieved is increased the complexity of the code with no perceivable benefits."* See [`02-EVIDENCE.md`](./02-EVIDENCE.md) Part B for the full evidence.

**Wave 3 — Prompt as a Process (~mid-2025-onwards).** Models reliable enough to follow complex SOPs end-to-end. Anthropic launched the SKILL.md format on October 16, 2025 — *"a directory that contains a `SKILL.md` file [...] with YAML frontmatter that contains [...] `name` and `description`."* The format was opened as a multi-vendor standard on December 18, 2025, adopted by Microsoft, OpenAI, Atlassian, Figma, Cursor, and GitHub. As of this repo's v0.1 ship date, the format is ~6 months old as a formal product feature and ~4 months old as a cross-vendor standard. **PaaP is not documenting an old pattern. It is formalizing patterns within a format that became real less than a year ago.**

---

## What changed in mid-2025

Models got reliable enough to follow a complex SOP. That changes more than you'd think.

Before mid-2025, if you handed an LLM a 20-step process, it would skip step 7, invent step 12, and present the output confidently as if nothing went wrong. You couldn't trust it to execute a structured workflow. You needed code to enforce the structure: verify that step 3 actually ran before step 4, parse outputs, retry when the model drifted.

Sonnet-class models changed this. When the SOP calls for it, they spawn sub-agents. When a quality gate fails, they loop back. They maintain state across 8 phases without losing the thread. Not because it's enforced like code. Because they've become reliable enough that following the process is what they do.

The format was always available. What unlocked it was the model becoming reliable enough to treat the SOP as a contract. Not perfectly, but well enough to build on.

---

## What Prompt as a Process actually is

Claude Code's SKILL.md system is the clearest example. A skill file has two parts:

- **A YAML header** — a `name`, a `description`, and optional constraints like which tools are allowed or whether to run in an isolated subagent.
- **A Markdown body** that *is* the process — phases, decision trees, quality gates, output format.

When you type `/deep-research about X`, Claude loads that Markdown and follows it. The orchestration logic is prose. Scripts and tools are optional companions, not the program.

Structurally, yes, this is a formatted system prompt with a loader. What makes it different is the **standardization**: a file format with a slash-command invoker, a shareable artifact that can be forked and improved like code. That's what created the ecosystem around it. There are 1,200+ community skills on GitHub. Garry Tan's `gstack` models an engineering team in 50 SKILL.md files. The pattern is real, and the question is what makes it work — which is what [`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md) answers.

This is not prompt engineering. Prompt engineering figures out how to phrase a one-shot query. PaaP writes a process with phases, branches, and quality gates that the model follows end-to-end.

> The artifact is a `.md` file. The runtime is the model. The deploy is dropping it in a folder.

---

## Where it works

**Research pipelines** are the strongest case. A well-written research SOP — scope it, triangulate sources, synthesize, critique what you got, package it — produces better results than any one-shot query. The process forces rigor. The model follows it.

Anything where the steps are clear and the output is text. **Editorial pipelines.** **Codebase analysis with a structured report format.** **Competitive research.** Workflows where you'd normally write a brief for a person, you write a SKILL.md instead.

[`gstack`](https://github.com/garrytan/gstack) by Garry Tan (President & CEO of Y Combinator) is the largest production case study. 50 SKILL.md files modeling an engineering team — CEO review, design review, QA, release management, deploy. All Markdown files. ~82,000 stars in 6 weeks. Tan reports shipping *"3 production services and 40+ features in 60 days, while running YC full-time"* using this setup. People fork skills and contribute back the way you'd contribute to an open-source library. See [`02-EVIDENCE.md`](./02-EVIDENCE.md) Part C for the full case study.

---

## Where it breaks, and where I've broken it

**Debugging is the worst part, and it's the thing nobody mentions.** When code fails, you get a stack trace. When a Markdown SOP fails, you get the wrong output. You read the whole execution trying to figure out which phase went sideways and why. I've spent more time on a broken 8-phase SOP than I'd have spent writing equivalent Python. For complex processes, this cost is real and it compounds.

One thing that helps: write the SOP to log its reasoning between phases. *"Phase 2 found 12 sources, 3 scored above threshold, proceeding to synthesis."* When something breaks, you read the logs instead of re-running the whole pipeline guessing where it drifted. It's not a stack trace, but it cuts the debugging time significantly. (This is principle #15 in the rubric, codified.)

**Model updates break your SOPs in ways that are hard to catch.** I've had processes calibrated to specific model behavior — how it handles edge cases, when it calls tools, how it formats output — that changed after a model update with no warning. With code you have versioned dependencies. With SKILL.md, you're trusting consistency you don't control.

**Context limits are a ceiling.** Long processes with intricate state across many steps will eventually lose coherence. The same pipeline can work nine times and fail on the tenth for no apparent reason. There's no clean answer to this yet. Persistent state on disk (principle #4) helps, but doesn't fully solve it.

The other two constraints are real but I hit them less in practice:

- **Determinism is gone.** Two identical inputs don't produce identical outputs. If you need exact reproducibility, you still need code.
- **Volume kills the economics.** Each run pays full inference cost. For personal workflows, irrelevant. For a product with concurrent users, the cost structure breaks.

---

## What this means

The more interesting thing isn't whether Markdown can replace Python. It's what people build when the cost drops from weeks to an afternoon.

More people will build more pipelines. They'll experiment with processes they never would have bothered to code. They'll throw things away when they don't work. The iteration speed changes what's worth attempting.

The ceiling is real. These aren't SaaS products. The determinism and scaling constraints are genuine. But personal and team-scale tools is a large space, and most useful software throughout history has lived exactly there.

The part that gets me thinking: Karpathy's autoresearch pattern applied to SOPs. Run the pipeline, evaluate the output against a rubric, mutate the SOP, run again. Keep what scores better. The SOP improves itself. I've started doing this with a few of my own skills and the quality jumps are noticeable after three or four cycles. The iteration loop that used to require a human reading every output can partially close on its own.

The gap between *"I have a workflow I do manually"* and *"I have a slash command that does it"* used to be a code project. Now it's a Markdown file and an afternoon.

---

## What this repo formalizes

PaaP isn't a product or a framework. It's a name for a pattern that practitioners and platform vendors have converged on independently. This repo's contribution is:

- A **22-principle rubric** ([`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md)) describing what makes one SKILL.md higher-quality than another, with archetype-aware applicability so reference and creative skills aren't penalized for not being procedural.
- A **scoring template** ([`04-RUBRIC/scoring-template.md`](./04-RUBRIC/scoring-template.md)) anyone can use to audit their own skills or community skills.
- An **empirical validation** ([`04-RUBRIC/empirical-validation.md`](./04-RUBRIC/empirical-validation.md)) testing the rubric against `gstack` (single-author depth) and a 50-skill community survey (breadth).
- A **canonical authoring guide** ([`03-ANATOMY.md`](./03-ANATOMY.md)) with a worked example.
- A **meta-skill** ([`06-META-PAAP/`](./06-META-PAAP/)) that generates skills following the rubric, plus an n=4 evaluation of its outputs ([`05-EVALUATION/`](./05-EVALUATION/)).
- An **evidence chapter** ([`02-EVIDENCE.md`](./02-EVIDENCE.md)) anchoring the framework's research lineage and corpus findings.

If you have a workflow you repeat at least once a week and you can't get it down to a slash command in an afternoon, the rubric and the meta-skill are the highest-leverage starting points.
