# 03 — Anatomy

> How to write a SKILL.md that actually runs. The canonical authoring guide.

My first three SOPs produced garbage. Not because the model failed. Because I wrote them like prompts.

A prompt says: give me X. A process says: do A, check B, if C then D, produce E in format F. The failure mode of a prompt is a bad answer. The failure mode of a SOP is a decision branch you didn't define. The model hits a fork, invents a path, and confidently produces the wrong thing.

This chapter is how to avoid that. It assumes you've read [`01-CONCEPT`](../01-CONCEPT/) and want to know how to write one yourself. The principles cited (#1, #2, etc.) are defined in [`04-RUBRIC/principles.md`](../04-RUBRIC/principles.md).

---

## The fast path (5 principles)

If you only remember five things, remember these. They cover ~70% of what separates good Procedural skills from bad ones in the 50-skill corpus survey:

1. **Description as router (#1).** YAML `description` is routing logic. Include anti-triggers ("Do NOT use for..."). Only 6% of community skills do this.
2. **Phase 0 routing (#2).** First phase classifies the request and identifies STOP conditions before any work runs.
3. **Exit conditions as binary questions (#10).** "Exit when you can answer X" — not "exit when complete."
4. **Quality gates with all 3 parts (#12).** Check + failure condition + recovery path. Without the recovery path, the model invents one.
5. **Output spec, defined first (#11, #20).** Format, sections, length, per-section content rules. Define before phases; phases are the path.

The rest of this chapter walks through these in detail, plus the other 17 principles for cases where they apply.

---

## The mental model

You're writing for something that interprets instructions **literally at structure points** and **creatively at content points**.

At a decision branch — *"if fewer than 5 sources, expand the search before continuing"* — the model follows the instruction exactly. At a content task — *"synthesize the findings"* — it uses judgment. The job is being explicit about the former and leaving room for the latter.

Most first SOPs get this backwards: vague at the structure level, prescriptive at the content level. Flip that.

---

## The two parts of a SKILL.md

A SKILL.md has two parts: a YAML header and a Markdown body. Both are load-bearing.

### The YAML header — routing logic, not metadata

Two required fields:

```yaml
---
name: skill-name
description: What this does, when to invoke it, and when NOT to
---
```

`name` is the slash command. The `description` is **routing logic**, not metadata (rubric principle #1). The model reads it before deciding whether to load the skill body. A vague description loads a 600-line pipeline on a 2-sentence query.

The `/deep-research` skill's description ends with: *"Do NOT use for simple lookups, debugging, or questions answerable with 1-2 searches."* That line matters. Write the **anti-triggers** explicitly. The 50-skill survey found only 6% of community skills include anti-triggers in YAML — this is the highest-leverage single fix most skills need.

Optional fields worth knowing:
- `tools: [...]` — explicit tool allowlist; principle #14 (Context scope)
- `composed_skills: [...]` — composition graph metadata; principle #19

### The Markdown body — the process itself

Every working SOP needs four things, each mapped to one or more rubric principles:

1. **Phases with explicit exit conditions** (#2 Route before work, #10 Exit = question)
2. **Decision branches at every fork** (#2 Route before work, #3 Modes)
3. **Quality gates that trigger loops, not just checks** (#12 Gates = 3 parts, #21 Decision class drives gating)
4. **Output spec that leaves nothing to interpretation** (#11 Output spec, #20 Output-first)

Each of these is detailed below.

---

## The four required components

### 1. Phases with explicit exit conditions

"Research phase" is too vague. *"Retrieve: run parallel searches across these 5 angles. Exit when you have 15+ sources"* is a phase. **The exit condition is what makes it a phase rather than a vague instruction.**

Phrase exit conditions as binary, answerable questions (principle #10):

> Bad: "Exit when research is complete."
> Good: "Exit when you can answer: *what has this person been doing in the last 90 days?*"

The first is circular — the model decides what complete means. The second forces a specific assertion the model has to commit to.

### 2. Decision branches at every fork

If you don't write the branch, the model invents one.

> "If fewer than 5 sources found, expand search to adjacent topics before continuing."

Phase 0 routing is the most important — it sets the path before any work runs (principle #2). The `/deep-research` SOP opens with a literal decision tree: *Simple lookup? Stop. Complex analysis? Continue. Mode selection? Map to time estimate.* Every fork, written out.

### 3. Quality gates with all three parts

A quality gate isn't *"verify the output."* It has all three parts (principle #12):

- **Check** — what specific property to verify
- **Failure condition** — what "fail" looks like concretely
- **Recovery path** — return to which phase, with which instruction

Example, all three parts in one sentence:

> "If the synthesis doesn't address at least 3 of the 5 research questions from Phase 1, return to the retrieve phase and expand coverage."

Without a recovery path, the model hits a failure and invents its own next step. The 50-skill survey found 26% of community skills have quality gates at all, and most of those are missing the recovery path. **This is the single biggest gap between rubric and practice.**

The `/deep-research` SOP has a full critique phase where the model red-teams its own synthesis. If the critique surfaces a material gap, it loops back to retrieve. That single loop accounts for most of the quality difference between one-shot queries and a real research pipeline.

### 4. Output spec — nothing left to interpretation

Format, sections, file location, length, per-section content rules. Principle #11.

The strongest output specs in the corpus are honest about omission:

> "8-10 bullets each containing a concrete claim. Skip this section entirely if all terms are common knowledge. If nothing applies to current work: write 'No direct application' — do not force it." — `tapestry/article-extractor`

Honest omission rules prevent bloat. The output spec should also include **anti-templates** for creative skills (principle #11 with #22 voice rules):

> "Avoid purple gradients, generic AI aesthetics, default Inter font." — `anthropic-canvas-design`

---

## Worked example: `pre-call`

The skill in [`examples/pre-call/SKILL.md`](../examples/pre-call/SKILL.md) is the canonical worked example referenced from the rubric. Here's why it's the canonical example: it's the simplest skill that demonstrates all four required components.

### Goal

Before a scheduled call with someone new, generate a 3-minute briefing. Background, recent work, company context, three concrete talking points.

### The full skill

```yaml
---
name: pre-call
description: Research a person before a call or meeting. Use when you have a
scheduled meeting with someone new in the next 24-48 hours. Provide their name
and company. Do NOT use for people you already know or recurring contacts.
---
```

```markdown
# Pre-Call Research

## Context
Goal: a briefing the user can read in 3 minutes before the call.
Recency matters more than career history — focus on the last 90 days.

## Phase 1: Person
Search for their LinkedIn, recent writing, talks, and public posts.
Capture: current role, how long they've been there, 1-2 things they've
recently shipped or written, anything public from the last 90 days.

Exit condition: Can you answer "what has this person been doing and
what do they care about right now"?

## Phase 2: Company
If founder or executive: focus on funding news, product direction, recent launches.
If IC or manager: focus on the product area relevant to their role.

Exit condition: Can you answer "what is this company focused on right now"?

## Quality Check
Do the talking points reference something they specifically built, wrote,
or said? If not: return to Phase 1 and find one concrete thing.
Is the company context from the last 90 days? If not: return to Phase 2.

## Output

# Pre-Call Brief: [Name] @ [Company]

**Background:** [2 sentences — role, tenure, relevant background]
**Recent work:** [1-2 specific things they've shipped or published]
**Company context:** [What they do + what they're focused on now]

**Talking points:**
1. [Ties directly to something they built or said]
2. [Connects to their current focus]
3. [A question that shows you've read their work]
```

One unstated dependency the file doesn't mention: **it needs web search enabled**. Without it, the model fabricates. (Worth mentioning in the skill's accompanying README.)

### Why each part is worded the way it is

- **Description as routing logic** — *"Do NOT use for people you already know or recurring contacts"* prevents the skill from running on your co-founder when you mention them in passing.
- **Exit conditions as binary questions** — *"Can you answer X?"* is harder to shortcut than *"exit when complete."* The model has to commit to a specific assertion.
- **Quality gate with all three parts** — *"If the talking points don't reference something they specifically built, return to Phase 1, find one concrete thing"* — check, failure condition, recovery path, all in one sentence.
- **Decision branches in Phase 2** — founder vs IC vs manager routes to different research foci. Written out.
- **Output spec with named sections** — six sections, exact format, no ambiguity.

This skill scores well across the rubric because each component does its job. It's also intentionally short — under 60 lines including YAML. **Most skills should start at this size and grow only when failure modes demand it.**

---

## The three parts most people underwrite

Across the 50-skill survey and the n=4 evaluation, three components are consistently the weakest. If you're going to over-invest somewhere, invest here.

### Description as routing logic

Most descriptions read as project taglines: *"A skill for research."* That's metadata. A real description carries trigger phrases AND anti-triggers:

> "Use when you have a scheduled meeting with someone new in the next 24-48 hours. Provide their name and company. Do NOT use for people you already know or recurring contacts."

The model reads this before deciding whether to invoke. Anti-triggers stop a 600-line pipeline from loading on a query that doesn't need it.

### Exit conditions as tests, not statements

*"Exit when research is complete"* is circular. The model decides what complete means and moves on too early. *"Exit when you can answer [specific question]"* is harder to shortcut: it forces a specific assertion rather than a vague one.

The model can still pass itself on a weak answer, but it has to commit to one. Each phase ends with a question for exactly this reason.

### Quality gates with a recovery path

*"Verify the output"* tells the model nothing. Three parts, all required:

- The check (*"do the talking points reference something they specifically built?"*)
- The failure condition (*"if not"*)
- The recovery path (*"return to Phase 1, find one concrete thing"*)

The loop-back isn't guaranteed — the model grades its own homework — but an explicit condition cuts the "polished-looking but wrong" failure mode significantly. **Read the output anyway.**

---

## Before you write yours

Before writing a single phase, nail down two things:

1. **What the output looks like.** Format, sections, length, content rules. Principle #20 — output-first thinking. The phases are the path to get there. If you can't describe the output precisely, the phases will ramble.

2. **Where the workflow breaks.** The places it breaks become quality gates. The places it branches become decision trees. Both written explicitly before you touch a phase. The model invents missing forks, and they'll point toward looking-done rather than toward correctness.

Exit conditions fall out of this. For each phase: what answer would tell you this stage is done? If you can't state it as a yes/no test, you don't know enough about the phase yet.

---

## A minimal starting template

```markdown
---
name: your-skill
description: What this does. When to invoke it. When NOT to.
---

# Skill Name

## Context
What the model needs to know before starting.

## Phase 1: [Name]
What to do here.
Exit condition: Can you answer "[specific question]"? Yes → proceed. No → [action].

## Phase 2: [Name]
What to do here.
If [condition], do [X]. If [other condition], do [Y].
Exit condition: Can you answer "[specific question]"? Yes → proceed. No → [action].

## Quality Check
Before producing output: verify [specific criteria].
If not met: return to Phase [N].

## Output
[Exact format, sections, file location, length]
```

Start with two phases. Add quality gates as you discover failure modes. **Don't write the 600-line version first.**

---

## Iteration

When it breaks (and it will), the loop is short: read the execution, find the phase where it went sideways, add the missing gate or branch, run again.

You're editing prose. My `/deep-research` SOP started at 80 lines. It's 600 now. Each version fixed one specific failure mode I'd observed.

Karpathy's autoresearch pattern applied to skills: run the pipeline, evaluate the output against the rubric, mutate the SOP, run again. Keep what scores better. The quality jumps are noticeable after three or four cycles. See [`05-EVALUATION/methodology.md`](../05-EVALUATION/methodology.md) for the rubric-driven evaluation protocol.

---

## What to build first

Pick the simplest workflow you repeat at least once a week. Write the SOP for it. Keep it under 100 lines. Run it.

The goal of the first one isn't to model a complex pipeline. It's to **close the loop once: blank file to working slash command.** That's where the leverage actually is.

The first version's job is just to close the loop once. The quality gate probably won't trigger on the first run. But it will make the failure visible. Read the output. You'll see exactly where to add it.

The concept is easy. The first working SOP is where most people stop. Don't.

---

## Choosing the archetype

Before writing the first phase, decide: what archetype is this skill?

- **Procedural** — multi-step workflow with ordering, gates, exits. Default. Apply the full rubric.
- **Reference** — library/API documentation reformatted as SKILL.md. Don't add gates or exits; they don't fit. Focus on description, output spec, and worked code examples.
- **Creative** — output-spec-and-voice driven. Lean on principle #11 (output spec, including anti-templates) and #22 (voice rules). Don't force gates.

See [`04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) for the applicability matrix — which principles apply to which archetypes. A skill that doesn't fit cleanly can declare itself **Hybrid** and apply the principles of the dominant mode.

---

## Using this guide as a Claude Code prompt

Paste this chapter into Claude Code, then add:

```
Build me a SKILL.md using the template and principles above.

Workflow: [what you're automating, step by step]
Where it breaks: [what usually goes wrong when you do this manually]
Output: [what the final result should look like — format, sections, length]
Archetype: [Procedural / Reference / Creative / Hybrid]
```

Those four lines are what Claude can't fill in on its own. Or use the [`meta-paap`](../06-META-PAAP/) skill, which generates the same output with elicitation prompts and self-critique.

---

## Cross-references

- [`01-CONCEPT`](../01-CONCEPT/) — Why PaaP, why now
- [`04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — The 22 principles, with applicability matrix and grading scale
- [`04-RUBRIC/scoring-template.md`](../04-RUBRIC/scoring-template.md) — How to score your finished skill
- [`examples/pre-call/SKILL.md`](../examples/pre-call/SKILL.md) — The runnable worked-example artifact
- [`06-META-PAAP/`](../06-META-PAAP/) — The skill that generates skills
