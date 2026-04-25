# Empirical Validation of the 20 Principles

> The 20 principles are top-down hypotheses. This file presents the bottom-up evidence: a survey of 50 community skills, scored and clustered, comparing observed patterns to the rubric.

**Status:** Skeleton — content populated in Phase 2b (survey) + Phase 3 (writeup).

---

## Why this exists

A rubric you derived yourself, scored by yourself, on skills you wrote, is not a rubric. It's a self-portrait.

This file is the falsification attempt: take ~50 skills written by other people, classify them, score a sub-sample, and check whether the principles hold up empirically. Where they don't, the principles get revised.

---

## Methodology (Phase 2b)

**Corpus:**
- `anthropics/skills` (official)
- `awesome-claude-skills` curated lists
- Top-starred individual SKILL.md repos on GitHub
- gstack (28 commands, treated as one connected corpus)

**Sample:**
- N = 50 skills
- Stratified sampling across:
  - Domain (research / code / ops / content / knowledge / other)
  - Complexity tier (lean / full / orchestration)
  - Authoring origin (community / Anthropic / individual practitioner)

**Classification axes (recorded for all 50):**
- Domain
- Complexity tier (lean: <100 lines / full: 100-400 / orchestration: 400+)
- Composition (standalone / N composed)
- Persona pattern (none / scoped role / behavioral)
- Has YAML anti-triggers? (Y/N)
- Has Phase 0 routing? (Y/N)
- Has explicit exit conditions? (Y/N — quick visual)
- Has quality gates with all 3 parts? (Y/N — quick visual)

**Deep scoring (10 of 50):**
- Sub-sample of 10 fully scored against the 20 principles using the template
- Sub-sample chosen to span the complexity spectrum

---

## Findings (placeholder)

Phase 3 fills in:

### Distribution observations

(Tables: domain × complexity, composition × complexity, etc.)

### Most-violated principles

Ranking of principles by frequency of violation in the sample. Hypothesis: principles 12 (Gates = 3 parts), 10 (Exit = question), and 16 (Errors) are the most-violated, because they're the hardest to do well and easiest to skip.

### Most-respected principles

Ranking of principles consistently met. Hypothesis: principles 1 (Description as router) and 11 (Output spec) are most-respected, because they're forced by the format.

### Bottom-up clusters

Patterns observed in the corpus that *don't* map cleanly to any of the 20 principles. Candidate additions to the rubric.

### Top-down principles that didn't survive

Principles in the 20 that the survey suggests are too narrow, too broad, or redundant. Candidate revisions or removals for v0.2.

### Score distribution (10-skill deep dive)

Histogram of overall grades. Comparison to the n=4 `meta-paap` regression study in `05-EVALUATION/`.

---

## Limitations (state honestly)

- N=50 is enough for direction, not statistics
- Sampling bias toward visible / starred skills
- Single scorer (until v0.2 when multi-scorer reliability becomes the next experiment)
- Rubric author scoring against own rubric — known weakness

---

## Source material (public)

- Phase 2b corpus — `anthropics/skills`, `awesome-claude-skills` curated lists, top-starred individual repos
- gstack public repo (Garry Tan)
- Cross-reference: [`../02-LANDSCAPE.md`](../02-LANDSCAPE.md) Part D for the narrative version of these findings

---

*Populated in Phase 2b + Phase 3.*
