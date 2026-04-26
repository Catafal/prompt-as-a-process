---
name: meta-paap
version: 2.0
description: Designs and generates a production-ready Claude Code skill (SKILL.md) by applying Prompt As A Process architecture patterns. Use when you want to turn a repeatable multi-step workflow into a slash command. Provide a workflow description — rough notes or a few sentences is enough. Do NOT use for single-step tasks, simple one-shot prompts, or anything that doesn't benefit from phased execution with quality gates.
---

# meta-paap — Skill Generator (v2.0)

Turns a workflow description into a production-ready SKILL.md.
Applies the architecture patterns documented in the [25 principles](../04-RUBRIC/principles.md), with concrete shapes drawn from mature reference skills like `/deep-research`, `/blog-factory`, and `obra/test-driven-development`.

**v2.0 changes (added 2026-04-26 in response to v0.3 priority #3 + #4 findings):**
- **Persona depth**: skills enforcing behavioral discipline now produce an **Iron Law + Rationalizations to Reject** table (the pattern that made `obra/test-driven-development` distinctive). v0.3 priority #3 found generated skills consistently lacked this depth on humanizer-class voice work.
- **Self-observation loop**: meta-paap reads `~/.claude/meta-paap/learnings.jsonl` on every run (Phase 1.5b) and appends to it after self-critique (Phase 4). Closes the framework's own honest C grade on principle #24, externally validated by GPT-5.4 (7/7 near-F) and Gemini-3 (5/6 F-or-near-F) at the corpus level.
- **v0.3 principle checks**: Phase 4 self-critique now explicitly checks #23 (host-portable), #24 (self-observation), and #25 (spawn-detection).
- Backwards-compatible — v1 skills still run unchanged; v2 generates higher-depth output for new skills.

---

## Pre-Phase — Invocation Parsing

Before classification, parse the invocation for explicit skill references.

Scan the user's message for any slash command names (e.g., `/deep-research`, `/humanizer`,
`/blog-factory`) or plain skill name mentions (e.g., "use deep-research", "with the humanizer").

```
If skill names found in invocation:
    EXPLICITLY_REQUESTED = [list of named skills]
    Note: these will be composed regardless of the Phase 1.5 relevance filter.
    Do not ask whether to include them — the user already said so.

Else:
    EXPLICITLY_REQUESTED = []
```

This list is carried through to Phase 1.5.

---

## Phase 0 — Classification

Before anything else, classify the workflow from context. Do not ask — infer.

```
Is this a single-step task ("summarize this", "translate that", "write X")?
→ STOP. This doesn't need a skill — it needs a prompt.
  Tell the user: "This workflow is a single step. A SKILL.md would add overhead
  without value. Use a direct prompt instead. If you want, I can write that prompt."

Does the workflow have 2-3 linear phases, no parallel agents, no human gate needed?
→ LEAN PATH. Generate a simple skill using the lean template. Skip to Phase 3.

Does the workflow require any of: multiple independent perspectives, iterative rounds,
human judgment mid-process, parallel agents, or persistent state across sessions?
→ FULL PATH. Continue to Phase 1.
```

If classification is ambiguous from context: proceed with FULL PATH.
You can always simplify in Phase 2.

---

## Phase 1 — Elicitation

Use AskUserQuestion. Ask all questions in ONE message, numbered.
Wait for the full reply before continuing.

```
I'll design the skill architecture. To do it right, I need your answers to these:

1. Walk me through the workflow step by step — what do you do manually, in order?
   (Be specific. "Research the topic" is less useful than "search LinkedIn, then
   read their recent posts, then check the company news.")

2. Where does it break? What goes wrong most often when you do this manually?
   (This becomes the quality gate. Be honest about the failure mode.)

3. What does the final output look like?
   (Format, sections, approximate length. The more specific, the better the output spec.)

4. Does it need web search, file access, code execution, or other external tools?

5. How often do you run this, and does each run need to resume if interrupted?
   (Frequency + resumability determines whether the skill needs persistent state.)

6. Are there specific installed skills you want to use inside this workflow?
   (Name them by slash command — e.g., /deep-research, /humanizer. Say "none" if unsure
   and I'll suggest candidates in the next step.)
```

If EXPLICITLY_REQUESTED is non-empty from the invocation:
skip question 6 — the user already answered it. Acknowledge it:
"I saw you mentioned [skill names] — I'll include those in the architecture."

---

## Phase 1.5 — Skills Discovery

Consolidate all composition candidates from three sources:

**Source A — Explicitly named in invocation (EXPLICITLY_REQUESTED from Pre-Phase)**
These are confirmed. No need to ask. Resolve their paths now:
```bash
find ~/.claude/skills -name "SKILL.md" 2>/dev/null | xargs grep -l "^name: [skill-name]"
```

**Source B — Named in elicitation question 6**
If the user named additional skills in their answer: add to the confirmed list.
Resolve their paths the same way.

**Source C — Auto-discovered (relevance filter)**
Scan installed skills silently:
```bash
find ~/.claude/skills -name "SKILL.md" 2>/dev/null
```
For each found: read only the YAML header (first 15 lines) to extract `name` and
the first sentence of `description`.

Filter for relevance against the workflow description:
- Workflow involves research/analysis → flag research/search skills
- Workflow involves writing/content → flag writing/humanizer/editorial skills
- Workflow involves lead generation → flag lead research skills
- Workflow involves code → flag code quality/review skills
- Any other domain overlap with the described workflow

Exclude skills already in the confirmed list (Sources A and B).

**Present to user (one AskUserQuestion combining all three sources):**

Build the message as follows:

```
[If confirmed skills exist (Sources A + B):]
Confirmed for composition (you named these):
- /[name]: [first sentence of description — so user can verify it's the right one]

[If auto-discovered candidates exist (Source C):]
I also found [N] installed skill(s) that might be relevant:
- /[name]: [first sentence of description]
- /[name]: [first sentence of description]

[Always include:]
Anything to add or remove from the composition list?
- To include one from the suggestions: tell me which phase it belongs to and what it produces.
- To remove a confirmed one: name it.
- To add a skill not on either list: name the slash command.
- Say "looks good" to proceed with the confirmed list as-is.
```

**If no confirmed skills AND no auto-discovered candidates:**
Skip the presentation. Note "standalone" in the architecture. Proceed to Phase 2.

**After user reply:**
Finalize the COMPOSITION list. Every skill on this list will have:
- Resolved path (or "not found — will design as if standalone for this component")
- Assigned phase
- Expected output

---

## Phase 1.5b — Prior-run lookup (self-observation, v2)

Read prior generations to avoid repeating mistakes and to surface relevant patterns.

```bash
LEARNINGS_PATH = ~/.claude/meta-paap/learnings.jsonl

If file exists at LEARNINGS_PATH:
    Read all entries (one JSON object per line)
    Extract key terms from the current brief (the workflow description from Phase 1)
    For each prior entry:
        Substring-match key terms against entry.brief_summary
        If ≥2 key terms overlap: add to RELEVANT_PRIOR
Else:
    RELEVANT_PRIOR = []
    (First-run case is fine — write side will start the file in Phase 4)
```

**If RELEVANT_PRIOR is non-empty (≥1 match):**

Surface the prior-run summary inline before Phase 2:

```
Prior similar generations found (from ~/.claude/meta-paap/learnings.jsonl):

- /<skill-name> (generated <date>): <brief_summary>
  Architecture: <phases> phases, parallel=<bool>, composed=<list>
  Self-critique fixes: <generation_notes>
  Open questions: <open_questions>

Relevance: this brief shares <N> key terms with the prior generation. Note any patterns you'd want to keep or change.
```

This is *informational only* — it does not auto-apply prior decisions. Phase 2 architecture design proceeds normally; the user (and the model) now have the prior context to consult.

**If LEARNINGS_PATH file is corrupted (invalid JSON on any line):**

Skip the lookup, log a one-line warning to stderr, proceed to Phase 2. Do NOT halt — corrupted state should not block new generations.

---

## Phase 2 — Architecture Design

Load the architecture checklist: `./references/architecture-checklist.md`

Work through each decision point in the checklist against the elicitation answers.
Produce an architecture spec with these fields:

```
SKILL NAME: [slash command name — lowercase, hyphenated]

DESCRIPTION:
  What it does: [one sentence]
  Trigger phrases: [2-3 phrases that should invoke it]
  Anti-triggers: [2-3 explicit "Do NOT use for..." cases]

MODES: [yes/no — if yes, list mode names and what distinguishes them]

PHASES:
  [For each phase:]
  Phase N — [Name] ([type: sequential | parallel-burst | synthesis | human-gate | verification])
    Purpose: [what this phase accomplishes]
    Input: [what it reads — previous phase output, user input, files, etc.]
    Output: [exact file name and what it contains]
    Exit condition: [binary question — "Can you answer: [X]?"]
    If parallel-burst: [list each agent with persona and lens]
    If human-gate: [what question gets asked and when]

PERSONA DEPTH (v2): If the skill enforces behavioral discipline (TDD, voice rules, refusal-by-default, "no AI vocabulary", "always check X before Y", etc.):
  Persona MUST include:
    - Iron Law: [one-sentence non-negotiable behavior the skill enforces]
    - Rationalizations to Reject table (≥3 rows):
      | The model will say | Why it's wrong | What to do instead |
      |---|---|---|
      | [bad argument the model produces in production] | [why it's wrong, in 1 sentence] | [the correct behavior, specific] |
  Generic role-framing ("you are a senior engineer") is rejected — the discipline IS the persona.
  If the skill is purely Reference (library docs reformatted) or pure data-transformation (no discipline being enforced): mark this N/A in the architecture spec.

COMPOSITION: [list skills to compose, or "standalone"]
  For each: skill name | invoked at Phase N | what it produces

STATE: [yes/no — if yes: factory-state.json pattern with fields listed]

QUALITY GATES:
  [For each gate:]
  Gate [N]: Check [X]. If fails: [exact recovery — return to Phase N with instruction Y].

OUTPUT CONTRACT:
  File: [exact path and name]
  Format: [markdown / json / etc.]
  Sections: [list every required section]
  Length: [specific target or constraint]
  Nothing left to interpretation: [confirm or add any remaining specs]

TOOLS REQUIRED: [list: WebSearch / Bash / Write / Read / Task / AskUserQuestion / etc.]

PORTABILITY: [does it need path resolution? vault-first fallback pattern?]
```

**Present the architecture spec to the user before generating:**

```
Here's the architecture I'll use for /[skill-name]:

[architecture spec]

Any changes before I generate? (Or say "build it" to proceed.)
```

Wait for confirmation. If the user says "build it" or equivalent: proceed to Phase 3.
If they request changes: update the architecture spec, present again, wait.

---

## Phase 3 — Generation

**Confirm save path:**
Ask: "Where should I save the SKILL.md? Default: `~/.claude/skills/[skill-name]/SKILL.md`"
If no answer or "default": use the default path. Create directory if it doesn't exist.

**Generate the complete SKILL.md.** Write it section by section using the confirmed architecture.

### Generation rules (apply to every skill generated)

**YAML Header:**
- `name`: the slash command
- `description`: what it does + trigger phrases + at least 2 "Do NOT use for..." lines
- Add `tools: [list]` if the skill requires specific tools that must be enabled

**Phase 0 block (always present):**
Every skill needs a decision tree at the top. At minimum:
- Is this the right tool for this request? → yes/no check
- If modes exist: mode selection logic

**Per phase:**
- Heading: `## Phase N — [Name]`
- What to do (specific instructions, not vague goals)
- For parallel-burst phases: each agent as a named sub-section with persona spec
  - Persona must answer: what does this agent focus on AND what does it deliberately ignore?
- Exit condition at the end of every phase, stated as: `Exit condition: Can you answer "[specific question]"? Yes → proceed. No → [action].`

**Persona depth — Iron Law + Rationalizations (v2, REQUIRED for discipline-enforcing skills):**

If Phase 2's PERSONA DEPTH section flagged this skill as discipline-enforcing, generate the persona block as:

```markdown
## Persona

**Iron Law:** [the one-sentence non-negotiable].

**Rationalizations to reject:**

| The model will say | Why it's wrong | What to do instead |
|---|---|---|
| [bad argument 1, specific to this domain] | [1 sentence] | [specific corrective behavior] |
| [bad argument 2] | [1 sentence] | [specific corrective behavior] |
| [bad argument 3] | [1 sentence] | [specific corrective behavior] |
```

The rationalizations table is *the persona*. Do not also add a separate "you are a senior X" block — that was rejected in v2 as decoration.

**How to source the rationalizations:**
1. From Phase 1 elicitation question 2 ("where does it break?") — failure modes are rationalizations.
2. From the workflow domain — every discipline has known bad arguments models make against it (TDD: "skip the test for one quick fix"; humanizer: "this AI signature isn't that bad, leave it"; refusal-by-default: "this query seems benign, just answer it").
3. If <3 rationalizations come naturally: ask the user explicitly during Phase 2 confirmation: "What bad arguments do you find yourself rejecting most often when you do this manually?"

**Self-observation block (v2, REQUIRED for procedural skills with state):**

If the generated skill has STATE: yes (per Phase 2 architecture), include a self-observation pattern that mirrors meta-paap's own:

```markdown
## Self-observation

After every run, append a one-line entry to `~/.claude/[skill-name]/learnings.jsonl`:

{"timestamp":"<iso>", "input_summary":"<1-sentence reduction>", "key_decisions":[<list>], "open_questions":[<list>]}

Before starting any new run, read `~/.claude/[skill-name]/learnings.jsonl` (if present) and:
- Find prior entries where input_summary shares ≥2 key terms with the current input
- Surface them inline as "Prior similar runs" before proceeding
- Do not auto-apply prior decisions; just inform the current run
```

If STATE: no (short skill, no resume needed): mark this N/A in the architecture spec; do not insert the block.

**Synthesis phases:**
- Must follow every parallel-burst phase
- Must include explicit priority rules: "[Agent A] wins [specific decisions]. [Agent B] wins [other decisions]."
- Without priority rules, the synthesis agent invents its own arbitration

**Human gate phases:**
- Use AskUserQuestion
- Position after enough context exists — never at the start
- Extract the questions from markers left by previous phases, not pre-scripted

**Quality gates section:**
Each gate must have all three parts:
1. The check (what specific property to verify)
2. The failure condition (what "fail" looks like concretely)
3. The recovery path (return to Phase N with this specific instruction)

**Output spec:**
- Exact file name and path (no variables left unresolved)
- Every required section named
- Length as a specific number or range, not "appropriate length"
- Any format requirements (headers, code blocks, citation style, etc.)

**State block (if state = yes):**
Include a `factory-state.json` structure with all required fields.
Include a Resume Protocol section: "If state file exists, read it and continue from current_phase."

**Composition blocks (if composing skills):**
Resolve paths at runtime using this pattern:
```
[SKILL_NAME]_PATH = [primary path]
If file exists at [primary path]: use it
Else if file exists at [fallback path]: use it
Else: proceed without composition, note limitation in output
```

**Error handling:**
At minimum, a 3-row error table:
| Error | Action |
|---|---|
| [most likely failure mode from Phase 1] | [specific response] |
| [second failure mode] | [specific response] |
| Unexpected interruption | Read state file, resume from current_phase |

**Lean path template (for LEAN PATH from Phase 0):**
```
---
name: [skill-name]
description: [what it does]. Use when [trigger]. Do NOT use for [anti-trigger].
---

# [Skill Name]

## Context
[What the model needs to know before starting.]

## Phase 1 — [Name]
[Instructions.]
Exit condition: Can you answer "[specific question]"? Yes → proceed. No → [action].

## Phase 2 — [Name]
[Instructions.]
If [condition]: [do X]. If [other condition]: [do Y].
Exit condition: Can you answer "[specific question]"? Yes → proceed. No → [action].

## Quality Check
[Specific check]. If fails: return to Phase [N].
[Second check]. If fails: return to Phase [N].

## Output
[Exact format, sections, file name, length.]
```

---

## Phase 4 — Self-Critique

Red-team the generated SKILL.md before saving.

**Critical issues (fix before saving — regenerate affected sections):**

| Check | Pass condition | Fix if fail |
|---|---|---|
| Exit conditions | Every phase ends with a binary question | Rewrite as "Can you answer [X]?" |
| Quality gates | Every gate has check + failure condition + recovery path | Add missing parts |
| Parallel without synthesis | No parallel burst exists without a synthesis phase after | Insert synthesis phase |
| Anti-triggers present | Description has at least 1 "Do NOT use for..." | Add 2 anti-triggers |
| Output spec completeness | No field says "appropriate" or "reasonable" | Replace with specific values |
| Tool dependencies declared | Every tool used is listed in header | Add missing tools |
| Composition paths | No hardcoded absolute paths | Replace with runtime resolution pattern |
| **Persona depth (v2)** | **Discipline-enforcing skills have an Iron Law + ≥3-row Rationalizations to Reject table; Reference / pure-transform skills mark this N/A** | **Generate the table from Phase 1 question 2 (failure modes) + workflow-domain known bad arguments; if <3 rationalizations come naturally, ask the user during Phase 2 confirmation** |
| **#23 Host-portable (v2, principle promoted v0.3)** | **No hardcoded `/Users/<author>/...` or `C:\Users\<author>\...` paths; relative paths or `~/.claude/...` patterns used; harness-specific subprocess calls behind explicit flags** | **Replace absolute paths with runtime resolution; if a harness-specific call is genuinely required, gate it on a `--host` flag with a documented default** |
| **#24 Self-observation (v2, principle promoted v0.3)** | **Procedural skills with STATE: yes include a `learnings.jsonl` write+read pattern (write on completion, read on next-run lookup); short skills with STATE: no mark this N/A** | **Insert the self-observation block per the generation rules; if N/A, document why in the architecture spec** |
| **#25 Spawn-detection (v2, principle promoted v0.3)** | **Skills using AskUserQuestion include a non-interactive fallback OR the description states the skill is interactive-only** | **Add `If invoked non-interactively (no TTY, --batch flag, spawned by another agent): skip AskUserQuestion, default to [reasonable default]`; or mark the skill interactive-only in the description** |

**Moderate issues (flag, don't block):**

- Human gate positioned before model has enough context to ask meaningful questions
- State pattern needed but not implemented (resumability gap)
- Missing error handling for the workflow's primary failure mode from Phase 1

Print critique inline before saving:

```
Self-critique (v2 — 11 critical checks + moderate flags):
✅ [checks that passed, including v2 additions: persona depth, #23/#24/#25]
⚠️  Fixed: [critical issues found and corrected, named by check]
ℹ️  Known limitations: [moderate issues — not blocking, worth knowing]
🆕 v2 notes: [whether persona depth applied (and the 3+ rationalizations sourced) OR explicit N/A justification; whether self-observation block included OR explicit N/A justification]
```

If critical fixes were applied: note which sections were regenerated.

---

## Output

Save the SKILL.md to the confirmed path. Create parent directory if needed.

**Self-observation write (v2):**

After saving, append a one-line entry to `~/.claude/meta-paap/learnings.jsonl`:

```bash
LEARNINGS_PATH = ~/.claude/meta-paap/learnings.jsonl
mkdir -p $(dirname LEARNINGS_PATH)

ENTRY = {
  "timestamp": "<iso-8601 now>",
  "skill_name": "/[skill-name]",
  "brief_summary": "<1-sentence reduction of the workflow brief from Phase 1>",
  "architecture": {
    "phases": <N>,
    "parallel": <bool>,
    "state": <bool>,
    "composed": [<list of composed skill names>],
    "discipline_enforcing": <bool — true if Iron Law + Rationalizations table was generated>
  },
  "self_critique_fixes": [<list of fixes applied during Phase 4>],
  "open_questions": [<any unresolved decisions noted during generation>]
}

Append ENTRY as one JSON line to LEARNINGS_PATH (newline at end).
```

If the write fails (disk full, permission denied): log a one-line warning, do not block the save. The SKILL.md is the primary artifact; the learnings entry is the secondary artifact.

Print:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
meta-paap — done
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Skill:    /[skill-name]
Saved:    [full path]
Phases:   [N] ([breakdown: X sequential, Y parallel-burst, Z synthesis])
Agents:   [N parallel agents, or "none"]
Composed: [list of skills composed, or "standalone"]
Gates:    [N quality gates]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
To run: type /[skill-name] in any Claude Code session.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Error Handling

| Situation | Action |
|---|---|
| No installed skills found during discovery | Proceed with standalone design, skip Phase 1.5 |
| User says "none" to composition question | Design standalone, continue |
| Named skill not found on disk | Note in architecture: "Could not resolve /[name] — designing as standalone for that phase. Install the skill and update the path after generation." |
| Named skill found but description doesn't match expected use | Flag to user: "I found /[name] but its description suggests [X]. Is this the right skill for [intended use]?" Wait for confirmation before including. |
| Architecture review reveals contradictory requirements | Note the contradiction, ask which constraint takes priority before proceeding |
| User requests a skill that should be a prompt instead | Explain why, offer to write the prompt instead |
| Phase 3 generates a skill >400 lines | Flag: consider splitting into sub-skills or using external reference files |
