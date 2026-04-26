# Example — `pre-call`

> Research a person before a call or meeting. The canonical worked example referenced from `03-ANATOMY.md`.

**Status:** Runnable canonical example.

---

## What this skill does

Before a scheduled call with someone new, generate a 3-minute briefing covering:
- Background (role, tenure, relevant context)
- Recent work (specific things they've shipped or written, last 90 days)
- Company context (focus area, recent news)
- Three talking points grounded in something concrete

## Why this is the canonical example

It's the simplest skill that demonstrates **all four required components** of a working SKILL.md:
- Phases with explicit exit conditions (Person, Company)
- Decision branches (founder vs IC vs manager)
- Quality gate with all 3 parts (check + failure condition + recovery path → "If talking points don't reference something specific, return to Phase 1")
- Output spec (exact format with named sections)

It's also concrete enough to run on a real meeting today, and short enough to read in one screen.

## Drop-in instructions

```
1. Copy SKILL.md to your Claude Code skills folder
   (typically ~/.claude/skills/pre-call/SKILL.md)
2. Restart Claude Code or reload skills
3. Type: /pre-call [Name] @ [Company]
4. Make sure web search is enabled — without it, the model fabricates
5. Read the output before the call. Verify the citations.
```

## Known dependencies

- Web search must be enabled; the SKILL.md stops rather than fabricating if search is unavailable.
- Output quality depends on how public the person is. Founders and execs: high signal. Heads-down ICs at unannounced companies: low signal.

## Known limitations

- Recency check is heuristic, not enforced ("last 90 days" is asked for but not validated)
- No guard against hallucinated quotes — verify before using
- Designed for B2B / professional contexts, not personal social

---

## Cross-references

- [`../../03-ANATOMY.md`](../../03-ANATOMY.md) — The canonical authoring guide where this example is referenced
- [`../../04-RUBRIC/principles.md`](../../04-RUBRIC/principles.md) — The principles this skill is graded against

---

*Runnable as the canonical example for the PaaP rubric.*
