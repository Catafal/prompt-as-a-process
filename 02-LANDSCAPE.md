# 02 — Landscape

> The terrain PaaP sits in: three waves of LLM-application thinking, the framework backlash, the gstack case study, and an empirical survey of 50 community skills.

**Status:** Skeleton — full content lands in Phase 2 (heavy investigation) + Phase 3 (writeup). This is the most substantive new chapter; the four articles + regression doc don't already cover it.

---

## Outline

### Part A — Three waves with citations

1. **Prompt engineering era (2020-2023)**
   - One-shot prompts as the unit of work
   - Few-shot, chain-of-thought (Wei et al. 2022), zero-shot CoT
   - The prompt as a *module inside a code system*
   - Citations: CoT, ReAct (Yao et al. 2022), Toolformer (Schick et al. 2023)

2. **Orchestration framework era (2023-2024)**
   - LangChain, LlamaIndex, AutoGen, CrewAI, DSPy
   - The premise: chain prompts with code to enforce structure
   - Trade-off: as much complexity created as removed
   - The backlash: Octomind ripped LangChain out of production after 12 months
   - Citations: LangChain releases, Octomind blog post, Hacker News framework-fatigue threads
   - Position DSPy specifically (it's *not* in the backlash bucket — it's an interesting parallel evolution)

3. **PaaP era (mid-2025-onwards)**
   - Models reliable enough to follow SOPs end-to-end
   - SKILL.md format as the de-facto convention (Anthropic Claude Code)
   - File-share as distribution mechanism
   - 1,200+ community skills on GitHub
   - This isn't "prompt engineering with extra steps" — the unit changed from query to process

### Part B — The framework backlash, evidenced

- Octomind case (primary citation)
- Other documented removals (cross-reference HN threads, blog posts)
- Pattern: framework removed → custom code or PaaP-style SOPs replace it
- Why: leaky abstraction, debugging cost, framework churn
- DSPy as the exception — programmatic but doesn't impose runtime orchestration assumptions

### Part C — Garry Tan / gstack case study

**Source:** Tweet (`https://x.com/garrytan/status/2046876981711769720`) + the gstack public repo + Garry's other posts.

- 28 slash commands modeling an engineering team (CEO review, design review, QA, release management, deploy)
- Structural patterns observed (cross-reference 20 principles)
- Where gstack confirms PaaP principles
- Where gstack diverges or extends
- Where gstack offers something PaaP rubric doesn't yet capture
- Why this matters: a credible YC-scale practitioner converged on the same pattern independently

### Part D — Empirical survey of 50 community skills

**Methodology:**
- Sources: `anthropics/skills`, `awesome-claude-skills` lists, top-starred individual repos
- Sample: 50 skills, sampled across domain (research / code / ops / content / knowledge) and complexity (lean / full / orchestration)
- Classification axes:
  - Domain
  - Complexity tier (lean / full / orchestration)
  - Composition (standalone / N composed)
  - Persona pattern (none / scoped role / behavioral)
- Scoring: 10-skill sub-sample fully scored against the 20 principles

**Findings (placeholder until Phase 2b runs):**
- Distribution by domain
- Distribution by complexity
- Distribution by composition pattern
- Common principle violations
- Bottom-up clusters → comparison to top-down rubric
- Principles that hold up empirically vs principles that may need revision

### Part E — Trends & current state

- Model reliability inflection: what changed mid-2025 (Sonnet-class instruction-following improvements)
- Karpathy autoresearch pattern → applied to SOPs (self-improving skills)
- Anthropic ecosystem evolution (slash command convention, sharing pattern, sub-agent primitives)
- Sub-agent + state + composition as emergent patterns
- Where the next wave likely goes (mostly speculative — frame as such)

---

## Source material (public)

- Garry Tan public posts and the gstack public repo (Phase 2a)
- 50-skill GitHub corpus from `anthropics/skills`, `awesome-claude-skills`, and top-starred individual repos (Phase 2b)
- Academic papers — CoT (Wei et al. 2022), ReAct (Yao et al. 2022), Toolformer (Schick et al. 2023), Reflexion (Shinn et al. 2023), agent surveys (Phase 2c)
- Documented framework-removal cases — Octomind blog post, Hacker News framework-fatigue threads (Phase 2c)
- Vivek Trivedi's "Agent = Model + Harness" article (Phase 2d)
- Practitioner workflow accounts — Harper Reed, Simon Willison, Boris Cherny, incident.io engineering team (Phase 2d)

---

## Length budget

This chapter will be the longest in the repo. Hard cap: 1000 lines. If exceeded, split into a `landscape/` subdirectory with one file per Part (A-E).

---

*Populated in Phase 2 (research) + Phase 3 (writeup).*
