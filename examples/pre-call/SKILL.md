---
name: pre-call
description: Research a person before a call or meeting. Use when you have a scheduled meeting with someone new in the next 24-48 hours. Provide their name and company. Do NOT use for people you already know or recurring contacts. Do NOT use for purely social meetings.
---

# Pre-Call Research

## Context

Goal: a briefing the user can read in 3 minutes before the call.
Recency matters more than career history — focus on the last 90 days.

**Required:** web search must be enabled for this skill to function. Without it, the model will fabricate. If web search is unavailable, stop and tell the user.

## Phase 1: Person

Search for their LinkedIn, recent writing, talks, and public posts.

Capture:
- Current role and how long they've been in it
- 1-2 specific things they've recently shipped or written
- Anything public from the last 90 days (posts, podcasts, talks, articles)

Exit condition: Can you answer "what has this person been doing and what do they care about right now"? Yes → proceed to Phase 2. No → expand search to adjacent contexts (their company's recent news, mutual connections' work).

## Phase 2: Company

Branch by role type:

- **If founder or executive:** focus on funding news, product direction, recent launches, strategic shifts.
- **If IC or manager:** focus on the product area relevant to their role, recent team news, hiring posts.

Capture:
- What the company does (one sentence)
- What they're focused on right now (last 90 days)
- 1-2 recent material events (funding, launches, layoffs, leadership changes)

Exit condition: Can you answer "what is this company focused on right now"? Yes → proceed to Quality Check. No → return to Phase 1, expand person research to surface the work context.

## Quality Check

Before producing output, verify:

1. **Talking points reference something concrete.** Do the talking points reference something they specifically built, wrote, or said? If not: return to Phase 1, find one concrete thing, then re-run the synthesis.

2. **Company context is recent.** Is the company context from the last 90 days? If not: return to Phase 2 with a recency filter on the search.

3. **No unverified quotes.** Does the briefing contain any direct quotes? If yes: confirm each quote is from a public source. If you can't confirm: paraphrase or remove.

## Output

```
# Pre-Call Brief: [Name] @ [Company]

**Background:** [2 sentences — role, tenure, relevant background]

**Recent work:** [1-2 specific things they've shipped or published, with dates]

**Company context:** [What they do + what they're focused on now, last 90 days]

**Talking points:**
1. [Ties directly to something they built or said — be specific]
2. [Connects to their current focus]
3. [A question that shows you've read their work]
```

Length target: 200-350 words total.

## Error handling

| Error | Action |
|---|---|
| Web search unavailable | Stop. Tell the user web search is required and abort. |
| LinkedIn profile not found | Search for them on company website "team" page; fall back to recent press mentions |
| Person has no public profile | Output explicit note: "Limited public footprint. Talking points based on company context only." |
| Company is too obscure to research | Note: "Company information limited; rely on what the person has shared." |

## Notes for the author of this skill

This is a **Procedural skill** under the [PaaP rubric](../../04-RUBRIC/principles.md). It demonstrates:

- **#1 Description as router** — anti-triggers prevent over-invocation
- **#2 Route before work** — no Phase 0 needed; the description handles routing
- **#10 Exit = question** — both phases end with binary questions
- **#12 Gates = 3 parts** — Quality Check has check + failure + recovery in each item
- **#11 Output spec** — exact format, sections, length target
- **#16 Errors** — table mapping specific error → specific action

It deliberately skips:

- **#4 State** (runs in <2 min, no resume needed)
- **#5 Parallel** (single-threaded by design)
- **#7 Files = bus** (no inter-phase data files)
- **#19 Composition** (standalone)

This is the canonical example referenced from [`03-ANATOMY`](../../03-ANATOMY/).
