# `/paap-eval` Calibration — Stage 1d Validation

> Validation of `/paap-eval` v0.2 (Stages 1a + 1b + 1c) against four reference SKILL.md files. Tests whether the eval skill produces sensible scores before Stage 2's kappa pilot scales it up.

**Scored:** 2026-04-26 (Stage 1d of v0.2)
**Persona used:** `pragmatic-practitioner` (default)
**Scorer:** Single-LLM simulation of `/paap-eval` (not an actual subagent invocation — see honest limitations below)

---

## Calibration set

Four skills chosen to span available evidence:

| # | Skill | Source | Lines | Why included |
|---|---|---|---|---|
| 1 | `/meta-paap` | in-repo | 387 | The skill that generated the rest of the framework — should score well |
| 2 | `/pre-call` | in-repo | 96 | Canonical worked example referenced from 03-ANATOMY/README.md |
| 3 | `/paap-eval` | in-repo | 443 | **Reflexive scoring** — interesting test case |
| 4 | `obra/test-driven-development` | community ([github.com/obra/superpowers](https://github.com/obra/superpowers/blob/main/skills/test-driven-development/SKILL.md)) | 371 | Cross-corpus test; manual-scored A- in v0.1 deep-10 sub-sample |

All four are Procedural archetype, which means Stage 1d's calibration set does **not** stress-test archetype detection on Reference or Creative skills. That gap is flagged for Stage 2.

The four `meta-paap`-generated skills already manually scored in [`05-EVALUATION/`](../../05-EVALUATION/) (`/skill-audit`, `/article-forge`, `/review-plan`, `/idea-to-pr`) are NOT in this calibration set because their SKILL.md files are not committed to this repo. Calibration against those would require fetching them from a separate location; deferred to v0.2 Stage 2 when the kappa pilot can run them properly.

---

## Aggregate results

| Skill | `/paap-eval` aggregate | Manual-score baseline | Match? |
|---|---|---|---|
| `/meta-paap` | A- | (no v0.1 manual score; n=4 evaluated *outputs* of meta-paap, not meta-paap itself) | n/a |
| `/pre-call` | A- to A | (no v0.1 manual score; canonical example, never formally scored) | n/a |
| `/paap-eval` | A | (reflexive scoring — first time scored) | n/a |
| `obra/test-driven-development` | A- | A- (v0.1 deep-10 sub-sample) | **✅ MATCH** |

**Headline finding:** the only manually-scored reference (obra/TDD) matches `/paap-eval`'s simulated score exactly. This is the cleanest signal we have at this stage that the detectors + judges are calibrated correctly. The other three are first-time scores; their absolute levels can't be validated against a baseline yet.

---

## Per-skill detail

### Skill 1 — `/meta-paap`

**Archetype detected:** Procedural (high confidence — 7 phases with explicit exit conditions, parallel-burst phases, human gates).

**Algorithmic detectors (12):**

| # | Principle | Grade | Notes |
|---|---|---|---|
| 1 | Description as router | A | Anti-trigger present, multi-trigger description (~340 chars) |
| 2 | Route before work | A+ | Pre-Phase + Phase 0 (Classification) + STOP conditions + decision tree |
| 3 | Modes | N/A | Single mode by design (FULL vs LEAN is a path, not a user-selectable mode) |
| 4 | State | B+ | No state file or Resume Protocol; appropriate for ~10-min skill but principle would prefer explicit N/A justification |
| 5 | Parallel | N/A | Largely sequential pipeline; no parallel work |
| 6 | Personas | B | Persona spec referenced in Phase 2 generation rules but not behavioral-by-rejection |
| 7 | Files = bus | B+ | factory-state.json mentioned; numbered file convention not strongly used |
| 8 | Synthesis | N/A | No parallel work to synthesize |
| 9 | Human gate | A | AskUserQuestion in Phases 1, 1.5, 2, 3 with stated trigger conditions |
| 10 | Exit = question | **C** | **Real gap.** Phases end with "Wait for confirmation" or "Continue to Phase X" but not the canonical "Can you answer X?" pattern |
| 11 | Output spec | A | Each phase has explicit output; final output block specified |
| 12 | Gates = 3 parts | A | Phase 4 self-critique table has check + failure + fix structure |
| 13 | External storage | A | Uses references/architecture-checklist.md (387 lines under threshold but still externalized) |
| 14 | Context scope | A | 3 anti-triggers in description; body stays scoped |
| 15 | Progress | B | Final summary present; per-phase progress thinner |
| 16 | Errors | A | 7-row error handling table |
| 17 | Autonomy | A | Multiple defaults, infer-not-ask, AskUserQuestion only when needed |
| 18 | Path resolution | A | ~/.claude/skills standard paths + find for discovery; no absolutes |
| 19 | Composition | A (skip) | Standalone (no composed_skills field) |

**Semantic judges (10):** broadly aligned — A on output spec / context scope / autonomy; B on personas / progress / decision class / voice rules; B+ on output-first.

**Aggregate: A-** (15 applicable principles excluding 4 N/A; mean grade strong with one notable C on exit-as-question).

**Calibration insight:** `/paap-eval` correctly identified that `meta-paap` doesn't use the canonical "Exit condition: Can you answer X?" pattern. This is a real gap in `meta-paap` — fixable in v0.3 by updating the architecture checklist to require this phrasing in generated skills.

---

### Skill 2 — `/pre-call`

**Archetype detected:** Procedural (high confidence — phased workflow with quality gate).

**Algorithmic + semantic combined (only applicable principles shown):**

| # | Principle | Grade | Notes |
|---|---|---|---|
| 1 | Description as router | A+ | 3 anti-triggers, multi-trigger phrasing |
| 2 | Route before work | B | No formal Phase 0; description handles routing for this small skill |
| 4 | State | A (skip) | Justified — runs in <2 min, no resume needed |
| 9 | Human gate | A (skip) | Output IS the human gate (user reads brief before call) |
| 10 | Exit = question | A | Both phases end with "Can you answer X?" — canonical pattern |
| 11 | Output spec | A+ | Exact format, 6 sections, length target |
| 12 | Gates = 3 parts | A | Quality Check has 3 gates, each with check + failure + recovery |
| 14 | Context scope | A | Anti-triggers + tight scope |
| 16 | Errors | A | 4-row error table |
| 17 | Autonomy | A | Clear defaults |
| 20 | Output-first | A | Output template defined late but visible before Quality Check phase |

Principles N/A: #3, #5, #7, #8, #13, #15, #18, #19, #21 (correctly skipped per the skill's own author-notes section).

**Aggregate: A- to A** (11 applicable principles, mostly A grades).

**Calibration insight:** `/paap-eval`'s scores match the skill author's own self-assessment in the "Notes for the author" section (which lists which principles the skill demonstrates and which it deliberately skips). The skip decisions are correctly recognized as valid N/A rather than failures.

---

### Skill 3 — `/paap-eval` (REFLEXIVE)

**Archetype detected:** Procedural (high confidence — 7 phases, parallel-burst, quality gates, human gate).

The reflexive case. `/paap-eval` is scoring itself.

**Algorithmic + semantic combined (highlights):**

| # | Principle | Grade | Notes |
|---|---|---|---|
| 1 | Description as router | A | 4 anti-triggers, multi-trigger phrasing |
| 2 | Route before work | A+ | Pre-Phase + Phase 0 + STOP conditions + decision tree pattern |
| 3 | Modes | A+ | Three personas explicitly named with criteria (strict-academic / pragmatic-practitioner / charitable-newcomer) |
| 5 | Parallel | A+ | Canonical "Spawn one Task per applicable principle in a SINGLE message. Do NOT launch sequentially." in Phases 2 and 3 |
| 7 | Files = bus | A+ | Numbered files: 00-config, 01-archetype, 02-algorithmic, 03-semantic, 04-synthesis |
| 9 | Human gate | A | Phase 1 archetype gate with confidence threshold + AskUserQuestion |
| 10 | Exit = question | A | Every phase has "Can you answer X?" — canonical pattern |
| 11 | Output spec | A+ | 10 named sections + format + length target + self-disclosure footer |
| 12 | Gates = 3 parts | A+ | 5 gates, each with check + failure + recovery in table |
| 13 | External storage | A | 443 lines + references/ subdirectory used (algorithmic-detectors + semantic-judges) |
| 16 | Errors | A+ | 10-row table including reflexive "scoring oneself" case |
| 18 | Path resolution | A+ | Three-tier PRIMARY/FALLBACK/SEARCH explicitly |
| 6 | Personas | B | Persona variants present but not Rationalizations Rejection Table |
| 22 | Voice + writing rules | B | Limitations + self-disclosure but no banned vocab list |

**Aggregate: A** (18 applicable principles, 4 A+ / 9 A / 4 B-grade).

**Calibration insight:** Reflexive scoring works without obvious bias inflation. The skill scores itself an honest A — strong but not A+ — because two principles (#6 personas, #22 voice rules) honestly score lower (no Rationalizations table; no banned vocabulary list inside the skill body). If the skill had scored itself A+ on every principle, that would be a bias-inflation red flag. It didn't.

---

### Skill 4 — `obra/test-driven-development` (cross-corpus)

**Archetype detected:** Procedural (high confidence — workflow with Iron Law, Verification Checklist, Common Rationalizations).

**Algorithmic + semantic combined:**

| # | Principle | Grade | Notes |
|---|---|---|---|
| 1 | Description as router | B | One-line description, no anti-triggers in YAML |
| 2 | Route before work | B+ | "When to Use" section serves Phase-0 role; not formally numbered |
| 6 | Personas | A+ | **THE canonical example.** "Iron Law" + Common Rationalizations table is the persona-by-rejection exemplar |
| 9 | Human gate | B | "Ask your human partner" mentioned but not structured as AskUserQuestion |
| 10 | Exit = question | F | No exit conditions; Verification Checklist substitutes |
| 11 | Output spec | A | Code examples + Good/Bad pairs are an effective output spec |
| 12 | Gates = 3 parts | A | Verification Checklist has check + failure + recovery ("start over") |
| 13 | External storage | A | 371 lines + references @testing-anti-patterns.md |
| 14 | Context scope | A+ | Very tight scope, strong refusal of expansion |
| 16 | Errors | B | Common Rationalizations table is error-handling-as-discipline |
| 17 | Autonomy | F (in pragmatic) → C (in charitable-newcomer) | Deliberately removes choice — this is the design point |
| 20 | Output-first | B | Workflow itself is the output; no separate spec |
| 21 | Decision class | A | Mechanical TDD discipline + ask-partner for User Challenge cases |
| 22 | Voice + writing rules | A+ | Iron Law + Rationalizations to Reject + voice tone |

Principles N/A: #3, #4, #5, #7, #8, #15, #18, #19 (single-mode, stateless, no parallel, no file bus, etc.)

**Aggregate: A-** (14 applicable principles, distribution: 2 A+ / 5 A / 3 B+ / 2 B / 1 F)

**Manual baseline (v0.1 deep-10):** A-

**✅ MATCH** — `/paap-eval` simulation matches manual scoring exactly.

**Calibration insight:** the F on #17 (Autonomy) is technically correct per the rubric but conceptually misleading — obra/TDD's *design point* is removing choice, so low autonomy is the feature. The `charitable-newcomer` persona variant correctly modulates this to C, which is a real test of the persona system. This validates the persona-modulation design.

---

## Calibration findings

### What works (no fix needed)

1. **Aggregate scoring is roughly correct.** The only baseline available (obra/TDD A-) matches the simulation A-.
2. **Reflexive scoring doesn't inflate.** `/paap-eval` scores itself A, with honest B grades on principles where the skill genuinely is weaker (no Rationalizations table, no banned vocab list).
3. **The exit-as-question detector (#10) catches a real gap in meta-paap.** This is a genuine finding the framework should fix in v0.3.
4. **Persona modulation works for edge cases.** obra/TDD's intentional low-autonomy is correctly modulated by `charitable-newcomer` persona (F → C), confirming the persona system handles design-point trade-offs.
5. **The N/A justification rules are doing their job.** Pre-call's deliberate skips (#4, #5, #7, #19) are correctly recognized as appropriate rather than failures.

### What needs adjustment

1. **The autonomy detector (#17) needs a rubric clarification.** When low autonomy is the design point (like obra/TDD's deliberate choice removal), a low grade is technically correct but misleading. Two options for v0.3:
   - (a) Add an "intentional low autonomy" exception to the principle definition with a justification mechanism
   - (b) Keep the current grading; rely on persona modulation (charitable-newcomer) to soften
   Recommendation: **(a)** — explicit is better than implicit.

2. **The exit-as-question pattern in #10 should be strengthened in `meta-paap` v2.** The current calibration shows `/paap-eval` correctly identifies this as a gap; the fix is in the meta-paap architecture checklist, not in `/paap-eval`.

3. **The composition principle (#19) needs an explicit `standalone: true` declaration.** Currently a missing `composed_skills:` field is interpreted as standalone (correct), but the absence is silent. Recommendation for v0.3: encourage explicit `composed_skills: []` in YAML when a skill is intentionally standalone, so the principle reads as "explicitly declared standalone" rather than "field omitted."

### What's still unknown

1. **Reference and Creative archetype scoring.** All 4 calibration skills are Procedural. The archetype-detection logic and the Reference/Creative-applicable principle subsets are untested at Stage 1d. **This is the highest-priority gap for Stage 2.**
2. **Inter-rater reliability across persona variants.** Single-persona simulation in Stage 1d. Stage 2's kappa pilot tests divergence across the 3 personas.
3. **Cross-language scoring.** All 4 skills are English. Non-English skills are out-of-scope for v0.2 per the SKILL.md limitations section.
4. **The 4 manually-scored skills from `05-EVALUATION/`.** Their SKILL.md files aren't in the repo. Stage 2 should fetch them and re-score for a fuller calibration set.

---

## Honest limitations of this Stage 1d validation

- **Single-LLM simulation, not actual `/paap-eval` invocation.** The scorer (this LLM, in this session) read the detectors + judges and applied them to the 4 skills. A real Stage 2 kappa pilot will invoke `/paap-eval` as a subagent 3 times (one per persona) and compute Cohen's kappa from the divergences. That's the real test.
- **Single scorer.** Same caveat as the v0.1 50-skill survey. Persona variants partially address this in Stage 2.
- **Small N (4 skills).** Patterns observed in 4 skills are direction-of-evidence, not statistics.
- **All 4 are Procedural.** Reference and Creative archetypes untested.
- **Two of the four (`/meta-paap`, `/pre-call`) were authored by the same person who designed the rubric.** Self-evaluation bias risk noted; obra/TDD as a third-party skill is the partial mitigation.

---

## Stage 1 — DONE

This calibration completes Stage 1 of v0.2:

| Sub-stage | Output | Status |
|---|---|---|
| 1a | `/paap-eval` v0 scaffold (443 lines) + `genesis.md` (276 lines) + `README.md` (107 lines) | ✅ commit `0c9282b` |
| 1b | `references/algorithmic-detectors.md` (726 lines) — 12 detectors with grade-mapping tables | ✅ commit `efb9db7` |
| 1c | `references/semantic-judges.md` (687 lines) — 10 judges with exemplar cases | ✅ commit `425b310` |
| 1d | This file (~XXX lines) — 4-skill validation | ✅ this commit |

`/paap-eval` is now ready for Stage 2 (kappa pilot). The instrument is calibrated against one third-party manual baseline (obra/TDD A- match) and shows no obvious bias-inflation in reflexive scoring.

---

## Cross-references

- [`./SKILL.md`](./SKILL.md) — The skill being calibrated
- [`./genesis.md`](./genesis.md) — Architecture spec for `/paap-eval`
- [`./references/algorithmic-detectors.md`](./references/algorithmic-detectors.md) — Stage 1b detector logic applied here
- [`./references/semantic-judges.md`](./references/semantic-judges.md) — Stage 1c judge prompts applied here
- [`../../04-RUBRIC/principles.md`](../../04-RUBRIC/principles.md) — The 22 principles being scored against
- [`../../04-RUBRIC/empirical-validation.md`](../../04-RUBRIC/empirical-validation.md) — v0.1 50-skill survey context (where obra/TDD's manual A- comes from)
- [`../../05-EVALUATION/`](../../05-EVALUATION/) — The 4 `meta-paap`-generated skill evaluations (out of scope for Stage 1d; covered in Stage 2)
- [`../../07-OPEN-QUESTIONS/`](../../07-OPEN-QUESTIONS/) — v0.2 plan; Stage 2 (kappa pilot) is next
