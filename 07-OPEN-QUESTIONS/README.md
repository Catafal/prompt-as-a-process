# 07 — Open Questions

> What v0.3 and v1.0 will tackle, and where contributions are most useful right now.

**Status as of 2026-04-26:** v0.2 RELEASED. See [`../CHANGELOG.md`](../CHANGELOG.md) for what shipped. v0.3 priorities below are derived from v0.2's surfaced findings.

---

## v0.2 in retrospect (released 2026-04-26)

**Theme:** evidence + tooling. v0.2 built the operational instrument (`/paap-eval`) and used it to close — proportionally — every academic blocker v0.1 left open.

### What v0.2 delivered

| v0.1 academic blocker | v0.2 deliverable | Outcome |
|---|---|---|
| Single-scorer rubric (no inter-rater data) | 3-persona kappa pilot via `/paap-eval` | Mean inter-rater 1.83 grade-steps documented |
| N=50 corpus with 4-author concentration | Extended to N=80 across 36 distinct authors | Procedural distribution dropped 76% → 60% |
| 8 deferred gstack candidates without evidence | Re-evaluated against new corpus | 3 promote, 3 confirmed gstack-only, 2 keep deferred |
| No head-to-head outcome data | 5 hand-written vs 5 generated + 1 blind output test | Generated mean A vs HW B+ on rubric; TIE on blind output; provenance mis-attributed |
| `meta-paap` self-critique systematic weaknesses | (deferred to v0.3 — needs `/paap-eval` execution-trace pass) | Documented for v0.3 |

### What v0.2 evidence supports (now defensible)

1. `meta-paap` produces skills scoring B+ to A on the 22-principle rubric across diverse workflows
2. Generated skills consistently meet rubric structure (output contract, decision class, gate completeness) better than typical hand-written equivalents — +0.66 grade-step delta
3. For at least one workflow domain, generated skill output is **indistinguishable from hand-written** by a careful blind reader (humanizer task, judge mis-attributed provenance)

### What v0.2 cannot claim (deferred to v0.3)

1. Output-quality parity *across all workflow domains* — only 1 task tested
2. Reliability under multi-model judging — single Sonnet judge throughout
3. The 3 promotion-ready candidates (#26, #29, #30) are integrated into the rubric

The v0.3 priorities below address these gaps.

---

## v0.3 priorities (planned next)

### 1. Promote 3 corpus-validated candidates → 25-principle rubric ✅ DONE

v0.2 Stage 3's headline finding: 3 of 8 deferred gstack candidates appeared in ≥20% of community skills, making them real emerging patterns rather than gstack-specific:

- **#29 Skills are portable; host is config knob** (8/30 = 27%) → promoted as **principle #23 (host-portable)**
- **#26 Skills observe themselves and feed prior runs forward** (6/30 = 20%) → promoted as **principle #24 (self-observation)**
- **#30 Skills detect spawn vs interactive and adapt** (6/30 = 20%) → promoted as **principle #25 (spawn-detection)**

Promoted in v0.3 (commit landed 2026-04-26). Numbering follows community-evidence rank, not original gstack order. The rubric in [`../04-RUBRIC/principles.md`](../04-RUBRIC/principles.md) now has 25 principles; the scoring template ([`../04-RUBRIC/scoring-template.md`](../04-RUBRIC/scoring-template.md)) has 25 rows; `/paap-eval` ([`../06-META-PAAP/paap-eval/SKILL.md`](../06-META-PAAP/paap-eval/SKILL.md)) has 13 algorithmic detectors and 12 semantic judges; the reflexive self-audit ([`../04-RUBRIC/reflexive-self-audit.md`](../04-RUBRIC/reflexive-self-audit.md)) has been re-scored at 25-principle scale (aggregate dropped from A to A− because the repo scores honest C on #24).

**Still pending in v0.3:** kappa pilot re-run at 25-principle scale (combined with priority #2 below) and architecture-checklist updates inside `meta-paap` for the new principles.

### 2. Multi-model kappa (Claude + GPT-5 + Gemini) — IN PROGRESS

v0.2's kappa pilot is **prompt-variant reliability**, not multi-rater. All 3 personas ran on Claude Sonnet. v0.3 runs the same 10-skill corpus through additional model families.

**v0.3 Codex/GPT-5.4 + Gemini-3-pro-preview runs (✅ DONE 2026-04-26).** Same 10 skills, full 25-principle rubric, single pragmatic-practitioner persona, both vendors. Full results: [`../05-EVALUATION/kappa-pilot-multimodel.md`](../05-EVALUATION/kappa-pilot-multimodel.md).

**Headline (post-Gemini correction):** GPT-5.4 ↔ Claude-pragmatic = 1.20 grade-steps; **Gemini-3 ↔ Claude-pragmatic = 2.30** — the largest pair distance in the dataset, *larger* than within-Claude strict↔pragmatic (1.83). Cross-vendor distances cluster around within-Claude strict↔pragmatic; model-vendor identity and persona contribute roughly comparable variance. **GPT-5.4 was the well-aligned outlier, not the representative case.** The "rubric travels" framing the GPT-5.4-only data initially supported was overturned once Gemini was added.

Both vendors confirm #24 self-observation as a corpus-wide gap (GPT-5.4: 7/7 near-F; Gemini: 5/6 F-or-near-F) — the framework's honest C self-audit on #24 is externally validated across two independent model families. Archetype detection is stable across all 5 raters (8/10 Reference + Creative unanimous). Disagreement is on grading severity, not skill classification.

**Candidate explanation worth testing in v0.4:** the corpus may have been authored primarily for Claude Code; Claude family models grade them generously; modern GPT-5-class models (gpt-5.4) are strong enough at long-instruction-following to read the rubric similarly to Claude; Gemini-3 may apply the rubric more literally or its training distribution diverges enough that the same instruction text produces a stricter reading. Test: re-run on a deliberately Claude-friendly subset, plus run a Gemini-friendly skill subset on Claude, and see if the asymmetry inverts.

**Still pending in v0.3+:**
- Within-Claude family expansion (Claude Opus / Sonnet / Haiku — 3 model sizes within Anthropic family)
- GPT-5.5 once account access lands
- Per-principle Cohen's kappa across all 5 raters (currently aggregate-grade-distance + a few per-principle observations only)
- Sharpening the rubric's N/A rule for principle #25 (Gemini and GPT-5.4 disagreed on whether #25 applies to Procedural skills generically)

When the multi-vendor matrix is more complete, principles with low cross-model agreement need rewording for v0.4. This is the actual multi-rater study academic reviewers will demand.

### 3. Output-quality test expansion ✅ DONE

v0.2 Stage 4 ran 1 output-quality task (humanizer). Result was directionally meaningful (TIE + mis-attributed provenance) but N=1.

**v0.3 delivered (2026-04-26):** 5 workflows × 3 inputs × 3 cross-vendor judges = 45 paired quality judgments. Full results: [`../05-EVALUATION/head-to-head-expanded.md`](../05-EVALUATION/head-to-head-expanded.md).

**Headline:** narrow handwritten preference overall (24/45 vs 20/45) but **the picture is workflow-specific**:
- `remember` 9/9 unanimous Gen
- `humanizer` 8/9 HW
- `prompt-engineering` 7/9 HW
- `eod` 6/9 HW
- `5d-thinking` 5/9 Gen

**Provenance prediction:** GPT-5.4 67%, Claude 60%, Gemini 53% (chance). v0.2's N=1 mis-attribution finding generalizes. **Cross-judge cluster pattern from the kappa pilot replicates here** at the output-quality level — Claude+GPT cluster, Gemini-3 outlier.

**Per-dimension split:** handwritten dominates voice/AI-signature/action-specificity (taste-shaped); generated dominates title-quality/distillation/decision-relevance (rubric-articulable). The rubric is not purely circular — it encodes both sides. v0.4+ work: third-party hand-written control arm, human-rater layer, larger N per workflow.

### 4. meta-paap v2 — rationalizations + self-observation ✅ DONE

v0.2 Stage 4's most actionable finding for `meta-paap` improvement: generated skills consistently scored lower on persona depth than hand-written exemplars like `obra/test-driven-development`. The gap is the "rationalizations to reject" pattern — naming the bad arguments the model will make and providing the counter, rather than just stating positive behavior.

**v0.3 delivered (2026-04-26):** [`../06-META-PAAP/SKILL.md`](../06-META-PAAP/SKILL.md) bumped to v2.0. Three changes:

- **Persona depth (priority #4 main goal):** discipline-enforcing skills now produce an Iron Law + Rationalizations to Reject table (≥3 rows). The architecture-checklist [§21](../06-META-PAAP/references/architecture-checklist.md) propagates the pattern to every generated skill that enforces behavioral discipline.
- **Self-observation loop (closes the framework's own #24 gap):** Phase 1.5b reads `~/.claude/meta-paap/learnings.jsonl`; Output appends a one-line entry per run. Architecture-checklist [§22](../06-META-PAAP/references/architecture-checklist.md) propagates this to generated procedural skills with state.
- **v0.3 principle checks in self-critique:** Phase 4 now explicitly checks #23, #24, #25 (was 7 critical checks in v1; now 11).

**Validation experiment (N=1, directional):** regenerated humanizer with v2 meta-paap, ran it on the same technical AI passage from priority #3, blind judge compared against v0.3-handwritten output. **v2-generated won 21/25 vs handwritten 11/25** — 10-point margin. Handwritten arm hit the task-compliance cap on 3 dimensions (substance preservation, editorial discipline, AI-signature removal) because it changed the argument — the failure mode rationalizations-to-reject was designed to prevent. Judge correctly predicted provenance both ways. **Honest scope:** priority #3 had handwritten 8/9 humanizer wins; this is N=1 directional confirmation, not full replication. **v0.4: re-run priority #3 with v2-generated arm to test whether v2 closes the persona-depth gap broadly.**

**Reflexive self-audit:** #24 upgraded from C to B+; aggregate from A− back to A. Grounded in observable mechanism (Phase 1.5b + Output write of learnings.jsonl, auditable in the SKILL.md text), not just claim.

### 5. Run head-to-head on community skills (not just author's hand-written)

v0.2 Stage 4's hand-written baseline came from the rubric author's local skill folder. This is a self-evaluation bias: the author may write skills in ways the rubric rewards.

v0.3 runs head-to-head against community skills (e.g., 5 from Stage 3's N=80 corpus across the 4 archetypes), feeding their workflow descriptions to `meta-paap` and comparing.

### 6. `meta-paap` v2 self-critique improvements (deferred from v0.2)

The 4/4 systematic weakness from v0.1's [n=4 regression study](../05-EVALUATION/regression.md):

- Add an **execution-trace pass** — data flow from Phase N output → Phase N+1 references
- Add a **reference-validation pass** — do named skills/files actually exist at resolved paths?
- Add a **safety-audit pass** — read project `CLAUDE.md`, check generated skill against it

These were deferred from v0.2 because they belong with `/paap-eval` (which is the natural place to trace execution paths and validate references). v0.3 can either (a) re-run n=4 evaluation against fixed `meta-paap` v2 OR (b) integrate the three passes into `/paap-eval`'s synthesis phase.

### 7. Resolve v0.2 Stage 4's persona-depth gap finding

v0.2 Stage 4 surfaced that generated skills lack the "rationalizations to reject" depth seen in production-iterated hand-written skills. v0.3 closure depends on Item 4 above (architecture-checklist update).

---

## Items still under research (deferred to v0.3+)

The community survey at v0.2 (N=80) surfaced 6 patterns the rubric only partially captures. v0.3 (after the 3-promotion candidates land) decides which (if any) become explicit principles vs. continue as sub-patterns of existing ones:

1. **Refusal-as-skill** (currently absorbed into #2 Phase 0 routing) — promote to its own principle?
2. **Rationalizations Rejection Table** (currently in #6 Personas, #22 Voice rules) — surface as canonical pattern?
3. **Aesthetic anti-patterns** (currently in #11 Output spec) — own principle for creative skills?
4. **Tool-availability fallback chain** (currently in #12 Gates 3 parts) — surface as canonical example?
5. **Tone-as-instruction** (currently in #6 Personas, #22 Voice rules) — same as #6 or distinct?
6. **Reference-style skill archetype** — addressed in v0.1 via the archetype framing; no further action needed.

Of these 6, the most likely v0.3 promotion is **#1 Refusal-as-skill** based on the v0.2 corpus extension's evidence (Refusal Gate pattern visible in `daymade/fact-checker`, `glebis/jtbd`, `wrsmith108/linear` — at least 3/30 community sightings).

For full v0.2 verdicts on the original 8 deferred gstack candidates, see [`04-RUBRIC/empirical-validation.md`](../04-RUBRIC/empirical-validation.md). Three are promotion-ready (#26 self-observation, #29 host-portable, #30 spawn-detection); three confirmed gstack-only (#22 section-skip, #24 dual-voice, #28 plan-rubric-reuse); two stay deferred (#21 build-artifact, #25 hooks).

---

## v1.0 (defensible after v0.2; conditional on v0.3 expansions)

v0.2 shipped the evidence base v1.0 needs:

- ✅ Inter-rater reliability data (3-persona kappa pilot, mean 1.83 grade-steps)
- ✅ N=80 community corpus across 36 distinct authors
- ✅ Head-to-head experiment with blind judge mis-attributing provenance
- ✅ Reflexive self-audit demonstrating dogfooding discipline

The honest v1.0 paper title:

> *"Prompt-as-a-Process: Evidence That Generator-Produced Skill Files Match Hand-Authored Ones On Structural Quality and Output Quality, From a Single-Practitioner Tooling Study."*

This is defensible. v0.3 expansions (multi-model judging, output-quality test on 5 workflows × 3-5 inputs each, multi-author baseline) determine whether the title strengthens or stays in single-practitioner scope.

Likely venues: workshops at NeurIPS / ICLR / ACL on agent evaluation, prompting, developer tools, or LLM-as-judge methodology. Citable via [`CITATION.cff`](../CITATION.cff) in the meantime.

---

## Where contributions help most (right now, post-v0.2)

### High value
1. **Run `/paap-eval` on one of your skills and submit the scored output** as a PR under `05-EVALUATION/community/`. With v0.2's instrument shipped, this takes ~1 minute per skill instead of 30+ minutes manually.
2. **Run `/paap-eval` on community skills not in v0.2's N=80 corpus** to push toward N=100+ and validate the v0.2 archetype-distribution finding (60% Procedural / 20% Reference / 11% Creative / 9% Hybrid).
3. **Multi-model judge cross-check.** Run `/paap-eval` against a skill, then re-score the same skill with a different model (GPT-5, Gemini). Submit the disagreement table — this is the v0.3 multi-model kappa pilot raw data we need.
4. **Argue for promoting/demoting a principle** with concrete corpus evidence. v0.2 promoted 3 candidates and confirmed 3 as gstack-only; #21 (build-artifact) and #25 (hooks) are still ambiguous and would benefit from more data.

### Medium value
5. **Bug reports on `/paap-eval`** when its scoring diverges sharply from your own assessment of a skill — divergence patterns inform v0.3 detector and judge revisions.
6. **Bug reports on `examples/pre-call/`** if it fails to run as documented.
7. **Citations the evidence chapter missed** — papers, blog posts, framework documentation.
8. **Tonal sharpening** — flag any AI-slop or vague claims. The repo's credibility depends on this.

### Low value (don't PR these)
- New `meta-paap` or `/paap-eval` features (architectural changes happen in source skill repos)
- Tonal rewrites without substantive change
- README overhauls without thesis change
- Self-promotional skill submissions dressed as evaluations

---

## Things v0.2 deliberately doesn't try to answer

- **Whether PaaP scales to multi-tenant SaaS.** It doesn't, and that's fine. The determinism and cost economics are wrong for SaaS. Personal and team-scale tools are the right scope.
- **Whether the 22 principles generalize beyond Claude Code.** Probably yes for Cursor / Codex / OpenClaw — gstack already runs on 10 hosts via setup config. Cross-host kappa is v0.3+ work.
- **Whether `meta-paap` is the optimal generator design.** Almost certainly not — Stage 4 showed gaps in persona depth. Better generators will emerge; the rubric is what they should be measured against. v0.3 will close some of the persona-depth gap via the "rationalizations to reject" addition.
- **Long-term ecosystem dynamics.** Skill marketplaces, monetization, certification, version-pinning conventions. Speculative. Out of scope until empirical evidence accumulates.
- **The "Tan endorses PaaP" question.** He doesn't use the term. Cite gstack as evidence the architecture works; do not cite Tan as PaaP's author.
- **Cross-language generalization.** v0.2 corpus is English-dominant despite 5/36 non-English authors writing in English. Skills authored in Chinese/Russian/Spanish primary languages haven't been corpus-scored.
- **Per-domain rubric tuning.** v0.2 treats all skills with one rubric. Domain-specific extensions (e.g., security-focused additions for security skills, accessibility additions for design skills) might be valuable but are deferred indefinitely.

---

## Citing this work

If you build on the rubric, the methodology, the `/paap-eval` instrument, or the empirical findings, cite via [`CITATION.cff`](../CITATION.cff). GitHub renders this into a one-click citation block. When v1.0 ships as a paper, it will get its own DOI.

**Citation formats:**
- Framework citation: *"PaaP framework v0.2 (Catafal, 2026)."*
- Rubric content citation (rubric content unchanged in v0.2): *"PaaP rubric v0.1 (Catafal, 2026)."*
- Instrument citation: *"`/paap-eval` v0.2.0 (Catafal, 2026)."*

Include the version. The framework will evolve; v0.3 is planned.
