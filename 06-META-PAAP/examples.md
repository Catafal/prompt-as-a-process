# meta-paap — Example invocations and outputs

> Four worked cases showing what `meta-paap` produces from different inputs. Each example: the invocation, the elicitation answers, the architecture spec, and notable features of the generated skill.

These are the same four skills evaluated in detail in [`../05-EVALUATION/`](../05-EVALUATION/). This file shows the *generation* side — what was fed to `meta-paap` and what it produced. The evaluation side (scoring against the rubric) lives in the per-test files.

---

## Example 1: `/skill-audit` (parallel agents, analytical tool)

### The invocation

> "Build me a skill that audits my installed Claude Code skills. It should classify them by usage from my JSONL session logs, score them by maintenance need, and surface candidates for removal or consolidation."

### Elicitation answers (paraphrased from conversation context)

1. **Steps:** Inventory installed skills → score them on three dimensions (usage frequency, recency, overlap with other skills) → produce a prioritized report.
2. **Where it breaks:** JSONL parsing is fragile; usage statistics need to be aggregated correctly across sessions.
3. **Output:** A scored report with QUICK and FULL modes (table vs. detailed).
4. **Tools:** Bash (for find + grep over skill files), Read (SKILL.md headers), JSONL parsing.
5. **Frequency:** Weekly. No resume needed; runs in under 2 minutes.

### Architecture meta-paap chose

- **3 parallel agents** with explicit context scoping (Usage Agent, Maintenance Agent, Overlap Agent)
- **Synthesis phase** with named priority rules ("Usage wins tiers, Staleness wins maintenance, Overlap wins merges")
- **2 modes** (QUICK report and FULL report) with default ("if mode unclear: FULL")
- **File bus**: 01-inventory.json → 02a/b/c → 03-scored.json
- **Standalone composition** (no other skills used)

### Notable in the generated skill

- 567 lines (above the 400-line external-storage guideline — flagged in evaluation)
- Inlined agent prompts (would be cleaner as `references/` files)
- Strong synthesis with priority rules; weak JSONL parsing details

**Full evaluation:** [test-1-skill-audit.md](../05-EVALUATION/test-1-skill-audit.md). **Overall: B+.**

---

## Example 2: `/article-forge` (linear pipeline, composition)

### The invocation

> "Build me a skill that processes articles from URLs or pasted text. Use `/defuddle` for cleanup, `/obsidian-markdown` for formatting, and `/humanizer` to remove AI-slop. Save the output to my knowledge vault."

The user named three skills explicitly. `meta-paap`'s Pre-Phase parsed these and set them as confirmed composition candidates.

### Elicitation answers

1. **Steps:** Detect input type (URL vs paste) → extract content → process with composed skills → format → save.
2. **Where it breaks:** Defuddle sometimes fails on paywalled URLs; AI-slop sometimes survives the humanizer pass.
3. **Output:** 3 markdown files (raw extract, reflection, applications) saved to vault.
4. **Tools:** WebSearch (URL fallback), Read, Write.
5. **Frequency:** Multiple times per week. No resume; short runs.

### Architecture meta-paap chose

- **5 sequential phases**, no parallel agents
- **3 composed skills** (defuddle, obsidian-markdown, humanizer) with runtime path resolution and fallback chains
- **`composed_skills` YAML metadata** — new pattern that became the canonical example for principle #19
- **Per-section output rules** ("8-10 bullets each containing a concrete claim. Skip this section entirely if all terms are common knowledge.")

### Notable in the generated skill

- 350 lines (well within the external-storage guideline)
- First skill to use the `composed_skills` YAML metadata pattern
- Honest output spec rules ("If you can't name one, remove the application")
- Hardcoded vault path primary (B+ on portability — flagged in evaluation)

**Full evaluation:** [test-2-article-forge.md](../05-EVALUATION/test-2-article-forge.md). **Overall: A-.**

---

## Example 3: `/review-plan` (dual-mode, behavioral personas)

### The invocation

> "Build me a skill that reviews implementation plans for code projects. It should have an auto mode (parallel agents critique the plan) and a manual mode (interactive section-by-section review with the user)."

### Elicitation answers

1. **Steps:** Read plan + codebase context → critique structure → critique quality → present findings (mode-dependent).
2. **Where it breaks:** Plans often look good structurally but have execution-path bugs; manual mode needs to surface the right issue at the right time.
3. **Output:** Mode-specific report templates with severity-tagged issues.
4. **Tools:** Read, AskUserQuestion (manual mode), Task (auto mode subagents).
5. **Frequency:** Per-feature. Resume needed if user pauses manual mode.

### Architecture meta-paap chose

- **3 modes**: auto, manual-BIG (full plan), manual-SMALL (section)
- **Behavioral personas** for parallel agents — "Burned by untested edge cases. Trust tests more than comments." Major step up from generic role assignments in earlier tests.
- **State management** with `review-plan-state.json` and resume protocol
- **External reference file** (`references/review-agents.md`, 326 lines) with fallback to inline prompts
- **6 quality gates**, mode-specific (4 auto, 5 manual, 6 both)
- **User preference mapping** — every recommendation must map to one of 5 named user values (PREF_DRY, PREF_TESTS, etc.)

### Notable in the generated skill

- 508 lines main + 326-line reference (correctly externalized)
- First skill with state management
- Genuine behavioral personas — became the canonical example for principle #6
- Variable name inconsistency between Phase 1 and Phase 2 (HIGH risk — flagged in evaluation)

**Full evaluation:** [test-3-review-plan.md](../05-EVALUATION/test-3-review-plan.md). **Overall: A- / A.**

---

## Example 4: `/idea-to-pr` (full orchestration, 10 composed skills)

### The invocation

> "Build me a skill that takes a feature idea and produces a reviewable PR. It should describe the spec, observe the codebase, plan implementation, review the plan, implement, run quality checks, and ship."

The user named 14 candidate skills in conversation. After elicitation, `meta-paap` and the user collapsed the design from "6 skills + 19 composed" to "1 skill + 10 composed" — pushback against over-engineering.

### Elicitation answers

1. **Steps:** Spec → observe → plan → review-plan → implement → quality-chain → ship.
2. **Where it breaks:** Vague specs cause everything downstream to fail; plans drift after review iterations.
3. **Output:** A reviewable PR with linked artifacts (spec, observations, plan versions, review).
4. **Tools:** Read, Write, Bash, Task, AskUserQuestion.
5. **Frequency:** Multiple per day. Resume essential — these run for hours.

### Architecture meta-paap chose

- **5 phases + routing** with **2 human gates** (spec confirmation, plan approval)
- **10 composed skills**: 6 mandatory + 4 conditional. Conditional routing based on spec content analysis (auth/PII → security review, big scope → engineering review, backend changes → docs writer)
- **State**: `meta.json` with phase-specific artifact re-injection on resume
- **Plan versioning**: PLAN-v1 → v2 (post-GitNexus) → v3 (post-review) → PLAN-final, each preserved as a separate file
- **Artifact schemas in external reference** (5 templates: SPEC.md, OBSERVE.md, PLAN-vN.md, REVIEW.md, meta.json)
- **10-row error handling table** including context window pressure and `/ship` failure recovery

### Notable in the generated skill

- 555 lines main + 173-line reference
- Most composition of any test (10 skills with conditional routing)
- The SPEC.md template ("NOT 'improve X' — instead 'when user does Y, system responds with Z'") became a canonical pattern for outcome-driven specs
- `git add -A` in the fallback PR creation — HIGH safety risk; flagged in evaluation
- Two non-existent skills referenced (`/cso`, `/plan-design-review`) — caught by user post-generation, missed by self-critique

**Full evaluation:** [test-4-idea-to-pr.md](../05-EVALUATION/test-4-idea-to-pr.md). **Overall: A-.**

---

## What these examples teach

### Quality of input drives quality of output

The progression from Test 1 (B+) to Test 4 (A-) is largely the user learning what to feed the generator. Test 1 had loose elicitation; by Test 4 the user provided decision points, specific failure modes, and explicit preferences. The generator improved because its inputs improved.

### `meta-paap` correctly scales architecture to workflow complexity

- Test 2 (linear pipeline) → 5 sequential phases, no agents
- Test 3 (dual-mode review) → 3 modes, behavioral personas, external references
- Test 4 (full orchestration) → 10 composed skills, conditional routing, plan versioning

The generator doesn't over-engineer simple workflows or under-engineer complex ones.

### The systematic weaknesses are stable

In all 4 tests, the self-critique was lenient and the hardest technical phase was under-specified. These are reliable patterns to expect on first run. **Read the output. Fix the one thing that broke. Run again.**

### Composition gets richer with each test

| Test | Composition |
|---|---|
| 1 | 0 (standalone) |
| 2 | 3 skills, runtime resolution + fallbacks + new YAML metadata pattern |
| 3 | 2 skills, optional with graceful degradation |
| 4 | 10 skills (6 mandatory + 4 conditional), full dependency graph |

The composition design pattern stabilizes across tests, suggesting the rubric's principle #19 is correctly capturing how composition should work.

---

## Cross-references

- [`README.md`](./README.md) — When to use, when not to use, performance characteristics
- [`SKILL.md`](./SKILL.md) — The skill itself, ready to drop in your skills folder
- [`references/architecture-checklist.md`](./references/architecture-checklist.md) — The Phase 2 decision-point checklist
- [`../05-EVALUATION/`](../05-EVALUATION/) — Full per-test scoring + cross-test regression
- [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) — The principles `meta-paap` enforces
