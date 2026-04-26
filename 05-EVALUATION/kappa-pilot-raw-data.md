# Kappa Pilot — Raw Subagent Outputs

> Verbatim outputs from the 3 persona-variant subagents in v0.2 Stage 2's kappa pilot. Preserved for reproducibility and auditability.

**Date:** 2026-04-26
**Method:** 3 parallel general-purpose subagents (Sonnet model), each scoring 10 SKILL.md files with one consistent persona.
**Skills evaluated:** 10 community SKILL.md files at `/tmp/paap-eval-pilot/01-*.md` through `/tmp/paap-eval-pilot/10-*.md`
**Subagent IDs (run 2026-04-26):** strict-academic `a0fa8ff`, pragmatic-practitioner `acd4c2c`, charitable-newcomer `aee38da`

The aggregated analysis is in [`kappa-pilot.md`](./kappa-pilot.md). This file is the raw data.

---

## Strict-academic persona output

### Skill 1: obra/test-driven-development
- ARCHETYPE: Procedural (high)
- Aggregate: **C+**
- Notable scores: #6 A+ (Iron Law), #22 A+ (Rationalizations), #4 F (no state), #7 F (no file bus), #16 D (no error table)
- N/A: 3, 5, 8, 13, 18

### Skill 2: trailofbits/agentic-actions-auditor
- ARCHETYPE: **Hybrid** (high) — only persona to detect Hybrid
- Aggregate: **B+**
- Notable: #1 A, #2 A+, #14 A, #4 C (no state for long audits)

### Skill 3: anthropics/skill-creator
- ARCHETYPE: Procedural (high)
- Aggregate: **B+**
- Notable: #5 A (parallel), #11 A, #16 C (no error table)

### Skill 4: tapestry/article-extractor
- ARCHETYPE: Reference (high)
- Aggregate: **C**
- Notable: #15 D (no progress), #16 C (prose not table)

### Skill 5: expo/expo-deployment
- ARCHETYPE: Reference (high)
- Aggregate: **C-**
- Notable: #1 C (no anti-triggers), #20 D (no output spec)

### Skill 6: K-Dense-AI/biopython
- ARCHETYPE: Reference (high)
- Aggregate: **B-**
- Notable: #13 A (extensive references/), #14 B+ (alternatives stated)

### Skill 7: chrisvoncsefalvay/d3
- ARCHETYPE: Reference (high)
- Aggregate: **C+**
- Notable: #13 B (820 lines, partial externalization)

### Skill 8: anthropics/canvas-design
- ARCHETYPE: Creative (high)
- Aggregate: **B+**
- Notable: #11 A, #20 A, #22 A (anti-AI-aesthetic rules)

### Skill 9: anthropics/frontend-design
- ARCHETYPE: Creative (high)
- Aggregate: **C+**
- Notable: #22 A (banned fonts/aesthetics), #15 D, #16 C

### Skill 10: anthropics/algorithmic-art
- ARCHETYPE: Creative (high)
- Aggregate: **B**
- Notable: #11 A, #20 A, #22 A

**Persona summary (strict-academic):**
- Archetype distribution: P:2 R:4 C:3 H:1
- Grades: B+:3 B:2 B-:1 C+:2 C:2 C-:1
- Most-N/A principles: 21 (8), 12 (8), 7 (7), 10 (7)
- 0 needs-human-judgment marks

---

## Pragmatic-practitioner persona output

### Skill 1: obra/test-driven-development
- ARCHETYPE: Procedural (high)
- Aggregate: **B+**
- Notable: #6 A+, #21 A+, #22 A, #17 A
- N/A: 3, 4, 5, 8, 13, 19

### Skill 2: trailofbits/agentic-actions-auditor
- ARCHETYPE: **Procedural** (high) — disagrees with strict's Hybrid
- Aggregate: **A-**
- Notable: #1 A+, #2 A+, #11 A, #16 A

### Skill 3: anthropics/skill-creator
- ARCHETYPE: **Hybrid** (high) — disagrees with strict's Procedural
- Aggregate: **B+**
- Notable: #4 A, #5 A, #11 A, #15 A, #19 A

### Skill 4: tapestry/article-extractor
- ARCHETYPE: **Procedural** (high) — disagrees with strict's Reference
- Aggregate: **B-**
- Notable: #6 D, #7 D, #9 D, #12 D — many F-level marks for missing procedural elements

### Skill 5: expo/expo-deployment
- ARCHETYPE: Reference (high)
- Aggregate: **B-**
- Notable: #13 B+ (references/ externalization)

### Skill 6: K-Dense-AI/biopython
- ARCHETYPE: Reference (high)
- Aggregate: **B+**
- Notable: #13 A (7 reference files), #1 A, #14 A

### Skill 7: chrisvoncsefalvay/d3
- ARCHETYPE: Reference (high)
- Aggregate: **B**

### Skill 8: anthropics/canvas-design
- ARCHETYPE: Creative (high)
- Aggregate: **B+**
- Notable: #6 A, #11 A, #20 A, #22 A

### Skill 9: anthropics/frontend-design
- ARCHETYPE: Creative (high)
- Aggregate: **B+**
- Notable: #1 A, #6 A, #14 A, #22 A+

### Skill 10: anthropics/algorithmic-art
- ARCHETYPE: Creative (high)
- Aggregate: **B+**
- Notable: #6 A, #11 A, #20 A

**Persona summary (pragmatic-practitioner):**
- Archetype distribution: P:4 R:3 C:3 H:1
- Grades: A-:1 B+:4 B:3 B-:2
- Most-N/A: 8 (6), 5 (6), 4 (5), 9 (5)
- 0 needs-human-judgment marks

---

## Charitable-newcomer persona output

### Skill 1: obra/test-driven-development
- ARCHETYPE: Procedural (high)
- Aggregate: **B+**
- Notable: #6 A+, #21 A, #22 A, #17 A, #11 A

### Skill 2: trailofbits/agentic-actions-auditor
- ARCHETYPE: **Procedural** (high) — agrees with pragmatic
- Aggregate: **B+**

### Skill 3: anthropics/skill-creator
- ARCHETYPE: **Hybrid** (high) — agrees with pragmatic
- Aggregate: **B+**

### Skill 4: tapestry/article-extractor
- ARCHETYPE: **Procedural** (high) — agrees with pragmatic
- Aggregate: **C+**

### Skill 5: expo/expo-deployment
- ARCHETYPE: Reference (high)
- Aggregate: **B-**

### Skill 6: K-Dense-AI/biopython
- ARCHETYPE: Reference (high)
- Aggregate: **B+**

### Skill 7: chrisvoncsefalvay/d3
- ARCHETYPE: Reference (high)
- Aggregate: **B**

### Skill 8: anthropics/canvas-design
- ARCHETYPE: Creative (high)
- Aggregate: **B+**

### Skill 9: anthropics/frontend-design
- ARCHETYPE: Creative (high)
- Aggregate: **B+**
- Notable: #22 A+, #6 A, #14 A

### Skill 10: anthropics/algorithmic-art
- ARCHETYPE: Creative (high)
- Aggregate: **B+**

**Persona summary (charitable-newcomer):**
- Archetype distribution: P:3 R:3 C:3 H:1
- Grades: B+:6 B:2 B-:1 C+:1
- Most-N/A: 5 (7), 8 (7), 3 (6), 4 (6), 9 (5)
- 0 needs-human-judgment marks

---

## Cross-persona aggregate comparison

| # | Skill | Strict | Pragmatic | Charitable |
|---|---|---|---|---|
| 1 | obra-tdd | C+ | A- | B+ |
| 2 | tob-auditor | B+ | A- | B+ |
| 3 | anthropic-skill-creator | B+ | B+ | B+ |
| 4 | tapestry-article-extractor | C | B- | C+ |
| 5 | expo-deployment | C- | B- | B- |
| 6 | kdense-biopython | B- | B+ | B+ |
| 7 | chrisvoncsefalvay-d3 | C+ | B | B |
| 8 | anthropic-canvas-design | B+ | B+ | B+ |
| 9 | anthropic-frontend-design | C+ | B- | B+ |
| 10 | anthropic-algorithmic-art | B | B+ | B+ |

---

## Cross-persona archetype comparison

| # | Skill | Strict | Pragmatic | Charitable | Agreement |
|---|---|---|---|---|---|
| 1 | obra-tdd | Procedural | Procedural | Procedural | ✅ unanimous |
| 2 | tob-auditor | Hybrid | Procedural | Procedural | 2/3 |
| 3 | anthropic-skill-creator | Procedural | Hybrid | Hybrid | 2/3 |
| 4 | tapestry-article-extractor | Reference | Procedural | Procedural | 2/3 |
| 5 | expo-deployment | Reference | Reference | Reference | ✅ unanimous |
| 6 | kdense-biopython | Reference | Reference | Reference | ✅ unanimous |
| 7 | chrisvoncsefalvay-d3 | Reference | Reference | Reference | ✅ unanimous |
| 8 | anthropic-canvas-design | Creative | Creative | Creative | ✅ unanimous |
| 9 | anthropic-frontend-design | Creative | Creative | Creative | ✅ unanimous |
| 10 | anthropic-algorithmic-art | Creative | Creative | Creative | ✅ unanimous |

**Archetype agreement: 7/10 unanimous, 3/10 majority (2/3).**
