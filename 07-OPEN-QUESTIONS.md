# 07 — Open Questions

> What v0.2 and v1.0 will tackle, and where contributions are most useful right now.

**Status:** Skeleton — full content lands in Phase 3.

---

## v0.2 priorities (next 4-8 weeks after v0.1 publish)

### 1. Head-to-head experiment — hand-written vs `meta-paap`-generated
The biggest unanswered question. The current evaluation measures structural compliance against the rubric. It does **not** measure whether `meta-paap` skills produce better *outputs when run* than skills hand-written by a competent practitioner.

**Design (draft):**
- 5-8 workflows
- Each authored twice: once hand-written by an experienced skill author, once via `meta-paap`
- Each run against a defined task battery
- Outputs scored blind by a quality rubric (separate from the 20 architectural principles)
- Authoring time recorded for each

**Open design decision:**
- What metric defines output quality? Three candidates:
  - (a) Task completion rubric (acceptance criteria per workflow)
  - (b) Blind preference rating (panel pairs)
  - (c) Downstream outcome metric (workflow-specific real-world value)
- Likely hybrid of (a) + (b)

### 2. Multi-scorer rubric reliability
Currently the 20 principles are scored by one person. Inter-rater agreement is unknown.

**Design (draft):**
- 3-5 scorers independently grade the same 10 skills
- Compute Cohen's kappa per principle
- Identify principles with low agreement (likely too vague or too overlapping)
- Revise the rubric based on findings

### 3. Extending the empirical survey to N=100
v0.1 ships with N=50. Doubling the sample tests whether the patterns observed are stable or sample-dependent.

### 4. `meta-paap` self-critique improvements
The 4/4 systematic weakness:
- Add an execution-trace pass (data flow from Phase N output → Phase N+1 references)
- Add a reference-validation pass (do named skills/files actually exist at resolved paths?)
- Add a safety-audit pass (read project `CLAUDE.md`, check generated skill against it)

Then re-run the n=4 evaluation to see if the systematic weakness closes.

---

## v1.0 priorities (paper conversion)

- Convert v0.2 results into a workshop-paper-format submission
- Likely venues: workshops at NeurIPS / ICLR / ACL on agent evaluation, prompting, or developer tools
- Citable via CITATION.cff in the meantime
- The repo remains the living artifact even if a paper publishes

---

## Where contributions help most (right now, v0.1)

### High value
1. **Score one of your skills** against the 20 principles, contribute to `05-EVALUATION/community/`
2. **Argue for adding/removing/rewording a principle** with concrete evidence from a real skill
3. **Propose new test workflows** that stress-test the rubric in ways the current 4 don't

### Medium value
4. **Bug reports on `examples/pre-call/`** if it fails to run as documented
5. **Citations the landscape review missed** — papers, blog posts, framework documentation
6. **Tonal sharpening** — flag any AI-slop, vague claims, or inflated symbolism

### Low value (don't PR these)
- New `meta-paap` features (happens in the source skill repo)
- Tonal rewrites without substantive change
- README overhauls without thesis change

---

## Things I'm deliberately NOT trying to answer in v0.1

- Whether PaaP scales to multi-tenant SaaS (it doesn't, and that's fine)
- Whether the 20 principles generalize beyond Claude Code (probably yes for Cursor/Goose/etc., but not tested)
- Whether `meta-paap` is the optimal generator design (almost certainly not — it's a starting point)
- Long-term ecosystem dynamics (skill markets, monetization, certification) — speculative, out of scope

---

## Citations of *this* file

If you contribute work that builds on these open questions, cite the repo via [CITATION.cff](./CITATION.cff). When the v1.0 paper drops it'll get its own DOI.

---

*Populated in Phase 3.*
