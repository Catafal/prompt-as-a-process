# The 22 Principles

> The architectural rubric for evaluating a SKILL.md. Each principle: definition, why it matters, anti-pattern, concrete example from the corpus, and which archetypes it applies to.

This is the canonical reference for the Prompt-as-a-Process framework. The principles below are derived from analysis of mature hand-written skills, an n=4 evaluation of `meta-paap`-generated skills, a 50-skill empirical survey, and a deep-dive into Garry Tan's gstack repo (50 SKILL.md files at production scale). See [`empirical-validation.md`](./empirical-validation.md) for the bottom-up evidence.

The headline number used to be 20. After corpus validation against 50 community skills, two patterns surfaced consistently enough to promote: principle 21 (decision class drives gating) and principle 22 (voice + writing rules as skill content). Eight other candidates from gstack are documented in [`empirical-validation.md`](./empirical-validation.md) as observed-but-not-yet-promoted.

---

## How to read this rubric

### The three archetypes

Skills come in three legitimate archetypes. Not all principles apply to all archetypes.

**Procedural skill** — Multi-step workflow with ordering, gates, and exits. The skill executes a process. Examples: `obra/test-driven-development`, `trailofbits/agentic-actions-auditor`, `anthropics/skill-creator`, `meta-paap`. Default rubric applies fully.

**Reference skill** — Library or API documentation reformatted as SKILL.md. Description plus tool/method index plus code examples. The skill is read, not executed end-to-end. Examples: `expo-deployment`, `kdense-biopython`, `chrisvoncsefalvay-d3-viz`. Reference skills should NOT be expected to have gates, exits, synthesis, error tables, or persistent state.

**Creative skill** — Output-spec-and-voice driven; aesthetic or qualitative judgment dominates over procedural discipline. Examples: `anthropic-canvas-design`, `anthropic-frontend-design`. Creative skills should have strong output specs, anti-templates, and voice rules — but not gates, exits, or error tables.

A skill that doesn't fit cleanly into one of these archetypes can mark itself **Hybrid** and apply the principles of the dominant mode.

### Applicability matrix

| # | Principle | Procedural | Reference | Creative | Notes |
|---|---|:---:|:---:|:---:|---|
| 1 | Description as router | ✅ | ✅ | ✅ | Universal |
| 2 | Route before work | ✅ | — | — | Procedural-only |
| 3 | Modes | ⚪ | ⚪ | ⚪ | Conditional — only if multiple paths exist |
| 4 | State | ✅ | — | — | Procedural-only |
| 5 | Parallel | ⚪ | — | — | Conditional — only if parallel subtasks exist |
| 6 | Personas / voice | ✅ | — | ✅ | Procedural + Creative |
| 7 | Files = bus | ✅ | — | — | Procedural-only |
| 8 | Synthesis | ✅ | — | — | Procedural-only |
| 9 | Human gate | ✅ | — | — | Procedural-only |
| 10 | Exit = question | ✅ | — | — | Procedural-only |
| 11 | Output spec | ✅ | ✅ | ✅ | Universal |
| 12 | Gates = 3 parts | ✅ | — | — | Procedural-only |
| 13 | External storage | ⚪ | ⚪ | — | Conditional — only if SKILL.md exceeds ~400 lines |
| 14 | Context scope | ✅ | ✅ | ✅ | Universal |
| 15 | Progress | ✅ | ✅ | ✅ | Universal |
| 16 | Errors | ✅ | — | ✅ | Procedural + Creative |
| 17 | Autonomy | ✅ | — | ✅ | Procedural + Creative |
| 18 | Path resolution | ⚪ | ⚪ | ⚪ | Conditional — only if external resources are referenced |
| 19 | Composition | ✅ | ✅ | — | Procedural + Reference |
| 20 | Output-first | ✅ | ✅ | ✅ | Universal |
| 21 | Decision class drives gating | ✅ | — | — | Procedural-only (promoted from gstack candidates) |
| 22 | Voice + writing rules | ✅ | — | ✅ | Procedural + Creative (promoted from gstack candidates) |

**Legend:** ✅ applies — required for full grade · ⚪ conditional — applies only when triggered · — not applicable

### Grading scale

When scoring a skill against any principle:

- **A+** — Exemplary; sets the standard for this principle
- **A** — Fully meets the principle as defined
- **B+** — Meets with one minor gap
- **B** — Mostly meets, one structural shortcut
- **C** — Partially meets; visible failure mode if stressed
- **D** — Largely violates the principle
- **F** — Violates outright
- **N/A** — Doesn't apply to this skill's archetype or design; **must include one-sentence justification**

A skill scoring N/A on a principle marked `⚪ conditional` for its archetype is fine. A skill scoring N/A on a principle marked `✅` for its archetype is a structural gap.

---

## The 22 principles

### 1. Description as router

**Definition:** The YAML `description` field is routing logic, not metadata. It tells the harness when to invoke the skill and, equally important, when NOT to.

**Why it matters:** The model reads the description before deciding whether to load the skill body. A vague description loads a 600-line pipeline on a 2-sentence query. A description with explicit anti-triggers ("Do NOT use for...") prevents over-invocation.

**Anti-pattern:** Treating the description as a project tagline ("A skill for research").

**Concrete example:** `meta-paap` description: *"Designs and generates a production-ready Claude Code skill (SKILL.md) by applying Prompt As A Process architecture patterns. Use when you want to turn a repeatable multi-step workflow into a slash command. Provide a workflow description — rough notes or a few sentences is enough. **Do NOT use for single-step tasks, simple one-shot prompts, or anything that doesn't benefit from phased execution with quality gates.**"*

**Archetypes:** All. Universal — even Reference and Creative skills need routing.

---

### 2. Route before work

**Definition:** A skill's first phase is routing — classifying the request, selecting the path, identifying STOP conditions — before any substantive work runs.

**Why it matters:** Without explicit routing, the model invents a path, often the wrong one. Phase 0 is what makes a skill *resilient to ambiguous invocations*.

**Anti-pattern:** Jumping into Step 1 work immediately. The classic failure: a research skill invoked on a question already answered in the user's message proceeds to spend 10 minutes researching anyway.

**Concrete example:** `trailofbits/agentic-actions-auditor` Phase 0: detect mode (URL vs. local) → parse target → fetch path → STOP if target isn't an AI-actions workflow. Three explicit STOP conditions before any analysis.

**Archetypes:** Procedural-only. Reference and Creative skills don't have a "before any work" phase — they are the work.

---

### 3. Modes

**Definition:** When a skill has multiple legitimate execution paths (auto vs. manual, quick vs. full, lean vs. orchestration), modes are explicit, named, and selected with stated criteria.

**Why it matters:** Implicit modes leak — the model picks based on context cues you didn't anticipate. Explicit modes are auditable.

**Anti-pattern:** "The skill adapts to the situation." It doesn't. It picks one mode and the user is left guessing why.

**Concrete example:** gstack's `plan-ceo-review` declares four modes — `SCOPE EXPANSION`, `SELECTIVE EXPANSION`, `HOLD SCOPE`, `SCOPE REDUCTION` — with context-dependent defaults (greenfield → EXPANSION, hotfix → HOLD).

**Archetypes:** Conditional. Only applies when multiple paths legitimately exist. Linear pipelines that always do the same thing should mark this N/A.

---

### 4. State

**Definition:** Skills that span enough work to potentially fail mid-run write durable state to disk and include a Resume Protocol.

**Why it matters:** Long-horizon skills hit context limits, model errors, or interruptions. Without state, a 30-minute skill that fails at minute 27 starts over.

**Anti-pattern:** Treating state as optional for any skill that runs more than ~5 minutes.

**Concrete example:** `anthropics/skill-creator` writes per-iteration state to `<skill-name>-workspace/iteration-N/eval-N/`, with explicit "If interrupted, read the latest iteration directory to resume."

**Archetypes:** Procedural-only. Short skills can mark N/A with justification ("runs in <2 min, no resume needed").

---

### 5. Parallel

**Definition:** When N independent subtasks exist, the skill explicitly invokes them in parallel and states the rule: *"Single message; do NOT launch sequentially."*

**Why it matters:** Sequential when parallel is possible wastes time. Worse: the model defaults to sequential unless told otherwise, and prose like "research these three topics" gets executed one at a time.

**Anti-pattern:** "Then research X. Then research Y. Then research Z." Three sequential agent invocations on independent inputs.

**Concrete example:** `meta-paap`'s parallel-burst phases include the literal instruction *"Spawn agents A, B, C in a single message. Do NOT launch sequentially."*

**Archetypes:** Procedural-only. **Caveat:** This principle applies only when independent parallel subtasks exist. Skills that are inherently linear (pipelines where each phase depends on the previous one) should mark this N/A — that is not a failure.

---

### 6. Personas / voice

**Definition:** When a skill uses agents (sub-tasks with distinct viewpoints), or when the skill itself enforces a behavioral discipline, it does so through specific persona definitions or voice rules — not generic "you are an expert in X" framing.

**Why it matters:** Generic personas produce generic output. The skills that actually shape behavior name *what to focus on AND what to ignore*, OR list the *rationalizations to reject*. Behavioral discipline beats character framing.

**Anti-pattern:** "You are a senior engineer." This is decoration. The model already tries to be one.

**Concrete examples:**
- `obra/test-driven-development` defines persona-by-rejection: an "Iron Law" plus a "Rationalizations to Reject" table listing the specific bad arguments the model will make ("just one quick fix without a test", "the test is obvious"). Each rejection has a counter.
- gstack's review skills name agent personas with sharp scope: *"Burned by untested edge cases. Trusts tests more than comments, edge case tests more than happy path tests."*

**Archetypes:** Procedural + Creative. Reference skills don't need personas — they're describing libraries, not enforcing discipline.

---

### 7. Files = bus

**Definition:** Multi-phase skills pass data between phases via numbered files (e.g., `01-spec.md`, `02-research.md`, `03-synthesis.md`), not via in-memory variables or implicit context.

**Why it matters:** Files survive context resets. They're auditable. They're the cleanest way to compose phases without coupling them.

**Anti-pattern:** "Then synthesize the research." Where? In what file? Read by which phase?

**Concrete example:** gstack uses standardized JSONL bus across all skills (`~/.gstack/projects/$SLUG/{ceo-plans,timeline.jsonl,learnings.jsonl}`). Skills don't invoke each other directly; they read and write filesystem artifacts.

**Archetypes:** Procedural-only.

---

### 8. Synthesis

**Definition:** Whenever parallel subtasks produce independent outputs, an explicit synthesis phase merges them with stated priority rules and conflict resolution.

**Why it matters:** Without priority rules, the synthesis agent invents arbitration on the fly. Same input, different runs, different outputs.

**Anti-pattern:** "Synthesize the findings." The model decides which findings to keep, which to drop, by criteria you didn't define.

**Concrete example:** gstack's `autoplan` Phase 1 synthesis with phase-context tiebreakers — *"CEO phase: P1 (completeness) + P2 (boil lakes) dominate. Eng phase: P5 (explicit) + P3 (pragmatic) dominate."* Different phases, different priority weights.

**Archetypes:** Procedural-only.

---

### 9. Human gate

**Definition:** When a skill requires human judgment that the model can't substitute for (taste, ethics, irreversible action), there's an explicit checkpoint with `AskUserQuestion` and the skill genuinely waits.

**Why it matters:** Skipped human gates produce confidently-wrong autonomous output. Pretending the gate is optional defeats the point.

**Anti-pattern:** "Optionally, check with the user." The model picks "skip" every time.

**Concrete example:** `emaynard/family-history-planning` opens with *"ABSOLUTELY PROHIBITED: DO NOT perform unsolicited web searches"* — the entire skill exists to refuse-until-user-approves. The human gate IS the skill.

**Archetypes:** Procedural-only.

---

### 10. Exit = question

**Definition:** Every phase exit condition is phrased as a binary, answerable question — not a vague statement of completion.

**Why it matters:** "Exit when research is complete" is circular; the model decides what complete means. "Exit when you can answer: what has this person been doing in the last 90 days?" is testable. The model has to commit to a specific assertion.

**Anti-pattern:** "Continue until the analysis feels thorough."

**Concrete example:** From `meta-paap`-generated skills: *"Exit condition: Can you answer 'what is this company focused on right now'? Yes → proceed. No → return to Phase 1."*

**Archetypes:** Procedural-only.

---

### 11. Output spec

**Definition:** The output specification leaves nothing to interpretation — exact format, named sections, length constraints, per-section content rules, and (where useful) anti-templates.

**Why it matters:** Vague output specs produce polished-looking but wrong output. The most common failure mode in skills is output that *looks* right but misses the actual requirement.

**Anti-pattern:** "Produce a comprehensive analysis." How long? What sections? What if a section is empty?

**Concrete example:** `tapestry/article-extractor` per-section content rules: *"8-10 bullets each containing a concrete claim. Skip this section entirely if all terms are common knowledge. If nothing applies to current work: write 'No direct application' — do not force it."* Honest omission rules prevent bloat.

**Archetypes:** All. Universal — Reference skills need format spec for the documentation; Creative skills need anti-templates ("don't produce purple-gradient AI-generic art").

---

### 12. Gates = 3 parts

**Definition:** Every quality gate has all three parts: (a) the **check** (what specific property to verify), (b) the **failure condition** (what "fail" looks like concretely), (c) the **recovery path** (return to which phase with which instruction).

**Why it matters:** Gates without recovery paths produce a fail-state with no defined next step — the model invents one. The skills with the highest output quality in the corpus all have explicit recovery paths.

**Anti-pattern:** "Verify the output." No check criteria, no failure condition, no recovery path. Prose theater.

**Concrete example:** *"If the talking points don't reference something the person specifically built, wrote, or said: return to Phase 1, find one concrete thing, then re-run the synthesis."* All three parts in one sentence.

**Archetypes:** Procedural-only.

---

### 13. External storage

**Definition:** When a SKILL.md exceeds ~400 lines, agent prompts, reference materials, and long shared blocks live in separate files (e.g., `references/architecture-checklist.md`), not inline in the main file.

**Why it matters:** Long SKILL.md files are harder to read, harder to diff, harder to maintain. External storage keeps the orchestration logic legible and lets references evolve independently.

**Anti-pattern:** A 1,200-line SKILL.md with three inlined agent prompt blocks.

**Concrete example:** gstack's `SKILL.md.tmpl` system: shared blocks like `{{PREAMBLE}}`, `{{COMMAND_REFERENCE}}`, `{{REVIEW_DASHBOARD}}` are stored separately and rendered into committed SKILL.md files at build time.

**Archetypes:** Procedural + Reference. **Caveat:** Skills under ~400 lines with all content in the main file should mark this N/A — that is appropriate, not a violation.

---

### 14. Context scope

**Definition:** The skill explicitly states what it is for and what it is not for. Per-agent scoping (when agents are used) names what each agent can read AND what they're denied.

**Why it matters:** Scope creep is the most common skill-decay pattern. A skill that "does research" eventually does email, calendar, and database queries. Explicit boundaries prevent this.

**Anti-pattern:** No stated boundaries. The skill expands until it's used for everything.

**Concrete example:** gstack's review skills explicitly scope each reviewer agent: *"Agent B is denied access to GitNexus data; reasoning: architecture-level data would invite scope creep into design decisions outside this agent's mandate."*

**Archetypes:** All. Universal.

---

### 15. Progress

**Definition:** The skill emits status updates at meaningful checkpoints — phase transitions at minimum, with key stats ("Found 12 sources, 3 scored above threshold, proceeding to synthesis").

**Why it matters:** When a skill fails, you read the progress log to find where it drifted. Without progress reporting, debugging is reading the whole execution and guessing.

**Anti-pattern:** No status output until the final result. The user has no signal whether the skill is working or hung.

**Concrete example:** gstack's `[PROGRESS]` directive: *"During long-running skill sessions, periodically write a brief [PROGRESS] summary (2-3 sentences: what's done, what's next, any surprises)."*

**Archetypes:** All. Universal.

---

### 16. Errors

**Definition:** Errors are handled via an explicit table mapping specific error → specific action. Not generic try/catch prose; a row-by-row map of failure modes.

**Why it matters:** Generic error handling produces generic recovery. The error table is where you encode the specific failure modes you've actually seen, with the specific responses that worked.

**Anti-pattern:** "If errors occur, ask the user." That's not an error-handling strategy.

**Concrete example:** From `meta-paap`-generated skills: *"| URL is paywalled | Ask user to paste article text. | Tool not installed | Try fallback tool, then ask user. | Search returns < 5 results | Expand to adjacent topics, retry. |"*

**Archetypes:** Procedural + Creative. Reference skills typically don't need an error table — they're descriptive, not executive.

---

### 17. Autonomy

**Definition:** The skill has sensible defaults, infers mode from context, treats interactive-prompts as the exception (only when genuine human judgment is required). Manual mode is the safe fallback.

**Why it matters:** Skills that ask too many questions become unusable. Skills that ask too few become dangerous. The right calibration: ask only when you cannot infer.

**Anti-pattern:** Asking the user to confirm every decision, including ones the skill could infer.

**Concrete example:** `meta-paap`: *"If mode unclear: FULL mode."* One sentence, sensible default, no prompt.

**Archetypes:** Procedural + Creative.

---

### 18. Path resolution

**Definition:** All paths are resolved at runtime with fallbacks. No hardcoded absolute paths to a specific machine.

**Why it matters:** Hardcoded paths break the moment someone forks the skill. Runtime resolution lets the skill run on any machine.

**Anti-pattern:** `VAULT_PATH = /Users/<username>/projects/vault` baked into the skill body. The skill works on the author's machine and breaks on every fork.

**Concrete example:** Three-tier resolution: `PRIMARY = ~/.claude/skills/meta-paap/SKILL.md` → `FALLBACK = ./skills/meta-paap/SKILL.md` → `SEARCH find . -name "SKILL.md" | grep meta-paap`. Each tier is tried; only the failure of all three is an error.

**Archetypes:** Conditional. **Caveat:** Skills that don't reference any external files (a self-contained one-shot skill) should mark this N/A.

---

### 19. Composition

**Definition:** When a skill invokes other skills, the composed paths are resolved at runtime with fallbacks. Composition metadata (which skills are used, at which phase, for what purpose) is declared explicitly.

**Why it matters:** Hardcoded composition paths break on forks. Implicit composition makes the dependency graph invisible.

**Anti-pattern:** Hardcoding `/Users/.../my-other-skill/SKILL.md` and assuming it exists.

**Concrete example:** Recommended pattern for the YAML header:

```yaml
composed_skills:
  - name: defuddle
    phase: 1
    purpose: extract clean content from URL
    optional: true
  - name: humanizer
    phase: 4
    purpose: remove AI-slop signatures from output
    optional: false
```

**Archetypes:** Procedural + Reference.

---

### 20. Output-first

**Definition:** The output specification is defined before the phases. The phases are the path to the defined output, not the other way around.

**Why it matters:** Phase-first thinking produces skills that ramble. Output-first thinking forces clarity about what the skill is actually for.

**Anti-pattern:** Designing the workflow first, then deciding what output it produces.

**Concrete example:** `idea-to-pr` defines the PR description template (6 sections, exact format) in Phase 0 before any phase is described. Every subsequent phase is justified by what it contributes to the final output.

**Archetypes:** All. Universal — every skill, regardless of archetype, should have its output spec defined before its process.

---

### 21. Decision class drives gating policy

**Definition:** Decisions in a skill are classified into three types — **Mechanical** (auto-decide silently), **Taste** (auto-decide but surface at gate), **User Challenge** (never auto-decide, always escalate) — and each class triggers a different gating treatment.

**Why it matters:** Without this distinction, skills either over-prompt (asking about every decision) or under-prompt (auto-deciding things the user should weigh in on). The decision-class taxonomy is what calibrates the human-gate frequency to genuine need.

**Anti-pattern:** A skill that gates on every choice (annoying) OR a skill that auto-decides everything including irreversible or values-laden choices (dangerous).

**Concrete examples:**
- `obra/test-driven-development` is fundamentally a **Mechanical** skill — TDD discipline is non-negotiable, no user prompt needed.
- `emaynard/family-history-planning` is fundamentally a **User Challenge** skill — every research action requires explicit user approval.
- gstack's `autoplan` distinguishes all three classes explicitly: Mechanical decisions auto-decide, Taste decisions auto-decide-but-flag, User Challenge decisions escalate.

**Archetypes:** Procedural-only.

**Note:** This principle was promoted from a gstack-specific candidate after the 50-skill survey found ~5 community skills calibrating gating to a decision class without naming it. See [`empirical-validation.md`](./empirical-validation.md) for evidence.

---

### 22. Voice + writing rules as skill content

**Definition:** Tone, banned phrases, prose structure rules, and anti-AI-vocabulary lists are first-class skill content — written into the skill body, not externalized as a separate style guide.

**Why it matters:** Skills don't just orchestrate work — they orchestrate the language of the work. When voice rules live outside the skill, they're not enforced; when they live inside, they shape every output the skill produces.

**Anti-pattern:** A skill that produces text without specifying *how* the text should sound. Default: AI-flavored marketing copy with em-dashes and inflated symbolism.

**Concrete examples:**
- `anthropic-canvas-design` encodes aesthetic anti-patterns (avoid purple gradients, Inter font, generic AI aesthetics) directly in the skill.
- `obra/test-driven-development` specifies prose voice ("Iron Law", "Rationalizations to Reject") that shapes how the skill talks to the user.
- gstack preambles include 600+ lines of voice rules: banned AI vocabulary lists ("delve", "crucial", "landscape", "tapestry"), required prose structure (D-numbered AskUserQuestion with ELI10 + Stakes + Recommendation + Completeness score + ≥40-char pros/cons + Net line).

**Archetypes:** Procedural + Creative.

**Note:** This principle was promoted from a gstack-specific candidate after the 50-skill survey found voice rules strongly present in `anthropic-canvas-design`, `scrum-sage`, `anthropic-frontend-design`, and `obra/test-driven-development`. See [`empirical-validation.md`](./empirical-validation.md) for evidence.

---

## Deferred candidates (not in v0.1)

Eight additional patterns surfaced from gstack's 50-skill corpus but did not appear consistently enough across the broader 50-skill community survey to merit promotion in v0.1. They are documented in [`empirical-validation.md`](./empirical-validation.md) and may be promoted in v0.2 if community contributions provide additional evidence:

- SKILL.md as build artifact (template-rendered, CI-enforced)
- Composed skills declare which sections parent owns (section-skip-list composition)
- Dual-voice consensus for verification
- Hard guardrails via hooks, not prose
- Skills observe themselves and feed prior runs forward
- Plan-stage rubric reused at audit time
- Skills are portable; host is a config knob
- Skills detect spawn vs. interactive and adapt

These are real architectural patterns at gstack scale. They may not apply at smaller scale. v0.2 will revisit with more data.

---

## Versioning policy

The rubric will evolve. Major changes (adding/removing principles, changing applicability) trigger a version bump and a changelog entry. Wording changes that don't shift applicability are minor.

- **v0.1 (rubric content frozen here, 2026-04-25):** 22 principles, 3 archetypes, 8 deferred gstack candidates documented
- **v0.2 (released 2026-04-26 — evidence + tooling):** `/paap-eval` skill (auto-scoring instrument), N=80 corpus extension (3 deferred candidates promotion-ready, 3 confirmed gstack-only), 3-persona kappa pilot (mean inter-rater 1.83 grade-steps), head-to-head experiment (5 paired skills + 1 blind-output test, judge mis-attributed provenance). **Rubric content unchanged from v0.1.** See [`../CHANGELOG.md`](../CHANGELOG.md).
- **v0.3 (planned):** Promote 3 corpus-validated candidates (#26 self-observation, #29 host-portable, #30 spawn-detection) → 25-principle rubric. Multi-model kappa. Output-quality test expansion. "Rationalizations to reject" pattern added to `meta-paap` persona generation.
- **v1.0 (conditional, unlocked by v0.2):** Workshop-paper format. v0.2 evidence makes this defensible (kappa data, N=80 corpus, head-to-head with mis-attributed provenance). Honest defensible paper title: *"Prompt-as-a-Process: Evidence That Generator-Produced Skill Files Match Hand-Authored Ones On Structural Quality and Output Quality, From a Single-Practitioner Tooling Study."* v0.3 expansions determine whether v1.0 ships.

When you cite this rubric, include the version: *"PaaP rubric v0.1 (Catafal, 2026)."*

See [`../07-OPEN-QUESTIONS.md`](../07-OPEN-QUESTIONS.md) for what v0.2 specifically aims to resolve.

## Dogfooding — does the repo pass its own rubric?

The repo applied this rubric to itself in [`reflexive-self-audit.md`](./reflexive-self-audit.md). Aggregate: A (15 applicable principles; 4 A+, 9 A, 1 A-, 1 B+, 1 B). Honest weak points and known caveats (single-scorer issue, archetype declaration as judgment call) documented in that file.
