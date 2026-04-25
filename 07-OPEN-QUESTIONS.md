# 07 — Open Questions

> What v0.2 and v1.0 will tackle, and where contributions are most useful right now.

## v0.2 priorities (next 4-8 weeks after v0.1 publish)

### 1. Head-to-head experiment — hand-written vs `meta-paap`-generated

The biggest unanswered question. The current evaluation measures structural compliance against the rubric. It does **not** measure whether `meta-paap` skills produce better *outputs when run* than skills hand-written by a competent practitioner.

**Design (draft):**
- 5-8 workflows spanning the three archetypes (Procedural / Reference / Creative)
- Each authored twice: once hand-written by an experienced skill author, once via `meta-paap`
- Each run against a defined task battery
- Outputs scored blind by a quality rubric (separate from the 22 architectural principles)
- Authoring time recorded for each

**Open design decision:**
- What metric defines output quality? Three candidates:
  - (a) Task completion rubric (acceptance criteria per workflow)
  - (b) Blind preference rating (panel pairs)
  - (c) Downstream outcome metric (workflow-specific real-world value)
- Likely hybrid of (a) + (b)

### 2. Multi-scorer rubric reliability

Currently the 22 principles are scored by one person. Inter-rater agreement is unknown — and the rubric author scoring his own rubric is a known weakness.

**Design (draft):**
- 3-5 scorers independently grade the same 10 skills
- Compute Cohen's kappa per principle
- Identify principles with low agreement (likely too vague or too overlapping)
- Revise the rubric based on findings — the principles with the lowest kappa are the weakest

### 3. Extending the empirical survey to N=100

v0.1 ships with N=50. Doubling the sample tests whether the patterns observed are stable or sample-dependent.

Specific things v0.1 found at N=50 that need confirming at N=100:
- The archetype distribution (~76% Procedural / ~12% Reference / ~6% Creative / ~6% Hybrid)
- The author-concentration problem (4 authors = 66% of v0.1 corpus)
- The 6 bottom-up clusters surfaced in [`04-RUBRIC/empirical-validation.md`](./04-RUBRIC/empirical-validation.md)

### 4. `meta-paap` self-critique improvements

The 4/4 systematic weakness from the [n=4 regression study](./05-EVALUATION/regression.md):

- Add an **execution-trace pass** — data flow from Phase N output → Phase N+1 references
- Add a **reference-validation pass** — do named skills/files actually exist at resolved paths?
- Add a **safety-audit pass** — read project `CLAUDE.md`, check generated skill against it

Then re-run the n=4 evaluation to see if the systematic weakness closes. If it does, that's the v2 ship.

### 5. Re-evaluate the 8 deferred gstack candidates

Eight patterns from gstack didn't clear the v0.1 promotion bar against the 50-skill community survey. With N=100 and possibly more case studies, these may merit promotion:

- SKILL.md as build artifact (template-rendered, CI-enforced)
- Composed skills declare which sections parent owns (section-skip-list composition)
- Dual-voice consensus for verification
- Hard guardrails via hooks, not prose
- Skills observe themselves and feed prior runs forward
- Plan-stage rubric reused at audit time
- Skills are portable; host is a config knob
- Skills detect spawn vs. interactive and adapt

See [`04-RUBRIC/empirical-validation.md`](./04-RUBRIC/empirical-validation.md) for current evidence.

### 6. Refine the principles surfaced from bottom-up clusters

The community survey found 6 patterns the rubric only partially captures. v0.2 should decide which (if any) become explicit principles vs. sub-patterns of existing ones:

1. **Refusal-as-skill** (currently absorbed into #2 Phase 0 routing) — promote to its own principle?
2. **Rationalizations Rejection Table** (currently in #6 Personas, #22 Voice rules) — surface as canonical pattern?
3. **Aesthetic anti-patterns** (currently in #11 Output spec) — own principle for creative skills?
4. **Tool-availability fallback chain** (currently in #12 Gates 3 parts) — surface as canonical example?
5. **Tone-as-instruction** (currently in #6 Personas, #22 Voice rules) — same as #6 or distinct?
6. **Reference-style skill archetype** — addressed in v0.1 via the archetype framing.

---

## v1.0 priorities (paper conversion)

- Convert v0.2 results into a workshop-paper-format submission
- Likely venues: workshops at NeurIPS / ICLR / ACL on agent evaluation, prompting, or developer tools
- Citable via CITATION.cff in the meantime
- The repo remains the living artifact even if a paper publishes

---

## Where contributions help most (right now, v0.1)

### High value
1. **Score one of your skills** against the 22 principles using [`04-RUBRIC/scoring-template.md`](./04-RUBRIC/scoring-template.md). Submit as a PR adding a file under `05-EVALUATION/community/`.
2. **Argue for adding/removing/rewording a principle** with concrete evidence from a real skill. Open an issue tagged `[principle]`.
3. **Propose new test workflows** that stress-test the rubric in ways the current 4 don't — particularly skills in archetypes other than Procedural.
4. **Score gstack skills against the rubric** — gstack is already a confirmed exemplar at the corpus level; per-skill scoring against the 22 principles would be a major contribution.

### Medium value
5. **Bug reports on `examples/pre-call/`** if it fails to run as documented (e.g., LinkedIn search behavior changes).
6. **Citations the landscape review missed** — papers, blog posts, framework documentation.
7. **Tonal sharpening** — flag any AI-slop, vague claims, or inflated symbolism. The repo's credibility depends on this.

### Low value (don't PR these)
- New `meta-paap` features (happens in the source skill repo, not here)
- Tonal rewrites without substantive change
- README overhauls without thesis change
- Self-promotional skill submissions dressed as evaluations

---

## Things v0.1 deliberately doesn't try to answer

- **Whether PaaP scales to multi-tenant SaaS.** It doesn't, and that's fine. The determinism and cost economics are wrong for SaaS. Personal and team-scale tools are the right scope.
- **Whether the 22 principles generalize beyond Claude Code.** Probably yes for Cursor / Codex / OpenClaw — gstack already runs on 10 hosts via setup config. Not yet tested in this repo.
- **Whether `meta-paap` is the optimal generator design.** Almost certainly not — it's a starting point. Better generators will emerge; the rubric is what they should be measured against.
- **Long-term ecosystem dynamics.** Skill marketplaces, monetization, certification, version-pinning conventions. Speculative. Out of scope until empirical evidence accumulates.
- **The "Tan endorses PaaP" question.** He doesn't use the term. Cite gstack as evidence the architecture works; do not cite Tan as PaaP's author.

---

## Citing this work

If you build on the rubric, the methodology, or the empirical findings, cite via [`CITATION.cff`](./CITATION.cff). GitHub renders this into a one-click citation block. When v1.0 ships as a paper, it will get its own DOI.

Rubric citation format: *"PaaP rubric v0.1 (Catafal, 2026)."* Include the version — the rubric will evolve.
