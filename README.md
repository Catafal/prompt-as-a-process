# Prompt as a Process (PaaP)

> A framework for treating Markdown SOPs as deployable applications, runnable end-to-end by sufficiently reliable language models.

[![License: MIT](https://img.shields.io/badge/code-MIT-blue.svg)](./LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/docs-CC--BY--4.0-lightgrey.svg)](./LICENSE-docs)
[![Status](https://img.shields.io/badge/status-v0.3%20released-brightgreen.svg)](./CHANGELOG.md)

---

## v0.3 in one paragraph

v0.3 (2026-04-26) tests whether Prompt as a Process holds up at output time. The answer is nuanced: meta-paap-generated PaaP skills often **match or beat hand-written skills** when quality can be described in the workflow brief; production-iterated hand-written skills still win where quality depends on tacit domain discipline. The headline finding is the form-vs-substance split: **PaaP captures form quickly through articulable process; production iteration deepens substance the rubric cannot describe.** v0.3 lands the empirical layer that makes this claim defensible — multi-model kappa across three vendors, output-quality experiments at 5×3×3 + 4×3×3 scales, and a generator (`meta-paap v2`) upgraded with Iron Law + Rationalizations to Reject patterns.

---

## TL;DR

**Prompt as a Process** is a framework for writing Markdown workflows that agents can execute reliably: phases, branches, gates, output contracts, and recovery paths. The `.md` file is the application; the model is the runtime; deploy is dropping the file in a folder.

By mid-2025, frontier models became reliable enough in practice for many users to treat structured Markdown SOPs as executable workflows. This repo formalizes that pattern. v0.3 adds the empirical layer that lets you ask whether the pattern survives output-time scrutiny:

1. **25 architectural principles** with applicability across **3 skill archetypes** (Procedural / Reference / Creative), a **scoring rubric**, and a **scoring template**. v0.3 promoted 3 corpus-validated principles (#23 host-portable, #24 self-observation, #25 spawn-detection) with ≥20% community-prevalence in the N=80 corpus.
2. An **empirical corpus of 80 community skills** across 36 authors + a deep-dive on **`gstack`** (50 SKILL.md, ~83.5k stars at snapshot — see [02-EVIDENCE](./02-EVIDENCE/) and [04-RUBRIC](./04-RUBRIC/)).
3. **`/paap-eval`**, an auto-scoring instrument with algorithmic detectors + semantic judges, validated through a 5-rater multi-model kappa pilot spanning 3 Claude personas + GPT-5.4 (Codex) + Gemini-3 (Gemini CLI) — see [`05-EVALUATION/kappa-pilot.md`](./05-EVALUATION/kappa-pilot.md) and [`05-EVALUATION/kappa-pilot-multimodel.md`](./05-EVALUATION/kappa-pilot-multimodel.md).
4. **`meta-paap v2.0`** ([`06-META-PAAP/`](./06-META-PAAP/)) — the skill generator, upgraded with Iron Law + Rationalizations to Reject patterns and a closed self-observation loop. Tested across two output-quality experiments: **priority #3** ([5 workflows × 3 inputs × 3 judges = 45 judgments](./05-EVALUATION/head-to-head-expanded.md)) and **priority #5** ([4 community skills × 3 inputs × 3 judges = 36 judgments](./05-EVALUATION/community-head-to-head.md)).
5. A **reflexive self-audit** of this repo against its own rubric ([`04-RUBRIC/reflexive-self-audit.md`](./04-RUBRIC/reflexive-self-audit.md)) — aggregate **A** at 25-principle scale — and a **runnable example** ([`pre-call`](./examples/pre-call/)).

Use it to write better skills, evaluate existing ones, extend the rubric, or contribute test data.

### v0.3 experiments at a glance

| Experiment | Scale | Headline finding |
|---|---|---|
| [Multi-model kappa](./05-EVALUATION/kappa-pilot-multimodel.md) | 5 raters × 10 skills | Cross-vendor distance varies by vendor: GPT-5.4 ↔ Claude-pragmatic = 1.20 grade-steps (tighter than within-Claude); Gemini-3 ↔ Claude-pragmatic = 2.30 (looser). Rubric travels, but model-vendor identity is a real source of grade-shift. |
| [Output-quality 5×3×3](./05-EVALUATION/head-to-head-expanded.md) | 5 workflows × 3 inputs × 3 judges = 45 judgments | Workflow-specific picture: handwritten 24/45 vs generated 20/45. Handwritten wins on voice work (humanizer 8/9); generated wins on structured tasks (`remember` 9/9 unanimous). Provenance accuracy 53-67% (near chance). |
| [Community 4×3×3](./05-EVALUATION/community-head-to-head.md) | 4 community skills × 3 inputs × 3 judges = 36 judgments | meta-paap v2 wins 29/36 (81%); only `obra/test-driven-development` holds (5/9 community) — production-iteration moat. **0/36 provenance accuracy** — judges systematically mis-attribute generated as hand-authored. |

---

## Who this is for

- **People writing Claude Code / Codex / Cursor / agent skills.** The 25-principle rubric and the [`03-ANATOMY`](./03-ANATOMY/) authoring guide are calibrated for you.
- **Teams turning repeatable research, coding, or editorial workflows into agent-run SOPs.** The [`meta-paap`](./06-META-PAAP/) generator is the fastest on-ramp; the [`pre-call`](./examples/pre-call/) example is the canonical pattern to copy.
- **Researchers studying how prose instructions become executable process in agent harnesses.** [`02-EVIDENCE`](./02-EVIDENCE/), [`05-EVALUATION/`](./05-EVALUATION/), and [`/paap-eval`](./06-META-PAAP/paap-eval/) document the empirical work; honest limitations are stated in each.
- **Anyone evaluating whether a Markdown workflow is robust enough to share.** Use [`/paap-eval`](./06-META-PAAP/paap-eval/) for fast scoring, or [`04-RUBRIC/scoring-template.md`](./04-RUBRIC/scoring-template.md) for manual self-audit or peer review.

## What this is not

- **Not a new runtime or file format.** Uses Anthropic's existing SKILL.md spec (launched October 2025).
- **Not a claim that prompts replace software engineering.** Determinism, reproducibility, multi-tenant scaling — all still need code.
- **Not a claim that PaaP is invented here.** The pattern emerged independently across the community (gstack, obra/superpowers, Anthropic's own skill-creator). PaaP names and formalizes it.
- **Not yet an academic paper.** v0.3 is a practitioner framework with a substantially stronger evidence base than v0.2: N=80 corpus, multi-model kappa across 3 vendors, two output-quality experiments (5×3×3 author-skill + 4×3×3 community-skill), and meta-paap v2 with the rationalizations-to-reject pattern. Workshop-paper conversion is more plausible than at v0.2 but still requires third-party validation work — see [07-OPEN-QUESTIONS](./07-OPEN-QUESTIONS/) for v0.4 priorities (third-party rubric author, random-sample community skills, human-rater layer).
- **Not a competitor to Claude Code or Anthropic's `skill-creator`.** It's a vocabulary, a rubric, and a corpus *on top of* what Anthropic ships.

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

Calling it "just a system prompt" misses what's interesting: standardization (a file format with a slash-command invoker, a shareable artifact that forks like code) created an ecosystem. Anthropic launched the SKILL.md format on October 16, 2025; the spec was opened as a multi-vendor standard on December 18, 2025, with adoption announced by Microsoft, OpenAI, Atlassian, Figma, Cursor, and GitHub (sources in [02-EVIDENCE](./02-EVIDENCE/) Part A). As of v0.2's release date (2026-04-26), the format is ~6 months old.

The community ecosystem is large and growing — Anthropic's own `anthropics/skills` repo had ~124k stars at snapshot 2026-04-26; community-curated lists track several hundred SKILL.md files (links in [02-EVIDENCE](./02-EVIDENCE/)). Garry Tan's `gstack` models an engineering team in 50 SKILL.md files (~83.5k stars and 12.2k forks at snapshot 2026-04-26; numbers update daily). The pattern is real; the question is what makes it work.

> Yes, structurally a SKILL.md is a system prompt with a loader. The contribution PaaP makes is the **process architecture**, the **standardized artifact**, and the **evaluation rubric** — not the file format itself.

This repo is the answer, organized as a framework.

### What this adds beyond Anthropic's own docs and `skill-creator`

A fair question: Anthropic ships the SKILL.md format and a 486-line `skill-creator` skill that already implements many of the patterns documented here. What does PaaP add?

Three things, with honest scope:

1. **A vocabulary and a rubric.** Anthropic ships the *format* and *one* canonical generator. PaaP names the *patterns* across the format — 25 principles you can score any skill against, with archetype-aware applicability so reference and creative skills aren't penalized for not being procedural.
2. **An empirical corpus.** An 80-skill survey across 36 community authors plus a deep-dive on `gstack`, comparing observed patterns to the rubric. That cross-corpus evidence does not exist anywhere else as of this writing.
3. **Operational skills.** [`meta-paap`](./06-META-PAAP/) generates SKILL.md files that score well on the 25 principles; [`/paap-eval`](./06-META-PAAP/paap-eval/) scores existing skills against the rubric. They are downstream of `skill-creator`, not competitors — optimized for rubric compliance, evaluation, and workflow architecture.

What PaaP does NOT add: a new file format, a new runtime, or a competitor to Claude Code itself.

---

## What's in here

| Chapter | What it is |
|---|---|
| [01 — Concept](./01-CONCEPT/) | Why PaaP, why now, what changed in mid-2025 |
| [02 — Evidence](./02-EVIDENCE/) | Three waves of AI-replaces-code, the framework backlash, gstack case study, empirical survey baseline |
| [03 — Anatomy](./03-ANATOMY/) | How to write a working SKILL.md — the canonical authoring guide |
| [04 — Rubric](./04-RUBRIC/) | The 25 architectural principles, scoring template, N=80 corpus extension, bottom-up empirical validation |
| [05 — Evaluation](./05-EVALUATION/) | n=4 regression, kappa pilot, corpus extension raw data, head-to-head experiment |
| [06 — meta-paap](./06-META-PAAP/) | `meta-paap` generator + `/paap-eval` scoring instrument |
| [07 — Open questions](./07-OPEN-QUESTIONS/) | v0.2 retrospective, v0.3 priorities, and v1.0 paper path |
| [examples/](./examples/) | Runnable skills — start with [`pre-call/`](./examples/pre-call/) |

---

## The fast path (if you remember nothing else)

The full rubric has 25 principles across 3 archetypes. If you only internalize five, internalize these — they cover ~70% of what separates good Procedural skills from bad ones in the corpus survey:

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
1. Read [03 — Anatomy](./03-ANATOMY/).
2. Copy the template from `examples/pre-call/SKILL.md`.
3. Write your phases, exit conditions, and quality gates. Drop in your skills folder. Run.

**Generate a skill with `meta-paap`:**
1. Drop [`06-META-PAAP/SKILL.md`](./06-META-PAAP/SKILL.md) in your skills folder.
2. Type `/meta-paap` in Claude Code.
3. Describe what you want to automate. Answer the five questions. Review the architecture. Generate.

**Evaluate an existing skill:**
1. Drop [`06-META-PAAP/paap-eval/SKILL.md`](./06-META-PAAP/paap-eval/SKILL.md) in your skills folder.
2. Type `/paap-eval` with the path to a SKILL.md file.
3. Review the scorecard, identify weak principles, iterate. For manual scoring, use [`04-RUBRIC/scoring-template.md`](./04-RUBRIC/scoring-template.md).

---

## Status

**v0.3** — Released 2026-04-26. Living research repo with: evaluation tooling, 25-principle rubric, N=80 corpus, multi-model kappa across 3 vendors, two output-quality experiments (5×3×3 author + 4×3×3 community), `meta-paap v2` with Iron Law + Rationalizations + closed self-observation loop. Forks and contributions welcome.

This is not a frozen artifact. The rubric will evolve. The evaluation set will grow. Open questions are tracked in [07-OPEN-QUESTIONS](./07-OPEN-QUESTIONS/).

### Roadmap

- **v0.1 (released 2026-04-25)** — Framework, rubric (20 principles), n=4 evaluations, 50-skill empirical survey, `meta-paap` skill, runnable example, reflexive self-audit. See [CHANGELOG.md](./CHANGELOG.md) for details.
- **v0.2 (released 2026-04-26)** — `/paap-eval` skill (the auto-scoring instrument), 3-persona kappa pilot (mean inter-rater 1.83 grade-steps), corpus extended to N=80 across 36 distinct authors (3 deferred candidates promotion-ready, 3 confirmed gstack-only), head-to-head experiment (5 paired skills + 1 blind-output test where the judge mis-attributed provenance). See [CHANGELOG.md](./CHANGELOG.md).
- **v0.3 (released 2026-04-26)** — Rubric grew 22 → 25 principles. Multi-model kappa pilot extended to 5 raters (Claude × 3 personas + GPT-5.4 + Gemini-3). Output-quality test expanded to 5 workflows × 3 inputs × 3 cross-vendor judges (45 judgments). `meta-paap v2.0` shipped with Iron Law + Rationalizations to Reject pattern + closed self-observation loop (closes the framework's own #24 grade from C to B+; aggregate A− → A). Community-skill head-to-head (4 archetype-stratified community skills × 3 inputs × 3 judges = 36 judgments) — v2-generated wins 29/36, with `obra/test-driven-development` 5/9 community as the production-iteration moat. **Headline finding: form-vs-substance split.** PaaP captures form quickly; production iteration deepens substance the rubric cannot describe. See [CHANGELOG.md](./CHANGELOG.md).
- **v0.4 (planned)** — Third-party rubric author (breaks v0.3's measurement-side self-bias loop). Third-party hand-authored skills (random sample from N=80 corpus, not corpus exemplars). Anthropic-family kappa expansion (Claude Opus / Sonnet / Haiku). Larger N per workflow (5+ inputs each). `learnings.jsonl` feedback loop into meta-paap (closes the substance gap from priority #5's finding). Human-rater layer. paap-eval re-calibration at 25-principle scale. See [07-OPEN-QUESTIONS](./07-OPEN-QUESTIONS/).
- **v1.0 (conditional, more defensible after v0.3)** — Workshop-paper format. The v0.3 evidence base — multi-model judge data, two output-quality experiments at 45 + 36 judgment scales, mechanism-grounded form-vs-substance finding — supports a more defensible workshop submission than v0.2 did. v0.4 third-party validation work determines whether v1.0 ships.

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
3. **Multi-model judge checks** — run the same skill through different models and submit disagreement tables
4. **Bug reports on `/paap-eval` or examples** — especially where scoring diverges from expert judgment

See [CONTRIBUTING.md](./CONTRIBUTING.md) for specifics.

---

## Acknowledgements

This repo builds on prior work by the Anthropic Claude Code team (the SKILL.md format), Garry Tan (`gstack`), Andrej Karpathy (the autoresearch pattern), the Octomind team (the documented LangChain-removal case), and the broader Claude Code skills community. Specific citations live in [02-EVIDENCE](./02-EVIDENCE/).

---

*Maintained by [Jordi Catafal](https://x.com/jorcagra). Issues and pull requests welcome.*
