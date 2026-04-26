# Scoring Template

> Copy this file to score any SKILL.md against the 25 principles. Use it for self-audit, peer review, or contribution to the community evaluation set.

This template is the canonical scoring instrument for the rubric in [`principles.md`](./principles.md). Use it consistently and the resulting evaluations are comparable across authors and skills.

---

## Usage

1. Copy this file to a new location (e.g., `05-EVALUATION/community/your-skill-name.md` for contributions, or anywhere local for self-audit).
2. Fill in the metadata block.
3. **Declare the archetype first.** It determines which principles apply.
4. Score each applicable principle using the grade scale in [`principles.md`](./principles.md).
5. Mark `N/A` with explicit one-sentence justification for principles that don't apply to your skill's archetype or design.
6. Compute the overall grade.
7. Write the narrative sections (strengths, weaknesses, risk-ranked failure modes, what you'd change in v2).

A scored skill takes ~30-45 minutes for a thorough first pass. Don't rush it; the value is in the honest weaknesses, not the headline grade.

---

## Metadata block

```
Skill name:        /your-skill-name
Repo / location:   https://github.com/.../skills/your-skill-name/SKILL.md
Lines:             N
Archetype:         Procedural / Reference / Creative / Hybrid
Path:              LEAN (<100 lines) / FULL (100-400) / ORCHESTRATION (400+)
Composition:       standalone / N composed (list names if visible)
Authored by:       human / meta-paap / hybrid
Date scored:       YYYY-MM-DD
Scorer:            Your name + handle
Rubric version:    v0.3 (Catafal, 2026)
```

---

## Archetype declaration

Before scoring, state and justify the archetype.

```
Archetype: [Procedural / Reference / Creative / Hybrid]

Justification (1-2 sentences):
[Why this archetype? What's load-bearing in this skill — phases-and-gates, library-documentation, output-spec-and-voice, or a mix?]

If Hybrid:
[Which dominant mode does the skill lean toward, and which principles will be applied?]
```

Once the archetype is declared, only the applicable principles (per the matrix in [`principles.md`](./principles.md)) need to be graded. Mark non-applicable principles `N/A — archetype mismatch` with one-sentence justification.

---

## Principle-by-principle scoring

Fill in the table. Use the grade scale: A+, A, B+, B, C, D, F, or N/A. For every grade, add a one-line note. For every N/A, the note IS the justification.

| # | Principle | Grade | Notes / evidence |
|---|---|---|---|
| 1 | Description as router | | |
| 2 | Route before work | | |
| 3 | Modes | | |
| 4 | State | | |
| 5 | Parallel | | |
| 6 | Personas / voice | | |
| 7 | Files = bus | | |
| 8 | Synthesis | | |
| 9 | Human gate | | |
| 10 | Exit = question | | |
| 11 | Output spec | | |
| 12 | Gates = 3 parts | | |
| 13 | External storage | | |
| 14 | Context scope | | |
| 15 | Progress | | |
| 16 | Errors | | |
| 17 | Autonomy | | |
| 18 | Path resolution | | |
| 19 | Composition | | |
| 20 | Output-first | | |
| 21 | Decision class drives gating | | |
| 22 | Voice + writing rules | | |
| 23 | Host-portable | | |
| 24 | Self-observation | | |
| 25 | Spawn-detection | | |

**Aggregate grade:** [computed from applicable principles only — N/A grades excluded from average]

---

## Required narrative sections

After the table, fill in:

### Key strengths (3-5 bullets)

What this skill does notably well. Specific, with line references where useful. Each bullet should name *the principle it exemplifies* and *what makes the skill's implementation distinctive*.

### Key weaknesses (3-5 bullets)

What's missing or under-specified. Honest. Be willing to flag your own work. Each bullet should name *the principle the skill scored worst on* and *the specific shape of the gap*.

### Risk-ranked failure modes

For each weakness, classify likelihood of failing on first run:
- **HIGH** — likely to fail or produce wrong output on first run if the skill is invoked
- **MEDIUM** — likely to fail in some contexts, work in others
- **LOW** — unlikely to cause a visible failure but is a structural gap worth noting

### What you'd change in v2

One paragraph. The single highest-leverage edit. If you only got to fix one thing, what would it be?

### Honest summary

2-3 sentences. What is this skill genuinely good for? What is it NOT good for? Would you recommend it to a colleague who needed to do the same task?

---

## Aggregating across multiple skills

If you're scoring 5+ skills as a coordinated evaluation:

- Tabulate the grades per principle across all skills
- Identify principles where most skills score similarly (consensus signal — either consistently strong or consistently weak across the corpus)
- Identify principles where grades vary widely (signal that the principle's wording is ambiguous, or that the skills genuinely differ on this dimension)
- Surface bottom-up patterns the principles don't yet name; document those as candidates for [`empirical-validation.md`](./empirical-validation.md) updates

This is exactly the protocol used in v0.1's [`05-EVALUATION/regression.md`](../05-EVALUATION/regression.md) and the 50-skill survey documented in [`empirical-validation.md`](./empirical-validation.md). Replicating that protocol on new skills is the most valuable contribution this repo can receive.
