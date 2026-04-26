# Changelog

All notable changes to **Prompt as a Process** documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning is **content-tied**, not strict semver: each release describes both repository state and rubric state. See [`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md) "Versioning policy" for the canonical version log.

---

## [Unreleased] — v0.3 in progress

**Theme:** structural cleanup + rubric promotion + planned multi-model kappa + output-quality test expansion.

### Added

- **v0.3 priority #3 — output-quality head-to-head expansion (5×3×3)** ([`05-EVALUATION/head-to-head-expanded.md`](./05-EVALUATION/head-to-head-expanded.md)). Scaled v0.2's N=1 humanizer head-to-head into 5 workflows × 3 inputs × 3 cross-vendor judges = 45 paired quality judgments. **Aggregate handwritten preference, narrow margin** (24 wins / 20 / 1 TIE across 45 judgments). **Workflow-specific picture:** `remember` is a clean *generated* victory (9/9 unanimous), `humanizer` a clean *handwritten* victory (8/9 — Gemini dissents on marketing only), `5d-thinking` slightly favors generated (5/9), `eod` and `prompt-engineering` favor handwritten. **Provenance prediction barely above chance:** GPT-5.4 67% (10/15), Claude 60% (9/15), Gemini-3 53% (8/15 = chance baseline). v0.2's N=1 mis-attribution finding generalizes — blind judges cannot reliably tell hand-tuned from generated. **Cross-judge cluster pattern from the kappa pilot replicates here:** Claude+GPT cluster on most pairs, Gemini-3 is consistently the outlier. Per-dimension finding: handwritten dominates voice/AI-signature/action-specificity (taste-shaped dimensions); generated dominates title-quality/distillation/decision-relevance (rubric-articulable dimensions). The framework can defensibly claim: meta-paap-generated skills *meet or exceed hand-tuned quality on workflows the rubric describes well*; handwritten still wins on production-iterated voice work.
- `05-EVALUATION/head-to-head-expanded-raw-data.md` — verbatim 30 outputs (handwritten + generated arms × 15 inputs) + 45 judge JSONs (3 cross-vendor judges × 15 pairs) for full reproducibility.

- **v0.3 multi-model kappa pilot — 5-rater matrix (Claude × 3 + GPT-5.4 + Gemini-3-pro-preview)** ([`05-EVALUATION/kappa-pilot-multimodel.md`](./05-EVALUATION/kappa-pilot-multimodel.md)). Same 10 skills as v0.2, single-persona pragmatic-practitioner on the non-Claude raters, full 25-principle rubric. Headline (corrected after Gemini-3 was added): **GPT-5.4 ↔ Claude-pragmatic = 1.20** grade-steps but **Gemini-3 ↔ Claude-pragmatic = 2.30** — the largest pair distance in the dataset, *larger* than within-Claude strict↔pragmatic (1.83). Cross-vendor distances cluster around within-Claude strict↔pragmatic, suggesting model-vendor identity and persona are roughly comparable sources of grade-shift. GPT-5.4 was the well-aligned outlier, not the representative case.
- **5-rater archetype agreement is stable.** All 5 raters unanimous on Reference + Creative skills; disagreements only on the same Procedural↔Hybrid borderline cases v0.2 named. Gemini-3 ↔ Claude-pragmatic on archetype: 8/10 (better than GPT-5.4's 7/10) — disagreement is on grading severity, not skill classification.
- **First inter-model evidence on the 3 v0.3 principles, now from two independent vendors.** Both GPT-5.4 (7/7 near-F) and Gemini-3 (5/6 F-or-near-F) confirm #24 self-observation as a real corpus-wide gap — externally validating the framework's own honest C self-audit across two model families. #23 host-portable: Gemini grades higher (mean ord 9.6 ≈ A−) than GPT-5.4 (7.9 ≈ B). #25 spawn-detection: meta-level applicability disagreement — Gemini marked 9/10 N/A, GPT-5.4 4/10 applicable; the rubric's N/A rule for #25 needs sharpening in v0.4.
- `05-EVALUATION/kappa-pilot-multimodel-raw-data.md` — verbatim per-principle outputs (GPT-5.4 + Gemini-3 sections; both single-attempt successes, no retries).

- **Rubric grew from 22 to 25 principles.** Three deferred candidates from the v0.2 N=80 corpus extension crossed the ≥20% community-prevalence threshold and were promoted into the canonical rubric:
  - **Principle #23 — Host-portable; agent harness is a config knob** (was deferred candidate #29; 8/30 = 27% N=80 evidence — highest of the three)
  - **Principle #24 — Skills observe themselves and feed prior runs forward** (was #26; 6/30 = 20%)
  - **Principle #25 — Skills detect spawn vs. interactive context and adapt** (was #30; 6/30 = 20%)
  Numbering follows community-evidence rank, not original gstack order. Five candidates remain deferred (full list in [`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md) "Deferred candidates (post-v0.3)").
- `04-RUBRIC/scoring-template.md` extended with 3 new rows (now 25 rows).
- `06-META-PAAP/paap-eval/references/algorithmic-detectors.md` adds Detector 23 (host-portable; full grade-mapping table + persona modulation + known limitations).
- `06-META-PAAP/paap-eval/references/semantic-judges.md` adds Judge 24 (self-observation) and Judge 25 (spawn-detection); both with exemplar A+/A/B/C/D/F/N/A cases plus persona modulation.
- `04-RUBRIC/reflexive-self-audit.md` v0.3 delta section: repo re-scored on #23 (B+), #24 (C — honest weakness, write side present, read-back missing), #25 (N/A justified). New aggregate: **A−** (down from A on the 22-principle scale).

### Changed

- **Numbered top-level chapters reorganized into folders for consistency.** Every numbered entry is now a folder (`01-CONCEPT/`, `02-EVIDENCE/`, `03-ANATOMY/`, `04-RUBRIC/`, `05-EVALUATION/`, `06-META-PAAP/`, `07-OPEN-QUESTIONS/`). Single-file chapters live as `<NN-NAME>/README.md` so GitHub auto-renders them on folder navigation.
- All 318 relative cross-references updated to the new paths; cross-link audit reports 0 broken.
- Added folder-index `README.md` to `04-RUBRIC/` and `05-EVALUATION/` orienting readers to the contents of each.
- `06-META-PAAP/paap-eval/SKILL.md` updated to reference the 25-principle rubric (was 22). Algorithmic principle list grew from 12 to 13; semantic principle list grew from 10 to 12. Self-disclosure footer scorer string bumped to `v0.3.0-dev`.
- `06-META-PAAP/paap-eval/calibration.md` v0.3 scope note added: existing 22-principle calibration remains valid; 25-principle re-calibration deferred to a follow-up task.
- `04-RUBRIC/principles.md` versioning section updated; rubric citation form bumped to `v0.3 (Catafal, 2026)`.
- `README.md`, `CITATION.cff`, `06-META-PAAP/SKILL.md`: principle count references updated from 22 to 25.

### Migration note

- External links pointing to `01-CONCEPT.md`, `02-EVIDENCE.md`, `03-ANATOMY.md`, or `07-OPEN-QUESTIONS.md` will 404 after the structural commit. Replace with the folder form (e.g., `01-CONCEPT/`) or `<NN-NAME>/README.md`.
- v0.1 and v0.2 evaluations cited *"PaaP rubric v0.1"* or *"v0.2"* — both used the 22-principle rubric. v0.3+ evaluations should cite *"PaaP rubric v0.3 (Catafal, 2026)."* Past evaluations remain valid at their cited rubric version.
- `/paap-eval` runs against the 25-principle rubric. The detectors/judges for #23, #24, #25 are wired in but not calibration-tested yet — grades on these three principles are provisional until the v0.3 kappa re-run completes.

---

## [v0.2] — 2026-04-26

**Theme:** evidence + tooling. **Rubric content unchanged from v0.1**; v0.2 builds the empirical case and operational infrastructure that v0.1 deliberately deferred.

### Added

**The instrument: `/paap-eval` skill** (06-META-PAAP/paap-eval/, 6 files, ~2,400 lines)
- Stage 1a — scaffold via `meta-paap` protocol (`SKILL.md`, `genesis.md`, `README.md`)
- Stage 1b — 12 algorithmic detectors with persona-modulated grade mappings (`references/algorithmic-detectors.md`)
- Stage 1c — 10 semantic LLM-judge prompts with exemplar cases per grade level (`references/semantic-judges.md`)
- Stage 1d — calibration validation against 4 reference skills, including the only third-party manual baseline (obra/TDD A- match)

**Inter-rater reliability data** (`05-EVALUATION/kappa-pilot.md` + raw data)
- 3-persona × 10-skill pilot study (30 independent evaluations)
- Mean inter-rater grade-step distances quantified:
  - strict ↔ pragmatic: 1.83
  - strict ↔ charitable: 1.63
  - pragmatic ↔ charitable: 0.60
- 7/10 archetype unanimous detection (3 dissents on Procedural↔Hybrid borderlines)
- 5 v0.3 rubric-revision recommendations surfaced (auto-N/A column, exit-as-question rebroadening, primary archetype forcing)

**Corpus extension N=50 → N=80** (`04-RUBRIC/corpus-extension-30-skills.md` + raw scoring)
- 30 new skills scored via `/paap-eval` across 18 distinct new authors (combined N=80, 36 distinct authors)
- 5 new authors from non-English-speaking backgrounds (Chinese, Russian, Egyptian, Polish, Indian/Korean)
- Domain expansion: finance, healthcare/biometrics, scientific computing, design audit, content quality, product management, crypto APIs
- Archetype distribution at N=80: Procedural 60% (down from 76%) / Reference 20% (up from 12%) / Creative 11% / Hybrid 9%

**Deferred-candidate verdicts** (`04-RUBRIC/empirical-validation.md` updated)
- **PROMOTE for v0.3** (≥20% community-corpus prevalence at extended N): #26 self-observation, #29 host-portable, #30 spawn-detection
- **CONFIRM gstack-only** (0% community sightings): #22 section-skip composition, #24 dual-voice consensus, #28 plan-rubric-reuse-at-audit
- Keep deferred (insufficient evidence): #21 build-artifact (10%), #25 hooks-as-enforcement (7%)

**Head-to-head experiment** (`05-EVALUATION/head-to-head.md`)
- 5 hand-written production skills (real daily-use, not authored for the test) compared against 5 fresh `meta-paap`-generated equivalents
- Generators never saw hand-written implementations (blind generation from workflow briefs only)
- **Structural rubric:** generated mean **A**, hand-written mean **B+** (+0.66 grade-step delta consistent across 4 archetypes)
- **Blind output-quality test (humanizer):** TIE 22/25 — both successfully removed AI signatures, different strengths (generated wins on editorial discipline, hand-written wins on voice)
- **Blind judge MISATTRIBUTED provenance** — couldn't distinguish generated from hand-written, guessed wrong on both

**Five new chapters/files in evaluation directory:**
- `05-EVALUATION/kappa-pilot.md`
- `05-EVALUATION/kappa-pilot-raw-data.md`
- `05-EVALUATION/corpus-extension-raw-data.md`
- `05-EVALUATION/head-to-head.md`
- `04-RUBRIC/corpus-extension-30-skills.md`

### Changed

- README status badge: "v0.1 → v0.2 in progress" → "v0.2 released"
- README roadmap: v0.2 marked released, v1.0 marked conditional-unlocked
- `07-OPEN-QUESTIONS/README.md` restructured: full v0.2 plan replaced with v0.2-delivered summary + v0.3 priorities
- `04-RUBRIC/empirical-validation.md` headline: N=50 → N=80; archetype distribution table updated; all 8 deferred candidates given v0.2 verdicts
- `04-RUBRIC/principles.md` versioning policy: v0.2 marked released, v0.3 priorities listed, v1.0 unlocked
- `06-META-PAAP/README.md` "See also" surfaces `/paap-eval` as the complementary scoring skill
- `04-RUBRIC/reflexive-self-audit.md` updated with v0.2 delta section
- `CITATION.cff` version 0.1.0 → 0.2.0; date-released bumped; abstract expanded with v0.2 deliverables

### Removed

Nothing. v0.2 is purely additive.

### Deferred to v0.3

- **Promote 3 corpus-validated candidates** (#26, #29, #30) — turns rubric into 25-principle artifact
- **Multi-model kappa** (Claude + GPT-5 + Gemini) — current pilot is prompt-variant reliability only
- **Output-quality test expansion** to 5 workflows × 3-5 inputs each — current head-to-head is N=1 task
- **Add "rationalizations to reject" pattern to `meta-paap` persona generation** — closes the persona-depth gap surfaced in head-to-head
- **Run head-to-head on community skills** (not just author's hand-written) to remove self-evaluation bias from baseline
- **Test output quality on Reference and Creative archetypes** — Stage 4's axis-2 used only Hybrid (humanizer)

### What v0.2 evidence enables

A workshop-paper-conditional v1.0 becomes concretely defensible. The defensible paper title:

> *"Prompt-as-a-Process: Evidence That Generator-Produced Skill Files Match Hand-Authored Ones On Structural Quality and Output Quality, From a Single-Practitioner Tooling Study."*

Honest, not over-claimed, and supported by the v0.2 evidence base. v1.0 ship depends on whether the v0.3 expansions (multi-model, multi-task, multi-author baseline) hold up.

---

## [v0.1] — 2026-04-25

**Theme:** framework + rubric + first evaluation. Initial public release.

### Added

- **22-principle PaaP rubric** with 3-archetype applicability matrix (Procedural / Reference / Creative)
- **gstack case study** — 50 SKILL.md from Garry Tan analyzed (~82k stars at snapshot, ~43k lines)
- **50-skill community survey** — N=50 baseline corpus across 18 authors
- **`/meta-paap` skill** — the skill-that-generates-skills, with 7-phase architecture protocol
- **n=4 regression study of `meta-paap` outputs** (`/skill-audit`, `/article-forge`, `/review-plan`, `/idea-to-pr`) with cross-test pattern analysis
- **Reflexive self-audit** — repo scoring itself against own rubric (A overall, 4 A+ / 9 A / 1 A- / 1 B+ / 1 B)
- **7 chapters:** CONCEPT, EVIDENCE (originally LANDSCAPE), ANATOMY, RUBRIC, EVALUATION, META-PAAP, OPEN-QUESTIONS
- **Runnable example:** `examples/pre-call/SKILL.md`
- **Dual licensing:** MIT (code) + CC-BY-4.0 (docs)

### Documented limitations (v0.1 academic gaps)

- Single-scorer rubric work (no inter-rater reliability)
- N=4 convenience-sampled evaluation (no comparison baseline)
- 4-author concentration (66% of v0.1 corpus from Anthropic + obra + ToB + michalparkola)
- No head-to-head outcome test (no evidence generated skills produce comparable outputs)
- No multi-scorer reliability data
- 8 deferred gstack candidates without community-corpus evidence

**All v0.1 limitations are addressed (in proportion) by v0.2.**

### Acknowledgements (v0.1)

- Anthropic Claude Code team — SKILL.md format
- Garry Tan — `gstack` (largest production case study)
- Andrej Karpathy — autoresearch pattern
- Octomind team — documented LangChain-removal case
- Broader Claude Code skills community — 50-skill corpus contributors
- External-reviewer feedback (Clicky Codex audit) — applied as part of v0.1 final polish

---

## Versioning conventions

- **Major versions** (v1.0, v2.0): rubric content changes (principles added, removed, or substantially reworded) OR significant scope shifts (e.g., paper publication, multi-vendor adoption)
- **Minor versions** (v0.1 → v0.2): evidence + tooling additions; rubric content stable
- **Patch versions** (v0.2.1, v0.2.2): bug fixes, minor wording tweaks, cross-reference corrections

The rubric in [`04-RUBRIC/principles.md`](./04-RUBRIC/principles.md) is the source of truth for what each version "contains" intellectually. The repository is the operational artifact.

When citing this work, include the version: *"PaaP framework v0.2 (Catafal, 2026)."*
