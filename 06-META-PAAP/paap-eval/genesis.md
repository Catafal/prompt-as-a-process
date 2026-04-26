# `/paap-eval` — Genesis Document

> The elicitation answers and architecture spec that drove the v0 generation of `/paap-eval`. Equivalent to invoking `/meta-paap` with the v0.2 design spec from [`07-OPEN-QUESTIONS/`](../../07-OPEN-QUESTIONS/) — but executed manually with the dogfooding visible to readers and reviewers.

**Generated:** 2026-04-26 (Stage 1a of v0.2)
**Method:** Manual execution of `meta-paap`'s 7-phase generation protocol against the design spec
**Why this file exists:** A future reviewer asking "did `/paap-eval` actually follow the meta-paap protocol?" can read this file and audit the elicitation, architecture, and self-critique decisions. Without this, the dogfooding claim is unverifiable.

---

## Pre-Phase — Invocation parsing

**Hypothetical invocation:** *"Build me a skill called /paap-eval that scores any SKILL.md file against the 22-principle PaaP rubric. Use the design spec in 07-OPEN-QUESTIONS/README.md."*

**Skills explicitly named in invocation:** None — `/paap-eval` is intended to be standalone.

**EXPLICITLY_REQUESTED:** [] (empty)

---

## Phase 0 — Classification

Decision tree from `meta-paap`:

- Single-step task? → No. The skill has 6+ phases, multiple input types, conditional branches.
- 2-3 linear phases, no parallel agents, no human gate needed? → No. Has algorithmic + semantic phases that could be parallelized, plus archetype-detection user-confirmation gate.
- Multiple perspectives, iterative rounds, human judgment mid-process, parallel agents, or persistent state? → Yes — archetype gate, scorer-persona variants, optional resume.

**Verdict: FULL PATH.** Continue to Phase 1.

---

## Phase 1 — Elicitation (the 5 questions, answered)

### Q1 — Walk through the workflow step by step

1. Receive a path to a SKILL.md file as input
2. Validate the file exists and has YAML frontmatter (otherwise stop)
3. Read the entire file
4. Auto-classify the archetype (Procedural / Reference / Creative / Hybrid). If confidence is low, ask the user to confirm.
5. Determine the applicable principles based on archetype (use the matrix from `principles.md`)
6. For each algorithmic principle, run a regex/pattern detector against the file content. Output: grade + confidence + line evidence.
7. For each semantic principle, run an LLM-judge prompt with the file content + principle definition + scorer-persona context. Output: grade + confidence + reasoning + uncertainty notes.
8. Aggregate algorithmic + semantic into one score table using the `scoring-template.md` format.
9. Compute aggregate grade (excluding N/A, weighted equally for v0.2).
10. Write the scored evaluation to a file with a self-disclosure footer.

### Q2 — Where does it break? What goes wrong most often when done manually?

When this is done manually (the v0.1 way), three failure modes recur:

- **Archetype-blindness.** Manual scorers default to Procedural treatment, penalizing Reference and Creative skills unfairly. The applicability matrix exists but is easy to skip.
- **Principle confusion.** Some principles overlap (e.g., #6 Personas vs #22 Voice rules). Manual scorers double-count or split inconsistently.
- **Confidence inflation.** Manual scoring tends to commit to a grade even when uncertain. The honest "I'm not sure" gets buried.

So the quality gates need to enforce: archetype declared first, principles confidence-rated explicitly, low-confidence principles flagged for human review.

### Q3 — Output format

A markdown file matching `04-RUBRIC/scoring-template.md` exactly, plus three additional sections:

- **Confidence map** — per-principle confidence (high/medium/low) with one-line reasoning
- **What I was uncertain about** — list of principles where the eval skill flagged its own uncertainty
- **What needs human judgment** — irreducibly subjective items the eval skill explicitly defers on

Length target: 200-400 lines per scored skill. Saved to `./scored/<skill-slug>-<YYYY-MM-DD>.md` by default.

### Q4 — Tools/dependencies

- `Read` (read SKILL.md and rubric files at runtime)
- `Bash` (regex/grep for algorithmic detectors)
- `Write` (output the scored evaluation)
- `AskUserQuestion` (only on low-confidence archetype detection)
- `Task` (optionally — parallel sub-agents for the 10 semantic principles)

External resources required:
- `04-RUBRIC/principles.md` — the rubric (read at runtime)
- `04-RUBRIC/scoring-template.md` — the output format

### Q5 — Frequency + resumability

Frequency: Multiple times per session during v0.2 execution (kappa pilot runs it 30× across 3 personas × 10 skills; corpus extension runs it 100×).

Resumability: Not required. Each evaluation is a fresh run; the per-evaluation output file IS the persistent state. State management within a single run not needed (each run is <5 min).

### Q6 — Composition with other installed skills

None at v0.2 launch. Standalone by design — depends only on `principles.md` (rubric) and `scoring-template.md` (output format) which are read at runtime, not invoked as skills.

(Future v0.3 candidates: compose with `/humanizer` to clean LLM-judge prose, or with `/defuddle` if the input SKILL.md is fetched from a URL.)

---

## Phase 1.5 — Skills discovery

Standalone. No composition candidates. Skip.

---

## Phase 2 — Architecture spec

```
SKILL NAME: /paap-eval

DESCRIPTION:
  What it does: Score any SKILL.md file against the 22-principle PaaP rubric
                with archetype-aware applicability and per-principle confidence.
  Trigger phrases:
    - "score this skill against PaaP"
    - "evaluate this SKILL.md"
    - "audit this skill"
    - "run /paap-eval on X"
  Anti-triggers:
    - Do NOT use for scoring non-SKILL.md files (Markdown docs, READMEs, etc.)
    - Do NOT use to claim objective grades — this is an LLM-judge with stated limits
    - Do NOT use for promotion/hiring decisions about a skill author
    - Do NOT use for skills written in languages other than English (v0.2 Procedural-skill scope)

MODES:
  Three scorer-persona variants (selectable via --persona flag):
  - strict-academic (default for kappa pilot): higher confidence threshold, harder graders
  - pragmatic-practitioner (default for general use): real-world weighting
  - charitable-newcomer: weights "what would a novice find useful?" higher
  Default if no flag: pragmatic-practitioner

PHASES:

  Pre-Phase — Input Validation (sequential)
    Purpose: Reject inputs that aren't SKILL.md files before doing any work
    Input: SKILL.md path from invocation
    Output: validated path OR explanatory STOP
    Exit condition: Can you answer "is this file a SKILL.md with valid YAML frontmatter"?

  Phase 0 — Configuration (sequential)
    Purpose: Resolve output location, scorer persona, and runtime settings
    Input: invocation flags + defaults
    Output: 00-config.json
    Exit condition: Can you answer "what persona, what output path, what archetype hint"?

  Phase 1 — Archetype Detection (sequential, with optional human gate)
    Purpose: Classify the skill's archetype before scoring
    Input: SKILL.md content + the rubric's archetype definitions
    Output: 01-archetype.json with classification + confidence
    Exit condition: Can you answer "what archetype is this skill, and am I confident enough to proceed without asking?"
    Human gate: If confidence < 0.75, AskUserQuestion with the top 2 candidate archetypes

  Phase 2 — Algorithmic Auto-Score (parallel-burst)
    Purpose: Pattern-match the ~12 principles that can be detected algorithmically
    Input: SKILL.md content + applicability matrix from Phase 1
    Output: 02-algorithmic-scores.json
    Exit condition: Can you answer "have I run a detector for every applicable algorithmic principle?"
    Parallel agents: detector per principle (12 total), single message
    NOTE: detector logic itself is in references/algorithmic-detectors.md (filled in by Stage 1b)

  Phase 3 — Semantic LLM-Judge (parallel-burst)
    Purpose: LLM-judge the ~10 principles requiring reading and judgment
    Input: SKILL.md content + applicability + scorer-persona context
    Output: 03-semantic-scores.json
    Exit condition: Can you answer "have I judged every applicable semantic principle with explicit confidence rating?"
    Parallel agents: judge per principle (10 total), single message
    NOTE: judge prompts in references/semantic-judges.md (filled in by Stage 1c)

  Phase 4 — Synthesis (sequential)
    Purpose: Aggregate algorithmic + semantic into one score table; compute aggregate grade
    Input: 02-algorithmic-scores.json + 03-semantic-scores.json + 01-archetype.json
    Output: 04-synthesis.json
    Exit condition: Can you answer "do I have a grade for every applicable principle, with confidence ratings, and an aggregate?"

  Phase 5 — Report Generation (sequential)
    Purpose: Write the scored evaluation in scoring-template.md format
    Input: 04-synthesis.json + scoring-template.md
    Output: scored/<skill>-<date>.md
    Exit condition: Can you answer "is the evaluation file complete, formatted correctly, and self-disclosed as LLM-judge?"

COMPOSITION: standalone

STATE: no
  Justified: each evaluation runs in <5 min; per-evaluation output IS persistent state.
  Phase outputs (00-04 JSON files) are scratch artifacts, deleted after Phase 5 completes.

QUALITY GATES:
  Gate 1 (after Phase 1): Archetype confidence >= 0.75 OR user has confirmed.
    If fails: ask user; if user can't confirm, default to Hybrid and note in report.
  Gate 2 (after Phase 2): Every applicable algorithmic principle has a grade + evidence.
    If fails: re-run failed detectors; if still failing, mark as "detector-error" in report.
  Gate 3 (after Phase 3): Every applicable semantic principle has a grade + confidence + reasoning.
    If fails: re-run failed judges with simpler prompts; if still failing, mark as "needs-human-judgment".
  Gate 4 (after Phase 4): Aggregate grade matches the per-principle distribution (sanity check).
    If fails: re-aggregate.
  Gate 5 (after Phase 5): Output file exists, has all required sections, has self-disclosure footer.
    If fails: regenerate Phase 5 output.

OUTPUT CONTRACT:
  File: ./scored/<skill-slug>-<YYYY-MM-DD>.md (configurable via --output flag)
  Format: markdown matching 04-RUBRIC/scoring-template.md
  Sections (exact, in order):
    1. Metadata block (skill name, repo path, archetype, scorer persona, date, rubric version)
    2. Archetype declaration with one-line justification
    3. Principle-by-principle scoring table (22 rows, with N/A grades for non-applicable)
    4. Confidence map (per-principle confidence rating)
    5. Key strengths (3-5 bullets)
    6. Key weaknesses (3-5 bullets, risk-ranked HIGH/MEDIUM/LOW)
    7. What I was uncertain about
    8. What needs human judgment
    9. Aggregate grade (computed)
    10. Self-disclosure footer
  Length: 200-400 lines per scored evaluation

TOOLS REQUIRED:
  - Read (SKILL.md content, rubric files)
  - Bash (regex/grep for algorithmic detectors)
  - Write (output file)
  - AskUserQuestion (low-confidence archetype gate)
  - Task (parallel sub-agents for Phases 2 + 3)

PORTABILITY:
  - Skill itself uses runtime path resolution: principles.md and scoring-template.md found via three-tier lookup
    (PRIMARY: ./04-RUBRIC/, FALLBACK: ../04-RUBRIC/, SEARCH: find . -name "principles.md")
  - Output path defaults to ./scored/ relative to invocation; configurable
  - No hardcoded absolute paths anywhere
```

---

## Phase 3 — Generation

The generated SKILL.md follows from this architecture spec. Two key implementation details deferred to subsequent stages:

- **Stage 1b** fills in `references/algorithmic-detectors.md` — the actual regex/pattern logic for the ~12 algorithmic principles
- **Stage 1c** fills in `references/semantic-judges.md` — the per-principle LLM-judge prompts for the ~10 semantic principles

The Stage 1a artifact (`SKILL.md` v0) has all 7 phases written out with placeholders pointing to the references files. It is runnable in skeleton form: a model can follow the structure, but the per-principle scoring will be coarse until 1b + 1c complete.

---

## Phase 4 — Self-critique

Red-teaming the architecture before generation:

| Check | Status | Notes |
|---|---|---|
| Exit conditions on every phase | ✅ Pass | All 7 phases have binary exit-as-question conditions |
| Quality gates with all 3 parts | ✅ Pass | All 5 gates have check + failure + recovery |
| Parallel without synthesis | ✅ Pass | Phases 2 + 3 (parallel) feed into Phase 4 (synthesis) |
| Anti-triggers in description | ✅ Pass | 4 anti-triggers in YAML description |
| Output spec completeness | ✅ Pass | Exact file path, exact section list, length target |
| Tool dependencies declared | ✅ Pass | All 5 tools listed |
| Composition paths | ✅ Pass | Standalone — no composition paths to manage |
| Hardcoded paths | ✅ Pass | All paths resolved at runtime with fallbacks |

**Moderate issues flagged (not blocking, worth knowing):**

- The "scorer persona" parameter introduces complexity that won't be tested until Stage 2 (kappa pilot). If the persona system reveals design problems, this skill will need a v0.2.1.
- The references files (algorithmic-detectors.md, semantic-judges.md) don't exist yet — the v0 SKILL.md is technically incomplete until Stages 1b and 1c land. This is by design (matches the staged build plan), but the skill should not be invoked as production-ready until 1b+1c+1d complete.

**Critical issues found and corrected:** None. The architecture spec passed all critical checks.

---

## Generation outcome

`SKILL.md` v0 generated and saved to `./SKILL.md` (sibling of this file). 

Subsequent stages:
- **Stage 1b:** Algorithmic detectors → `references/algorithmic-detectors.md`
- **Stage 1c:** Semantic judges → `references/semantic-judges.md`
- **Stage 1d:** Validation against the 4 existing manual evaluations → `calibration.md`
- **Stage 2:** Three persona variants tested in the kappa pilot

---

## Note on the dogfooding claim

If a reviewer asks "did `/paap-eval` actually follow the `meta-paap` protocol?", the verifiable answer is in this file. The 7 phases above mirror `meta-paap`'s 7 phases exactly. The elicitation answers are explicit. The architecture spec is complete. The self-critique was applied.

The honest caveat: this protocol was executed by Sir + Alfred manually rather than by invoking `/meta-paap` directly. This was a deliberate choice — it makes the elicitation answers visible and editable. A future round could invoke `/meta-paap` for real and compare the outputs; that comparison is itself a useful Stage 2 experiment if scoped.
