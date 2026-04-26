# Architecture Checklist — PaaP Skill Design

Load this file during Phase 2 of meta-paap. Work through each decision point
against the elicitation answers from Phase 1. Each principle is a yes/no decision
that adds a specific component to the generated SKILL.md.

---

## 1. Description as Router

**Question:** Are there at least 2 scenarios where someone might incorrectly invoke this skill?

**If yes:** Write those scenarios as explicit "Do NOT use for..." lines in the description.
The model reads the description before invoking the skill. Anti-triggers prevent
the skill from running when it shouldn't.

**Pattern:**
```
description: [What it does]. Use when [trigger condition].
Do NOT use for [wrong use case 1]. Do NOT use for [wrong use case 2].
```

---

## 2. Upfront Decision Gate

**Question:** Are there different request types that should route to different execution paths?

**If yes:** Add a Phase 0 decision tree in code block format before any phases.
Every skill needs at least a minimum gate: "Is this the right tool for this request?"

**Pattern:**
```
## Phase 0 — Routing
Is [condition A]? → [path A]
Is [condition B]? → [path B]
Else: → [default path]
```

---

## 3. Modes

**Question:** Should the skill run at different depths depending on context (e.g., quick vs. thorough)?

**If yes:** Define modes in Phase 0. Mode selection should be inferred from context signals,
not asked (unless truly ambiguous). Each mode maps to a different subset of phases or depth.

**Pattern:**
```
Quick mode: Phases 1, 3 only. ~5 min.
Standard mode: All phases. ~15 min. [DEFAULT]
Deep mode: All phases + extended Phase 2. ~30 min.
```

---

## 4. Persistent State

**Question:** Is this workflow long enough that an interruption would waste significant work?
Or does it need to pass context between multiple agents?

**If yes:** Include a state file pattern. Write state after every phase.

**Pattern:**
```json
{
  "skill_name": "[name]",
  "run_id": "[timestamp-slug]",
  "phases_complete": [],
  "current_phase": "[phase-name]",
  "output_dir": "[path]",
  "key_context": {}
}
```

Include a Resume Protocol:
```
## Resume Protocol
If [state-file] exists in working directory: read it, skip to current_phase.
```

---

## 5. Parallel Execution

**Question:** Are there 2+ independent sub-tasks that don't depend on each other's output?

**If yes:** Design a parallel-burst phase. All agents launch in ONE message as simultaneous
Task tool calls. Never sequential. State this explicitly in the skill.

**Pattern:**
```
## Phase N — [Name] (Parallel)
Launch all [N] agents simultaneously in a single message.
Do NOT launch sequentially.

Agent A — [Persona name]
[Persona spec...]

Agent B — [Persona name]
[Persona spec...]
```

**Critical:** Every parallel-burst phase requires a synthesis phase after it (see #8).

---

## 6. Agent Persona Design

**Question:** Does the parallel phase need agents with distinct perspectives?

**If yes:** Design personas with behavioral specs, not just role titles. A persona spec answers:
- What does this agent focus on?
- What does this agent deliberately ignore?
- What is this agent's emotional/professional disposition?
- What specific output format does this agent produce?

**Weak (avoid):** `Agent A — Research Agent: Research the topic.`

**Strong (use):**
```
Agent A — The Skeptic
Persona: A practitioner who has tried 3 similar approaches in the past 2 years
and been disappointed by each. Time-poor. Change-averse.
Lens: adoption barriers, what would make them reject this immediately.
Output: 3 specific objections, each tied to a concrete detail in the input.
End with: "The one thing that would change my mind: [specific condition]."
```

---

## 7. Files as Inter-Agent Protocol

**Question:** Does the skill use multiple agents or phases that need to share information?

**If yes:** Design the communication through files, not model memory.
Each agent writes to a named file. The next agent reads that file.
Name files systematically: `[NN]-[phase-name]-[agent-role].md`

**Pattern:**
```
Agent A writes: {OUTPUT_DIR}/01-research.md
Agent B reads: {OUTPUT_DIR}/01-research.md
Agent B writes: {OUTPUT_DIR}/02-analysis.md
```

---

## 8. Synthesis Phase

**Question:** Does the skill have any parallel-burst phase?

**If yes (mandatory):** Add a dedicated synthesis phase immediately after the parallel burst.
Synthesis must include explicit priority rules — which agent's output wins which decisions.
Without priority rules, the synthesis agent invents its own arbitration.

**Pattern:**
```
## Phase N+1 — Synthesis
Agent reads all [N] parallel outputs.
Priority rules:
- [Agent A] wins: [specific decision domain]
- [Agent B] wins: [other decision domain]
- [Agent C] wins: [other decision domain]
Conflicts (where agents disagree): [how to handle]
```

---

## 9. Human Gate

**Question:** Does the workflow require human judgment, personal knowledge, or approval
at any point that the model cannot provide?

**If yes:** Design a human gate. Position it after the model has enough context
to ask specific, meaningful questions — not at the start.

The questions should be derived from markers left by previous phases, not pre-scripted.

**Pattern:**
```
## Phase N — Human Gate
Read [previous output file]. Extract all [HUMAN INPUT NEEDED: ...] markers.
Use AskUserQuestion:
  "To complete this, I need your input on [N] points:
  [1] [specific question derived from context]
  [2] [specific question derived from context]"
Wait for response. Save to {OUTPUT_DIR}/[NN]-human-inputs.md.
Continue to Phase N+1.
```

---

## 10. Exit Conditions

**Applies to:** Every phase in the skill.

Exit conditions must be binary questions, not evaluations.

**Weak (avoid):** `Exit when research is complete.`
**Weak (avoid):** `Exit when the output looks good.`

**Strong (use):** `Exit condition: Can you answer "[specific question]"? Yes → proceed. No → [action].`

For each phase, ask: "What specific thing would tell me this phase accomplished its job?"
That thing becomes the exit condition question.

---

## 11. Output Specification

**Applies to:** Every skill.

The output spec must leave nothing to interpretation. Unspecified fields get invented.

**Required fields:**
- File name (exact, no variables unresolved)
- File path (resolved or with resolution pattern)
- Format (markdown, JSON, HTML, plain text)
- Every required section, named
- Length as a specific number or range (not "appropriate" or "reasonable")
- Any special format requirements (citation style, heading levels, code blocks)

**Pattern:**
```
## Output
File: {OUTPUT_DIR}/final-[slug].md
Format: Markdown

Required sections:
# [Title]
## Summary (2-3 sentences)
## [Section A] (200-400 words)
## [Section B] (3-5 bullet points with reasoning)
## Next Steps (numbered list, 3 items)

Length: 500-800 words total.
```

---

## 12. Quality Gates

**Question:** What does failure look like for each phase? What specific property of the output
indicates the phase didn't do its job?

For each identifiable failure mode: design a quality gate with all three required parts.

**Required parts:**
1. The check (specific property to verify — binary, not subjective)
2. The failure condition (what "fail" looks like concretely)
3. The recovery path (return to Phase N with this specific instruction)

**Weak (avoid):** `Verify the output quality before proceeding.`

**Strong (use):**
```
Quality gate: Do the outputs reference [specific thing from input]?
If not: return to Phase [N] with instruction: "You missed [X]. Focus specifically on [Y]."
```

---

## 13. External Prompt Storage

**Question:** Are any agent prompts longer than ~100 words, or likely to be updated independently?

**If yes:** Store those prompts in `./references/[phase-name]-agents.md`.
Reference them in the main SKILL.md: "Load agent prompt from `./references/phase-agents.md` → [section name]."
This keeps the main skill readable and makes agent prompts editable without touching the architecture.

---

## 14. Context Scoping Per Agent

**Applies to:** Every parallel-burst phase and every sub-agent.

Each agent should receive only what it needs. Enumerate it explicitly:

**Pattern:**
```
Agent receives: [output_dir path], [specific file it reads], [its role spec].
Agent does NOT receive: [other agents' outputs] (until synthesis phase).
```

Agents with too much context produce worse output on their specific task.

---

## 15. Progress Reporting

**Question:** Will this skill run for more than ~2 minutes?

**If yes:** Add progress announcements after each phase.
The user must know the skill is working, not stuck.

**Pattern:**
```
After Phase N completes:
Print: "Phase [N] — [Name] complete. ([key stat from this phase])"
```

For long skills: update a state file or report file after each phase.

---

## 16. Error Handling

**Applies to:** Every skill.

Minimum: a 3-row error table mapping specific errors to specific actions.
Generic "if error, stop" is useless. The model needs to know what to do.

**Required rows:**
1. The most likely failure mode from the elicitation (Phase 1, question 2)
2. A tool unavailability scenario (e.g., web search not enabled, file not found)
3. Unexpected interruption → read state file, resume

**Pattern:**
```
## Error Handling
| Error | Action |
|---|---|
| [primary failure mode] | [specific response — not "stop"] |
| [tool unavailable] | [fallback or graceful degradation] |
| Interrupted mid-run | Read state file, resume from current_phase |
```

---

## 17. Autonomy Principle

**Applies to:** Every skill.

Default behavior: proceed autonomously. Only stop when:
- The request is genuinely incomprehensible (not just ambiguous)
- Proceeding would waste significant work in the wrong direction
- A human gate is explicitly designed into the skill (see #9)

State this explicitly if the skill has complex mode selection:
"If mode is unclear: proceed with [default mode]. User will redirect if incorrect."

---

## 18. Portability — Runtime Path Resolution

**Question:** Does the skill reference files that might be in different locations on different machines?

**If yes:** Resolve paths at runtime using vault-first, fallback pattern:

**Pattern:**
```
RESOURCE_PATH = [primary location]
FALLBACK_PATH = [bundled fallback within the skill folder]

If file exists at RESOURCE_PATH: use it
Else if file exists at FALLBACK_PATH: use it
Else: note limitation, proceed without the resource
```

Never hardcode absolute paths. Paths that work on the author's machine fail everywhere else.

---

## 19. Skill Composition

**Question:** Does any phase of this workflow already have a good skill that handles it?
(Answered during Phase 1.5 of meta-paap.)

**If yes:** Compose that skill rather than rebuilding its logic.

**Pattern:**
```
COMPOSED_SKILL_PATH = [primary location]
FALLBACK_PATH = [alternative location]

Resolve path at runtime.
Pass the skill file path to the agent handling Phase N.
The agent reads the skill and follows its methodology for that phase.
```

Document the dependency in the YAML header:
```yaml
composed_skills:
  - name: [skill-name]
    phase: N
    purpose: [what it handles]
```

---

## 20. Output-First Design Verification

**Final check before writing Phase 3.**

Before generating, confirm:
- The output spec is complete (all fields specified, no vague terms)
- Every phase connects to the output (each phase produces something the next phase needs,
  ultimately leading to the output)
- The quality gates check properties of the final output, not intermediate state
- The exit conditions of the final phase confirm the output is ready

If any phase produces nothing that leads toward the output: remove it.
If any output field is still unspecified: specify it now, before generating.

---

## 21. Persona Depth — Iron Law + Rationalizations to Reject (v2, principle #6 + #22)

**Trigger:** the skill enforces *behavioral discipline* — a non-negotiable stance the model would otherwise erode. Examples: TDD ("write the test first"), humanizer ("kill the AI signature even when it sounds fine"), refusal-by-default ("don't auto-research without approval"), voice rules ("no banned vocabulary regardless of fluency").

**Anti-pattern:** "You are a senior engineer." This is decoration. The model already tries to be one; the role-framing produces no behavior change.

**The pattern (from `obra/test-driven-development` and gstack review preambles):**

```markdown
## Persona

**Iron Law:** Write the failing test first. Make it red, then green. Never the other way.

**Rationalizations to reject:**

| The model will say | Why it's wrong | What to do instead |
|---|---|---|
| "Just one quick fix without a test" | Untested code is unmeasurable; "quick" debt compounds; the bug WILL recur | Write the failing test first, then the fix. No exceptions. |
| "The test is obvious — skip it" | Obvious-to-you ≠ caught-by-CI; obvious tests are the cheapest to write | Write it anyway. Cost: 90 seconds. Benefit: regression coverage forever. |
| "We'll add tests later" | "Later" never arrives; tested-late ≠ tested | Stop. Write the test now. Or don't ship. |
```

**How to source rationalizations (≥3 rows required):**

1. **From the workflow's failure modes** (Phase 1 question 2 in meta-paap elicitation): every "where it breaks" is a rationalization the model would produce.
2. **From the workflow's domain** — every discipline has known bad arguments models produce against it. If you've worked in this domain, you know them.
3. **If you can't list 3** — ask the user explicitly: *"What bad arguments do you find yourself rejecting most often when you do this manually?"*

**N/A justification rule:** Pure Reference skills (library docs reformatted) and pure data-transformation skills (in → out, no discipline) mark this N/A in the architecture spec. The bar is whether the skill *enforces* a behavior, not whether it *describes* one.

**Why this beats role-framing:** the rationalization table is *concrete* (the model sees the exact bad argument it would produce and the counter); role-framing is *aspirational* (the model nods along but doesn't change behavior on borderline cases).

---

## 22. Self-Observation — write+read learnings loop (v2, principle #24)

**Trigger:** the skill is procedural with state (STATE: yes per Phase 2). Short skills with STATE: no mark this N/A.

**The pattern:**

```markdown
## Self-observation

**Write side (after every successful run):**

Append a one-line entry to `~/.claude/[skill-name]/learnings.jsonl`:

{"timestamp":"<iso>", "input_summary":"<1-sentence reduction>", "key_decisions":[<list>], "open_questions":[<list>]}

**Read side (before any new run):**

Read `~/.claude/[skill-name]/learnings.jsonl` (if present) and:
- Find prior entries where input_summary shares ≥2 key terms with the current input
- Surface them inline as "Prior similar runs" before proceeding
- Do NOT auto-apply prior decisions — just inform the current run with the prior context

**Corruption handling:** if the file is unreadable or contains invalid JSON, skip the lookup and log a one-line warning. Do not halt — corrupted state should never block a new run.
```

**Why this matters:** a stateless skill relearns the same lessons every invocation. A self-observing skill stops suggesting the same broken approach the user already rejected last time.

**Mechanism is intentionally simple.** Substring match on key terms is not RAG. It's a designed-for-prose feature in the v0.4 era of agent skills. The point is the *closed loop* (write + read, both present), not sophistication.

**N/A justification rule:** Reference skills, pure-transformation skills, and short Procedural skills (<2 min runtime, no resume needed) mark this N/A. The bar is whether prior-run memory would change the next run's behavior usefully — for a one-shot translator, it wouldn't.

---

## Quick Reference — What Triggers What

| Workflow signal | Architecture addition |
|---|---|
| Multiple independent perspectives needed | Parallel-burst + synthesis (#5, #6, #8) |
| Long-running or multi-session | State + resume protocol (#4) |
| Human knowledge required mid-process | Human gate (#9) |
| Different complexity levels | Modes (#3) |
| Multiple agents sharing information | Files as protocol (#7) |
| Variable depth per use case | Mode selection in Phase 0 (#3) |
| Risk of model shortcuts | Quality gates (#12) |
| Existing skill covers a phase | Skill composition (#19) |
| Personal experience needed | Human gate + experience prompts (#9) |
| Tool dependency | Declare in header, add error handling (#16) |
| **Skill enforces a behavioral discipline (v2)** | **Iron Law + Rationalizations to Reject table (#21)** |
| **Procedural skill with state, recurring use (v2)** | **Self-observation: learnings.jsonl write+read loop (#22)** |
| **Skill calls AskUserQuestion AND may be invoked by another agent (v2)** | **Spawn-detection: non-interactive fallback OR interactive-only declaration (#25 in 04-RUBRIC/principles.md)** |
| **Skill references external paths (v2)** | **Host-portable: relative or `~/.claude/...` paths only; no `/Users/<author>/...` (#23)** |
