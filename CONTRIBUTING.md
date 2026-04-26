# Contributing to Prompt as a Process

This is a living research repo. The rubric evolves, the evaluation set grows, and the framework only gets sharper if practitioners push back on it. The most useful contributions are critical, specific, and grounded in real skills.

---

## Most valuable contributions (in order)

### 1. Score one of your skills against the rubric
This is the highest-leverage contribution. Pick a skill you've written, score it against the [22 principles](./04-RUBRIC/principles.md), and submit the evaluation.

**How:**
1. Copy `04-RUBRIC/scoring-template.md` to a new file under `05-EVALUATION/community/your-skill-name.md`.
2. Fill it in honestly. The repo is more useful if you flag your *own* B+s, not just A+s.
3. Open a PR with a one-paragraph summary of what the rubric helped you see (or where it failed you).

### 2. Argue for changing a principle
The 20 principles are top-down hypotheses. Some will be wrong, some will need rewording, some are missing. If you've found one — open an issue with the tag `[principle]`.

**Format:**
- Which principle (number + name)
- Your proposed change (add / remove / reword)
- One concrete example from a real skill that supports your case
- Optional: which evaluation in `05-EVALUATION/` would change grade if the principle changed

### 3. Propose a new test case
The `meta-paap` evaluation set is currently n=4. Workflows that stress-test the rubric in new ways are welcome. Particularly useful: workflows that *don't* fit cleanly into the rubric and reveal gaps.

**Format:**
- Workflow description (3-5 sentences)
- What it stresses (parallel agents? conditional routing? state? composition? human gates?)
- Why the existing 4 tests don't already cover it

### 4. Bug reports on examples
If `examples/pre-call/SKILL.md` (or any other example) fails to run as documented, file an issue with:
- Your model + version
- The exact invocation
- What you expected vs what happened
- Minimal repro if possible

---

## Style

- **Claims as titles.** Section headings should be linkable claims, not topics.
- **No AI slop.** Cut inflated symbolism, vague attributions, excessive em dashes.
- **Evidence-based.** Every claim either links to a source, references a concrete skill, or is explicitly framed as opinion.
- **Honest about scores.** A repo of A+ self-evaluations is worthless. The B-grade rows in `05-EVALUATION/` are the load-bearing parts.

---

## What not to PR

- New `meta-paap` features (architectural changes to the skill itself happen in the source skill repo, not here)
- Tonal rewrites of existing chapters without a substantive change
- README overhauls without a clear thesis change
- Third-party skill *advertising* dressed up as evaluations

---

## Process

1. Open an issue first for anything beyond a typo or a one-skill scoring submission. It saves both of us time.
2. Branch off `main`, name it `add-skill-eval-X` or `principle-N-revise` etc.
3. One contribution per PR.
4. Sign your commits if you can. Not required.

---

## License of contributions

By submitting a PR you agree that your contributions will be licensed under:
- **MIT** for code, scripts, and skill artifacts
- **CC-BY-4.0** for documentation and written content

Matching the repo's [LICENSE](./LICENSE) and [LICENSE-docs](./LICENSE-docs).

---

## Code of conduct

Be direct and substantive. Disagreement is welcome — performative civility is not. No grandstanding, no LinkedIn-influencer posturing. If you wouldn't say it to a colleague's face in a room, don't write it in a PR review.
