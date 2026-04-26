# Corpus Extension — 30 Additional Skills (v0.2 Stage 3)

> 30 community SKILL.md files added to the v0.1 corpus during v0.2 Stage 3. Combined with the original 50 in [`corpus-50-skills.md`](./corpus-50-skills.md), this gives **N=80 effective corpus** for v0.2 analysis.

**Snapshot date:** 2026-04-26
**Discovery method:** GitHub web search + curated awesome-claude-skills lists, prioritizing diversity (long-tail individual practitioners, non-Procedural archetypes, non-English authors, domains absent from v0.1)
**Honest scope:** the v0.2 plan targeted N=100 (50 new skills); actual delivery is 30 new skills (N=80). Reasons: (a) finding diverse new skills in a single session is bounded; (b) sample diversity matters more than raw count for the rubric-validation use case; (c) remaining 20-skill gap is documented as v0.3 work.

---

## Why these 30 (diversity prioritization)

The v0.1 corpus had **66% author concentration** (4 authors = 33/50 skills) and was **76% Procedural** by archetype. v0.2 Stage 3 deliberately selected to dilute both biases.

**Author diversity:** all 30 new skills are from **18 distinct authors not in v0.1**. The combined N=80 corpus now has 36 distinct authors instead of 18.

**Archetype diversity:**

| Archetype | v0.1 (N=50) | Stage 3 (N=30) | Combined (N=80) | Change |
|---|---:|---:|---:|---:|
| Procedural | 38 (76%) | 10 (33%) | 48 (60%) | **−16 pp** |
| Reference | 6 (12%) | 10 (33%) | 16 (20%) | **+8 pp** |
| Creative | 3 (6%) | 6 (20%) | 9 (11%) | **+5 pp** |
| Hybrid | 3 (6%) | 4 (13%) | 7 (9%) | +3 pp |

The 76% Procedural figure in v0.1 was partly a sourcing artifact. The N=80 number (60%) is closer to a real community-corpus distribution.

**Domain diversity:** v0.1 covered code/content/ops/research/knowledge/education. Stage 3 added: finance, healthcare/biometrics, scientific computing, design audit, content quality, product management, crypto APIs, and Chinese cultural platforms.

**Non-English authors:** 5 of 18 new authors are from non-English-speaking backgrounds (Chinese, Russian, Egyptian, Polish, Indian/Korean). This is improvement vs v0.1's near-exclusive English author base, but non-English authors remain a minority of the long tail.

---

## The 30 skills (Tier 1 from discovery, all included)

| # | Author | Skill | Repo | Archetype | Lines | Domain |
|---|---|---|---|---|---:|---|
| 51 | jamesrochabrun | apple-hig-designer | [skills](https://github.com/jamesrochabrun/skills) | Reference | 946 | Mobile/iOS design |
| 52 | jamesrochabrun | leetcode-teacher | [skills](https://github.com/jamesrochabrun/skills) | Procedural | 921 | Education |
| 53 | jamesrochabrun | kids-book-writer | [skills](https://github.com/jamesrochabrun/skills) | Creative | 679 | Education/creative |
| 54 | jamesrochabrun | trading-plan-generator | [skills](https://github.com/jamesrochabrun/skills) | Procedural | 729 | Finance |
| 55 | jamesrochabrun | math-teacher | [skills](https://github.com/jamesrochabrun/skills) | Creative | 369 | Education |
| 56 | daymade *(Chinese)* | deep-research | [claude-code-skills](https://github.com/daymade/claude-code-skills) | Hybrid | 544 | Research |
| 57 | daymade | terraform-skill | [claude-code-skills](https://github.com/daymade/claude-code-skills) | Reference | 233 | DevOps/IaC |
| 58 | daymade | financial-data-collector | [claude-code-skills](https://github.com/daymade/claude-code-skills) | Procedural | 152 | Finance |
| 59 | daymade | fact-checker | [claude-code-skills](https://github.com/daymade/claude-code-skills) | Procedural | 296 | Editorial |
| 60 | daymade | douban-skill | [claude-code-skills](https://github.com/daymade/claude-code-skills) | Procedural | 131 | Chinese platform export |
| 61 | daymade | iOS-APP-developer | [claude-code-skills](https://github.com/daymade/claude-code-skills) | Reference | 372 | Mobile dev |
| 62 | glebis *(Russian — Gleb Kalinin)* | health-data | [claude-skills](https://github.com/glebis/claude-skills) | Reference | 249 | Healthcare/biometrics |
| 63 | glebis | jtbd | [claude-skills](https://github.com/glebis/claude-skills) | Hybrid | 263 | Product strategy |
| 64 | glebis | tufte-report | [claude-skills](https://github.com/glebis/claude-skills) | Creative | 173 | Data viz |
| 65 | glebis | decision-toolkit | [claude-skills](https://github.com/glebis/claude-skills) | Hybrid | 359 | Decision/cognitive |
| 66 | agamm | owasp-security | [claude-code-owasp](https://github.com/agamm/claude-code-owasp) | Reference | 536 | Security |
| 67 | AgriciDaniel | cybersecurity | [claude-cybersecurity](https://github.com/AgriciDaniel/claude-cybersecurity) | Procedural | 986 | Security/orchestration |
| 68 | ryanbbrown | revealjs | [revealjs-skill](https://github.com/ryanbbrown/revealjs-skill) | Creative | 438 | Presentations |
| 69 | zarazhangrui *(Chinese)* | frontend-slides | [frontend-slides](https://github.com/zarazhangrui/frontend-slides) | Creative | 322 | Presentations/design |
| 70 | sanjay3290 | azure-devops | [ai-skills](https://github.com/sanjay3290/ai-skills) | Reference | 477 | Enterprise DevOps |
| 71 | sanjay3290 | elevenlabs | [ai-skills](https://github.com/sanjay3290/ai-skills) | Procedural | 130 | Media/audio |
| 72 | BehiSecc | VibeSec-Skill | [VibeSec-Skill](https://github.com/BehiSecc/VibeSec-Skill) | Reference | 758 | Security |
| 73 | tasteray | elicitation | [skills](https://github.com/tasteray/skills) | Hybrid | 475 | Psychology/UX |
| 74 | HeshamFS *(Egyptian)* | mesh-generation | [materials-simulation-skills](https://github.com/HeshamFS/materials-simulation-skills) | Reference | 192 | Scientific computing |
| 75 | conorbronsdon | avoid-ai-writing | [avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) | Reference | 480 | Editorial/content |
| 76 | coinpaprika *(Polish org)* | coinpaprika-api | [skills](https://github.com/coinpaprika/skills) | Reference | 330 | Crypto/finance API |
| 77 | wrsmith108 | linear | [linear-claude-skill](https://github.com/wrsmith108/linear-claude-skill) | Procedural | 677 | Project management |
| 78 | olgasafonova | skill-check | [SkillCheck-Free](https://github.com/olgasafonova/SkillCheck-Free) | Procedural | 680 | Meta (validates SKILL.md) |
| 79 | product-on-purpose | deliver-prd | [pm-skills](https://github.com/product-on-purpose/pm-skills) | Procedural | 72 | Product management |
| 80 | glacierphonk | naming | [naming](https://github.com/glacierphonk/naming) | Creative | 209 | Branding/language |

---

## How these 30 were sourced

Search strategies that worked:

1. **`BehiSecc/awesome-claude-skills`** — highest-yield curated list outside v0.1; surfaced 20+ new authors
2. **GitHub repo search for `*-claude-skill`, `*-claude-skills`** patterns
3. **Following individual practitioners' repo lists** — once I found one skill from `jamesrochabrun` or `daymade`, their other skills were in the same repo
4. **Cross-referencing recently-pushed repos with the SKILL.md spec format**

Strategies that didn't work well:
- **GitHub API code search** (rate-limited heavily)
- **Searching for legal / clinical-medical / non-English-only skills** — these remain rare in public repos as of 2026-04-26

Skills NOT included despite being public:
- Skills from `garrytan/gstack` (covered separately as Phase 2a case study, ~50 skills)
- Forks of `anthropics/skills` with no novel content (e.g., `smartnews/claude-skills`)
- Skills duplicated across multiple lists (kept the canonical version)
- Skills where SKILL.md was unfetchable at snapshot time

---

## Important caveats

- **No commit SHAs pinned.** All URLs target `main` branch as of 2026-04-26. SKILL.md content may shift.
- **Author concentration partially improved.** Combined N=80 has 36 distinct authors (vs 18 in v0.1), but `jamesrochabrun` and `daymade` each contribute 5-6 skills in this batch, so a few authors still have multiple representations.
- **Still English-dominant.** Non-English authors (5/18 in this extension) write in English most of the time, even when their primary language differs.
- **Single-scorer scoring.** All 30 new skills were scored by `/paap-eval` with `pragmatic-practitioner` persona. Stage 2's kappa pilot showed ~1.8 grade-step variance vs `strict-academic`; aggregate grades here may shift ±1-2 grade-steps under different personas.

See [`empirical-validation.md`](./empirical-validation.md) for analysis built on this extended corpus and [`../05-EVALUATION/corpus-extension-raw-data.md`](../05-EVALUATION/corpus-extension-raw-data.md) for the per-skill `/paap-eval` scoring.

---

## How to extend further (v0.3 contribution path)

Highest-value additions to push toward N=100+:

- **More legal / regulatory / compliance skills** — domain absent from current N=80
- **Clinical or medical-decision skills** — only personal-biometrics covered so far (`glebis/health-data`)
- **More skills from non-English-first authors** — currently 5/36 distinct authors
- **Multi-host skills (Codex, Cursor, Goose, OpenClaw)** — current N=80 is Claude-Code-anchored even when format-portable
- **Skills explicitly designed by skill-experienced authors who've shipped 10+** — long-tail individual practitioners with deep practice

If you contribute a skill scored against the rubric, add it here and submit alongside the scored evaluation file in `05-EVALUATION/community/`.
