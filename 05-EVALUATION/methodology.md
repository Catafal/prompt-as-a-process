# Evaluation Methodology

> How we test, why this rubric, and what an n=4 study can and cannot tell you.

**Status:** Skeleton — full content lands in Phase 3, formalized from the original n=4 regression study into a proper methods section.

---

## What this evaluates

`meta-paap` is a skill that generates other skills. It takes a workflow description, asks five elicitation questions, scans installed skills for composition candidates, designs an architecture, presents it for review, generates the SKILL.md, and red-teams its own output.

The evaluation question:

> **Does meta-paap-generated output reliably meet the 20 principles, across workflow types?**

Not "is the output good in some abstract sense." Specifically: **does the structural rubric hold?** That's a falsifiable question with a defined rubric.

---

## What this does NOT evaluate (yet)

- **Output quality of skills when run.** Whether a generated `/skill-audit` skill actually produces a better audit than a hand-written `/skill-audit`. That's the v0.2 head-to-head experiment.
- **Authoring time savings.** Anecdotal claim only at v0.1; quantified in v0.2.
- **Comparative rubric scoring against hand-written skills.** Also v0.2.

---

## Test design

**Workflows tested (n=4):**
1. Analytical tool with parallel agents (`/skill-audit`)
2. Knowledge processing pipeline with skill composition (`/article-forge`)
3. Dual-mode plan reviewer with behavioral personas (`/review-plan`)
4. Full orchestration pipeline with 10 composed skills (`/idea-to-pr`)

**Workflows deliberately not tested (yet):**
- Simple personal workflow (lean path) — was planned as test 5; deferred to v0.2

**Why these four:**
- Span the complexity spectrum (567 / 350 / 508+326 / 555+173 lines)
- Stress different principles (parallel agents, composition, modes, state, human gates)
- Realistic — all four are skills the author actually uses or built for real work

---

## Scoring protocol

Each generated skill scored on:

1. **Process compliance** — did `meta-paap` execute its own protocol correctly? (7 phases per generation)
2. **The 20 principles** — A+/A/B+/B/C/D/F/N-A per principle, with notes and evidence
3. **Key strengths** — 3-5 narrative bullets
4. **Key weaknesses** — 3-5 narrative bullets, risk-ranked HIGH/MEDIUM/LOW
5. **Overall grade** — derived

After all four tests: **cross-test regression analysis** identifying patterns that are:
- Consistently strong (4/4)
- Consistently weak (4/4) — these are the systematic generator weaknesses
- Improving across tests
- One-off

---

## Limitations (honest)

- **N=4** is enough for pattern detection, not statistical claims
- **Single scorer.** Multi-scorer reliability is a v0.2 priority
- **Rubric author scoring own rubric.** Self-reinforcement risk
- **Workflow selection is convenience-sampled** (skills the author wanted to build anyway)
- **No blinding.** The scorer knew which skills were `meta-paap`-generated
- **No comparison baseline.** Without a hand-written counterpart, "this skill scored A-" is a one-sided claim

The cross-test regression mitigates some of this by surfacing patterns *across* tests rather than relying on a single grade. But the limitations are real and stated upfront so readers can calibrate.

---

## Findings preview

(Full per-test files in this directory, summary in [`regression.md`](./regression.md).)

**Headline:** `meta-paap` produces skills scoring B+ to A across the 4 tests (mean A-). Two systematic weaknesses appeared in 4/4 tests: (1) self-critique is too lenient — validates structure but doesn't trace execution paths, validate named references, or check project safety rules; (2) the hardest technical phase is the least specified.

(Phase 3: full discussion.)

---

## Cross-references

- [`./regression.md`](./regression.md) — cross-test patterns and conclusions
- [`./test-1-skill-audit.md`](./test-1-skill-audit.md) through [`./test-4-idea-to-pr.md`](./test-4-idea-to-pr.md) — per-test detail
- [`../06-META-PAAP/SKILL.md`](../06-META-PAAP/SKILL.md) — the skill being evaluated

---

*Populated in Phase 3.*
