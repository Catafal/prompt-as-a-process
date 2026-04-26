# 02 — Evidence

> Three waves of LLM-application thinking, the framework backlash with primary sources, a deep-dive on Garry Tan's `gstack` as the largest production exemplar, an empirical survey baseline extended to 80 community skills, and what the current state suggests about where the pattern goes next.

This chapter is the empirical spine of the framework. [`01-CONCEPT`](../01-CONCEPT/) introduced the three-wave framing; this one makes it defensible. Every claim in this chapter has a primary source. Every quoted text is verbatim. Where investigation hit a paywall, that's stated.

---

## Part A — Three waves of "AI replaces code"

### Wave 1 — Prompt engineering (~2020-2023)

The unit of work is a one-shot query. Few-shot, chain-of-thought, zero-shot CoT. The prompt sits inside a code system; the system orchestrates. The two papers most directly upstream of PaaP:

**ReAct (Yao et al. 2022, [arXiv:2210.03629](https://arxiv.org/abs/2210.03629)).** The canonical formulation of interleaved reasoning and acting:

> "we explore the use of LLMs to generate both reasoning traces and task-specific actions in an interleaved manner, allowing for greater synergy between the two: reasoning traces help the model induce, track, and update action plans as well as handle exceptions, while actions allow it to interface with external sources, such as knowledge bases or environments, to gather additional information."

Every SKILL.md execution is a ReAct loop dressed up in workflow phases. The inner cycle hasn't changed; what changed is what wraps it.

**Reflexion (Shinn et al. 2023, [arXiv:2303.11366](https://arxiv.org/abs/2303.11366)).** Verbal self-improvement without weight updates:

> "Reflexion agents verbally reflect on task feedback signals, then maintain their own reflective text in an episodic memory buffer to induce better decision-making in subsequent trials."

Reflexion benchmarks at 91% pass@1 on HumanEval (vs. early-2023 GPT-4's 80%). Quality gates and `meta-paap`'s self-critique phase are the practical descendants of this idea — applied at the prose level, mediated by the rubric in [`04-RUBRIC/principles.md`](../04-RUBRIC/principles.md).

### Wave 2 — Orchestration frameworks (~2023-2024)

LangChain, LlamaIndex, AutoGen, CrewAI, DSPy. The premise: chain prompts with code to enforce structure. Different frameworks made different bets, and most teams either replaced them or rolled them up.

The pattern of the era: a framework hides the prompt structure behind class abstractions, the structure leaks anyway when you need anything original, and you end up debugging the framework more than your logic. The exit pattern: rip the framework out, expose the prompts, keep modular building blocks.

DSPy is worth carving out as the exception. It's programmatic but doesn't impose runtime orchestration assumptions — closer to a compiler for prompt programs than a workflow engine. The frameworks that took the heaviest backlash (LangChain especially) imposed an opinionated runtime; DSPy treats prompts as optimizable artifacts and stays out of the runtime layer.

### Wave 3 — Prompt as a Process (~mid-2025-onwards)

The format that crystallized this wave is Anthropic's SKILL.md, [launched October 16, 2025](https://claude.com/blog/skills). The canonical definition, verbatim from Anthropic's engineering blog:

> "At its simplest, a skill is a directory that contains a `SKILL.md` file. This file must start with YAML frontmatter that contains some required metadata: `name` and `description`."

Required structure from the [official spec page](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview):

> "Every Skill requires a `SKILL.md` file with YAML frontmatter. Required fields: `name` and `description`. `name`: Maximum 64 characters, must contain only lowercase letters, numbers, and hyphens. `description`: Must be non-empty, Maximum 1024 characters. The `description` should include both what the Skill does and when Claude should use it."

The format opened as a multi-vendor standard on December 18, 2025. Microsoft, OpenAI, Atlassian, Figma, Cursor, and GitHub have announced adoption. As of this repo's v0.1 ship date, the format is **~6 months old** as a formal product feature and **~4 months old** as a cross-vendor standard.

The window for owning the framework framing of this wave is small. PaaP is documenting a pattern that is genuinely new as a standardized artifact.

---

## Part B — The framework backlash, evidenced

### The Octomind case (June 13, 2024)

The most-cited backlash post is the Octomind team's *"Why we no longer use LangChain for building our AI agents"* — originally at [octomind.dev/blog/why-we-no-longer-use-langchain-for-building-our-ai-agents](https://www.octomind.dev/blog/why-we-no-longer-use-langchain-for-building-our-ai-agents), now mirrored at [octoclaw.ai/blog/why-we-no-longer-use-langchain-for-building-our-ai-agents](https://octoclaw.ai/blog/why-we-no-longer-use-langchain-for-building-our-ai-agents) following a company rebrand.

A production team running LangChain in agents for over twelve months removed it. Their stated reasons, verbatim:

> "All LangChain has achieved is increased the complexity of the code with no perceivable benefits."

> "When our team began spending as much time understanding and debugging LangChain as it did building features, it wasn't a good sign."

> "abstractions on top of other abstractions, so you're often forced to think in terms of nested abstractions."

> "for production usage, every component must be reasonably understood so it won't blow up on you unexpectedly under real-world usage conditions."

The post hit Hacker News and accumulated 480 points. The top-rated comment from `sc077y`:

> "the second you need to do something a little original you have to go through 5 layers of abstraction just to change a minute detail."

Octomind's complaint is the **abstraction-tax** failure mode: the framework imposed cost without delivering value. A separate failure mode shows up in [Shashank Guda's *"Challenges & Criticisms of LangChain"*](https://shashankguda.medium.com/challenges-criticisms-of-langchain-b26afcef94e7) (March 2025): *"things break often between updates."* The **API-instability** failure mode — the framework moves faster than your codebase can absorb it.

Two failure modes, one direction of travel. Production teams are unwinding orchestration frameworks and either writing direct calls or moving to PaaP-style file-based orchestration.

### Why this matters for PaaP

The Wave 2 → Wave 3 transition isn't theoretical. Teams that ran LangChain in production for over a year, documented the friction, and removed it. The space they removed it *into* is what PaaP describes — direct prompts, modular building blocks, prose-level orchestration.

PaaP is what's left when the framework is gone.

---

## Part C — gstack as production exemplar

The single largest deployment of the PaaP architecture in the wild is [`garrytan/gstack`](https://github.com/garrytan/gstack) — Garry Tan's open-source skill set.

### The repo at a glance

**Snapshot date:** 2026-04-26 · **Repo SHA at writing:** [`23c4d7b`](https://github.com/garrytan/gstack/commit/23c4d7b228f6c490bdacfc6926fb19488e6300b1) · **Note:** gstack is daily-cadence; star/fork counts will have shifted by the time you read this. Architectural patterns described below are stable.

- **License:** MIT
- **Stars:** 83,555 at snapshot (in ~6 weeks since launch — verify current count at the repo)
- **Forks:** 12,190 at snapshot (same caveat)
- **Total SKILL.md files:** 50 (47 production + 3 golden test fixtures)
- **Total skill lines:** ~43,000
- **Largest skills:** `ship` (3,253 lines), `office-hours` (2,337), `plan-ceo-review` (2,364)
- **Smallest skills:** `freeze`, `guard`, `careful` (~63-86 lines, hook-only)

For comparison context: Anthropic's `anthropics/skills` repo had **123,978 stars and 14,506 forks** at the same snapshot date. The genre is large.

### What gstack actually is

From the gstack README:

> "I've been building products for twenty years, and right now I'm shipping more products than I ever have. In the last 60 days: 3 production services, 40+ shipped features, part-time, while running YC full-time."

> "On logical code change... my 2026 run rate is ~810× my 2013 pace (11,417 vs 14 logical lines/day)."

> "gstack is how I do it. It turns Claude Code into a virtual engineering team — a CEO who rethinks the product, an eng manager who locks architecture, a designer who catches AI slop, a reviewer who finds production bugs, a QA lead who opens a real browser, a security officer who runs OWASP + STRIDE audits, and a release engineer who ships the PR. Twenty-three specialists and eight power tools, all slash commands, all Markdown, all free, MIT license."

The framing is verbatim PaaP without the term. *"All slash commands, all Markdown"* is the format. *"Virtual engineering team"* is composition + personas. *"Twenty-three specialists"* is named, scoped, repeatable workflows.

### Architectural patterns observed

**Naming as org chart.** Skills are named for organizational roles, not technical capabilities: `office-hours` (YC partner), `plan-ceo-review`, `plan-eng-review`, `design-review`, `qa`, `cso` (security officer), `ship` (release engineer), `land-and-deploy` (SRE). The skill names *are* the org chart. Users invoke `/plan-ceo-review`, not `/scope-analyzer-v2`.

**Dense YAML headers.** Every header carries `preamble-tier` (1-4, which preamble template to inject), `interactive: true` / `triggers: [...]` (explicit trigger lists), `benefits-from: [office-hours]` (composition graph), `allowed-tools: [...]` (per-skill tool scoping), and `hooks:` (declarative `PreToolUse` hooks pointing to bash scripts in `bin/`). The header itself is routing logic.

**Three-layer phase structure.** Every skill has (1) an auto-generated preamble that emits routing variables (`PROACTIVE`, `CHECKPOINT_MODE`, `EXPLAIN_LEVEL`, `SPAWNED_SESSION`), (2) numbered workflow phases with literal `STOP. AskUserQuestion once per issue. Do NOT batch.` directives, and (3) auto-generated tail blocks for completion status, operational self-improvement, and telemetry.

**Composition as runtime read.** When `autoplan` runs, it explicitly *reads* the methodology body of `plan-ceo-review/SKILL.md` from disk and follows it — skipping a named section list (Preamble, AskUserQuestion Format, Telemetry, etc.). This is more precise than "include skill X." The composing skill *names which sections of the composed skill it owns*.

### How gstack scores against the rubric

19 of the 20 original principles confirmed cleanly (4 of those *extended* — gstack does them more rigorously than the principle requires). Only #20 (Output-first) scored partial — gstack prefers per-section output specs over a single skill-level contract.

Beyond confirmation, gstack contributed **10 candidate new principles** observed at production scale. After cross-corpus testing against the 50-skill community survey (Part D), only two cleared the bar for promotion to v0.1:

- **#21 Decision class drives gating policy** — Mechanical / Taste / User Challenge as a structural taxonomy
- **#22 Voice + writing rules as skill content** — banned vocabulary, prose structure, anti-AI-slop lists baked into the skill body

The remaining 8 candidates (SKILL.md as build artifact, dual-voice consensus, hooks-as-enforcement, telemetry-driven self-observation, plan-rubric-reuse-at-audit-time, host-agnostic packaging, spawn-vs-interactive detection, section-skip-list composition) are documented in [`04-RUBRIC/empirical-validation.md`](../04-RUBRIC/empirical-validation.md). They are real architectural patterns at gstack scale; they may not generalize to smaller scale.

### Why gstack matters as evidence

Three independent reasons.

**(a) Author identity.** Garry Tan is President & CEO of Y Combinator. He has worked with thousands of startups. When this person open-sources the workflow he personally uses to ship at the velocity he describes, the signal is qualitatively different from a community contributor's. The ~83k-stars-in-6-weeks adoption velocity (snapshot 2026-04-26) confirms the signal.

**(b) Bottom-up convergence on the same architecture.** The 22 principles in this rubric were derived top-down. gstack was built bottom-up by a single practitioner trying to maximize his own throughput. **He arrived at the same place from a different direction.** That is suggestive cross-validation — one practitioner converging on the same architecture from a different starting point. A stronger version would involve multiple independent practitioners audited by independent scorers; that is on the v0.2 roadmap.

**(c) Tan's framing is the PaaP framing.** From `ETHOS.md`: *"AI-assisted coding makes the marginal cost of completeness near-zero."* That is the economic thesis underneath PaaP, quantified — Tan even includes a "Boil-the-Lake compression table" (2-day boilerplate → 15-min, 1-week feature → 30-min). PaaP gets to inherit that quantitative anchor.

**One important non-claim.** Tan does not use the term "Prompt as a Process." He uses "virtual engineering team," "specialists," "slash commands," "all Markdown." The PaaP labeling is downstream of him, not from him. Cite gstack as evidence the architecture works; do not cite Tan as the framework's author.

---

## Part D — Empirical survey of 50 community skills

### Why this exists

A rubric you derived yourself, scored on skills you wrote, is a self-portrait. The bottom-up validation comes from scoring skills written by people who have never heard of this rubric.

### Methodology

- **N = 50** SKILL.md files across **18 distinct authors**
- **Stratified sampling** across domain (research / code / ops / content / knowledge / education / other), complexity tier (lean / full / orchestration), and authoring origin (official Anthropic / org collection / individual practitioner)
- **Sources:** `anthropics/skills` (14 skills), `obra/superpowers` and `obra/superpowers-skills` (7), `trailofbits/skills` (7), `michalparkola/tapestry-skills-for-claude-code` (5), `expo/skills` (3), `K-Dense-AI/claude-scientific-skills` (2), 12 individual practitioner repos (1 each)
- **Discovery via:** `karanb192/awesome-claude-skills`, `travisvn/awesome-claude-skills`, `ComposioHQ/awesome-claude-skills`
- **gstack and `meta-paap` excluded** — gstack covered separately in Part C; `meta-paap` is the subject of the n=4 evaluation in [`05-EVALUATION/`](../05-EVALUATION/) and would be self-scoring

A 10-skill stratified sub-sample was scored against all 22 principles; the remaining 40 were classified on coarser axes (presence/absence of feature heuristics).

### Feature presence across the corpus

| Feature | Count | % |
|---|---:|---:|
| YAML anti-triggers | 3/50 | 6% |
| Phase 0 routing (any form) | 11/50 | 22% |
| Explicit exit conditions | 13/50 | 26% |
| Quality gates with all 3 parts | 13/50 | 26% |
| Error-handling table | 3/50 | 6% |
| Persona / behavioral header | 1/50 | 2% |

**The community ships a lot of skills that don't follow most of the rubric.** Even adjusting for heuristic under-detection, only error-handling tables and YAML anti-triggers might clear 50%.

This is not a failure of the rubric — it's a finding *about* the rubric. The principles are descriptive of best practice, not of average practice. Skills can be useful without scoring well; the rubric describes what's load-bearing for the *highest-quality* skills, not what's required for a skill to function.

### The biggest finding: archetypes are real

The most valuable disconfirmation from the survey: the original rubric assumed one archetype. The community produces at least three.

| Archetype | % of corpus | Examples | Load-bearing |
|---|---:|---|---|
| Procedural | ~76% | obra/TDD, tob/agentic-actions-auditor, anthropic/skill-creator | Phases, gates, exits, synthesis |
| Reference | ~12% | expo-deployment, kdense-biopython, chrisvoncsefalvay-d3 | Description, output spec, code examples |
| Creative | ~6% | anthropic-canvas-design, anthropic-frontend-design | Output spec, voice rules, anti-templates |
| Hybrid | ~6% | various | Variable |

Reference skills are *not* failed procedural skills — they're library/API documentation reformatted as SKILL.md, and they appropriately lack gates and exits. Creative skills lean on output spec and voice rather than procedural discipline.

Treating all skills as procedural would have penalized ~18% of the corpus for following genuinely sensible patterns. The applicability matrix in [`04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) was added explicitly to fix this.

### Best-in-corpus exemplars

Three skills scored A or A- and merit citation as canonical examples:

- **`obra/test-driven-development`** (372 lines) — best example of *prose-as-quality-gate*. Its "Iron Law" plus "Rationalizations to Reject" table is the cleanest implementation of behavioral discipline encoded as voice. Scores A on Personas (#6), Human gate (#9), Errors (#16), Context scope (#14).
- **`trailofbits/agentic-actions-auditor`** (328 lines) — best example of *full procedural pattern execution*. Strong on Description router (A+), Route before work (A+), Output spec (A+), Context scope (A+), Progress (A+).
- **`anthropics/skill-creator`** (486 lines) — Anthropic's own answer to many of the same problems gstack solves. State (A+), Parallel (A+), Files=bus (A+), External storage (A+), Composition (A). Different solutions to the same problems gstack solves — useful as a comparison case.

### Bottom-up clusters worth tracking

Six recurring patterns the rubric currently only partially captures:

1. **Refusal-as-skill** (n=3) — the skill's primary value is *refusing the wrong action*. Currently absorbed into Phase 0 routing (#2) but worth surfacing as a sub-pattern.
2. **Rationalizations Rejection Table** (n=4 explicit, ~8 weaker) — list the bad arguments the AI will make, give the counter. Now part of Personas (#6) and Voice rules (#22).
3. **Aesthetic anti-patterns** (n=3) — for creative skills, encoding *what NOT to produce*. Now part of Output spec (#11).
4. **Tool-availability fallback chain** (n=4) — the canonical real-world shape of a 3-part gate (#12).
5. **Tone-as-instruction** (n=5+) — imperative voice setting behavior. Now part of Personas (#6) and Voice rules (#22).
6. **Reference-style skill archetype** (n≈6) — addressed in v0.1 via the archetype framing.

See [`04-RUBRIC/empirical-validation.md`](../04-RUBRIC/empirical-validation.md) for full evidence and v0.2 promotion criteria for the remaining patterns.

### Limitations stated honestly

- N=50 is direction-of-evidence, not statistics. Differences within ±15% should be treated as noise.
- Single scorer with conservative bias.
- Sampling bias toward visible repos. Curated lists were the seed; obscure skills under-represented.
- Author concentration — 4 authors (Anthropic, obra, ToB, michalparkola) = 66% of the corpus.
- Heuristic detection ~80% precision, ~60% recall for feature-presence checks.
- Rubric author scoring own rubric — known weakness. v0.2's multi-scorer reliability test is designed to address this.

---

## Part E — Trends & current state

### What changed in mid-2025 (model reliability inflection)

The proximate cause of Wave 3 was Sonnet-class models becoming reliable enough to follow long structured SOPs without drifting. Three behavioral changes in particular:

1. **Sub-agent spawning.** When the SOP says "spawn 3 parallel agents," the model now does — without forgetting which output came from which agent.
2. **Quality gate loops.** When a quality gate fails, the model loops back to the named recovery phase instead of declaring success.
3. **Multi-phase state preservation.** 8-phase pipelines maintain coherence across phases without losing the thread.

None of these were reliable before mid-2025. They are now reliable enough to build on. Not perfect — the failure modes documented in [`01-CONCEPT`](../01-CONCEPT/) ("where it breaks") are real — but reliable enough that prose-based orchestration produces working software.

### Karpathy's autoresearch pattern → applied to SOPs

Andrej Karpathy's autoresearch loop — run the experiment, evaluate against a rubric, mutate the design, re-run, keep what scores better — has an obvious application to SKILL.md files. Run the SOP, score the output against the 22-principle rubric, mutate the SOP, re-run. Quality jumps are noticeable after three or four cycles.

`anthropics/skill-creator` implements a version of this directly: workspace-iteration directories (`<skill-name>-workspace/iteration-N/eval-N/`), blind subagent comparisons, a description-optimizer loop. The pattern is starting to show up natively in skills as well as a separate evaluation tool.

### How power users actually work today

Three operating models documented in early-2026 practitioner accounts:

- **Harper Reed's two-model pattern.** Slow reasoning model (o-class) generates the spec and prompt plan interactively; fast execution model (Claude Code) executes the plan step by step, marking each complete and committing as it goes. *"The model does thinking + execution; the human does direction + review."*
- **Simon Willison's parallel coding agents.** *"Six coding agents in six terminal tabs."* Mix of Claude Code, Codex CLI, Codex Cloud, with a "fire multiple agents on the same problem from different angles" research pattern.
- **Boris Cherny's plan → one-shot pattern.** The creator of Claude Code reports running 5 parallel Claude Code instances per checkout, shipping 20-30 PRs/day. Workflow: *"start in plan mode → iterate on plan → one-shot implementation. Once there's a good plan, it one-shots almost every time."* The plan is a contract; bad plan = iteration hell.

The shift across all three: **writer → reviewer**. Time spent validating output, not writing code. Decompose work into isolated tasks; launch agents; spend attention on selection and review, not execution.

PaaP makes the "decompose work into isolated tasks" step a first-class artifact. The SKILL.md is the decomposition. Sharing the SKILL.md is sharing the operating model.

### Sub-agent + state + composition as emergent patterns

Three patterns that didn't exist as standardized primitives before mid-2025:

- **Sub-agent spawning** — `Task` tool, isolated context, structured return. Patterns now codified in the rubric (principle #5 Parallel, #8 Synthesis).
- **Persistent state on disk** — `factory-state.json` or equivalent, with a Resume Protocol. Patterns codified in #4 State.
- **Skill composition** — runtime path resolution, optional fallbacks, declared-in-YAML composition graphs. Patterns codified in #19 Composition.

Each of these started as a hand-rolled pattern in mature skills (`/deep-research`, `/blog-factory`), got refined by `meta-paap` generating them consistently, and is now visible as a structural feature of the highest-scoring skills in the survey.

### Where the next wave likely goes

Speculative; flagged as such.

- **Multi-host portability** as a default. gstack runs on 10 different hosts via a config knob. The format being a multi-vendor standard (Microsoft, OpenAI, Atlassian, Figma, Cursor, GitHub) suggests this becomes table-stakes rather than an advanced feature.
- **Empirical evaluation as routine.** v0.2 of this repo ships a head-to-head experiment (hand-written vs `meta-paap`-generated, blind-scored outputs). Other authors will run similar evaluations on their skill sets. Multi-scorer reliability data, kappa scores per principle.
- **Skill marketplaces with quality scoring.** Once the rubric stabilizes, third parties will score skills, and curated lists will weight quality scores heavily.
- **Self-improving skills as a default pattern.** gstack already does this via telemetry-driven preamble injection. The pattern may become more common — skills that observe their own runs and feed prior learnings forward.

These are forward-looking guesses. v0.2 of this repo will document which actually held up.

---

## Sources

All accessed 2026-04-25.

**Research papers:**
- ReAct: https://arxiv.org/abs/2210.03629
- Reflexion: https://arxiv.org/abs/2303.11366

**Framework backlash:**
- Octomind original: https://www.octomind.dev/blog/why-we-no-longer-use-langchain-for-building-our-ai-agents
- Octomind mirror (post-rebrand): https://octoclaw.ai/blog/why-we-no-longer-use-langchain-for-building-our-ai-agents
- Hacker News thread (480 points): https://news.ycombinator.com/item?id=40739982
- Shashank Guda critique: https://shashankguda.medium.com/challenges-criticisms-of-langchain-b26afcef94e7

**SKILL.md format origin:**
- Anthropic launch announcement: https://claude.com/blog/skills (originally https://www.anthropic.com/news/skills)
- Engineering deep-dive: https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills
- Canonical spec: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview

**gstack:**
- Repo: https://github.com/garrytan/gstack
- TechCrunch coverage: https://techcrunch.com/2026/03/17/why-garry-tans-claude-code-setup-has-gotten-so-much-love-and-hate/

**50-skill community survey:** Full URL list documented in [`04-RUBRIC/empirical-validation.md`](../04-RUBRIC/empirical-validation.md).
