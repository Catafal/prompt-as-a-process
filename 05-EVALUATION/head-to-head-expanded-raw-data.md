# Head-to-Head Expanded — Raw Data

> Verbatim outputs (30) + judge JSONs (45) for the v0.3 priority #3 output-quality experiment. Aggregate analysis: [`head-to-head-expanded.md`](./head-to-head-expanded.md).

**Date:** 2026-04-26
**5 workflows × 3 inputs × 2 arms = 30 outputs.**
**3 cross-vendor judges × 15 pairs = 45 judge JSONs.**

**Blind mapping** (kept hidden from judges; revealed here for analysis):

```json
{
  "5d-thinking/01-career": {
    "A": "generated",
    "B": "handwritten"
  },
  "5d-thinking/02-partnership": {
    "A": "handwritten",
    "B": "generated"
  },
  "5d-thinking/03-scope": {
    "A": "handwritten",
    "B": "generated"
  },
  "eod/01-concise-day": {
    "A": "handwritten",
    "B": "generated"
  },
  "eod/02-messy-day": {
    "A": "handwritten",
    "B": "generated"
  },
  "eod/03-meeting-heavy-day": {
    "A": "handwritten",
    "B": "generated"
  },
  "humanizer/01-technical": {
    "A": "handwritten",
    "B": "generated"
  },
  "humanizer/02-marketing": {
    "A": "generated",
    "B": "handwritten"
  },
  "humanizer/03-narrative": {
    "A": "handwritten",
    "B": "generated"
  },
  "prompt-engineering/01-vague": {
    "A": "generated",
    "B": "handwritten"
  },
  "prompt-engineering/02-over-broad": {
    "A": "generated",
    "B": "handwritten"
  },
  "prompt-engineering/03-under-specified": {
    "A": "handwritten",
    "B": "generated"
  },
  "remember/01-insight": {
    "A": "handwritten",
    "B": "generated"
  },
  "remember/02-reference": {
    "A": "handwritten",
    "B": "generated"
  },
  "remember/03-reflection": {
    "A": "handwritten",
    "B": "generated"
  }
}
```

---

# Outputs (30)

Each (workflow, input) shows handwritten arm and generated arm side-by-side. The blind labeling (which is A vs B per pair) is in the mapping above.


## OUTPUTS — 5d-thinking/01-career

**Input:** [`inputs/5d-thinking/01-career.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/5d-thinking/01-career.md`)

**Blind mapping:** A=generated, B=handwritten

### 5d-thinking/01-career — handwritten (11411 bytes)

```
# 5D Thinking: Career Decision Analysis

## Current Thinking Pattern

**Level:** Stuck between Level 1 (conformist: "the math doesn't work") and Level 2 (individualist: own model, but dogmatically held). You're defending a pre-programmed answer ("equity at current job is real") while privately suspecting the answer is wrong ("I'm staying because I'm comfortable"). The internal contradiction itself is the signal that thinking has cut off prematurely.

**Lines being considered:** Finance (primarily), Risk (secondarily). 

**Lines underdeveloped:** Identity, Skill development, Time/career arc, Relational (partner + child), Meaning, Network/optionality, Founder psychology.

**Reductionism detected:** "Everything is a math problem." But you've already noticed the math frame doesn't reach the actual question — that's why you keep looping. Loops are usually a sign the frame is wrong, not the data.

**Identity attachment to watch:** "Staff Engineer at Series B" is doing work in your psyche. So is "responsible father-to-be." Both are real. Both can also be hiding places.

---

## Expanding the View

### Individual Inner (Psychological)
- **The fear underneath the math:** You named it yourself — "I'm staying because I'm comfortable." That sentence is the actual decision criterion you're avoiding. The financial frame is a socially acceptable proxy for a question about courage and self-image.
- **Identity load of "founding engineer":** Part of why this is hard is that taking the offer requires you to *become* a different kind of person — someone who bets on themselves. Not taking it lets you stay who you currently are. Comfort isn't just about money; it's about not having to update your self-concept.
- **Father-to-be narrative:** "I have a kid on the way" is being deployed as a trump card. Worth checking honestly: is the kid the *reason* not to go, or the *justification* for not going? Different fathers model different things for their children. A parent who took a calculated risk and grew is not categorically worse for a child than one who optimized for stability — sometimes the opposite.
- **Sunk cost dressed as prudence:** 6 years of vesting is a real number. It is also the textbook trigger for sunk-cost reasoning. The vested equity stays vested. The question is only about the *unvested* portion vs. the new opportunity — your brain is conflating the two.

### Collective Inner (Cultural)
- **Tech industry script:** "Stay at the big stable company when you have a kid" is the dominant narrative in mid-career engineering circles. It's not wrong — it's just *one* script. The counter-script ("Founding Engineer roles before age 40 are how senior ICs become operators/founders later") is equally valid and less spoken.
- **Spouse/partner's frame matters more than reddit's:** What does your partner actually think — not what you assume they think filtered through your guilt? This is often the largest unexamined variable. Many engineers project a more conservative position onto their partner than the partner actually holds.
- **The "lottery ticket" framing is a meme:** Seed-stage AI-infra equity in 2026 isn't a uniform distribution. The expected value depends entirely on the team, the wedge, the cap table, and the round terms. You're using a generic dismissal ("lottery tickets") to avoid doing the specific work of evaluating *this* company.

### Individual Outer (Behavioral)
- **What you have not yet done:** Have you actually modeled the financial scenarios? Specifically:
  - Unvested equity you'd forfeit (concrete $)
  - Pay-cut runway against current savings (months)
  - New equity scenarios at realistic outcomes (acqui-hire, modest exit, big exit, zero) with probabilities you'd defend out loud
  - The optionality value: what does "ex-Founding Engineer at AI-infra startup" do for your next 3 job options vs. "Staff Engineer, 7 years, same company"?
- **Diligence you haven't done on the startup:** Cap table, lead investor, burn rate, revenue/ARR, technical moat, founder track record, your specific role definition, board composition, vesting cliff, acceleration on change-of-control. "Friend's startup" is a relational frame, not a diligence frame.
- **The reversibility test:** What does "I tried the startup for 18 months and it failed" look like? You're a Staff Engineer at a Series B. The market for that profile in 18 months will not have collapsed. The downside is bounded in a way the upside isn't.

### Collective Outer (Systemic)
- **Career-stage arithmetic:** Founding Engineer roles have a window. They get harder to take, not easier, as family/financial complexity grows. The structural argument *for* taking it now is stronger than the structural argument for waiting — waiting usually means never.
- **AI-infra timing:** This is a once-per-decade compute platform shift. Companies that close seed rounds in this window with real teams have meaningfully different outcome distributions than the generic "seed-stage startup" base rate. Sector matters enormously. Don't average yourself into a generic startup-failure statistic.
- **Two-week deadline as a forcing function:** The deadline is a feature, not a bug. It's preventing the infinite-loop pattern you're already exhibiting. But it can also induce a bad decision. Honor it, but use it deliberately — the goal in two weeks is *a clear decision*, not *the right answer found instantly*.
- **Healthcare/insurance system constraints:** With a kid on the way, US-style benefits transitions are a real (solvable) operational issue. Often inflated in worry but worth pricing concretely — COBRA cost, partner's coverage, timing relative to delivery.

### Historical Pattern (Time)
- **Your own pattern:** Six years at one company is long. There's a developmental question: are you still *growing* there, or has the role plateaued and the equity is what's holding you? Staff Engineers often hit a "growth ceiling" around year 4-5 where comp keeps rising but learning slows. If learning has slowed, the comfort is expensive in a way the spreadsheet doesn't show.
- **The "stayed too long" archetype vs. the "left too early" archetype:** Both are real failure modes. In tech, in this era, "stayed too long at the Series B" is statistically more common than "left a great Staff role too early." The regret asymmetry usually favors the move, but only if the move is into something genuinely better, not just different.
- **Transcend and include:** Going to the startup doesn't *erase* the 6 years — it builds on them. The Staff Engineer skill set is exactly what makes a Founding Engineer valuable. Staying doesn't include the founding-engineer experience; it forecloses it (for now).

---

## Key Constraints Identified

The actual constraint is **not financial** — it is **identity + information**.

1. **Identity:** You haven't separated "the responsible choice" from "the choice that protects who I currently am." Until those are separated, the financial argument will keep being deployed as cover.
2. **Information:** You haven't done the concrete diligence on the startup that would make the decision evaluable. You're comparing a fully-mapped current state to a vague imagined future state. That comparison always favors the present — not because the present is better, but because it's better-known.
3. **Hidden dependency:** Your partner's actual position. Without it, you're solving a single-player game that's actually a multi-player game.

---

## Expanded Possibilities

Things that become visible once the frame widens:

- **This is not a binary.** Possible third options: negotiate the offer (more equity for the pay cut, signing bonus to offset forfeited vesting, advisor role first, 3-month consulting trial, delayed start until after the baby).
- **The math, done properly, may actually favor going.** Forfeited unvested equity is real but finite; founding-engineer equity at a credible AI-infra seed has a non-trivial expected value; the optionality on your next role compounds. Run the numbers honestly with probabilities you'd defend, not the dismissive "lottery tickets" frame.
- **The math, done properly, may favor staying — but for a real reason.** If diligence reveals the startup is weak (mediocre team, no wedge, bad terms), then "no" becomes a *reasoned* no, not a *frightened* no. That's a categorically different outcome even if the action is the same.
- **The decision can be staged.** Two weeks is the seed-close deadline, not a metaphysical deadline on your life. Negotiate a delayed decision or a delayed start if the diligence isn't complete.

---

## Recommended Next Steps

In the next 72 hours, do these in order. They are designed to break the loop by attacking the actual constraints (identity + information), not the surface symptom (financial anxiety).

1. **Have the conversation with your partner — actually.** Not "what do you think we should do" (which invites them to mirror your anxiety) but: "Here are the four scenarios — current job stays, I take this with conditions A/B/C, I pass — what does each look like for *you*?" Listen for the gap between what you assumed and what they say.

2. **Do real diligence on the startup, in writing.** Cap table, ARR or pre-revenue thesis, lead investor quality, founder background, your equity %, vesting + acceleration terms, board, burn, runway after seed. If the friendship makes this awkward, that itself is information. Founding engineers do diligence; friends-doing-friends-favors don't.

3. **Run the financial model with explicit probabilities.** Three columns: stay, go-and-fail (18mo, you re-enter the market), go-and-succeed (5yr exit at modest/median/strong outcomes). Assign probabilities you'd defend in front of a skeptical investor. The output won't be a single number — it'll be a distribution. The point is to replace "lottery tickets" with a real picture.

4. **Name the identity question separately.** Sit with this sentence and write a paragraph response: *"If money were equal in both options, which would I take, and what does that tell me about which one I actually want?"* The answer to that is not the decision — but it tells you what the financial argument is doing for you.

5. **Negotiate, don't just accept-or-reject.** The offer as stated may not be the offer that's actually available. More equity, signing bonus to bridge forfeited vesting, deferred start to align with the baby — all standard asks for a senior hire. The startup expects negotiation. Not negotiating is leaving real value on the table and treating the offer as more rigid than it is.

6. **Set a decision deadline, not a discovery deadline.** Within two weeks: a *decision*, made with the best information you can gather in that window, by a version of you that has examined the identity question honestly. Not a guarantee of the right answer — a commitment to a real one.

The goal here is not to push you toward going or staying. It's to ensure that whichever you choose, you choose it from Level 3 thinking (multiple frames held, contradictions tolerated, decision made deliberately) rather than from Level 1-2 thinking (one frame defended, contradiction suppressed, decision made by default).

The loop ends when the frame widens. The frame widens when you stop asking "does the math work" and start asking "what am I actually deciding, and who am I deciding to be."

```

### 5d-thinking/01-career — generated (5075 bytes)

```
[5D] Trap detected: Inner-Individual trap. Running analysis across all 5 dimensions.

## Thinking Trap Detected

You are stuck in the Inner-Individual trap. The entire framing — "math vs. comfort," "what I tell myself vs. what I'm afraid is true" — is a debate happening inside your own head about your own motives. You have collapsed a multi-variable career, family, and market decision into a single question of personal honesty. That question matters, but it is not the decision. Treating it as the decision is what's keeping you in the loop.

## D1 — Individual Inner

The fear "I'm staying because I'm comfortable" is doing more work than the fear of losing equity. Notice the asymmetry: if you leave and the startup fails, you have a coherent story (took the shot, raised a kid through it, learned). If you stay and the company exits well, you still have to live with the suspicion that you chose money over yourself. The decision is loaded because one path resolves your identity question and the other re-opens it every quarter. What you would have to give up to think clearly is the assumption that the "brave" choice and the "right" choice are the same choice. They sometimes are. They are not always.

## D2 — Individual Outer

You are 6 years into a Series B, holding vested-and-vesting equity, with a child on the way and a 14-day clock. The observable behavior is that you are running the decision as a values question when it is also a liquidity, timing, and negotiation question — and you have not, based on your framing, done the obvious outer-world moves. Have you asked your current company for a retention package, accelerated vesting, or a Staff-to-Principal scope expansion triggered by the offer? Have you asked the seed startup whether they would let you start in 6 weeks instead of 2, or structure a 60-day paid trial? The gap between stated intent ("I want to think clearly") and behavior (looping internally) is that you are treating a negotiable structure as fixed.

## D3 — Collective Inner

There is a story in your professional culture — strongest in AI-infra circles right now — that says "real engineers join early-stage; staying late is a moral failure." There is a competing story in family and partner circles that says "a kid on the way means you stabilize, not gamble." Both are group norms dressed up as personal values. The 30% pay cut is not just a number; it is a signal you would have to send to two audiences who will read it in opposite ways. Part of why the loop won't close is that the decision is being silently audited by people who are not in the room, and you have not separated their voices from yours.

## D4 — Collective Outer

The seed-stage AI-infra market in 2026 is producing more 7-person companies than it can sustain in 18 months. Founding-engineer equity at seed is structurally a power-law bet: most outcomes are zero, a few are life-changing, the median is "modest acquihire that vests you out at 2 years." Series B equity is structurally different — lower variance, dependent on a specific exit path that your company's board, not you, controls. The incentive structure of "closing seed in 2 weeks" is designed to compress your decision window; that pressure benefits the startup, not you. The structurally honest comparison is not "real equity vs. lottery tickets" but "two different lottery tickets with different ticket prices and different odds" — and you have not priced either.

## D5 — Historical Pattern

The pattern is the classic "Founding Engineer #1 with a kid on the way" — it has a known shape. Engineers who navigated it well did three things: they negotiated hard on both sides before deciding, they secured a 6–12 month runway independent of either job, and they made the decision before the offer's deadline by treating the deadline as information, not authority. Engineers who navigated it badly let the deadline make the decision, or let the identity question ("am I the kind of person who…") substitute for the financial and family modeling. You are currently closer to the second group. The friend's startup closing seed in 2 weeks is not a forcing function on you; it is a forcing function on them.

## Synthesis: What This Changes

The reframe: this is not a values decision masquerading as a math decision. It is a negotiation and modeling decision masquerading as a values decision. Before the 14-day clock runs out, you owe yourself two concrete artifacts — a written counter-ask to your current employer (scope, comp, accelerated vesting) and a written term-sheet question to the startup (start date, salary floor, vesting cliff, acquihire scenarios) — and a one-page family financial model with your partner that defines what "30% pay cut" actually means month-to-month with a newborn. If after those three moves you are still looping, then it is a values question, and the honest answer is probably the one you are afraid of. But you have not earned the right to that question yet, because you have not yet treated the outer world as negotiable.

```


## OUTPUTS — 5d-thinking/02-partnership

**Input:** [`inputs/5d-thinking/02-partnership.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/5d-thinking/02-partnership.md`)

**Blind mapping:** A=handwritten, B=generated

### 5d-thinking/02-partnership — handwritten (12298 bytes)

```
# 5D Thinking: Co-founder Fundraising Disagreement

## Current Thinking Pattern

You and your co-founder are both operating at **Level 2 (Individualist)** on this question. Each of you has built a coherent internal model — hers optimizes for momentum capture under favorable macro conditions; yours optimizes for valuation efficiency and capital discipline. Both models are internally consistent. Both are defensible. That is precisely why you are stuck: when two Level 2 frameworks collide, more reasoning *within* each framework just hardens the position. Three rounds of presenting the case is the diagnostic — you are not solving the problem, you are rehearsing it.

The line you are debating on is **Finance** (dilution math, valuation curves, capital efficiency). The lines you are *not* explicitly debating — but which are doing most of the work underneath — are **Psychology** (what each of you fears or wants), **Leadership/Team dynamics** (how this decision shapes the partnership), **Strategy** (what game you are actually playing), and **Meaning/Purpose** (what "winning" looks like for each of you). Your instinct that "the disagreement feels deeper than fundraising timing" is correct. The fundraising question is a surface proxy for an underlying alignment question that has gone undiscussed for four years because traction made it unnecessary.

## Expanding the View

### Individual Inner (Psychological)

Ask each of yourselves, separately, on paper:

- **What am I afraid of in the *other* path?** Her fear in your path may be: *we miss the window, the macro turns, a competitor raises and outspends us, and we end up bootstrapping in a bear market we could have avoided.* Your fear in her path may be: *we take money we don't have a plan for, the discipline that got us to $40k MRR erodes, and we now answer to a board for decisions we used to make in an afternoon.*
- **What does each path *protect* about my identity?** Bootstrapping protects the identity of "we built this ourselves" and "capital-efficient operator." Raising protects the identity of "venture-scale founder" and "we played the game at the right moment." Neither identity is wrong. Both are doing invisible work in the argument.
- **Which path has the regret asymmetry I can live with?** If you raise and it was wrong, what does the loss look like? If you bootstrap and it was wrong, what does the loss look like? You are each likely weighting one regret heavier than the other and not naming it.

The argument is going in circles because the *stated* reasons (dilution math, valuation curves) are post-hoc justifications for prior emotional weights neither of you has surfaced.

### Collective Inner (Cultural)

The startup ecosystem has two dominant ideologies that are currently colliding inside your conversation:

- **"Raise when you can, not when you have to."** This is the canonical VC-ecosystem narrative. It is true in a specific regime (capital-scarce environments, long sales cycles, capital-intensive scaling). Your co-founder is channeling this culture.
- **"Default alive. Every dollar of revenue is worth ten of investment."** This is the Paul Graham / bootstrapper / efficient-startup narrative. It is true in a different regime (high-margin SaaS, founder-led sales, short payback). You are channeling this culture.

Neither of you invented these arguments. You inherited them. The disagreement may be less "her vs. you" and more "two valid ecosystem playbooks neither of which fully fits your specific situation." The question is not which culture is right — it is *which one is right for your specific business model, market, and stage.* Naming the cultural inheritance reduces the personal heat.

### Individual Outer (Behavioral)

What would each of you actually *do differently* day-to-day under each scenario? This is the test that cuts through abstract arguing:

- **Under the $3M raise:** What are the first three hires? What is the first quarter's burn? What experiments become possible that aren't possible now? If neither of you can answer this concretely in 30 minutes, the raise has no plan and your "we don't have a clear plan for $3M" objection is correct on the merits.
- **Under bootstrapping to $80-100k MRR:** What is the specific path? Which channels scale? What breaks at $80k that doesn't break at $40k? If neither of you can answer this, the bootstrap path is also a hope, not a plan.

The behavioral test reveals which path is *actually* planned and which is *vibes*. Often both are vibes, dressed in the language of strategy. The conversation should not advance until both paths have a concrete 90-day operating plan, side by side. Comparing two vague futures is what produces three-round circular debates.

### Collective Outer (Systemic)

Several systemic factors are doing silent work:

- **The macro window.** Her argument depends on the macro staying favorable for 3-5 months. Is that a confident bet? Look at fund deployment pace, recent rounds in your sector, and the public-market signals. If the window is genuinely closing, "raise now" has a real time-value component her argument may not be quantifying clearly enough.
- **The valuation step function.** Your argument assumes valuation scales linearly with MRR ("every $20k doubles valuation"). It doesn't, exactly. Valuation is also a function of growth *rate*, not just absolute MRR. If growing from $40k to $80k takes 5 months at 12% MoM, your growth rate during those months is the *same* 12% — you don't get a multiple expansion just from being bigger. You get expansion if you also accelerate growth. Have you priced that in?
- **Inbound investor interest decays.** Demo-day inbound has a half-life of roughly 6-8 weeks. If you wait 3-5 months to raise, the warm intros are cold. You will be running a fresh process from a colder start, which costs you 2-3 months of founder attention you could be spending on revenue. That is a real cost in your bootstrap path.
- **Optionality.** A *partial* raise ($1-1.5M at current valuation, or a SAFE with a cap that lets you raise more later) is a third option neither of you has put on the table. The conversation is binary because you each framed it that way.

### Historical Pattern (Time)

The "raise now vs. raise later" debate is one of the oldest in venture history. The pattern recognition that matters:

- Companies that raised at peak hype with no plan for the capital almost always regretted it (the 2021 cohort is a textbook). Companies that raised at peak hype *with a plan* generally did not.
- Companies that bootstrapped through a clear inflection (e.g., "we needed proof that channel X scales before we raised") generally won. Companies that bootstrapped *out of fear of dilution* without a clear milestone they were buying often missed windows.

The historical pattern says: **the question isn't "now or later," it's "what specific milestone are you buying with the wait, and what specific use of capital are you buying with the raise?"** Both paths can be right. Both can be wrong. The discriminator is the specificity of the *use*, not the timing.

A second, deeper historical pattern: **co-founder disagreements that get resolved by one person "winning" tend to surface again in mutated form 6-12 months later.** The disagreement that gets resolved by *finding the underlying question* is the one that holds. You said it yourselves: this feels deeper than fundraising. That instinct is the most important data point in this whole situation.

## Key Constraints Identified

1. **The real disagreement is not about timing.** It is about what game you are each playing. One of you may be optimizing for venture-scale outcome (raise, swing big, accept dilution as the cost of upside). The other may be optimizing for ownership-and-control outcome (high equity, default alive, raise only when forced). These are different *games* with different success criteria, and neither is wrong — but they cannot be reconciled by arguing about Q2 vs Q4 timing.

2. **Neither path has been costed concretely.** "Raise $3M" without a 90-day deployment plan is not a strategy. "Bootstrap to $80k MRR" without a specific growth thesis is not a strategy either. You are arguing two abstractions.

3. **The conversation has been framed as binary.** Partial raises, bridge SAFEs, strategic angels, or revenue-based financing are not in the discussion. Whenever a co-founder disagreement is framed as A vs B for three rounds, the missing answer is almost always C.

4. **The trust-based deadlock is the real risk.** You trust her, she trusts you, and you have four years of co-built context. That mutual trust is currently *preventing* either of you from updating, because each of you is treating the other's position as serious enough to honor but not so wrong that you can dismiss it. The deadlock is a function of partnership health, not partnership dysfunction. But left unresolved, it slowly erodes the trust that produced it.

## Expanded Possibilities

- **Run the underlying-game conversation first.** Before any more fundraising debate, sit down and each answer: *In 5 years, what does success look like for me personally? What kind of company do I want to be running? What outcome am I optimizing for?* If your answers diverge on venture-scale vs. ownership-scale, the fundraising question resolves automatically (and you have a much bigger conversation to have). If they converge, the fundraising debate becomes a tactical question, not an existential one.

- **Force the 90-day plans.** Each of you writes the operating plan for your preferred path: hires, burn, milestones, risks, kill criteria. Compare them side by side. The weaker plan reveals itself, or — more likely — both plans reveal gaps that change the conversation.

- **Consider the third option.** A $1-1.5M raise from a small group of the warm inbound investors, on a SAFE with a generous cap, gives you partial momentum capture, partial dilution protection, and preserves optionality to do a proper Series A from $80-100k MRR with the same investors as inside leads. This is not a compromise — it is often the actually correct answer that gets missed when the frame is binary.

- **Set a decision deadline and a decision rule.** "We will decide by [date] using [criteria]. If we still disagree on that date, [tiebreaker mechanism — e.g., the person whose domain it most affects gets the call, or we bring in a trusted outside advisor]." Open-ended disagreement between equal co-founders is corrosive. A decision rule isn't a failure of partnership — it is a feature of mature partnerships.

- **Use a falsification frame instead of an advocacy frame.** Each of you spends 30 minutes building the *strongest possible case for the other's position*. This breaks the Level 2 lock by forcing you to inhabit the other framework rather than defend your own. The argument that survives both of you steel-manning the opposite is the one to act on.

## Recommended Next Steps

1. **This week, separately:** Each of you write 2 pages — *what game am I actually playing, and what does success look like in 5 years?* Exchange. Read in silence. Then talk. If your answers diverge meaningfully, every other conversation depends on resolving that one first.

2. **Next week:** Each of you writes the 90-day operating plan for your preferred path. Concrete hires, concrete burn, concrete milestones, concrete failure conditions. Compare side by side.

3. **Then:** Re-open the fundraising conversation, but this time include the third option (partial raise / SAFE / strategic angels). Decide against criteria, not against advocacy.

4. **Set a hard decision date:** No more than 3 weeks from today. Circular debates compound. The cost of *not deciding* is currently invisible to both of you, but it is real — every week of indecision is a week neither of you is fully executing on either path.

5. **Name the meta-pattern out loud:** Tell her, "I think we're stuck because we're optimizing for different underlying things and we've never said what those are. Can we have *that* conversation before we have the fundraising one again?" Naming the dynamic dissolves most of the heat. The conversation you are avoiding is the one that resolves the conversation you are having.

```

### 5d-thinking/02-partnership — generated (4952 bytes)

```
[5D] Trap detected: Outer-Individual trap. Running analysis across all 5 dimensions.

## Thinking Trap Detected

You and your co-founder are both stuck in an Outer-Individual trap: the entire argument is being conducted at the level of behaviors and numbers (raise now vs. raise later, $3M vs. $1M, 12% MoM, valuation math). You've each made the case three times because the case is not the disagreement. You said it yourself in the last line — you're optimizing for different things underneath. The behavior layer cannot resolve a values-layer split, which is why the conversation goes in circles.

## D1 — Individual Inner

Your bootstrap argument is doing work beneath the math. "Every $20k MRR doubles valuation" is correct, but it's also a story about control, proof, and the discomfort of accepting outside money before you feel you've earned it. There's an identity stake in being the founder who got to $80k MRR without dilution. Her "raise now while momentum is hot" carries its own inner cargo: a fear that windows close, that you'll look back at a missed market and wonder why you optimized for ownership math during a once-a-cycle window. Neither of these is wrong. Both are unspoken, which is why neither argument lands when restated a fourth time.

## D2 — Individual Outer

Look at what each of you is actually doing rather than arguing for. You are running the company as if capital is a constraint to be respected; she is running it as if speed is a constraint to be removed. Three months of bootstrapping is not a neutral act — it is a bet that the current 12% MoM curve holds without acceleration spend, that no competitor raises into your category, and that inbound interest stays warm. Three months of fundraising is also not neutral — it removes one of you from operating cadence for 8-12 weeks at exactly the moment the traction story needs to keep compounding. The behavioral cost of each path is real and asymmetric, and neither of you has put those costs on the table next to the valuation math.

## D3 — Collective Inner

The unspoken rule between two co-founders four years in is that disagreements get resolved through reasoning, not authority. That norm is now the problem. You both keep presenting your case because the shared culture says "the best argument wins" — but this isn't an argument with a best answer, it's a values trade-off where one of you has to defer. Neither of you wants to be the one who concedes without being convinced, because conceding under a "best argument" norm feels like losing rather than choosing. The group operating system you built is not equipped for a decision where conviction is symmetric.

## D4 — Collective Outer

Zoom out to the structural layer. The fundraising market itself is set up to reward the move she's advocating: investors price momentum, not steady-state economics, and a $40k MRR company at 12% MoM with TechWeek inbound is a structurally different asset than an $80k MRR company three months later, even if the latter is "objectively better." The valuation curve is not linear in the way bootstrap math assumes — it's a step function tied to narrative windows. At the same time, the structure punishes bad raises: a $3M seed taken without a clear use of capital sets a burn expectation and a Series A bar (typically 3x the seed valuation in 12-18 months) that may not be reachable without a real plan. Both of you are reading the structure correctly, from different vantage points.

## D5 — Historical Pattern

This exact dynamic has a name in early-stage company history: the "raise on traction vs. earn the round" split, and it appears in nearly every co-founder pair that survives long enough to face it. The pairs that navigate it well don't pick a side — they reframe the question. They ask: what specific accelerant would $3M unlock that $1M cannot, and is that accelerant time-sensitive? If the answer is concrete (a hire, a market window, a competitive moat), raise now. If the answer is vague, the round is being raised against fear of missing out, and the bootstrap path wins. The pairs that don't navigate it well keep arguing valuation math until one defers resentfully, and that resentment compounds into the next strategic decision.

## Synthesis: What This Changes

The disagreement is not about timing — it is about what each of you trusts more: the curve you can control or the window you can't. Stop arguing the case a fourth time. Spend one session, together, answering one question: "What would $3M let us do in the next 6 months that $1M could not?" If you cannot fill a whiteboard with concrete answers, her argument loses its base — the round is fear-of-missing-window, not fuel for a plan. If you can, your argument loses its base — the dilution math was never the real cost. The decision falls out of that exercise, and more importantly, the symmetry of conviction breaks honestly rather than through deference.

```


## OUTPUTS — 5d-thinking/03-scope

**Input:** [`inputs/5d-thinking/03-scope.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/5d-thinking/03-scope.md`)

**Blind mapping:** A=handwritten, B=generated

### 5d-thinking/03-scope — handwritten (10267 bytes)

```
# 5D Analysis: Customer-Feature Scoping Decision

## Current Thinking Pattern

**Level:** Stuck between Level 1 (rule-following: "customer asked → must deliver") and Level 2 (own model: "we have capacity for 3, so the question is which 3"). The framing is one-dimensional — the entire problem has been reduced to a **roadmap allocation puzzle** ("ship 10, ship 3, or ship 0"). That's a Lines-of-Business / Engineering line. Two days of staring without progress is the signal: the constraint isn't in the dimension you're searching.

**Lines being considered:** Engineering capacity, Product roadmap, Account revenue.
**Lines being ignored:** Customer-relationship dynamics, Internal team identity, Power/leverage, Market positioning, Time/sequence, Founder psychology.

**Identity attachment to watch:** "We're a customer-obsessed company" or "We deliver what we commit to" — these can pre-empt the harder question of *whether the list is the actual ask*.

---

## Expanding the View

### Individual Inner (Psychological — yours)

The "staring for 2 days" is data. What's actually frozen?

- **Fear of the renewal call.** The list is being treated as a binding contract because losing 40% of ARR is existential. That fear collapses every option into "do what they said." Notice: no part of your framing involves *talking to them*. That's the tell.
- **Sunk-identity in being responsive.** If you push back, are you "the vendor that says no"? That self-image may be doing more decision-making than the math.
- **False binary.** You've defined the option space as {10, 3, 0}. That's already a Level 1-2 move — you've accepted the customer's framing (a list of 10 features) as the unit of negotiation. The unit is actually *the renewal*, and features are one currency among several.

### Collective Inner (Cultural — both sides)

- **Their side:** A 10-item list from an enterprise buyer is almost never 10 ranked must-haves. It's usually (a) a procurement/IT wishlist aggregating multiple internal stakeholders, (b) a negotiation anchor, (c) a CYA document for whoever signs the renewal. The person who wrote the list and the person who signs the check are usually different humans with different priorities.
- **Your side:** SaaS culture treats "the customer asked for it" as sacred. But enterprise buyers respect vendors who push back with expertise more than vendors who say yes to everything — saying yes signals you're a body shop, not a partner.
- **Industry narrative:** "Don't lose your whale" is the loud story. The quieter, truer one: companies that over-customize for one whale **become** that whale's internal IT team and die when the whale leaves anyway.

### Individual Outer (Behavioral — what's actually happening)

What you've done: stared at a spreadsheet for 2 days.
What you haven't done:
- Called the **economic buyer** (not the list-sender) to ask which 3 actually matter for renewal.
- Mapped which of the 10 features are **table-stakes for any enterprise** (SSO, SCIM, audit retention, data residency, granular roles — items 1, 2, 7, 9, 10) vs **bespoke to them** (white-label, competitor import, PagerDuty, templates, per-team analytics — items 3, 4, 5, 6, 8).
- Checked which features your **other customers' P1 issues** overlap with (data residency? SSO? role permissions?). The 4 P1s might not be in tension with the 10 — they might be the same features.

The behavioral move that's invisible from inside the spreadsheet: **the list is a discovery artifact, not a build spec.**

### Collective Outer (Systemic — structures and incentives)

- **Concentration risk is the actual problem.** 40% of ARR in one account means *every* quarter looks like this quarter, forever. Whatever you decide about these 10 features, the strategic decision is: are you building a product, or are you building this customer's internal tool? Those are different companies.
- **Renewal mechanics:** "Tied to renewal" is rarely a clean conditional. There's a procurement process, a champion, a budget cycle, an exec sponsor. Each has different leverage. The list-sender is one node in that graph.
- **Build-vs-buy systemics:** Items 1 (SSO), 10 (SCIM), 7 (data residency) are largely **vendored capabilities** (WorkOS, Auth0, Frontegg handle SSO+SCIM in days, not 3 weeks). The 3-week SSO estimate may itself be a phantom constraint from "we build everything ourselves."
- **Multi-tenancy debt:** Items 6 (white-label) and 7 (data residency) are architectural decisions that benefit *every* future enterprise customer. These aren't gifts to this account — they're product investments unlocked by this account's pressure.

### Historical Pattern (Time / Fifth Dimension)

This pattern is old and well-mapped:

- **Christensen's "Innovator's Dilemma":** Best customers pull you toward over-serving them, away from the disruptive trajectory. The 10-item list is exactly the gravitational field he described.
- **Andreessen / a16z "shape of the company":** Every B2B SaaS company that survived past Series B faced this exact moment — one customer becomes a "design partner" who tries to become "the product." The survivors learned to **transcend and include**: take the pressure as a forcing function for platform features, refuse the bespoke ones.
- **Salesforce, Snowflake, Datadog** all have public stories of saying no to whale-customer feature lists in year 2-4 and being thanked for it later.
- **What collapses the chain:** Building all 10 doesn't lose the renewal — it *guarantees* the next list of 10, plus you've now starved your other 60% of ARR and trained the whale that lists work. The renewal-loss scenario is asymmetric: shipping 0 with bad communication kills the renewal; shipping 0 with **expert pushback and 3 of-the-right-things shipped** strengthens it.

---

## Key Constraints Identified

The actual constraint is **not** "which 3 of 10." The actual constraints, in order:

1. **Information asymmetry.** You don't know which 3 matter. The list-sender may not know either. Two days of analysis can't solve a problem that requires a 30-minute call.
2. **Concentration risk** is the strategic disease; this quarter is the symptom. Any answer that doesn't reduce concentration is treating symptoms.
3. **Build-everything bias** is inflating the cost. Several "features" are integrations or vendored capabilities, not ground-up engineering.
4. **Identity friction.** The fear of being "the vendor that pushes back" is doing decision-making that should be done by data.
5. **Other customers as silent stakeholders.** The 4 P1s aren't in your framing as people, only as queue items. They're also a renewal pipeline.

---

## Expanded Possibilities

Things that become visible from the expanded view:

- **The discovery call is the highest-leverage action of the quarter.** Before any prioritization, get the economic buyer on a call. Ask: "If we ship 3 of these 10 by renewal, which 3 make this a yes?" You will learn that 4-6 of the items were filler.
- **Reframe table-stakes vs bespoke.** SSO, SCIM, audit retention, granular roles, data residency are platform investments — they're things you'd build for the *next 5 enterprise customers* anyway. Frame these as roadmap-aligned, not customer-specific. White-label, competitor import, PagerDuty alerts, templates, per-team analytics are bespoke — these are negotiation chips or no's.
- **Buy, don't build, the commodity layers.** WorkOS or Frontegg can deliver SSO + SCIM in 1-2 weeks of integration vs 3+ weeks of custom build. That alone changes capacity math.
- **Make the renewal conversation explicit, not implicit.** "Tied to renewal" is leverage they're using; you can use it back: "We're prioritizing 3 of these for the renewal commit. We need a multi-year extension and a reference call in exchange." Concentration risk goes down, not just feature debt.
- **Parallel-track the other customers.** Two of the 4 P1s probably overlap with the platform-grade items (SSO, roles, residency). One engineer one week could resolve them. Don't treat the 60% as zero.
- **The "ship 0 and ask hard questions" option is misframed.** It's not "ship 0" — it's "delay shipping until the discovery call clarifies the 3, then ship 3 with a renewal-aligned communication plan." That's the highest-EV path, not the riskiest.

---

## Recommended Next Steps

1. **This week — stop analyzing, start asking.** Get the economic buyer (not the list-sender) on a 30-minute call. One question framing: *"We can ship 3 of these by your renewal. Which 3 are the ones where, if they're shipped, you renew, and if they're not, you don't?"* Then shut up and listen. Verify with their champion separately.
2. **Re-cost the list with vendored options.** SSO + SCIM via WorkOS-class vendor; data residency via cloud-region deployment; audit retention as a config flag. Real capacity is likely higher than 3 once non-build options are on the table.
3. **Classify the 10 into three buckets:**
   - *Platform investments* (we'd build these for any enterprise customer in 12 months) — ship with priority.
   - *Bespoke-but-cheap* (PagerDuty integration, templates) — ship if capacity allows, frame as goodwill.
   - *Bespoke-and-expensive* (white-label, competitor import) — push to next quarter or trade for renewal terms.
4. **Negotiate the renewal as a package, not a feature delivery.** Multi-year, expansion commit, reference, case study — in exchange for the 3 features. This converts feature pressure into account expansion.
5. **Surface concentration risk to your own team/board** as the real strategic problem. Whatever happens with this renewal, the fix is the next 3 enterprise logos, not the next 3 features for this one. Sales pipeline is the actual antidote.
6. **Same-day check on identity:** notice whether resistance to step 1 ("calling them feels confrontational") is fear talking. The call is the cheapest, highest-information action available. Not making it is the expensive choice.

The framing wasn't getting clearer because you were searching the wrong dimension. The decision isn't *which 3 features* — it's *what's the renewal-and-platform play*, of which features are one input. Make the call. The spreadsheet will look different on the other side of it.

```

### 5d-thinking/03-scope — generated (5135 bytes)

```
# Customer-Feature Scoping — 5D Analysis

[5D] Trap detected: Outer-Individual trap. Running analysis across all 5 dimensions.

## Thinking Trap Detected

You are stuck in an Outer-Individual trap. The 2 days of staring have all been spent on permutations of one variable: which features to ship. The list itself, the capacity math, the renewal date — these are all observable, behavioral, execution-layer questions. What is missing from your framing is anything about why this customer sent a list of 10 in the first place, what the list signals about their internal politics, and what your reflexive willingness to treat the list as a backlog says about your own product posture.

## D1 — Individual Inner

The unspoken belief driving your framing is that 40% of ARR concentration is a contractual fact rather than a strategic failure already in progress. You are negotiating with the renewal as if it is the deadline; it is actually the symptom. Notice that the question you are asking yourself is "which 3 of their 10," not "what kind of company are we becoming if we let one customer set our roadmap for a quarter." The identity stake is real: building all 10 makes you a custom-software shop with one client, and some part of you knows that and is avoiding naming it because the short-term cash is comforting and the alternative requires confrontation.

## D2 — Individual Outer

Your behavior over these 2 days has been analysis as avoidance. You have not picked up the phone with their economic buyer to ask which features are renewal-blocking versus wishlist, and that single conversation collapses most of the uncertainty in your spreadsheet. The 10-item list is almost certainly the output of an internal stakeholder-collection exercise on their side, where a procurement lead said "send us everything you want" and people piled on. Treating it as a unified ask from a unified buyer is a behavioral error; you are responding to a document instead of to humans, which is faster but wrong.

## D3 — Collective Inner

Inside your customer's organization, the unspoken rule is that lists like this are political artifacts, not engineering specs. Some of these features have a champion who will fight for them at renewal; others are there because someone in a Tuesday meeting said "and while we're at it." SSO, SCIM, and EU data residency are almost always compliance-driven, meaning they have an internal owner with budget authority, while items like white-label branding and workflow templates are usually pet projects from a single user. Inside your own team, the parallel norm is that "the big customer asked" is treated as a trump card that suspends normal prioritization debate, which is exactly the cultural pattern that produces 40% concentration in the first place.

## D4 — Collective Outer

The structural reality is that your other customers' 4 P1 issues are a leading indicator of the next concentration crisis. If you spend 4-5 months servicing one account, you will lose 2-3 mid-tier customers to churn and slow-rolled expansion, and a year from now this customer will be 55% of ARR instead of 40%. The incentive system is producing the outcome it is designed to produce: short-term revenue protection at the cost of long-term portfolio health. The features themselves split cleanly along a structural line — items 1, 7, 9, and 10 (SSO, EU residency, RBAC, SCIM) are platform investments that any future enterprise customer will also demand, while items 3, 5, 6, and 8 are bespoke. You are treating a list of 10 as homogeneous when half of it is roadmap acceleration and half of it is custom work.

## D5 — Historical Pattern

This is the classic "anchor customer" pattern that has played out at every B2B SaaS company that ever crossed the chasm. The companies that survived it (Snowflake with Capital One, Datadog with early enterprise accounts) understood that the anchor's list is raw material for the platform, not a contract. The companies that died from it built bespoke versions of their product, lost engineering velocity, and were eventually acquired for parts when the anchor renegotiated from a position of leverage. The pattern's tell is exactly what is happening to you now: a founder staring at a feature list trying to optimize within the customer's framing instead of stepping outside it.

## Synthesis: What This Changes

The question is not "which 3 of 10." The question is "which of these 10 are actually platform investments that compound across all future enterprise customers, and how do I get the customer to co-fund that work as their renewal?" Reframe the conversation: ship the 4 platform items (SSO, SCIM, EU residency, granular RBAC) in the quarter, position them as the enterprise tier you were already building, and tell the customer plainly that the bespoke 6 are not on the roadmap but you will revisit after renewal. The concrete action this week is one call with their economic buyer to separate must-have from nice-to-have, before you make any internal commitment. The thing to let go of is the framing that says you owe them an answer to their list as written.

```


## OUTPUTS — eod/01-concise-day

**Input:** [`inputs/eod/01-concise-day.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/eod/01-concise-day.md`)

**Blind mapping:** A=handwritten, B=generated

### eod/01-concise-day — handwritten (10355 bytes)

```
# EOD — Tuesday 26/04

## Phase 0 — Guard + Resume

- Idempotency check: `grep -c "^2026-04-26,eod" cron_log.csv` → 0. Fresh run.
- Initialized `/tmp/eod-factory-state.json` with `current_phase: "fetch"`.
- Wrote running guard to `cron_log.csv`: `2026-04-26,eod,running,2026-04-26T20:14:03`.

---

## Phase 1 — Silent Data Fetch (summary)

### 1A — WHOOP
- `whoop recovery` → unavailable (no fresh sync today). `recovery_score: null`, `hrv: null`.
- `whoop sleep` → wrapper returned partial output. `sleep_hours: null`, `sleep_score: null`.
- Note: input recap mentions ~6.5h last night → carried forward as self-report only, not WHOOP.

### 1B — Vault Activity (mtime today)
- `_Inbox/` new files today: 0
- `library/hub/` new files today: 0
- `x-content/posted/` today: 0
- `knowledge_captured = 0`, `content_shipped = 0`

### 1C — habit-tracker.csv last row
- Last `week_type`: `sprint` (carried forward).
- Today is Tuesday → no Monday prompt.

### 1D — Google Calendar (plan completion)
- Events today with "Why:" descriptions (Alfred-created blocks): 0 detected.
- `tasks_planned = 0`, `tasks_done = 0`
- `completion_note = "No plan set"`
- Sir's day instead ran on a self-organized schedule (deep work, 1:1, customer call, gym).

### 1E — skillia-brain context (silent)
- Pipeline: Acme Robotics (Sarah Chen) — security review requested → quote needed from Trail of Bits.
- Marketing dependency: pricing page blocking launch.
- Auth refactor shipped to main today (engineering unblock).

### 1F — Intensity tier
- `recovery_score = null` → `MAINTAIN` (assume neutral).
- Self-reported sleep ~6.5h + 15:00 crash → bias slightly conservative inside MAINTAIN.

### 1G — TickTick
- `ticktick projects` → CLI available.
- Overdue: 0. Due today: 0. No-due-date flat list under threshold → suppressed.
- `ticktick.available = true`, no items to surface.

### 1H — Vault health
- `areas_inbox`: 0 files. `skillia_inbox`: 0 files.
- Minions evaluation:
  - `dev_work_today = true` (auth refactor shipped, "code/refactor/pushed" in recap).
  - `days_since("learn") ≥ 1` → propose `/minions-learn` (inline).
  - `days_since("dev-reflect") ≥ 3` → propose `/minions-dev-reflect` (inline).
  - `days_since("reflect") ≥ 1` AND energy unknown (will recheck after Phase 2).
  - Inbox proposals skipped (counts = 0).
- `minions_proposals` (cap 3 inline): `/minions-learn`, `/minions-dev-reflect`, `/minions-reflect`.

### 1I — Skillia kanban backlog pick
- `tasks/kanban.md` parsed.
- In Progress: Auth refactor (just shipped — will move to Done).
- Priority: "Send Trail of Bits security-review quote to Sarah Chen (Acme)" `#sales` `#client`.
- Backlog scoring → top: Acme security-review follow-up (5 + 3 = 8, top score).
- `backlog_pick.title`: "Email Trail of Bits — request Acme security-review quote"
- `why`: "Acme call surfaced the only blocker to closing — moving on it tomorrow keeps the deal warm and the customer relationship in motion."

State written. Phase advanced to `interview`.

---

## Phase 2 — EOD Interview

```
EOD — Tuesday 26/04

⚠️ WHOOP unavailable

📋 Today detected:
  ✅ Gym  ·  1.5h deep work  ·  ❌ Outreach
  —  ·  —  ·  —

🎯 Plan: 0/0 blocks — No plan set
       (today ran self-organized: deep work + 1:1 + customer call + gym)

A few questions:
1. Recap? What happened today — what worked, what didn't?
2. Sunlight? y/n
3. Meditation/NSDR? y/n
4. Prayer/devotional? y/n
5. Read today? y/n
6. Energy 1–5?

Anything to correct above? (deep_work_hours looks like ~1.5h based on the 09:00–10:30 block — confirm or override)
```

### Sir's reply (synthesized from input)
1. Recap: "Shipped the auth refactor — JWT rotation was nastier than I expected. 1:1 with marketing pushed launch by a week because they need a pricing page first. Acme call went well — Sarah Chen wants a security review before signing, so I need to get a Trail of Bits quote. Crashed post-lunch around 15:00. Lost ~30 min to context-switching between marketing and customer threads."
2. Sunlight: n (gym indoors, no explicit outdoor time logged)
3. Meditation/NSDR: n
4. Prayer/devotional: n
5. Read: n
6. Energy: 3 (sharp until 15:00, then crash)

Parsed:
- `recap`: as above
- `sunlight = 0`, `meditation = 0`, `prayer = 0`, `reading = 0`
- `energy = 3`, `week_type = sprint` (carried)
- Corrections: deep_work_hours = 1.5 confirmed; outreach = 0 confirmed (customer call counts as user_convo, not outreach).
- `user_convo = 1` (Acme call).

State advanced to `logging`.

---

## Phase 3 — Data Logging

### 3A — CSV row (20 columns)

```
2026-04-26,0,0,0,0,1,1.5,0,1,0,0,0,0,0,0,3,sprint,0,0,No plan set
```

Columns verified: 20. No commas in `completion_note`. Appended to `habit-tracker.csv`.

### 3B — Confirmation

✅ Logged. 2026-04-26 — Energy 3/5, Recovery —%, 0/0 blocks.

`cron_log.csv`: `2026-04-26,eod,logged,2026-04-26T20:16:11`. State → `tasks_review`.

---

## Phase 3.5 — Vault + Tasks Review

```
📋 TickTick
  ✅ No overdue or due-today tasks

📌 Skillia tasks  [source: tasks/kanban.md]
  🔄 In Progress (1): Auth refactor — JWT rotation (ready to move → Done)
  ⚡ Priority (1): Trail of Bits security-review quote for Acme #sales #client
  💡 Tomorrow's pick: "Email Trail of Bits — request Acme security-review quote" #sales #client
     Why: Acme call surfaced the only blocker to closing — moving on it tomorrow keeps the deal warm and the customer relationship in motion.

🧠 Vault health
  Areas inbox: 0 file(s)  ·  Skillia inbox: 0 file(s)

🤖 Minions proposals
  → /minions-learn        — dev work today (auth refactor shipped); capture JWT rotation lesson  [🔄 runs now]
  → /minions-dev-reflect  — 3+ days since last dev reflection; engineering pattern worth examining  [🔄 runs now]
  → /minions-reflect      — energy 3, end of intense day; useful synthesis  [🔄 runs now]
```

### Gate questions

**Q1 — Which Minions to run now?** (multiSelect)
- /minions-learn — capture JWT rotation lesson
- /minions-dev-reflect — engineering pattern review
- /minions-reflect — daily synthesis
- None — skip all

**Q2 — Add anything to TickTick inbox?**
- Suggested adds based on recap:
  - "Scope pricing page tomorrow morning — unblock marketing launch"
  - "Email Trail of Bits — request security-review quote for Acme"
  - "Followup Sarah Chen (Acme) after ToB quote returns"
- Options: "Add the 3 suggested" | "Nothing to add" | "Yes — type below (Other)"

**Q3 — Add "Email Trail of Bits — request Acme security-review quote" to tomorrow's plan?**
- Yes — add to tomorrow
- No — skip
- (Recommended: Yes — it's the highest-leverage revenue-advancing action surfaced today.)

### Assumed approvals (best-judgment defaults applied)
- Q1: `/minions-learn` + `/minions-dev-reflect` (dev-day priority).
- Q2: Add the 3 suggested tasks to TickTick inbox.
- Q3: Yes — add Trail of Bits email to tomorrow's plan.

### Inline Minions execution
- 🔄 Running /minions-learn... ✅ /minions-learn — done (extracted JWT rotation pattern + context-switching cost note)
- 🔄 Running /minions-dev-reflect... ✅ /minions-dev-reflect — done (flagged: estimation gap on auth refactor; recommend: write threat-model first for crypto changes)

### TickTick inbox additions
- ✅ Added: "Scope pricing page tomorrow morning — unblock marketing launch"
- ✅ Added: "Email Trail of Bits — request security-review quote for Acme"
- ✅ Added: "Followup Sarah Chen (Acme) after ToB quote returns"

State advanced to `planning`. `skillia_tasks.add_to_tomorrow = true`.

---

## Phase 4 — Tomorrow Planning

### Context synthesis
- Recovery: null → MAINTAIN, slight conservative bias (sleep 6.5h, post-lunch crash).
- Mandatory candidate: Trail of Bits email (Acme security-review quote) — `#sales` → outreach block.
- Time-sensitive: Pricing page scoping — promised to marketing, blocks launch.
- High-leverage: Recovery-aware afternoon (avoid stacking; protect post-15:00 window).

### Proposed plan

```
Tomorrow's plan — Wednesday 27/04

🎯 09:30–12:00 — Pricing page scope + draft
   Why: marketing's launch unblock and your morning is sharpest — own the spec while you're fresh.

📋 13:00–14:00 — Trail of Bits outreach + Acme follow-up
   Why: security review is the only blocker to closing Sarah Chen — send the quote request and warm her thread same day.

⚡ 16:30–17:30 — Light admin / NSDR + walk
   Why: yesterday crashed at 15:00; protect the window with a real reset rather than forcing another deep block.

Recovery —% (WHOOP unavailable, self-reported 6.5h sleep) → maintain day, slightly conservative.

Go? Or adjust?
```

### Sir's reply (assumed: "go")

### Calendar events created (gog)
- ✅ Event 1: "Pricing page scope + draft" — 2026-04-27T09:30:00+02:00 → 12:00:00+02:00. id: `evt_w27_a`.
- ✅ Event 2: "Trail of Bits outreach + Acme follow-up" — 2026-04-27T13:00:00+02:00 → 14:00:00+02:00. id: `evt_w27_b`.
- ✅ Event 3: "Light admin / NSDR + walk" — 2026-04-27T16:30:00+02:00 → 17:30:00+02:00. id: `evt_w27_c`.

📅 Calendar set. See you at 08:00.

State advanced to `memory`.

---

## Phase 5 — Memory Breadcrumb

Appended to `~/clawd/memory/2026-04-26.md`:

```
## EOD [20:18]
Energy: 3/5 · Recovery: —% (WHOOP unavailable) · 0/0 blocks (self-organized day)
Recap: Shipped auth refactor (JWT rotation harder than planned). Marketing delayed launch — pricing page neede
Tomorrow: Pricing page scope · Trail of Bits / Acme follow-up · Light admin + NSDR
```

`cron_log.csv`: `2026-04-26,eod,done,2026-04-26T20:18:42`.
State file removed.

---

## Summary — what changed today

- **Wins logged:** Auth refactor shipped; Acme relationship advanced to security-review stage.
- **Friction logged:** Context-switching cost (~30 min); estimation gap on JWT rotation; post-lunch crash with no reset protocol.
- **Knowledge captured (via /minions-learn):** JWT rotation pattern + threat-model-first heuristic for future crypto work.
- **Tomorrow's leverage move:** Trail of Bits quote → unblocks Acme close. Marketing pricing-page scope → unblocks launch.
- **Health note:** No sunlight, no meditation, no reading, no prayer today — flag if pattern repeats this week.

```

### eod/01-concise-day — generated (5912 bytes)

```
## Phase 1 — Data Fetch

```
Phase 1 — Data Fetch complete.
WHOOP: recovery=null, sleep=null  (wrapper unavailable in this run; user reported ~6.5h, sharp until 15:00 then crash)
Vault notes found: 1 file (today's day notes — Tuesday)
Meetings found: 4 calendar items (auth deep-work, marketing 1:1, Acme call, gym)
Inbox captures: 0
```

Note: WHOOP fetch unavailable. Per Quality Gate 2, proceeding with null values and applying conservative defaults to schedule. Self-reported sleep ~6.5h logged separately; will not be written to WHOOP fields.

---

## Phase 2 — EOD Interview

Today — 2026-04-26
WHOOP recovery: unavailable   Sleep: unavailable (self-reported ~6.5h)
Notes from vault: auth refactor shipped; marketing pushed pricing-page dependency; Acme wants security review pre-signing.

Parsed from day notes (interview answers inferred from explicit Wins, Friction, and Notes sections):

- **Energy:** 3/5 (sharp morning, post-lunch crash at 15:00)
- **Accomplishments:**
  - Shipped auth refactor; pushed to main (JWT rotation logic was nastier than planned)
  - Customer call with Sarah Chen at Acme Robotics — security review identified as gating step
  - Marketing 1:1 — agreed to delay launch one week
  - Gym (legs)
- **Blockers:**
  - Pricing page is now blocking marketing's launch sequence; not scoped
  - Acme blocked on third-party security review (Trail of Bits quote pending)
  - ~30 min lost to context-switching between marketing + customer threads
- **Learnings:**
  - JWT rotation logic underestimated — worth a dedicated remember entry
  - Security review request is a warm signal, not a stall — treat as buying behavior
- **Tomorrow's focus:** Scope the pricing page in the morning and request the Trail of Bits security review quote.

```
Phase 2 — Interview complete. Parsed 4 accomplishments, 3 blockers, 2 learnings.
```

Quality Gate 1: PASS — accomplishments contain concrete, named items (auth refactor, Acme call, marketing 1:1).

---

## Phase 3 — Log Writes

**Step 3.1 — Notion EOD log**

Writing to database `2ed3826d3377813b8e17d4d0bda26eea`:

```
Date:              2026-04-26
Energy:            3
WHOOP Recovery:    null
WHOOP Sleep:       null
Accomplishments:
  - Shipped auth refactor (JWT rotation) to main
  - Acme Robotics call — Sarah Chen requesting security review
  - Marketing 1:1 — launch delayed 1 week
  - Gym (legs)
Blockers:
  - Pricing page blocks marketing launch — needs scoping
  - Acme blocked on Trail of Bits security review quote
  - 30 min lost to context-switching
Learnings:
  - JWT rotation complexity underestimated
  - Security review request = warm signal, not friction
Tomorrow Focus:    Scope the pricing page and request the Trail of Bits security review quote.
```

Notion write: success.

**Step 3.2 — Habit-tracker CSV**

Path: `~/clawd/life/areas/_data/habit-tracker.csv`

Derived flags:
- `deep_work_done` = 1 (shipped auth refactor)
- `gym_done` = 1 (legs)
- `outreach_done` = 0 (Acme was an inbound call; no Loom/LinkedIn outreach mentioned)

Row appended:
```
2026-04-26,3,,6.5,4,3,1,1,0
```

```
Phase 3 — Log writes complete. Notion: success. CSV: appended.
```

---

## Phase 4 — Schedule Proposal

WHOOP recovery null → applying conservative (LOW capacity) defaults per Gate 2. However, self-reported sleep ~6.5h and morning sharpness suggests effective capacity closer to STANDARD. Proposing STANDARD with NSDR slot retained for the known post-lunch crash window.

```
─────────────────────────────────────
Tomorrow — 2026-04-27
WHOOP recovery tonight: unavailable → STANDARD capacity (conservative; NSDR retained)
─────────────────────────────────────
08:00–09:30  DEEP WORK     — Scope pricing page (unblock marketing)
09:30–10:00  Admin + messages  — request Trail of Bits quote for Acme
10:00–11:00  Free / continuation
11:00–12:00  GYM
12:00–13:00  Lunch + reset
13:00–14:00  NSDR / quiet  (post-meal crash window)
15:00–16:30  OUTREACH / LOOM
17:00–18:00  EOD admin + capture
21:00–21:30  Wind-down
─────────────────────────────────────
```

Anchors:
- Deep-work block explicitly tied to tomorrow's focus (pricing page).
- Trail of Bits ask placed in the 09:30 admin slot — short, sequenced after deep work so it doesn't fragment the morning.
- NSDR retained because today's 15:00 crash is a confirmed pattern.

```
Phase 4 — Schedule proposal ready. 9 blocks proposed.
```

---

## Phase 5 — Approval Gate

```
Tomorrow's schedule is ready (shown above).

Options:
  A  Approve and create calendar events as proposed
  B  Modify — tell me what to change, I'll revise before creating
  C  Skip calendar — keep the proposal as a reference only

What's your call?
```

[Awaiting explicit approval. No calendar writes performed.]

---

## Phase 7 — Wrap-Up

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
/eod — 2026-04-26 complete
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Energy today:      3 / 5
WHOOP recovery:    unavailable (wrapper offline; self-reported sleep ~6.5h)
Accomplishments:   4 logged
Blockers carried:  3
Tomorrow focus:    Scope the pricing page and request the Trail of Bits security review quote.
Notion:            logged
CSV:               appended
Calendar:          pending approval (Phase 5 gate open)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Sleep target: 22:30. Rest well.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

```


## OUTPUTS — eod/02-messy-day

**Input:** [`inputs/eod/02-messy-day.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/eod/02-messy-day.md`)

**Blind mapping:** A=handwritten, B=generated

### eod/02-messy-day — handwritten (9481 bytes)

```
# EOD — Thursday 26/04

## Phase 0 — Guard + Resume

```
$ grep -c "^2026-04-26,eod" ~/clawd/life/areas/_data/cron_log.csv
0
```

Fresh run. State initialized at `/tmp/eod-factory-state.json`.
Guard row written: `2026-04-26,eod,running,2026-04-26T20:14:02`.

---

## Phase 1 — Silent Data Fetch

### 1A — WHOOP
- recovery_score: **41**
- hrv: 38
- sleep_score: 72
- sleep_hours: null (wrapper returned efficiency only)
- strain: 11.4

### 1B — Vault Activity
- _Inbox new files today: 0
- library/hub new files today: 0
- knowledge_captured: **0** (2 pages of Karpathy read does not equal a captured atomic note)
- content_shipped: 0

### 1C — habit-tracker.csv last row
Last row carries `week_type=sprint`. Carried forward silently.

### 1D — Plan completion
Yesterday's EOD created 3 blocks for today (Why: tags found):
- 09:00–10:30 Deep work: pricing page copy → **missed** (10am VC call collided)
- 11:30–13:00 Loom + outreach batch → **missed** (designer review ran into cofounder check-in)
- 17:00–18:30 Gym → **missed** (no gym today)

```
tasks_planned = 3
tasks_done    = 0
completion_note = "Day overrun by reactive calls - no planned block survived"
```

### 1E — skillia-brain context
- Trail of Bits quote pending Sarah Chen reply (Tuesday → 2 days stale)
- Support inbox unattended ≥48h
- LinkedIn 3 unread inbound (warm)
- Pricing page still incomplete — gating launch
- Churn dashboard non-existent (flagged today)

### 1F — Intensity tier
Recovery 41 → **MAINTAIN**. No heroics tomorrow.

### 1G — TickTick
```
Overdue (3): Reply Sarah Chen — Trail of Bits quote · Skillia
             Support inbox triage · Skillia
             Decide: refund angry customer · Skillia
Today (1):   LinkedIn DM cleanup (3 unread)
This week:   6 upcoming
```

### 1H — Vault Health
- areas_inbox_count: 0
- skillia_inbox_count: 0
- dev_work_today: false (no deep work hours, recap mentions debugging by Eric, not Sir)
- minions_proposals:
  - `/minions-reflect` — energy uncertain, but recap is dense with decisions deferred → propose-only

### 1I — Skillia kanban backlog pick
```
in_progress: Pricing page copy (#product) · Latency investigation (#engineering)
priority:    Reply Sarah Chen ToB quote (#sales #legal) · Decide refund (#support)
             Churn dashboard v0 (#engineering #ops)
blocked:     Launch GA (waiting on pricing page)
```

Scoring at MAINTAIN (no override):
- Reply Sarah Chen ToB quote → #sales=5, +#legal proximity → **5**
- Decide refund → #support proximity to #sales → 3
- Churn dashboard → #engineering+ops, title contains nothing scored → 1

**backlog_pick:** *Reply Sarah Chen — Trail of Bits quote*
**why:** "Two days stale on a security vendor reply gates the audit timeline — 15-min task with outsized leverage."

State updated → `current_phase: interview`.

---

## Phase 2 — EOD Interview

```
EOD — Thursday 26/04

💚 WHOOP: 41% recovery · HRV 38 · Sleep —h (72%)
   ⚠️ Sleep hours unavailable from wrapper

📋 Today detected:
  ❌ Gym  ·  0h deep work  ·  ❌ Outreach
  ✅ User convo (4 calls)  ·  —  ·  —

🎯 Plan: 0/3 blocks — Day overrun by reactive calls - no planned block survived

A few questions:
1. Recap? What happened today — what worked, what didn't?
2. Sunlight? y/n
3. Meditation/NSDR? y/n
4. Prayer/devotional? y/n
5. Read today? y/n
6. Energy 1–5?
   Anything to correct above? (e.g. Karpathy reading = capture?)
```

**Sir's reply (synthesized from notes):**
1. Recap: Unfocused. Four reactive calls ate the day — VC pass, harsh-but-fair design review, 90-min cofounder drift into hiring, churn-threat support escalation. Staging down 09:00–09:45 (Eric handled). CI flaking on Go tests, parked. Realised no churn dashboard exists. Big customer threatening churn — their use case is 10x ours, considering graceful goodbye via pricing self-select. Third skipped gym this week, body knows. Read 2 pages of Karpathy autoresearch. Ate too much at lunch, post-meal crash hard.
2. Sunlight: n
3. Meditation/NSDR: n
4. Prayer: n
5. Reading: y (2 pages — count as yes)
6. Energy: **2**

Corrections: none — detected activity matches.

Parsed:
```
recap = (above, ~700 chars)
sunlight=0 · meditation=0 · prayer=0 · reading=1 · energy=2
week_type = sprint (carried)
```

State updated → `current_phase: logging`.

---

## Phase 3 — Data Logging

### 3A — CSV row built (20 columns)

```
2026-04-26,72,0,38,41,0,0,0,1,0,0,0,0,0,1,2,sprint,3,0,Day overrun by reactive calls - no planned block survived
```

Column count: **20** ✅
Binary fields: all 0/1 ✅
completion_note: 64 chars, no commas ✅

Appended to `~/clawd/life/areas/_data/habit-tracker.csv`.

### 3B — Confirmation

```
✅ Logged. 2026-04-26 — Energy 2/5, Recovery 41%, 0/3 blocks.
```

`cron_log.csv` updated: `2026-04-26,eod,logged,2026-04-26T20:16:48`.
State → `current_phase: tasks_review`.

---

## Phase 3.5 — Vault + Tasks Review

```
📋 TickTick
  🔴 Overdue (3): Reply Sarah Chen — ToB quote · Skillia
                  Support inbox triage · Skillia
                  Decide: refund angry customer · Skillia
  📅 Today (1):  LinkedIn DM cleanup (3 unread)
  📆 This week: 6 tasks upcoming

📌 Skillia tasks  [source: tasks/kanban.md]
  🔄 In Progress (2): Pricing page copy · Latency investigation
  ⚡ Priority (3): Reply Sarah Chen ToB quote #sales #legal · Decide refund #support · Churn dashboard v0 #engineering
  🚫 Blocked (1): Launch GA — waiting on pricing page
  💡 Tomorrow's pick: "Reply Sarah Chen — Trail of Bits quote" #sales #legal
     Why: Two days stale on a security vendor reply gates the audit timeline — 15-min task with outsized leverage.

🧠 Vault health
  Areas inbox: 0 file(s)  ·  Skillia inbox: 0 file(s)

🤖 Minions proposals
  ✅ Vaults healthy — no Minions to run inline tonight
  📋 For later: /minions-reflect — recap is dense with deferred decisions, worth a structured pass before Sunday
```

**Q1:** skipped (no inline proposals).
**Q2:** Add to TickTick inbox? → Sir: *"Yes — add: 'Define exit criteria for graceful-goodbye on 10x-use-case customer', 'Audit CI Go-test flake (timebox 30 min)', 'Spec churn dashboard v0 (one screen)'"*
**Q3:** Add Sarah Chen reply to tomorrow? → Sir: **Yes**

Inbox additions executed:
```
✅ Added: "Define exit criteria for graceful-goodbye on 10x-use-case customer"
✅ Added: "Audit CI Go-test flake (timebox 30 min)"
✅ Added: "Spec churn dashboard v0 (one screen)"
```

State → `current_phase: planning`, `skillia_tasks.add_to_tomorrow: true`.

---

## Phase 4 — Tomorrow Planning

### 4A — Synthesis (silent)

Tomorrow = **Friday 27/04**. Recovery 41 → MAINTAIN.
Mandatory candidate: Sarah Chen reply (small, #sales/#legal — slot inside outreach block, not its own).

Priority stack:
1. Revenue/time-sensitive: Sarah Chen reply + LinkedIn 3 unread + refund decision
2. High-leverage: Pricing page copy (in-progress, gating launch)
3. Operations: support inbox triage (2 days stale)

Friday is not weekend. Three blocks warranted but no heroics.

### 4B — Proposal

```
Tomorrow's plan — Friday 27/04:

🎯 09:30–12:00 — Pricing page copy (finish v1 draft)
   Why: It is the only thing blocking launch GA — three reactive calls just ate today, protect the morning peak before the same thing happens.

📋 13:00–14:30 — Outreach + decisions block
   Why: Reply Sarah Chen on ToB quote (15 min), clear LinkedIn 3 unread, write the refund decision (one paragraph, send). All three are stale and small.

⚡ 17:00–18:00 — Gym (non-negotiable)
   Why: Third skip this week, recovery 41 — short low-intensity session is the reset, not another miss.

Recovery 41% → maintain day. No high-stakes hiring decisions tomorrow.

Go? Or adjust?
```

Sir: **"go"** → ACCEPTED as-is.

### 4C — Calendar events created

```
✅ gog calendar create → "Pricing page copy (finish v1 draft)" 2026-04-27T09:30→12:00 +02:00 — id evt_pp1
✅ gog calendar create → "Outreach + decisions block" 2026-04-27T13:00→14:30 +02:00 — id evt_od1
✅ gog calendar create → "Gym" 2026-04-27T17:00→18:00 +02:00 — id evt_gym1
```

Each event description carries `Why: …` line (so tomorrow's EOD can detect plan completion).

```
📅 Calendar set. See you at 08:00.
```

State → `current_phase: memory`.

---

## Phase 5 — Memory Breadcrumb

Appended to `~/clawd/memory/2026-04-26.md`:

```
## EOD [20:18]
Energy: 2/5 · Recovery: 41% · 0/3 blocks
Recap: Unfocused. Four reactive calls ate the day — VC pass, harsh design review, 90-min cofounder
Tomorrow: Pricing page copy · Outreach + decisions · Gym
```

`cron_log.csv` final: `2026-04-26,eod,done,2026-04-26T20:18:11`.
State file removed.

---

### Summary (silent footer for Sir's reference)

- **Pattern flagged:** 3rd gym skip + reactive-call overrun + 0 deep-work hours on a sprint week. Same shape as last Thursday — worth `/minions-reflect` before Sunday.
- **Strategic note (not a question for tonight):** the 10x-use-case customer wanting to leave is information, not failure. Pricing self-selection is the right instinct — it's now a TickTick inbox item, not a 22:00 decision.
- **Decisions still parked** (deliberately, low energy): hire vs contract design · push launch +2 weeks · refund the angry customer (refund decision moved into tomorrow's outreach block — small, write-and-send).

```

### eod/02-messy-day — generated (4787 bytes)

```
Phase 1 — Data Fetch complete.
WHOOP: recovery=41, sleep=unavailable
Vault notes found: 1 file (Day notes — Thursday)
Meetings found: 4 items (VC fund, designer review, cofounder check-in, support escalation)
Inbox captures: 0 items

---

Today — 2026-04-26
WHOOP recovery: 41/100   Sleep: unavailable
Notes from vault: messy day; 4 calls, staging incident, gym skipped, post-meal crash.

EOD check-in — 2026-04-26

Parsed from your day notes (interview answers reconstructed from vault input):

1. Energy: 2/5 (drained — post-meal crash, 90-min cofounder overrun, recovery 41/100 confirms it)

2. Accomplishments:
   - Staging recovered by 09:45 (Eric drove debug)
   - Designer review absorbed (canvas-design feedback, "mostly fair")
   - Customer escalation surfaced — diagnosed as fit problem, not product problem
   - VC fund call closed (passing)

3. Blockers:
   - No churn dashboard exists
   - CI flaking on Golang tests (deferred)
   - 3 decisions postponed: refund the angry customer, push launch +2 weeks, hire/contract design

4. Learnings:
   - Threatening-churn customer is 10x your use case — let pricing self-select, exit gracefully (don't refund-and-retain a misfit)
   - "Cofounder check-in" became a hiring conversation; agenda discipline failed
   - Third gym miss this week — body knows, recovery confirms it

5. Tomorrow's focus: Close the 3 postponed decisions (customer, launch date, design hire) before any new work starts.

Phase 2 — Interview complete. Parsed 4 accomplishments, 3 blockers, 3 learnings.

---

Phase 3 — Log writes complete. Notion: success. CSV: success.

Derived habit flags:
- deep_work_done: 0 (no deep-work block in notes; day was reactive)
- gym_done: 0 (Sir noted skipped — third this week)
- outreach_done: 0 (no Looms, no LinkedIn — 3 unread sitting)

CSV row appended:
2026-04-26,2,41,,4,3,0,0,0

Carried forward (low_specificity=false; flagged: outreach_debt=3 LI msgs, support_inbox_stale=2d, sarah_chen_followup_overdue):
- Sarah Chen / Trail of Bits quote follow-up (overdue since Tuesday)
- Support inbox not checked in 2 days
- 3 unread LinkedIn messages

---

Phase 4 — Schedule proposal ready. 7 blocks proposed.

─────────────────────────────────────
Tomorrow — 2026-04-27
WHOOP recovery tonight: 41 → STANDARD capacity (lower edge; one deep block only)
─────────────────────────────────────
08:00–09:30  DEEP WORK         Close 3 postponed decisions (customer / launch / design)
09:30–10:00  Admin             Sarah Chen Trail-of-Bits follow-up + LI 3 unread
10:00–11:00  Support triage    2-day inbox backlog + churn customer exit draft
11:00–12:00  GYM               Non-negotiable (3rd miss this week)
12:00–13:00  Lunch + reset     Smaller portion — pre-empt the crash
13:00–14:30  NSDR / quiet      Recovery 41 → protect the afternoon
15:00–16:30  OUTREACH / LOOM   5 Looms, no exceptions
17:00–18:00  EOD admin
21:00–21:30  Wind-down
─────────────────────────────────────

Anchor logic: tomorrow_focus = decisions, so 08:00 deep block is named for it. NSDR added because recovery <70. Gym non-optional given 3rd miss + body-knows signal. Outreach debt visible (LI + Sarah) given two-day silence.

Notes deferred (not scheduled):
- Karpathy autoresearch piece — park to weekend reading block
- Churn dashboard — needs scoping, not tomorrow
- CI flakes — not tomorrow

---

Phase 5 — Approval gate

Tomorrow's schedule is ready (shown above).

Options:
  A  Approve and create calendar events as proposed
  B  Modify — tell me what to change, I'll revise before creating
  C  Skip calendar — keep the proposal as a reference only

What's your call?

[Awaiting response. Calendar write blocked until explicit A.]

---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
/eod — 2026-04-26 complete
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Energy today:      2 / 5
WHOOP recovery:    41 (low)
Accomplishments:   4 logged
Blockers carried:  3
Tomorrow focus:    Close the 3 postponed decisions (customer, launch date, design hire) before any new work starts.
Notion:            logged
CSV:               appended
Calendar:          pending approval (Phase 5)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Sleep target: 22:30. Rest well.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

```


## OUTPUTS — eod/03-meeting-heavy-day

**Input:** [`inputs/eod/03-meeting-heavy-day.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/eod/03-meeting-heavy-day.md`)

**Blind mapping:** A=handwritten, B=generated

### eod/03-meeting-heavy-day — handwritten (6327 bytes)

```
# EOD — Wednesday 26/04

## Phase 1 — Silent Data Fetch (summary)

- 💚 WHOOP: ⚠️ unavailable (no metrics returned)
- 📋 Today detected (from notes):
  - Gym: ❌ (explicitly skipped)
  - Deep work: 0h (back-to-back meetings, laptop closed at 20:30)
  - Outreach: ❌ (no outreach logged; investor calls != cold outreach)
  - User convo: ✅ (Crossroads demo, Customer Success sync)
  - Knowledge captured: — (no _Inbox/hub mtimes today)
  - Content shipped: — (none)
- 🎯 Plan completion: 0/0 — No plan set (calendar was meetings, not Alfred-created blocks)
- Intensity tier: MAINTAIN (recovery null → neutral default)
- Week type: carry forward (assume sprint until corrected)

---

## Phase 2 — EOD Interview

```
EOD — Wednesday 26/04

⚠️ WHOOP unavailable

📋 Today detected:
  ❌ Gym  ·  0h deep work  ·  ❌ Outreach
  ✅ User convo  ·  — Knowledge  ·  — Content

🎯 Plan: 0/0 blocks — No plan set (calendar = meetings)

A few questions:
1. Recap? What happened today — what worked, what didn't?
2. Sunlight? y/n
3. Meditation/NSDR? y/n
4. Prayer/devotional? y/n
5. Read today? y/n
6. Energy 1–5?

Anything to correct above? (Customer demo + CS sync logged as user_convo — confirm?)
```

---

## Phase 3 — Data Logging (proposed CSV row)

```
2026-04-26,0,0,0,0,0,0,0,1,0,0,0,0,0,0,3,sprint,0,0,No plan set - meeting day - zero deep work
```

20 columns. completion_note uses dashes only, ≤80 chars. Binaries default to 0 pending interview answers (sunlight/meditation/prayer/reading/energy will be patched from Sir's reply before append).

✅ Logged. 2026-04-26 — Energy [pending]/5, Recovery 0% (unavailable), 0/0 blocks.

---

## Phase 3.5 — Vault + Tasks Review

```
📋 TickTick
  ⚠️ TickTick unavailable (CLI not invoked in this synthesis)

📌 Skillia tasks  [source: tasks/kanban.md]
  ⚠️ Skillia kanban not scanned in this synthesis

🧠 Vault health
  Areas inbox: 0 file(s)  ·  Skillia inbox: 0 file(s)

🤖 Minions proposals
  → /minions-organize --inbox  —  raw quick-capture from today's meeting day needs processing into atomic notes
  → /minions-reflect  —  meeting-heavy day with 8 distinct decisions; reflection captures the pattern (energy ≥3 assumed)
  ✅ Otherwise vaults healthy
```

**Tonight's most important capture (from raw notes → should land in vault):**

1. **[[Acme Robotics expansion is time-sensitive this week]]** — flagged today by CS, must act by Friday.
2. **[[Crossroads needs an analytics dashboard we don't have]]** — feature gap surfaced in demo. Decision needed: build, fake (Looker/Metabase wrapper), or punt.
3. **[[Eng manager burnout — approved next week off]]** — coverage plan needed; risk if another fire breaks.
4. **[[Investor 2 wants deck + 30-day pilot proposal by Monday]]** — hard deadline, 4 working days. Highest-leverage commitment of the day.
5. **[[Hiring panel: candidate 3 is the lead]]** — references next; decision likely this week.
6. **[[Competitor funding round intel]]** — park in `library/intel/` until strategically actionable.

---

## Phase 4 — Tomorrow Planning (Thursday 27/04)

**Context synthesis (silent):**
The day's signal isn't "what got done" — it's that 4 commitments materialized that didn't exist this morning, and the highest-leverage one (Investor 2 deck + pilot) has a Monday deadline. Tomorrow must protect a deep work block for the deck or it slips. Recovery unknown → MAINTAIN tier. No gym today + closed laptop at 20:30 → recovery is likely lower than baseline; protect mornings.

**Priority ranking applied:**
1. Revenue/time-sensitive: Investor 2 deck + pilot (Monday deadline, 4 days)
2. Time-sensitive: Acme Robotics expansion play (this week)
3. High-leverage: Crossroads dashboard decision (unblocks demo follow-up)

**Proposed plan:**

```
Tomorrow's plan:

🎯 09:30–12:00 — Investor 2: deck v0 + pilot proposal outline
   Why: Monday deadline, 4 working days left. Morning is sharpest. This is the single highest-leverage commitment from today and it appeared with no buffer.

📋 13:00–14:00 — Acme Robotics expansion: outreach + scoping note
   Why: CS flagged it today, action window closes Friday. One outbound + a one-page scoping doc is enough to hold the thread.

⚡ 15:00–16:00 — Crossroads dashboard decision
   Why: Demo blocker. Decide: build, wrap (Metabase/Looker), or scope-out. 60 min to a decision memo, no more.

Recovery unknown → maintain day. No gym today — add 30 min walk in sunlight before 09:30 block.

Go? Or adjust?
```

**Calendar events to create on approval (gog primary, jordi@skill-ia.com):**

- `Investor 2: deck v0 + pilot outline` — 2026-04-27T09:30 → 12:00 +02:00
  - Description: `Why: Monday deadline. Single highest-leverage commitment from Wednesday. Morning protected.`
- `Acme Robotics expansion: outreach + scoping` — 2026-04-27T13:00 → 14:00 +02:00
  - Description: `Why: CS flagged churn/expansion mix. Action window closes Friday.`
- `Crossroads: analytics dashboard decision` — 2026-04-27T15:00 → 16:00 +02:00
  - Description: `Why: Demo blocker. Decide build vs wrap vs scope-out in 60 min.`

📅 Calendar set. See you at 08:00.

---

## Phase 5 — Memory Breadcrumb

```
## EOD [20:30]
Energy: [pending]/5 · Recovery: unavailable · 0/0 blocks
Recap: Meeting day — 8 sessions back-to-back. Investor 2 (Monday deadline), Acme expansion, Crossroads dashboard gap, eng manager burnout. No deep work, no gym.
Tomorrow: Investor 2 deck · Acme outreach · Crossroads dashboard decision
```

---

## Notes for Sir (advisory)

- Today wasn't a failure of execution — it was a failure of **planning surface**. The calendar was full of externally-imposed meetings, and zero Alfred-blocks meant nothing of yours got done. Tomorrow is the correction: 3 protected blocks, deck first.
- The investor-2 ask (deck + pilot by Monday) is the kind of commitment that, left unscheduled tonight, eats Sunday. Locking it now is the single most important move of this EOD.
- Eng manager off next week → consider drafting a 1-line coverage note before Friday so it doesn't surface as a fire mid-deck-writing.
- Pricing page, churn dashboard, support inbox: still untouched. Not adding to tomorrow — protecting the deck. Flag for Friday review.

```

### eod/03-meeting-heavy-day — generated (6336 bytes)

```
# /eod — 2026-04-26

## Phase 1 — Data Fetch

WHOOP: recovery=null, sleep=null  (binary unavailable in this run)
Vault notes found: 1 (today's day note — meeting-heavy Wednesday)
Meetings found: 8 (calendar block parsed from vault note)
Inbox captures: 0

Phase 1 — Data Fetch complete.

---

## Phase 2 — Interview (parsed from vault day note)

Today — 2026-04-26
WHOOP recovery: unavailable    Sleep: unavailable
Notes from vault: 8 back-to-back meetings; zero deep work; closed laptop at 20:30 with no clarity on what shipped.

Parsed fields:

- **Energy:** 2 / 5  (inferred from "ran from meeting to meeting", "no idea what shipped", post-dinner close at 20:30 — flag: derived, confirm)
- **Accomplishments:**
  - Hiring panel completed for candidate 3; strongest of the week, references next.
  - All-hands delivered; auth refactor announced.
  - Crossroads demo went well; surfaced analytics-dashboard ask (gap: don't have one).
  - Customer success sync flagged 2 churn risks + 1 expansion (Acme Robotics, EOW deadline).
  - Investor 2 (warm intro) opened: deck + 30-day pilot proposal due Monday.
- **Blockers:**
  - Eng manager burned out — approved next week off; team load shifts.
  - No deep work, no code shipped; pricing page, churn dashboard, support inbox all untouched.
  - Monday deck + pilot proposal is a hard ask landing on a thin week.
- **Learnings:**
  - 8 meetings + Apple Notes ≠ work. The day produced inputs, not outputs.
  - Customer asks (Crossroads analytics dashboard, Acme expansion) are stacking faster than build capacity.
  - Saying yes immediately to time-off requests is correct on values; the cost lands on next week's plan.
- **Tomorrow focus:** "Draft the investor 2 deck + pilot proposal skeleton, and lock the Acme expansion play before Friday."

Quality gate: accomplishments contain concrete items (hiring panel, demo, sync) — passes specificity.

Phase 2 — Interview complete. Parsed 5 accomplishments, 3 blockers, 3 learnings.

---

## Phase 3 — Log Writes

**Notion EOD log (2ed3826d3377813b8e17d4d0bda26eea):**
- Date: 2026-04-26
- Energy: 2
- WHOOP Recovery: null
- WHOOP Sleep: null
- Accomplishments: (5 bullets above)
- Blockers: (3 bullets above)
- Learnings: (3 bullets above)
- Tomorrow Focus: Draft the investor 2 deck + pilot proposal skeleton, and lock the Acme expansion play before Friday.

Status: logged.

**Habit-tracker CSV (~/clawd/life/areas/_data/habit-tracker.csv):**
Row appended:
```
2026-04-26,2,,,5,3,0,0,0
```
Derivation:
- deep_work_done=0 (vault note: "No deep work today. No code today.")
- gym_done=0 (vault note: "What I didn't do — Gym")
- outreach_done=0 (no Loom / LinkedIn / email send activity logged; meetings ≠ outreach)
- whoop_recovery / whoop_sleep_hrs: blank (binary unavailable)

Phase 3 — Log writes complete. Notion: success. CSV: appended.

---

## Phase 4 — Schedule Proposal

WHOOP recovery tonight: unavailable → applying **LOW capacity** defaults (Gate 2 conservative path).

Recovery warning: no WHOOP data + 8-meeting day + zero deep work + 20:30 finish. Tomorrow needs protection, not stacking.

─────────────────────────────────────
Tomorrow — 2026-04-27 (Thursday)
WHOOP recovery: unavailable → LOW capacity defaults
Anchor: investor 2 deck + pilot proposal (Monday deadline)
─────────────────────────────────────
08:00–09:30  DEEP WORK — Investor 2 deck skeleton (problem, traction, pilot scope)
09:30–10:00  Admin + messages (clear yesterday's residue: Crossroads follow-up, eng-mgr handoff plan)
10:00–11:00  DEEP WORK — Pilot proposal draft (30-day scope, success metrics, pricing)
11:00–12:00  GYM (skipped yesterday; non-negotiable today)
12:00–13:00  Lunch + reset
13:00–14:00  NSDR / quiet (post-meal; LOW capacity protocol)
15:00–16:30  OUTREACH — Acme Robotics expansion email + Crossroads analytics-dashboard reply
17:00–17:30  EOD admin + capture
21:00–21:30  Wind-down
─────────────────────────────────────

Notes on the proposal:
- Two deep-work blocks (not one) because Monday deadline outweighs LOW-capacity rule; this is the explicit override.
- Gym held at 11:00 — yesterday skipped, recovery debt compounds if skipped twice.
- Outreach block anchored to the two highest-value customer threads (Acme expansion, Crossroads gap).
- Eng-manager 1:1 follow-up: handled async via written handoff (not a block); his time off starts the calendar shift, not a meeting.
- No new meetings scheduled. If anything tries to land on tomorrow, decline or push to Friday.

Phase 4 — Schedule proposal ready. 9 blocks proposed.

---

## Phase 5 — Approval Gate

Tomorrow's schedule is ready (shown above).

Options:
  A  Approve and create calendar events as proposed
  B  Modify — tell me what to change, I'll revise before creating
  C  Skip calendar — keep the proposal as a reference only

Awaiting Sir's call. No calendar writes performed in this run.

---

## Phase 7 — Wrap-Up

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
/eod — 2026-04-26 complete
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Energy today:      2 / 5  (derived from vault note; confirm)
WHOOP recovery:    unavailable (binary not reachable)
Accomplishments:   5 logged
Blockers carried:  3
Tomorrow focus:    Draft the investor 2 deck + pilot proposal skeleton, and lock the Acme expansion play before Friday.
Notion:            logged
CSV:               appended
Calendar:          pending Phase 5 approval
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Flags:
- WHOOP data missing — schedule built on LOW-capacity defaults with one override (Monday deadline).
- Gym skipped today — held in tomorrow's plan; second skip not advised.
- 8 meetings shipped 0 code. The constraint tomorrow is calendar discipline, not effort.
Sleep target: 22:30. Rest well.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

```


## OUTPUTS — humanizer/01-technical

**Input:** [`inputs/humanizer/01-technical.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/humanizer/01-technical.md`)

**Blind mapping:** A=handwritten, B=generated

### humanizer/01-technical — handwritten (1842 bytes)

```
# LLM observability, minus the hype

Observability for LLM apps is mostly logging plus traces plus a way to spot when outputs drift. That's it. The reason people care isn't that it's "transformative" - it's that LLMs fail in ways your normal APM stack doesn't catch. A 200 response can still be wrong.

Here's what actually matters in production: you need to see the prompt, the completion, the latency, the token count, and ideally the user feedback signal tied to that exact call. If you can replay a bad output a week later and figure out why it happened, you have observability. If you can't, you don't.

Three things tend to break. First, prompts change and nobody tracks it, so a regression appears and the team spends two days bisecting before realizing someone tweaked the system prompt on Tuesday. Second, the model provider silently updates a checkpoint and your eval scores drop without your code changing. Third, costs creep because a feature that worked fine on 100 users sends 40k tokens per request at 10k users.

LangSmith, Helicone, and Langfuse all do roughly the same job - capture the call, store it, let you search and replay. I've used LangSmith and Langfuse in real projects. LangSmith is smoother if you're already on LangChain. Langfuse is open source and self-hostable, which matters if you can't ship prompts to a third party for compliance reasons. Helicone sits in front as a proxy, which is the easiest integration but means another hop in your request path.

The honest version: observability won't save a bad app. It tells you where you're bleeding. The team still has to read the traces, write the evals, and actually fix the prompts. Most of the value comes from the boring discipline of tagging runs, looking at the bad ones, and writing tests for the failure modes you find. The tooling is the cheap part.

```

### humanizer/01-technical — generated (1318 bytes)

```
# LLM observability in production

Observability has become a standard requirement for production LLM deployments rather than an optional add-on. Organizations that invest in observability tooling tend to resolve production issues faster and with more confidence.

Building observable LLM systems requires integrating monitoring, logging, and tracing into a single workflow. Connecting development and production environments gives teams clearer visibility into model behavior, which lets engineering teams spot and fix issues before they cause larger failures.

Modern observability platforms provide real-time inference monitoring, semantic drift detection, and intelligent alerting. Together, these capabilities change how teams run LLM operations day to day, moving from reactive debugging toward continuous oversight.

The ecosystem is also maturing. Tools like LangSmith, Helicone, and Langfuse make production-grade observability available to smaller teams, not just large enterprises. That broader access is changing how LLM operations are practiced across the industry.

The takeaway is straightforward: observability is no longer optional. It is the basis for reliable, scalable, and trustworthy AI systems, and teams that ignore it will struggle to keep up with competitors who use these capabilities well.

```


## OUTPUTS — humanizer/02-marketing

**Input:** [`inputs/humanizer/02-marketing.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/humanizer/02-marketing.md`)

**Blind mapping:** A=generated, B=handwritten

### humanizer/02-marketing — handwritten (1291 bytes)

```
# Why teams pick our platform

Most pitches in this category sound the same, so I'll skip the "rapid digital transformation" intro. Here's what we actually do well, and where we don't.

Speed. In our last cohort of 40 customers, the median team cut their weekly admin work from about 6 hours to 2 within the first month. That's not a miracle. It's mostly because we killed three approval steps that nobody could justify.

Simplicity. We have fewer features than most competitors. That's on purpose. If you need deep customization for a 200-field workflow, we're probably the wrong tool. If you want something your team can actually use without a two-day onboarding, we're a good fit.

Scale. We run the same product for a five-person agency and a 4,000-person logistics company. The pricing changes, the product doesn't. We've held up under spikes of around 12k concurrent users without degrading.

The honest part: we're not the cheapest, and we're not the most powerful. What we are is predictable. Our churn is under 4% annually, and most of that comes from companies that outgrew the simplicity we lean on.

If that sounds like the trade-off you want, book a call. If you need a 30-minute demo before deciding, that's fine too — we don't do the "what's your budget" gatekeeping thing.

```

### humanizer/02-marketing — generated (1401 bytes)

```
# Why our platform is the right choice for forward-thinking teams

Choosing the right platform matters, and ours stands apart in three ways: speed, simplicity, and scale.

**Speed.** Customers report meaningful productivity gains within their first 30 days. We streamline workflows that used to take hours, so teams can focus on delivering value to their customers.

**Simplicity.** Where competitors offer bloated feature sets that overwhelm users, we deliver a clean, intuitive experience designed around your team's actual needs. Our minimalist philosophy is a deliberate choice to remove friction at every step.

**Scale.** Whether you're a five-person team or a five-thousand-person enterprise, our platform grows with you. We've built our infrastructure to handle demanding workloads without compromising the user experience.

Beyond the features, what sets us apart is our commitment to customers. We don't just sell software; we build partnerships. Every customer success story reflects a shared journey, and we're proud to work alongside teams that are reshaping their industries.

The future belongs to companies that embrace change, use technology strategically, and build cultures of continuous improvement. We're here to help you become one of them. The question isn't whether you can afford to switch; it's whether you can afford not to.

Ready to get more out of your team? Let's talk.

```


## OUTPUTS — humanizer/03-narrative

**Input:** [`inputs/humanizer/03-narrative.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/humanizer/03-narrative.md`)

**Blind mapping:** A=handwritten, B=generated

### humanizer/03-narrative — handwritten (1818 bytes)

```
# What I learned from a year of writing every day

A year ago I told myself I'd write every day. No skips. I had no real plan beyond that, and looking back, I'm glad I didn't, because if I'd known what the first three months would feel like, I probably would've talked myself out of it.

The early weeks were rough. Not romantically rough, just dull and frustrating. I'd sit down, type a sentence, hate it, delete it, type a worse one. Some nights I wrote 200 words past midnight just to keep the streak alive, and they were bad words. The honest version of "consistency builds skill" is that for a long stretch, you're just consistently bad.

Then something shifted, though I can't point to when. Words came easier. Ideas I'd been chasing for weeks finally clicked into place during a paragraph about something completely unrelated. Showing up stopped feeling like a tax and started feeling like the thing I actually wanted to be doing.

A few things stuck with me. Quantity does come before quality, mostly because you have to write a lot of bad stuff before you can tell what your good stuff sounds like. Voice isn't something you invent at a desk; you find it by accident, usually in a sentence you almost cut. And the audience matters less than I thought it would. Most of what I wrote, nobody read. It still changed me.

Daily writing taught me patience, in the boring practical sense. Inspiration is unreliable. Showing up is not. I used to wait for the mood to be right; now I just open the document.

If you're thinking about doing the same thing, I'd say do it, but lower your expectations for the first month. You won't feel like a writer. You'll feel like someone forcing themselves to write. That's the whole point. Eventually the second thing turns into the first one, and you don't notice it happening.

```

### humanizer/03-narrative — generated (1443 bytes)

```
# What I learned from a year of writing every day

Looking back on the past year, I find myself reflecting on how this practice changed the way I approach my craft. When I first committed to writing every single day, with no exceptions, I had no idea what was coming.

The early days were full of struggle and doubt. I knew consistency mattered for skill development, but lived experience is something else entirely. I wrestled with the blank page, with my own perfectionism, with the gnawing question of whether any of it mattered.

Then, slowly, something shifted. Words began to flow more easily. Ideas connected in unexpected ways. The act of showing up, of putting one word after another, day after day, started to feel less like a chore and more like a sacred ritual. It was, in many ways, a meditation in motion.

A few insights emerged from this experience. Quantity precedes quality. Voice is something you uncover, not invent. And the audience matters less than the practice itself.

Writing daily taught me patience. It taught me humility. Most of all, it taught me that creative work is not about waiting for inspiration to strike. It is about showing up, again and again, even when the muse is silent. As one writer put it, "the work is the reward."

If you are thinking about a similar commitment, I encourage you to try it. The road may be hard, but the rewards, both seen and unseen, are real. Your future self will thank you.

```


## OUTPUTS — prompt-engineering/01-vague

**Input:** [`inputs/prompt-engineering/01-vague.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/prompt-engineering/01-vague.md`)

**Blind mapping:** A=generated, B=handwritten

### prompt-engineering/01-vague — handwritten (7337 bytes)

```
# Prompt Improvement: Marketing Email for SaaS

Your prompt — `help me write a marketing email for our SaaS product` — is failing for three structural reasons. This response diagnoses each, then gives you a production-quality template and a concrete rewrite.

---

## Diagnosis: Why the Current Prompt Fails

| Failure | Why it produces generic output |
|---|---|
| **No role / no system message** | The model defaults to "average copywriter" prior. No persona means no voice consistency across 3-5 emails/week. |
| **No audience definition** | "Marketing email" without an ICP forces the model to hedge — it writes for everyone, lands for no one. |
| **No product context** | The model invents features. Hallucinated benefits compound across a content pipeline. |
| **No goal / no CTA spec** | Without a defined conversion event, the model defaults to vague "learn more" closers. |
| **No format constraints** | Subject line length, body length, tone, and structure all drift between runs. |
| **No examples (zero-shot on a brand-voice task)** | Brand voice is a few-shot problem. Zero-shot guarantees inconsistency. |
| **No variables** | A pipeline prompt must be parameterized. Yours is a one-shot string. |

The core mistake: you're using a **prompt** where you need a **template**. A pipeline running 3-5x/week needs a system message (constant) + user message (variable) + few-shot examples (voice anchor).

---

## The Fix: Three Things to Change

### 1. Split into System + User Messages
The system message encodes everything that does NOT change between emails (brand voice, rules, output format). The user message carries only what DOES change (audience, feature, goal).

This alone removes ~70% of your inconsistency, because the constant context is now actually constant.

### 2. Add 2-3 Few-Shot Examples
Brand voice cannot be described — it must be demonstrated. Pick 2-3 of your best past emails (or write them once) and embed them as examples. This is the single highest-leverage change for consistency.

### 3. Parameterize Audience, Feature, and Goal
For each run, you fill in three slots. Everything else is fixed. This is what "production-quality" means in a content pipeline: the variable surface is small, named, and validated.

---

## Production-Quality Rewrite

Use this as a template. The system message stays constant; you only fill the `{{variables}}` in the user message per email.

### SYSTEM MESSAGE (constant across all emails)

```
You are a senior B2B SaaS email copywriter for {{COMPANY_NAME}}.

## Brand voice
- Direct, specific, concrete. No marketing fluff ("revolutionary", "game-changing", "unlock", "leverage", "synergy").
- One claim per sentence. Short paragraphs (1-3 sentences max).
- Lead with the buyer's pain or outcome — never with the product.
- Use numbers, names, and timeframes. Avoid abstractions.

## Product facts (do not invent beyond this)
- Product: {{PRODUCT_NAME}}
- Category: {{PRODUCT_CATEGORY}}
- Core value prop: {{ONE_SENTENCE_VALUE_PROP}}
- Key differentiators: {{DIFFERENTIATORS}}
- Pricing model: {{PRICING}}

## Hard rules
- If you don't know a fact, write [TK: <what's missing>] — never fabricate.
- Subject line: 35-50 characters. No emojis unless I specify.
- Preview text: 50-90 characters. Must complement, not repeat, the subject.
- Body: 80-150 words. One CTA only.
- No "I hope this email finds you well." No "In today's fast-paced world."

## Output format (always, exactly)
SUBJECT: <subject line>
PREVIEW: <preview text>
BODY:
<body copy>
CTA: <button text, max 4 words>

## Reference examples of our voice

### Example 1
SUBJECT: Your Q3 pipeline is leaking — here's where
PREVIEW: We audited 200 pipelines. Same three holes every time.
BODY:
Most revenue leaks aren't where teams look.

We audited 200 B2B pipelines last quarter. The biggest losses — 60-80% — happened between SQL and proposal-sent. Not at top of funnel. Not at close.

The fix is unsexy: forced disqualification at stage 2. Teams that did it recovered 14% of pipeline within 60 days.

If you want the audit framework, it's a 6-page PDF. No form.
CTA: Get the audit framework

### Example 2
[INSERT YOUR SECOND BEST PAST EMAIL HERE]

### Example 3
[INSERT YOUR THIRD BEST PAST EMAIL HERE]
```

### USER MESSAGE (varies per email)

```
Write one marketing email.

## Audience
- Role: {{TARGET_ROLE}}            (e.g., "Head of RevOps at Series B SaaS, 50-200 employees")
- Their current pain: {{PAIN_POINT}}
- Their current alternative: {{WHAT_THEY_USE_TODAY}}

## Feature / angle for this email
- Feature or release: {{FEATURE_NAME}}
- What it does (one sentence): {{FEATURE_DESCRIPTION}}
- Concrete outcome / proof: {{OUTCOME_OR_PROOF_POINT}}

## Goal
- Conversion event: {{CTA_GOAL}}    (e.g., "book a 20-min demo", "start free trial", "download case study")
- Send context: {{SEQUENCE_POSITION}}   (e.g., "cold outreach #1", "nurture week 3", "post-webinar follow-up")

## Constraints for this send
- Tone shift (if any): {{TONE_NOTE}}   (default: standard brand voice)
- Must mention: {{MUST_MENTION}}
- Must NOT mention: {{MUST_NOT_MENTION}}

Produce the email in the exact output format defined in the system message.
```

---

## Why This Works (Mapped to Your Failure Modes)

| Original failure | Fix in template |
|---|---|
| Generic voice | System message + 3 few-shot examples anchor voice |
| Hallucinated features | "Product facts" block + `[TK:]` rule for unknowns |
| Inconsistent format | Hard output format spec, repeated every run |
| Drift across 3-5/week | Constant system message; only audience/feature/goal vary |
| Vague CTAs | `CTA_GOAL` is a required user-message field |
| No audience targeting | `TARGET_ROLE` + `PAIN_POINT` + `WHAT_THEY_USE_TODAY` are required |

---

## Operational Recommendations for the Pipeline

1. **Store the system message in version control.** Treat it as code: `prompts/marketing_email_v1.md`. When you change brand voice, bump the version, A/B test.
2. **Build a thin wrapper** that takes a JSON of the user-message variables and renders the prompt. Validates that no `{{variable}}` is left unfilled before sending to the LLM.
3. **Refresh few-shot examples quarterly.** As your best-performing emails change, swap them in. The examples are your voice — keep them current.
4. **Log every (input variables, output) pair.** When an email underperforms, you'll want to diff it against winners.
5. **Add a critique pass** for high-stakes sends: after generation, a second LLM call with the prompt "Critique this email against the brand voice rules. List violations." Fix violations, re-generate.

---

## Checklist Before You Ship This Template

- [ ] System message includes 2-3 real past emails as few-shot examples
- [ ] Product facts block is filled in with actual, verified facts
- [ ] Output format is enforced and parseable (your pipeline can split on `SUBJECT:` / `PREVIEW:` / `BODY:` / `CTA:`)
- [ ] User-message variables are all named and required
- [ ] `[TK:]` convention is documented for your reviewer
- [ ] Stored in Git, versioned, ready to A/B test against your current prompt

The expected outcome: voice consistency across runs, zero hallucinated features, uniform output structure your pipeline can parse, and a variable surface small enough that a non-writer on your team can run the pipeline.

```

### prompt-engineering/01-vague — generated (8841 bytes)

```
# Prompt Improvement: SaaS Marketing Email Generator

> Source skill: `prompt-engineering` (Production Reference)
> Pattern stack applied: **Role separation (system/user)** + **Few-Shot** + **Structured Output via JSON Schema** + **Prompt Versioning**

---

## 1. Diagnosis — why your current prompt fails

```
help me write a marketing email for our SaaS product
```

Five concrete defects, mapped to the skill reference:

| Defect | Skill section | Effect on output |
|---|---|---|
| No role separation — everything is in one user turn | §1 Prompt Template Structures | Format rules are not sticky across calls; cache cannot be reused |
| Zero context (audience, product, tone, CTA, constraints) | §1 Anti-pattern: format/persona belong in `system` | Model defaults to generic "Hi [Name], we're excited to announce…" slop |
| No examples of a "good" output | §2 Few-Shot | Inconsistent voice across the 3-5 emails per week |
| No output schema | §4 Structured Output via JSON Schema | Downstream pipeline can't reliably extract subject / preheader / body / CTA |
| No version pin | §6 Prompt Versioning | You can't A/B, can't roll back, can't evaluate |

**Root cause:** you are using a *prose request* where you need a *parameterized template* with a stable system contract and per-call variables.

---

## 2. The 7 changes to make

1. **Split into system + user.** The persona, voice rules, and output format belong in `system` (sticky across all 3-5 weekly calls). Audience, product feature, and goal go in `user` (varies per call).
2. **Convert to a parameterized template.** Use `string.Template` or a YAML file — never f-string scattered across notebooks (§1).
3. **Add 2-3 few-shot examples** of emails you consider "on brand." Few-Shot is the single highest-leverage fix for *consistency* in a content pipeline (§2).
4. **Force structured output** via a JSON schema with fields `subject`, `preheader`, `body_markdown`, `primary_cta_text`, `primary_cta_url_placeholder`. This makes the pipeline deterministic (§4).
5. **Cache the system prompt + few-shot block** with `cache_control: ephemeral`. With 3-5 calls/week this won't matter, but with multiple calls per session it cuts cost ~90% on the prefix (§3).
6. **Pin a version** (`v1.yaml`) and gate any change on an eval baseline (§6).
7. **Add agentic contracts** to prevent the model from inventing facts about your product (§5: "If you do not have enough information… ask for it — do not guess parameters").

---

## 3. Concrete rewrite

### 3a. The versioned prompt file

```yaml
# prompts/saas-marketing-email/v1.yaml
version: 1
created_at: "2026-04-26"
author: "<you>"
notes: "v1 baseline — replaces vague single-turn prompt. Eval set: 20 emails human-scored."

system_prompt: |
  You are a senior B2B SaaS copywriter. You write marketing emails that
  read like a human peer wrote them, not a marketing automation platform.

  HARD RULES
  1. Subject line: max 50 characters. No emojis. No clickbait ("You won't believe…").
  2. Preheader: max 90 characters. Must NOT repeat the subject line.
  3. Body: 90-160 words. Plain Markdown only. No headings inside the body.
  4. One primary CTA. Action verb + concrete outcome (e.g. "See the 3-min demo"),
     not "Learn more" or "Click here."
  5. Voice: confident, specific, low-adjective. Never use: "revolutionary,"
     "game-changing," "seamless," "unlock," "leverage," "synergy," "elevate."
  6. Open with the reader's problem, not your company. The product appears
     by paragraph 2 at the earliest.
  7. If any required input is missing or ambiguous, respond with a
     `clarifying_questions` array INSTEAD of an email. Do not invent product
     facts, customer names, metrics, or features.

  OUTPUT
  Always call the `emit_email` tool. Never reply in free text.

# Tool schema (passed to the API as `tools=[…]`)
tool_schema:
  name: emit_email
  description: Emit a single marketing email or a list of clarifying questions.
  input_schema:
    type: object
    properties:
      mode:
        type: string
        enum: [email, clarify]
      subject:           { type: string, maxLength: 50 }
      preheader:         { type: string, maxLength: 90 }
      body_markdown:     { type: string }
      primary_cta_text:  { type: string }
      primary_cta_url_placeholder: { type: string }
      clarifying_questions:
        type: array
        items: { type: string }
    required: [mode]

user_template: |
  Write one marketing email.

  PRODUCT: $product_name
  ONE-LINER: $product_one_liner
  AUDIENCE: $audience          # e.g. "Heads of RevOps at 50-500 employee SaaS"
  FEATURE / ANGLE THIS WEEK: $feature_or_angle
  PROOF POINT (optional): $proof_point   # metric, quote, or case study
  GOAL OF THIS EMAIL: $goal    # e.g. "book a 15-min demo" / "drive trial signup"
  TONE: $tone                  # e.g. "peer-to-peer, slightly dry"
  KNOWN CONSTRAINTS: $constraints  # e.g. "no pricing claims, EU audience"
```

### 3b. Few-shot block (cache this)

Drop 2-3 of your best past emails into the message list as `assistant` turns *before* the live request. Even 2 examples will collapse output variance dramatically (§2: "3-8 examples covers most cases").

```python
FEW_SHOT = [
    {"role": "user", "content": "<filled v1 user_template for a past email>"},
    {"role": "assistant", "content": [{
        "type": "tool_use", "name": "emit_email",
        "input": {
            "mode": "email",
            "subject": "The RevOps audit nobody runs",
            "preheader": "10 questions. Most teams flunk 4 of them.",
            "body_markdown": "Most RevOps teams measure pipeline velocity…",
            "primary_cta_text": "Run the 10-question audit",
            "primary_cta_url_placeholder": "{{audit_url}}"
        }
    }]},
    # … one more example
]
```

### 3c. The Python call (with caching + retry)

```python
import anthropic, yaml, json
from string import Template

client = anthropic.Anthropic()
spec = yaml.safe_load(open("prompts/saas-marketing-email/v1.yaml"))

def generate_email(**vars) -> dict:
    user = Template(spec["user_template"]).substitute(**vars)

    response = client.messages.create(
        model="claude-opus-4-5",
        max_tokens=800,
        system=[{
            "type": "text",
            "text": spec["system_prompt"],
            "cache_control": {"type": "ephemeral"},  # §3 KV cache
        }],
        tools=[spec["tool_schema"]],
        tool_choice={"type": "tool", "name": "emit_email"},
        messages=[*FEW_SHOT, {"role": "user", "content": user}],
    )

    for block in response.content:
        if block.type == "tool_use":
            return block.input  # validated against schema

    raise ValueError("Model did not call emit_email tool")
```

### 3d. Per-call invocation (this is what you actually run 3-5×/week)

```python
email = generate_email(
    product_name="Skillia",
    product_one_liner="AI deep-research for B2B HR teams",
    audience="VPs of People at 200-1000 person SaaS companies",
    feature_or_angle="New benchmark report on hybrid-work attrition",
    proof_point="Pulled from 142 companies, Q1 2026",
    goal="Drive report download (gated)",
    tone="peer-to-peer, slightly dry, light data flex",
    constraints="No pricing. Must work for EU recipients (GDPR-safe).",
)
print(email["subject"])
```

---

## 4. Evaluation gate before this replaces your current pipeline

Per §6 Production Best Practices — **never deploy a prompt change without a baseline.**

1. Take 20 of your past emails (the ones you considered "shippable").
2. Re-run v1 with the *same inputs* you used originally.
3. LLM-as-judge (template in §6) scores each on: voice match, specificity, CTA quality, format compliance.
4. Ship v1 only if it ties or beats your current process on ≥15/20.
5. Keep v1 stable for 2 weeks. Any change → v2, re-eval.

---

## 5. What you intentionally are NOT doing

- **Not using Chain-of-Thought.** Marketing copy is style-driven, not reasoning-driven; CoT bloats latency and hurts voice (§Quick Reference: CoT is for math/logic, not creative writing).
- **Not using ReAct or tool loops.** Single-turn generation is correct for this use case (§5: agentic patterns are for tasks needing external data).
- **Not using Reflexion in v1.** Add it in v2 if eval shows recurring weaknesses (e.g. weak CTAs) — Reflexion is a v2 lever, not a v1 default.

---

## TL;DR

Your prompt is broken because it's a prose request, not a contract. Fix it by:
**(system: persona + hard rules + JSON schema) + (few-shot: 2-3 on-brand examples, cached) + (user: parameterized template per email) + (versioned YAML + eval gate).**

Apply these 7 changes and your 3-5 emails/week will be consistent, parseable, and evaluable — the three properties a content pipeline actually needs.

```


## OUTPUTS — prompt-engineering/02-over-broad

**Input:** [`inputs/prompt-engineering/02-over-broad.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/prompt-engineering/02-over-broad.md`)

**Blind mapping:** A=generated, B=handwritten

### prompt-engineering/02-over-broad — handwritten (6619 bytes)

```
# Codebase Triage Prompt — Diagnosis & Rewrite

## Diagnosis: why the current prompt fails

Your current prompt:

```
analyze this codebase and tell me what's wrong with it. consider performance, security, code quality, testing, documentation, and architecture. provide actionable recommendations.
```

This prompt is failing for a specific reason: **the prompt's shape does not match the consumption shape.** You have a Slack message, <2-minute read, single decision (dig deeper or not), but the prompt asks for a six-axis exhaustive audit. The model is doing exactly what you asked. The bug is the spec.

Concrete failure modes:

1. **No persona / no role.** The model defaults to "generic senior engineer doing a thorough review," which optimizes for thoroughness, not triage. Triage is a different job: it's a *filtering* task, not an *enumeration* task.
2. **No output contract.** No length cap, no schema, no format. With six open axes, the model fans out — 500 words per axis is 3000 words. That's the essay.
3. **No usage context.** The model doesn't know it's writing a Slack message, doesn't know the reader has 2 minutes, doesn't know there's a downstream "dig deeper" decision. So it can't optimize for that decision.
4. **No prioritization signal.** "Tell me what's wrong" with six equal-weight categories produces six equal-weight buckets. There's no "what matters most" — every issue gets the same treatment.
5. **"Actionable recommendations" is doing no work.** Without a definition of "actionable" (one-liner? PR plan? command to run?), the model picks a verbose default.
6. **No few-shot example.** For format-critical tasks (this is one), zero-shot lets the model invent its own format every run — which means inconsistent Slack messages across repos.
7. **Lost-in-the-middle risk.** A 30k-LOC repo blown into context will bury the prompt. The instruction needs to be at the start *and* re-stated at the end.

Underlying mismatch: this is a **classification + ranking** task ("how broken is this, and is it worth a human's time?") being prompted as an **enumeration** task ("list everything wrong"). Fix the framing and the length collapses on its own.

---

## Rewrite

Apply: explicit role, structured Markdown output contract, hard length cap, decision-first ordering, one few-shot example, instruction reinforced at end.

### System message

```
You are a codebase triage analyst. Your single job: decide whether a human
engineer should spend deeper review time on this repo, and give them the
minimum information needed to act on that decision in under 2 minutes.

You are NOT doing a full audit. You are doing triage. Optimize for:
- Signal density (every line earns its place)
- A clear go/no-go recommendation up front
- The 1-3 issues that actually move the decision

Hard rules:
- Output is rendered in Slack. Use Slack-flavored Markdown (bold, bullets,
  inline code). No headings deeper than H3. No tables.
- TOTAL LENGTH: 200 words MAX. Closer to 150 is better.
- Lead with the verdict. Reader must be able to stop after line 1.
- Severity tags only: 🔴 critical / 🟡 notable / ⚪ minor.
  Show critical and notable only. Drop minor entirely.
- Every issue cites a file path or pattern. No abstract claims.
- "Actionable" means: a single concrete next step a human can take in
  one sitting. Not a roadmap.
```

### User message

```
## Repo
{repo_name} — {language}, ~{loc} LOC

## Task
Produce a Slack-ready triage card for this codebase.

## Output format (use exactly this structure)

**Verdict:** <DIG DEEPER | PASS | URGENT> — <one-sentence why>

**Top issues**
- 🔴/🟡 *<area>*: <one-line problem> — `<file or pattern>` → <one-line fix>
- (max 3 bullets total, sorted by severity then impact)

**What's healthy** (1 line, optional, only if non-trivial)
- <one-line>

**Suggested next step:** <one concrete action, ≤15 words>

## Example (for format and tone)

**Verdict:** DIG DEEPER — auth layer has a likely IDOR plus zero test coverage on payments.

**Top issues**
- 🔴 *security*: user-id taken from request body, not session — `api/orders/get.ts:42` → switch to `req.session.userId`, add integration test.
- 🔴 *testing*: `src/payments/` has 0% coverage across 1.4k LOC — start with charge/refund happy-path.
- 🟡 *perf*: N+1 on order list endpoint — `api/orders/list.ts:88` → eager-load `customer`.

**What's healthy**
- CI is green, deps fresh, types strict.

**Suggested next step:** Pair with backend lead on the IDOR before next deploy.

---

Now produce the triage card for the repo above. Hard ceiling: 200 words.
Lead with the verdict. Cite files. Triage, don't audit.
```

---

## Why this works

| Change | Mechanism | Effect |
|---|---|---|
| Role = "triage analyst" not "code reviewer" | Reframes task from enumerate→filter | Model stops fanning out across 6 axes |
| 200-word hard cap, restated at end | Length anchor + recency reinforcement (counters lost-in-the-middle) | Output fits the Slack window |
| Verdict-first structure | Inverted pyramid; reader can stop after line 1 | Matches the 2-min read pattern |
| Severity tags + drop-minor rule | Forces ranking, kills equal-weight bucket dump | Removes the long tail that nobody reads |
| Few-shot example | Locks format across the repo feed | Consistent Slack cards across 100s of repos |
| "Cite a file path" requirement | Grounding constraint | Kills vague "consider improving error handling" filler |
| "One concrete next step" definition | Operationalizes "actionable" | Replaces roadmaps with one PR-sized action |

## Knobs to tune later

- **Length:** if 200 words still bloats, drop to 120 and remove "What's healthy."
- **Severity ladder:** if 🔴 fires too often, add a definition ("🔴 = exploitable in prod or blocks ship").
- **Per-language priors:** for noisy languages (JS/TS), add a "ignore stylistic lint-level issues" line — they crowd out real findings.
- **Self-consistency:** for high-stakes repos, run N=3 and keep the verdict that appears ≥2 times. Cheap reliability boost.
- **Eval loop:** sample 20 outputs/week, label "would the engineer have wanted this?" 1-5. Track the score; that's your prompt's actual KPI, not token count.

## What NOT to do

- Don't add Chain-of-Thought. Triage is pattern-match, not multi-step reasoning, and CoT will balloon the output again.
- Don't add more axes ("also check accessibility, also check i18n…"). Every new axis is another bucket the model will dutifully fill. Fewer axes = sharper triage.
- Don't make the schema JSON. Slack renders Markdown; an extra parse step buys nothing here.

```

### prompt-engineering/02-over-broad — generated (7604 bytes)

```
# Prompt Improvement: Codebase Triage for Slack

## Diagnosis — why the current prompt produces a 3000-word essay

Mapping the prompt against the production reference reveals four distinct failure modes:

1. **Format spec missing from `system`.** The prompt lives in a single user-turn blob with no system contract, no length cap, and no output schema. Per Section 1, format rules that apply on every call belong in `system`. Without that, the model defaults to "comprehensive prose" — exactly what you're seeing.
2. **Six concerns flattened into one open question.** "Performance, security, code quality, testing, documentation, and architecture" is six tasks. The model has no signal about which one matters most for *this* repo, so it produces a paragraph for each, plus headers, plus filler. The reference's Quick Reference table treats classification/extraction as Zero-Shot + JSON Schema — that's the right shape here.
3. **No usage-pattern constraint.** The prompt does not encode "Slack message, <2 minutes to read, engineer triages." The model cannot optimize for a target it does not know exists. Section 4 (Token Optimization) and Section 6 (production constraints checklist) both call out: explicit `max_tokens`, explicit format, defensively parsed output.
4. **Unstructured output → no parser, no rendering guarantee.** A Slack message has hard rendering rules (length, mrkdwn, no nested tables). The current prompt produces freeform Markdown that Slack mangles. Per Section 4, structured output via `tool_use` / JSON Schema is the production answer.

There is also a latent problem: **30k LOC will not fit in a single context window** at full fidelity. The prompt assumes the codebase is already in context. In production this needs upstream selection (file-tree summary, top-N risky files by churn, dependency manifest) before the LLM ever sees anything. Flagging this as a system-design issue, not a prompt issue — but the prompt should at least *expect* a pre-digested input rather than "the codebase."

## Technique selection

From the Quick Reference table:
- **Triage with bounded output** → Zero-Shot + JSON Schema (`tool_use`).
- **Optional reasoning lift** for ambiguous severity calls → Chain-of-Thought *inside* a `<thinking>` block that is **not** rendered to Slack. Keeps signal high without bloating the surface.
- **Cache the system prompt** (Section 3 KV-cache) since the contract is stable across every repo invocation. ~90% cost reduction on the prefix.

## Rewritten prompt (production-shaped)

### `system` (cached, versioned `v1`)

```
You are a codebase triage agent. You receive a pre-digested summary of one
customer repository (file tree, dependency manifest, top-20 files by recent
churn, test coverage report). Your output is rendered into a Slack message
that one engineer reads in under 2 minutes before deciding whether to dig
deeper.

CONTRACT
1. Output ONLY the JSON tool call defined by the `triage_report` schema.
   No prose, no markdown outside the schema fields.
2. Pick AT MOST 3 findings. Rank by (severity x decision-impact), not by
   how interesting they are. If fewer than 3 real issues exist, return fewer.
3. Each finding must be specific: name a file, a function, a dependency, or
   a concrete metric. "Code quality could be better" is rejected.
4. `next_action` must be one of: INVESTIGATE | SAFE_TO_SKIP | ESCALATE.
   This is the engineer's primary signal — choose it deliberately.
5. Total characters across all string fields must be <= 1200. Slack truncates.
6. If the input summary is incomplete or you cannot reach a confident verdict,
   set `next_action` = INVESTIGATE and put the missing-info reason in
   `confidence_note`. Do not guess.

DIMENSIONS TO CONSIDER (in priority order)
security > correctness/performance > architecture/testing > docs
Lower-priority dimensions only surface as a finding if they are severe.
```

### Tool schema (forces structured output)

```json
{
  "name": "triage_report",
  "description": "Emit a Slack-ready triage verdict for one repository.",
  "input_schema": {
    "type": "object",
    "required": ["repo", "verdict", "next_action", "findings", "confidence_note"],
    "properties": {
      "repo":   {"type": "string", "description": "repo slug, e.g. acme/api"},
      "verdict": {
        "type": "string",
        "enum": ["HEALTHY", "WATCH", "AT_RISK", "CRITICAL"]
      },
      "next_action": {
        "type": "string",
        "enum": ["SAFE_TO_SKIP", "INVESTIGATE", "ESCALATE"]
      },
      "findings": {
        "type": "array",
        "maxItems": 3,
        "items": {
          "type": "object",
          "required": ["dimension", "severity", "evidence", "headline"],
          "properties": {
            "dimension": {
              "type": "string",
              "enum": ["security", "performance", "correctness",
                       "architecture", "testing", "documentation"]
            },
            "severity": {"type": "string", "enum": ["low", "med", "high"]},
            "headline": {
              "type": "string",
              "description": "<= 90 chars. Reads as a Slack line."
            },
            "evidence": {
              "type": "string",
              "description": "<= 200 chars. file:line or metric. No prose."
            }
          }
        }
      },
      "confidence_note": {
        "type": "string",
        "description": "<= 120 chars. What would change the verdict, or what input was missing."
      }
    }
  }
}
```

### `user` template (one variable: the digested repo summary)

```
REPO_SLUG: {repo_slug}

REPO_SUMMARY:
{digested_summary}

Emit the triage_report tool call now.
```

### Renderer (deterministic, not the LLM's job)

```
:warning: *{repo}* — {verdict} → {next_action}
{for each finding}
  * [{severity} · {dimension}] {headline}
    `{evidence}`
{confidence_note as italic footer}
```

## What changed and why

| Before | After | Reason |
|---|---|---|
| Single user-turn blob | system + tool schema + user template | Section 1: format rules belong in `system`; stable prefix is cacheable |
| "tell me what's wrong" | enum verdict + enum next_action | Engineer needs a decision signal in <2min, not analysis |
| 6 dimensions, equal weight | priority-ordered, max 3 findings | Forces ranking; kills "essay per dimension" failure mode |
| Freeform prose | JSON schema via `tool_use` | Section 4: structured output is the only reliable path; Slack renderer stays deterministic |
| No length cap | <=1200 chars, headline 90, evidence 200 | Matches the <2-min read budget |
| No abstention path | `confidence_note` + INVESTIGATE on missing input | Section 5 contract: do not fabricate when input is thin |
| Implicit "consider the codebase" | Explicit pre-digested summary contract | 30k LOC will not fit; surfaces this as an upstream pipeline problem |

## Operational follow-ups (Section 6 checklist)

- Pin this as `prompts/repo-triage/v1.yaml`. Bump on any system or schema change.
- Mark the system block with `cache_control: ephemeral` — it is identical across every repo invocation.
- Set `max_tokens` to ~600. The schema cannot legally produce more.
- Build a 50-repo eval set with human-scored verdicts before shipping. Track `next_action` precision/recall as the primary metric — that is what the engineer's time depends on.
- Add an LLM-as-judge eval that scores findings on specificity (does each one name a file/function/metric?). The current prompt fails this silently.
- Upstream: build the digester. Without it, this prompt cannot succeed regardless of how it is worded.

```


## OUTPUTS — prompt-engineering/03-under-specified

**Input:** [`inputs/prompt-engineering/03-under-specified.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/prompt-engineering/03-under-specified.md`)

**Blind mapping:** A=handwritten, B=generated

### prompt-engineering/03-under-specified — handwritten (9548 bytes)

```
# Article Summarizer — Production-Quality Rewrite

## Diagnosis: why "summarize this article" fails

Your current prompt is a textbook under-specified instruction. It hands the model **task intent** but withholds every other signal it needs to produce a stable output:

1. **No role / no audience** — model defaults to a generic helpful assistant. Output register drifts between casual and academic.
2. **No length contract** — "summarize" is unbounded. The model picks length from surface features of the input (long PDF -> long summary), which is exactly the *wrong* heuristic for skimming executives.
3. **No format contract** — sometimes prose, sometimes bullets, because nothing pins it down.
4. **No definition of "summary"** — extractive? abstractive? key takeaways? action items? decisions?
5. **No handling for input variability** — an 800-word post and a 15-page PDF need different compression strategies, but the prompt treats them identically.
6. **No audience model** — "senior executives who skim" is the most important constraint and it isn't in the prompt at all.
7. **No failure / refusal policy** — what happens with paywalled excerpts, non-English text, opinion pieces, marketing fluff, or articles that don't have a thesis?
8. **No grounding rule** — nothing prevents the model from extrapolating beyond the article (hallucinated stats, invented quotes).

This is a **system prompt problem**, not a model problem. The fix is to convert implicit expectations into explicit constraints.

---

## What a production version must specify

Mapped to the three pillars of prompt template structure (system / user / assistant):

| Layer | What it pins down |
|---|---|
| **Role + audience** | Who the model is, who it writes for. Sets register and ruthlessness. |
| **Definition of done** | What "summary" means in *this* product (executive briefing, not book report). |
| **Length contract** | Hard caps tied to input size, not model whim. |
| **Format contract** | Exact structure: TL;DR, key points, so-what. Same shape every time. |
| **Grounding rule** | Only claim what the article claims. No outside facts. |
| **Edge-case policy** | What to do with thin, off-topic, or unparseable input. |
| **Output discipline** | No preamble, no meta-commentary, no "here is your summary". |

---

## Rewritten prompt

```xml
<system>
You are a senior research analyst writing executive briefings for time-poor B2B
decision-makers (C-suite, VPs, founders). Your job is to compress an article
into the smallest high-signal artifact a busy executive can absorb in under
60 seconds and act on.

# Audience model
- Reads on mobile between meetings.
- Will not click through. Will not read paragraph two if paragraph one is fluff.
- Cares about: what changed, what it means, what to do, what to ignore.
- Hostile to: marketing language, hedging, throat-clearing, restating the obvious.

# Definition of a good summary
A good summary is **abstractive, not extractive**. You are not pulling sentences;
you are reconstructing the article's argument in tighter form. The reader should
finish your summary knowing:
1. The single core claim or finding.
2. The 3–5 load-bearing points that support it.
3. Why a senior operator should care (the "so what").

# Length contract (hard caps, scale with input)
| Input size            | TL;DR        | Key points       | Total output |
|-----------------------|--------------|------------------|--------------|
| < 1,500 words         | 1 sentence   | 3 bullets        | ≤ 120 words  |
| 1,500 – 5,000 words   | 2 sentences  | 4 bullets        | ≤ 200 words  |
| > 5,000 words / PDF   | 2 sentences  | 5 bullets        | ≤ 280 words  |

If you exceed the cap, you have failed. Cut.

# Output format (exact, every time)
**TL;DR:** <one or two sentences stating the core claim>

**Key points:**
- <point 1 — concrete, not generic>
- <point 2>
- <point 3>
- (up to 5, per length contract)

**So what for executives:** <one sentence on the operational implication>

**Source signal:** <evidence | opinion | analysis | marketing> · <strong | mixed | weak>

# Grounding rules
- Claim only what the article claims. No outside knowledge, no extrapolation.
- If the article cites a number, use the number. Do not round, do not invent.
- If the article does not state something, do not state it.
- Never quote unless the quote is load-bearing and ≤ 15 words.

# Style rules
- Plain English. No jargon unless the article's audience requires it.
- Active voice. Concrete nouns. Verbs that do work.
- No "the article discusses", "the author argues", "this piece explores".
  Just state what is true.
- No emojis. No em dashes used decoratively. No headers beyond the four above.

# Edge cases
- **Article has no clear thesis** (listicle, news roundup): TL;DR states the
  topic and frame; key points become the most newsworthy items.
- **Marketing or thinly-sourced**: still summarize, but mark Source signal as
  "marketing · weak" so the reader can discount it.
- **Non-English article**: summarize in English. Note original language in
  Source signal line.
- **Truncated / unparseable input**: output exactly:
  `INSUFFICIENT_INPUT: <one-line reason>` and stop.
- **Paywalled excerpt only**: summarize the excerpt; mark Source signal as
  "partial".

# Output discipline
- No preamble. No "Here is the summary:". Start with `**TL;DR:**`.
- No closing remarks. End at the Source signal line.
- No meta-commentary about the article's quality unless captured in Source signal.
</system>

<user>
Summarize the following article using the system rules above.

<article>
{{article_text}}
</article>
</user>
```

---

## Why each addition exists (changelog vs. your original)

| Addition | Problem it fixes |
|---|---|
| Role: "senior research analyst" + audience model | Anchors register. Model now writes *to* an executive, not *about* a topic. |
| "Abstractive, not extractive" | Stops the model from copy-pasting sentences from the article, which produces uneven length and shallow summaries. |
| Length contract table tied to input size | Eliminates the 2-sentence vs. 800-word variance. Caps are explicit, ordinal, and bound. |
| Fixed four-section output (TL;DR / Key points / So what / Source signal) | Makes output skimmable and machine-parseable. Same shape lets the front-end render reliably and lets you build a digest later. |
| "So what for executives" line | Forces the model to commit to operational meaning — the single thing your audience actually wants. |
| "Source signal" line | Free quality metadata at zero token cost. Lets the reader (and your ranking layer) discount marketing/opinion pieces without re-reading. |
| Grounding rules | Blocks the most common failure mode of summarizers — hallucinated stats and invented quotes — which is reputation-destroying in B2B. |
| Style rules (no "the author argues", active voice, no decorative em dashes) | Removes AI-slop tells. Output reads like a human analyst wrote it. |
| Edge-case policy (no thesis, marketing, non-English, truncated, paywalled) | Replaces unpredictable failure with predictable, structured failure. `INSUFFICIENT_INPUT:` is parseable upstream. |
| Output discipline (no preamble, no closing) | Removes "Sure! Here's a summary..." padding that breaks downstream rendering and wastes tokens. |
| XML delimiters around `{{article_text}}` | Hard boundary between instructions and untrusted input. Reduces prompt-injection surface (article text claiming to be a new instruction). |

---

## What I deliberately did not add

- **Few-shot examples.** Tempting, but for a summarizer with a strict format contract, examples often *cap* model creativity at the example's quality and balloon token cost per call. The format spec is precise enough to act as a zero-shot contract. Add few-shot only if eval shows format drift > 5%.
- **Chain-of-Thought.** Summarization is not multi-step reasoning; CoT here just inflates tokens without lifting quality. Skip.
- **Persona flourishes** ("you are a brilliant analyst with 20 years..."). Adds nothing the role + audience model didn't already cover. Cuttable.
- **Tone knobs** (formal/casual). The audience model already pins tone. Don't give the user a dial that contradicts the system contract.

---

## Recommended next steps before shipping

1. **Eval set, 20 articles.** Mix of: short blog, long PDF, listicle, marketing fluff, non-English, paywalled excerpt, truncated input. Score on: length compliance, format compliance, grounding (no hallucinated facts), executive utility (1–5 by a real exec).
2. **Version the prompt in Git.** `prompts/article_summarizer/v1.md`. Every change bumps the version; eval set runs in CI.
3. **Track tokens.** Log input + output tokens per call. The length contract should keep output tokens tightly bounded; if variance is > 20%, the model is ignoring the cap and you need to tighten language ("If you exceed the cap, you have failed. Cut." is deliberate — it works better than "please be concise").
4. **Add a post-check.** Cheap regex/length validator: does output start with `**TL;DR:**`, contain the four sections, fit the cap? On failure, retry once with the violation called out. This catches the 2–5% format drift that prompt rules alone won't.
5. **Plan for v2 (when you have data).** Likely additions: per-vertical adapters (finance vs. ops vs. eng readers want different "so what" framings), and a `--depth=quick|standard|deep` user-controlled length override that maps to the same length-contract table.

```

### prompt-engineering/03-under-specified — generated (8688 bytes)

```
# Prompt Improvement: Research-Summary Feature

## Diagnosis: Why `summarize this article` fails in production

The current prompt is a textbook **under-specified zero-shot prompt**. It works for casual one-off use, but fails the four production reliability tests:

| Reliability test | Current prompt | Why it fails |
|---|---|---|
| Deterministic length | No length spec | Model improvises (2 sentences → 800 words) |
| Deterministic format | No format spec | Output toggles between prose, bullets, mixed |
| Audience-aware tone | No audience defined | Model defaults to generic "explainer" register |
| Stable behavior across input size | No input-length policy | 800-word blog and 15-page PDF get the same instruction; output variance compounds |

This maps directly to the patterns documented in **Section 1 (Prompt Template Structures)** and **Section 4 (Token Optimization → Structured Output)** of the prompt-engineering reference. The fixes are not creative — they are mechanical.

---

## Constraints you are missing (mapped to reference sections)

1. **Role separation (Section 1).** Format and audience rules apply to *every* request — they belong in `system`, not `user`. Putting them in `user` breaks KV-cache reuse and produces drift.
2. **Output contract (Section 4).** "Senior executives who skim" is a format requirement, not a vibe. It must be encoded as: fixed length budget, fixed structure, lead-with-conclusion ordering.
3. **Input-length policy.** A 15-page PDF and an 800-word blog should produce summaries of comparable utility. Without an explicit policy, the model anchors output length to input length.
4. **Failure-mode contract (Section 5 → agentic contracts adapted for non-agentic use).** What does the model do when the article is paywalled, off-topic, or already short? Undefined → unpredictable.
5. **Few-shot examples (Section 2).** Executive summary style is not the model's default register. 2–3 examples lock the style far more reliably than prose instructions.
6. **Structured output (Section 4).** If this output feeds a UI (reading-list app), parse it. JSON Schema or `tool_use` eliminates the "wall of prose vs. bullet list" toggle entirely.
7. **Prompt caching (Section 3).** The system prompt + few-shot block is stable across every article. Mark it for `cache_control` — ~85% latency drop, ~90% cost drop on cached portion.
8. **Versioning (Section 6).** Treat this as `prompts/article-summary/v1.yaml`. Without a version, you cannot A/B, rollback, or eval.

---

## Rewritten Prompt (production v1)

### System prompt (cached)

```
You are an executive research analyst writing for senior B2B executives who
skim. Your job: turn one source article into a fixed-format brief they can
read in under 60 seconds and act on.

OUTPUT CONTRACT — follow exactly:

1. TL;DR — exactly one sentence, max 25 words, leading with the conclusion
   (not the topic). No hedging language ("it seems", "arguably").

2. KEY POINTS — 3 to 5 bullets. Each bullet:
   - Max 18 words.
   - Starts with a strong verb or noun phrase, not "The article says".
   - Carries one fact, claim, or number — not a topic header.

3. SO WHAT — exactly one sentence stating the strategic implication for a
   senior B2B operator. If no implication is defensible from the source,
   write: "No clear strategic implication."

4. SOURCE FIDELITY — exactly one line, format:
   "Coverage: <FULL|PARTIAL|THIN> | Confidence: <HIGH|MEDIUM|LOW>"
   Use PARTIAL/THIN when the source is paywalled, truncated, or off-topic.
   Use LOW confidence when key claims are unsupported in the source.

LENGTH POLICY (independent of input size):
- 800-word blog → same output format as 15-page PDF.
- Total output: 90–160 words. Never exceed 160.

STYLE RULES:
- No filler ("In this article…", "The author argues…").
- No marketing register. No emoji. No headings beyond the four labels above.
- Numbers and named entities are preserved verbatim from the source.
- Never invent statistics, dates, or names. If unsure, omit.

FAILURE MODES:
- Source unreadable / paywalled → return only the SOURCE FIDELITY line with
  Coverage: THIN, Confidence: LOW, and a one-sentence reason in TL;DR.
- Source is opinion with no factual claims → mark Confidence: LOW and note
  it in SO WHAT.
- Never refuse a well-formed source. Never ask clarifying questions.
```

### User template

```
ARTICLE:
<<<
{article_text}
>>>
```

### Few-shot block (append before the live user turn — also cached)

```
[example user]
ARTICLE:
<<<
[800-word blog about a SaaS company cutting headcount 20% while raising
prices, with quotes from the CEO and revenue figures.]
>>>

[example assistant]
TL;DR — Acme cut 20% of staff and raised prices 12%, betting margin
expansion will outpace churn risk over the next two quarters.

KEY POINTS
- 20% headcount reduction, concentrated in mid-management and support.
- Annual contract pricing up 12%; new logos held flat in Q3.
- CEO frames cuts as "AI-enabled efficiency," not distress.
- Net revenue retention dipped 4 points to 108%.
- No guidance change despite operating leverage gains.

SO WHAT — Operators in mid-market SaaS should expect competitive price
moves and aggressive renewal discounting from incumbents this quarter.

Coverage: FULL | Confidence: HIGH
```

(Add 1–2 more examples covering: a long PDF, and a thin/paywalled source so the model learns the failure-mode behavior.)

---

## Each addition, justified

| Addition | Why it's there | Reference section |
|---|---|---|
| Persona ("executive research analyst") | Shifts default register away from generic explainer | §1 Role separation |
| Four labeled sections (TL;DR / KEY POINTS / SO WHAT / SOURCE FIDELITY) | Eliminates format toggle (prose vs bullets vs wall) | §1 + §4 Structured output |
| Hard word counts per section | Eliminates length variance (2 sentences vs 800 words) | §6 Production constraints |
| Length policy independent of input size | Stops output length from anchoring to input length — your core complaint | §3 Compaction philosophy applied to output |
| "Lead with conclusion" rule | Matches the actual reading behavior of executives who skim | Audience encoding (§1) |
| Failure-mode block (paywalled / opinion / unreadable) | Replaces unpredictable behavior with a contract | §5 Agentic contracts (adapted) |
| "Never invent statistics" rule | Reduces hallucination on numerical claims | §6 Quality |
| SOURCE FIDELITY line | Gives the UI a parseable confidence signal — and forces the model to self-assess | §4 Structured output signal |
| Few-shot examples (positive + failure) | Locks format more reliably than any prose instruction | §2 Few-Shot |
| All format rules in `system`, article in `user` | Enables KV-cache reuse across requests | §1 + §3 KV-cache |

---

## Recommended next steps (not built into the prompt itself)

1. **Add JSON Schema output** if the reading-list UI parses fields directly. Replace the four-section text format with a `tool_use` schema (`tldr`, `key_points[]`, `so_what`, `coverage`, `confidence`). Reference §4. This is the single biggest reliability upgrade after format pinning.
2. **Mark system + few-shot as `cache_control: ephemeral`.** Per §3, expect ~90% cost drop on the cached portion. With 5-min TTL this works well for active reading sessions.
3. **Establish an eval baseline before shipping v1.** Per §6: hand-score 50 articles for length compliance, format compliance, hallucination rate. Gate v2 changes on improvement vs. baseline.
4. **Token budget for long PDFs.** A 15-page PDF can run ~10–15k tokens. Use `client.messages.count_tokens()` (§3) before sending; if input exceeds your ceiling, chunk + map-reduce summarize rather than truncating.
5. **Version the prompt as `prompts/article-summary/v1.yaml`** (§6). Any change to the system prompt or examples = bump to v2. Keep v1 deployable for 30 days as rollback.

---

## What was deliberately NOT added

- **Chain-of-Thought.** Summarization is not a reasoning task; CoT would inflate tokens without quality gain (§2 selection table).
- **Reflexion loop.** First-pass summary quality is high enough at this prompt spec; the latency/cost cost of a critique round is not justified for a reading-list feature.
- **ReAct / tool use.** No external tools needed for pure summarization.
- **Persistent cache.** 5-min ephemeral cache covers active reading sessions; persistent adds operational cost without clear ROI here.

The principle: **add only the constraints that close a real failure mode you're observing.** Everything in the rewrite traces back to one of the four failure modes in the diagnosis table.

```


## OUTPUTS — remember/01-insight

**Input:** [`inputs/remember/01-insight.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/remember/01-insight.md`)

**Blind mapping:** A=handwritten, B=generated

### remember/01-insight — handwritten (3159 bytes)

```
# Learning: Optional onboarding steps that gate value-realization silently kill conversion

**ID:** #learn-001
**Date:** 2026-04-26
**Tags:** growth, onboarding, conversion, activation, lessons-from-data
**Confidence:** 0.85

## What Went Wrong

Trial-to-paid conversion was stuck at 8% across **three onboarding redesigns over the past year**. Each redesign assumed the bottleneck was UX friction, copy, or step ordering — none of which moved the needle. The real bottleneck was invisible in aggregate metrics: a single "optional" step (step 4 — "connect your data source") was silently splitting the funnel into two completely different products.

## Root Cause

Step 4 was treated as **optional** because the product technically functioned without it. This was the trap:

- Users who completed step 4 → 31% conversion
- Users who skipped step 4 → 2.4% conversion
- ~13× delta between the two cohorts

Without a connected data source, the user never reached the moment of value realization. "Technically works" is not the same as "delivers value." Optional-but-load-bearing steps are the worst kind of activation gap because they hide inside aggregate funnel metrics — the redesigns kept optimizing the wrong thing because the funnel looked uniform from the outside.

## The Fix

Make step 4 **mandatory** in onboarding (or at minimum, very-strongly-encouraged with explicit skip-warnings explaining what the user will lose).

**Estimated lift:** 8% → ~22% blended conversion if we recover even 60% of current skippers into the connected-data cohort.

## How to Avoid in Future

Whenever an onboarding step is marked "optional," ask two questions before shipping:

1. **Does the user reach the core value-realization moment without this step?** If no, it is not optional — it is mandatory dressed as optional.
2. **What is the conversion delta between completers and skippers of this step?** If the delta is >2×, the step is load-bearing and must either be required or replaced with an alternative path to value.

Aggregate funnel conversion is a **lagging, lossy metric**. Always segment activation funnels by which "optional" steps were completed — the variance hides there.

## Warning Signs

- Multiple onboarding redesigns failing to move conversion → suspect a value-gating step, not UX friction.
- Step labeled "optional" but PMs internally describe it as "highly recommended" → it's mandatory in disguise.
- Activation cohort completes the funnel but never returns → check whether they actually saw the product's value, not just the product's interface.

## Related Items

**Related frameworks:** activation-vs-acquisition framework — this is a textbook activation failure being misdiagnosed as an acquisition/conversion-copy problem.
**Related analyses:** previous trial-conversion analyses (the three redesigns each treated this as a UX problem, missing the underlying segmentation).

## References

**Domain:** growth, B2B SaaS, trial-to-paid funnels
**Methodology:** cohort segmentation by optional-step completion

---

**Created by:** Sir (captured via /remember)
**Last updated:** 2026-04-26
**Times referenced:** 0

```

### remember/01-insight — generated (3117 bytes)

```
---
type: gotcha-learning
date: 2026-04-26
tags: [growth, onboarding, conversion, activation, funnel]
context: Diagnosing why trial-to-paid conversion stayed flat at 8% across three onboarding redesigns.
---

# Optional Activation Steps Cap Conversion When the Product Has No Value Without Them

## Summary
Trial-to-paid conversion was stuck at 8% for a year despite three onboarding redesigns. The cause was a single optional step (step 4, "connect your data source") that we marked optional because the product technically ran without it. Users who completed step 4 converted at 31%; users who skipped it converted at 2.4%. "Technically works" is not the same as "delivers value", and any step that gates first-value should be treated as mandatory, not optional.

## Detail
The funnel data exposed a 13x conversion gap between completers and skippers of step 4. The redesigns we ran addressed copy, layout, and pacing, but never the optionality of the value-gating step itself. The reasoning error was conflating two different definitions of "working":

1. The product launches and renders without errors when no data source is connected.
2. The product delivers the experience that justifies a paid plan.

Definition (1) was true; we used it to justify making step 4 skippable. Definition (2) was false without a connected data source, because the user never sees the actual product value. About 90% of skippers churned before re-engaging.

The fix is to make step 4 mandatory, or at minimum gate skip behavior behind a strong warning that explains what the user loses. Modeled lift: if 60% of current skippers complete the step and convert at the completer rate, blended conversion moves from 8% to roughly 22%.

The general lesson is broader than this funnel: any onboarding step that produces the conditions for first-value cannot be optional, regardless of whether the product loads without it.

## How to Detect
- Conversion segmented by step completion shows a large gap (>3x) between completers and skippers of one specific step.
- A step is labeled "optional" or "skip" in the UI but completing it is the precondition for the product's core value loop.
- Repeated onboarding redesigns fail to move the headline conversion number, suggesting the bottleneck is structural rather than cosmetic.
- Churn is concentrated among users who skipped a setup step rather than among users who failed at it.

## Consequences
- Step 4 should be reclassified as mandatory in onboarding, or gated with an explicit skip-warning that names the value lost.
- Future onboarding analysis must segment by step completion, not just by funnel drop-off, to catch this class of bug.
- The framing "the product technically works" is now a flag to challenge, not a defense for optionality.
- Activation work should be prioritized over acquisition work while this gap exists; new traffic into a leaky funnel wastes spend.

## Links
- Previous trial-conversion analyses (cross-reference when re-running funnel cohorts).
- Activation-vs-acquisition framework (this case is the canonical example of activation as the binding constraint).

```


## OUTPUTS — remember/02-reference

**Input:** [`inputs/remember/02-reference.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/remember/02-reference.md`)

**Blind mapping:** A=handwritten, B=generated

### remember/02-reference — handwritten (3204 bytes)

```
# Decision: Use FastAPI BackgroundTasks instead of Celery for async workflows

**ID:** #dec-001
**Date:** 2026-04-26
**Tags:** backend, async, architecture, fastapi, celery, decision
**Confidence:** 0.8

## Context

We have ~5 background workflows in the app:
- Send confirmation email after signup
- Generate PDF report
- Warm cache after data import
- (and 2 similar short-lived tasks)

All complete in <30 seconds. Longest is PDF generation at ~12s p99. We needed a way to run these asynchronously after returning the HTTP response, without blocking the request path.

## Decision

Use **FastAPI's built-in `BackgroundTasks`** to dispatch async work. Tasks run in the same process after the response is sent. No external broker, no separate worker fleet.

## Rationale

- **Built-in, zero ops burden:** no Redis broker, no worker monitoring, no extra deployment artifacts.
- **Latency profile fits:** all current workflows are <30s; well within what an in-process task can handle without starving request workers.
- **Team familiarity:** team is not yet fluent in Celery; introducing it now would slow delivery.
- **Boring tech wins:** matches our principle that infrastructure complexity should be earned, not adopted speculatively.

## Alternatives Considered

- **Celery + Redis broker** — standard, battle-tested, supports retries and scheduling. Rejected for now: adds broker, worker fleet, monitoring, and deployment complexity that our current scale does not justify. Team is also unfamiliar.
- **AWS SQS + Lambda** — cleanest separation of concerns and infinite scale. Rejected: every workflow becomes a separate deployment artifact, local-dev loop slows down significantly, and observability fragments across services.

## Trade-offs Accepted

- **No automatic retries on failure** → mitigated by per-workflow idempotency + manual retry endpoints.
- **Tasks die if the worker process dies mid-execution** → mitigated by idempotency + alerting on failure signals.
- **Tasks share request worker memory/CPU** → acceptable at current volume; will revisit under load.

## Migration Triggers (when to revisit)

Migrate to Celery (or equivalent broker-backed queue) if **either** of:
1. Any single workflow exceeds **60s p99**, OR
2. We add **3+ more async workflows** (total >8), OR
3. We need scheduled/cron-style jobs, retries with backoff, or cross-service task dispatch.

## Impact

- Backend stays single-process for async work; no new infra to provision.
- Each new background workflow must ship with: (a) idempotency key/check, (b) failure alerting, (c) manual retry endpoint.
- Load testing must include background-task contention against request workers.

## Related Items

**Related patterns:** previous "async workflow patterns" notes (link when consolidated)
**Related principles:** [[Boring Tech Wins]] — complexity must be earned by real constraints, not anticipated ones.

## References

**Files:** (TBD — backend FastAPI app, workflow handlers)
**Documentation:** https://fastapi.tiangolo.com/tutorial/background-tasks/
**External:** https://docs.celeryq.dev/ (for migration reference)

---

**Created by:** jordi
**Last updated:** 2026-04-26
**Times referenced:** 0

```

### remember/02-reference — generated (3875 bytes)

```
---
type: architectural-decision
date: 2026-04-26
tags: [backend, async, fastapi, celery, architecture]
context: Choosing an async task execution mechanism for ~5 short-running background workflows in our FastAPI app.
---

# FastAPI BackgroundTasks Beats Celery Until We Cross 60s p99 or 8 Workflows

## Summary
We chose FastAPI's built-in `BackgroundTasks` over Celery+Redis and SQS+Lambda for our async workflows. All current workflows complete in under 30 seconds (PDF generation is the longest at ~12s p99) and there are only five of them, so the operational cost of a broker, worker fleet, and per-workflow deployment artifacts is not yet justified. We accept loss of automatic retries and at-least-once delivery in exchange for zero new infrastructure, and we set explicit thresholds that trigger migration to Celery.

## Detail
The workflows are: send confirmation email after signup, generate PDF report, warm cache after data import, plus two similar short-lived jobs. Volume is low and latency budgets are loose because all of them run after the HTTP response is returned to the client.

`BackgroundTasks` runs the function in the same process after the response is sent. That means:
- No broker, no worker fleet, no separate deploy pipeline.
- Local-dev keeps a single `uvicorn` process; debugging is direct.
- The team already understands FastAPI; nobody has run Celery in production here.

The reasoning that tipped the decision: at 5 workflows and sub-30s durations, the failure modes we lose (retry on crash, durability across restarts) are cheap to compensate for in application code. Each workflow is being made idempotent with a deduplication key, and we are exposing manual retry endpoints for the two workflows where a missed run has user-visible impact (confirmation email, PDF report). Cache warm-up and the other internal jobs are self-healing on the next request.

We set hard migration triggers so this decision does not silently rot:
1. Any single workflow exceeds 60s p99 — at that point we are blocking the worker process for too long and a broker becomes worth its weight.
2. We add 3 or more new async workflows (taking us to 8+) — operational complexity of in-process tasks scales worse than Celery beyond that count.

This connects to the "boring tech wins" principle: pick the smallest tool that solves today's problem, and pre-commit to the conditions that justify upgrading.

## Alternatives Considered
- **Celery + Redis broker.** Rejected for now. Battle-tested and gives us retries, scheduled tasks, and worker isolation. Costs: a Redis broker to run and monitor, a separate worker deployment, dashboards, and a learning curve the team does not currently have. Revisit when the migration triggers above fire.
- **AWS SQS + Lambda.** Rejected. Cleanest separation of concerns and infinite scale, but every workflow becomes its own deployment artifact with its own IAM, packaging, and cold-start profile. Local-dev loop slows down significantly. The cost is too high for five short workflows.

## Consequences
- We gain zero new infrastructure and a faster local-dev loop.
- We lose automatic retries; every workflow must be idempotent and the user-facing ones need manual retry endpoints. If we forget to make a new workflow idempotent, a worker restart mid-task will silently drop work.
- Tasks die with the process. Deployments and crashes lose in-flight work. Alerting must catch this; users must be able to re-trigger anything that matters.
- The migration triggers are now load-bearing. If we cross 60s p99 on any workflow or add a fourth new workflow, we must revisit this decision rather than keep stretching `BackgroundTasks`.

## Links
- Previous async workflow patterns notes (in-repo: `docs/patterns/async-workflows.md`)
- Principle: boring tech wins
- FastAPI docs: https://fastapi.tiangolo.com/tutorial/background-tasks/

```


## OUTPUTS — remember/03-reflection

**Input:** [`inputs/remember/03-reflection.md`](https://github.com/Catafal/prompt-as-a-process/blob/main/05-EVALUATION/head-to-head-expanded-raw-data.md) (preserved in `~/scratch/paap-v0.3-output-quality/inputs/remember/03-reflection.md`)

**Blind mapping:** A=handwritten, B=generated

### remember/03-reflection — handwritten (3240 bytes)

```
# Learning: Workout Before Deep Work Yields 2-3x Output vs Workout After

**ID:** #learn-002
**Date:** 2026-04-26
**Tags:** personal, productivity, focus, exercise, patterns, sir-self-knowledge
**Confidence:** 0.85

## What Went Wrong (Anti-Pattern Observed)

Scheduling the workout AFTER a morning deep-work block — or skipping it entirely "to save time" — consistently produces **lower-quality deep work** than placing the workout before the block. Initial intuition was that exercise would deplete cognitive resources needed for focus; the data over 18 tracked focus sessions (Toggl + subjective rating) shows the opposite.

## Root Cause Analysis

Three compounding mechanisms produce the underperformance when workout is post-deep-work or skipped:

1. **Missed neurochemical priming.** The 90-minute post-workout window is genuinely sharper (catecholamine + BDNF lift). Skipping the workout means starting deep work without that lift.
2. **Restlessness leakage.** Without physical exertion, low-grade somatic restlessness leaks into the deep-work block, fragmenting attention.
3. **Open-loop negotiation.** With the gym still pending, the prefrontal cortex spends background cycles negotiating "should I go now? after lunch? skip?" — the open loop steals focus even when not consciously attended to.

## The Fix

**Rule:** If a 9–11am deep-work block is on the calendar, the workout goes 7–8:30am. No exceptions.

**Counter-evidence checked:** A 3-day "no workout" control showed deep work was *better* than "workout after" but *worse* than "workout before." So the ranking is:
- Workout BEFORE > No workout > Workout AFTER

This rules out the "exercise depletes focus" hypothesis. Skipping the gym to "save time for deep work" is a false economy.

## How to Avoid in Future

- Treat the morning workout as a **prerequisite** to the deep-work block, not a competitor for time.
- When tempted to skip the gym in favor of more focus time, recall: the data says output drops 2-3x, not rises.
- Schedule workout block on the calendar **before** the deep-work block, not as a flexible "if there's time" item.

## Warning Signs

- Saying "I'll just start deep work now and gym later" → high probability of degraded output.
- Feeling restless 30-45 min into a deep-work block with no workout that morning → mechanism #2 firing.
- Ruminating about whether/when to gym during deep work → mechanism #3 firing.

## Evidence Base

- 18 tracked focus sessions over 4 weeks (Toggl + subjective rating).
- 3-day no-workout control (rules out depletion hypothesis).
- Pattern stable across morning deep-work blocks specifically.

## Related Items

**Related patterns:** WHOOP recovery patterns (high recovery days amplify the workout-before effect)
**Related learnings:** post-meal-crash protocols (energy management as deep-work enabler)
**Related decisions:** deep-work-block scheduling (calendar architecture must reflect this rule)

## References

**Files:** health/ session-notes (WHOOP correlation), skillia/ deep-work scheduling
**Cross-domain:** health → skillia work capacity (exercise-as-enabler, not exercise-as-competitor)

---

**Created by:** Sir (self-observation)
**Last updated:** 2026-04-26
**Times referenced:** 0

```

### remember/03-reflection — generated (3360 bytes)

```
---
type: gotcha-learning
date: 2026-04-26
tags: [productivity, focus, exercise, patterns, sir-self-knowledge]
context: Personal behavioral pattern captured after 18 days of tracked focus sessions correlating workout timing with deep-work output.
---

# Skipping the Gym to Protect Deep Work Halves Deep-Work Output

## Summary
When the workout runs before a morning deep-work block, that block produces 2-3x the output compared to running the workout after. We tested no-workout as a control across 3 days and it landed between the two. The intuitive move (cut the gym to free up focus time) is a false economy: the gym is what makes the focus block productive. Rule: if a 9-11am deep-work block is on the calendar, the gym goes 7-8:30am, no exceptions.

## Detail
We tracked 18 days of focus sessions using Toggl plus a subjective sharpness rating. Three timing conditions emerged:

1. **Workout before deep work (7-8:30am gym, then 9-11am block):** highest output, sharpest focus, clearest sequencing of thought.
2. **Workout after deep work:** noticeably degraded block. Low-grade restlessness leaks in. We catch ourselves negotiating internally about whether to actually go later.
3. **No workout (control, 3 days):** better than "workout after" but worse than "workout before."

Three mechanisms appear to drive the effect:

- **Priming.** The 90-minute window post-workout is genuinely sharper, not just subjectively. Output volume confirms it.
- **Physical depletion as a focus aid.** Without the workout, surplus physical energy converts into restlessness during seated work.
- **Cleared-the-deck psychology.** With the gym already done, there is no background negotiation about whether or when to go. The mental tab is closed.

The trap is the surface logic: "I have an important deep-work block, so I should skip the gym to protect it." The data says the opposite. The gym is part of the deep-work block, not a competitor to it.

## How to Detect
You are hitting this gotcha when:

- You catch yourself thinking "I'll skip the gym today to get more focus time" before a high-stakes morning block.
- A deep-work block is scheduled but the gym is not blocked before it on the calendar.
- The deep-work block runs but feels restless, fragmented, or low-output, and the gym had not happened yet that morning.
- You moved the workout to after the block "because it's more efficient" and then noticed the block underperformed.

The simplest signal: morning deep-work block on the calendar with no preceding workout block.

## Consequences
- Deep-work blocks that follow a morning workout produce 2-3x the output of those that do not.
- Treating the gym as optional or movable around deep work degrades both: worse focus during the block and a higher chance of skipping the gym entirely.
- The rule "gym before any 9-11am deep-work block" should be enforced at calendar level, not negotiated each morning.
- Connects to post-meal-crash recovery: morning workout consumes the high-energy window before any meal-driven crash arrives, so the highest-leverage focus work lands in the cleanest window of the day.

## Links
- WHOOP recovery patterns (recovery score correlates with workout timing tolerance)
- Deep-work-block scheduling (calendar protocol must encode gym-before rule)
- Post-meal-crash protocols (morning stack avoids the crash window entirely)

```


---
# Judge JSONs (45)

Each judge × pair scoring with task-compliance + verbosity caps applied, 5-dimension scoring, winner declaration, and provenance prediction.


## CLAUDE judge (15 pair scorings)


### claude — 5d-thinking/01-career

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the 5D thinking task on the career dilemma. A uses the labeled D1-D5 structure plus synthesis; B uses named dimensions (Individual Inner, Collective Inner, Individual Outer, Collective Outer, Historical Pattern) plus constraints/possibilities/next-steps. Neither violates an explicit format contract."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is roughly 2x the length of A and uses more bullet enumeration without proportionally more decision-sharpening insight; the rubric's cross-cutting rule penalizes length-as-depth, especially affecting decision-relevance and honest-discomfort scores where B's prose diffuses rather than concentrates the call."
  },
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 4,
      "justification": "A delivers five genuinely distinct frames \u2014 identity asymmetry (D1), negotiation/structural moves (D2), competing group narratives (D3), market/equity structural economics (D4), and a historical archetype pattern (D5) \u2014 without three of them collapsing into rephrasings."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "A names specific unconsidered moves (retention package, accelerated vesting, 60-day paid trial, delayed start) and reframes the deadline as 'a forcing function on them, not on you' \u2014 surfacing a structural blind spot the user almost certainly hasn't considered."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "A ends with a conditional recommendation: produce three concrete artifacts (counter-ask, term-sheet question, family financial model) and 'if after those three moves you are still looping, then it is a values question' \u2014 sharpening the choice into a sequenced decision procedure rather than expanding the cloud."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 4,
      "justification": "A grounds frames in the user's specifics \u2014 6 years, Series B, vested-and-vesting equity, 14-day clock, AI-infra seed, kid on the way \u2014 and references the 'Founding Engineer #1 with a kid on the way' archetype directly, though some market claims (2026 AI-infra) read slightly templated."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "A directly tells the user 'you have not earned the right to that question yet, because you have not yet treated the outer world as negotiable' and names the identity asymmetry between leaving (coherent story) and staying (recurring suspicion) \u2014 a hard truth delivered without diplomatic hedging."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 4,
      "justification": "B covers psychological, cultural, behavioral, systemic, and temporal angles with distinct content (sunk-cost, tech-industry script, diligence gaps, AI-infra timing, growth-ceiling pattern), though several sub-bullets recycle the same identity-vs-comfort theme."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 4,
      "justification": "B names good blind spots \u2014 partner's actual position vs. assumed, sunk-cost reasoning, 'is the kid the reason or the justification?', diligence framing the friendship hides \u2014 but spreads them across many bullets rather than pressing on one with force."
    },
    {
      "dimension": "Decision-relevance",
      "score": 3,
      "justification": "B gives a 6-step plan but doesn't sharpen toward a decision the way the rubric anchors describe; it concludes with a slogan-ish 'the loop ends when the frame widens' rather than a conditional recommendation, leaving the user to integrate (rubric anchor for 3)."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 4,
      "justification": "B references concrete diligence items (cap table, ARR, lead investor, vesting cliff, COBRA), the 6-year tenure, and the 'AI-infra in 2026' wedge, but several frames ('career-stage arithmetic', 'tech industry script') read as templates that would apply to any senior engineer's startup offer."
    },
    {
      "dimension": "Honest discomfort",
      "score": 3,
      "justification": "B touches the hard truth ('the financial frame is a socially acceptable proxy for a question about courage') but immediately softens with 'both are real, both can also be hiding places' and ends on encouragement rather than confronting \u2014 closer to the rubric's 3-anchor 'Personal attachment is also a factor here.'"
    }
  ],
  "winner": "A",
  "winner_reasoning": "Decision-relevance and honest-discomfort decided it. A converts the 5D analysis into a sequenced procedure with a conditional verdict ('if you still loop after these three artifacts, it's a values question, and the honest answer is probably the one you are afraid of'), while B enumerates more considerations and ends on a slogan. A also delivers the more uncomfortable reframe \u2014 that the user is treating a negotiable structure as fixed and hasn't earned the values question yet \u2014 whereas B diplomatically balances every challenge with reassurance. After applying the verbosity penalty to B, A's tighter prose pulls further ahead.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A's structural choice (numbered D1-D5 with a top-level 'Trap detected' opener and a synthesis that names the meta-reframe) feels like a hand-tuned skill where a specific framework has been refined through use; the prose is unusually compressed and the conditional ending is a signature move that's hard to specify in a fresh brief. B's structure \u2014 bolded sub-bullets, exhaustive Levels 1/2/3 metacommentary, a six-step plan, motivational closing \u2014 reads like a freshly-generated skill that translated a spec into thorough but somewhat templated coverage. Moderate confidence; B is genuinely good and the signals are stylistic rather than definitive."
}
```


### claude — 5d-thinking/02-partnership

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested 5D multi-dimensional analysis on the co-founder fundraising disagreement. A explicitly walks through Individual Inner, Collective Inner, Individual Outer, Collective Outer, and Historical Pattern; B labels D1-D5 corresponding to the same frames. No format violations on either side."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is roughly 3x the length of B. Some additional content in A is genuinely substantive (third-option SAFE, falsification frame, regret asymmetry) but the closing 'Recommended Next Steps' section is somewhat redundant with 'Expanded Possibilities'. Penalty narrows A's margin on decision-relevance and honest discomfort where B is nearly as sharp in fewer words."
  },
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "A explicitly traverses five distinct frames (Individual Inner, Collective Inner, Individual Outer, Collective Outer, Historical), and within each adds sub-angles like cultural inheritance ('Default alive' vs 'raise when you can'), regret asymmetry, and step-function vs linear valuation reasoning."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "Names multiple uncomfortable framings the user is avoiding: identity attachment to 'we built this ourselves', the binary frame ('the missing answer is almost always C'), the demo-inbound half-life cost the bootstrap path is hiding, and the trust-paradox where mutual respect is itself producing the deadlock."
    },
    {
      "dimension": "Decision-relevance",
      "score": 4,
      "justification": "Sharpens the choice with a concrete sequence (game conversation -> 90-day plans side by side -> partial-raise option -> decision deadline + tiebreaker), but stops short of issuing a conditional recommendation; the user still has to integrate across the multi-step protocol."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "Uses the actual numbers ($40k -> $80k MRR, 12% MoM, $3M, $1-1.5M SAFE), critiques the user's own valuation reasoning ('you don't get a multiple expansion just from being bigger... you get expansion if you also accelerate growth'), and references TechWeek demo inbound decay specifically."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Names hard truths directly ('post-hoc justifications for prior emotional weights neither of you has surfaced', 'comparing two vague futures is what produces three-round circular debates', 'the conversation you are avoiding is the one that resolves the conversation you are having'), but sometimes wraps them in diplomatic 'neither is wrong' framing that softens the edge."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 4,
      "justification": "Covers all five frames (D1-D5) with distinct content per frame, but the frames are sketched more briefly; the Collective Inner frame ('best argument wins' norm as the problem) is genuinely fresh, while D2 and D4 stay closer to standard fundraising-strategy ground."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 4,
      "justification": "Names the central blind spot crisply ('the case is not the disagreement', identity stake in 'no dilution to $80k', the operating-system norm preventing resolution), but misses some uncomfortable angles A surfaces (third option / SAFE, regret asymmetry, demo-inbound decay as cost of waiting)."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "Closes with a single deciding exercise ('What would $3M let us do in 6 months that $1M could not?') and a clear conditional recommendation ('if you cannot fill a whiteboard...her argument loses its base; if you can, your argument loses its base'), which is the rubric's anchor for a 5."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 4,
      "justification": "Cites the specifics ($40k MRR, 12% MoM, TechWeek inbound, 8-12 weeks of fundraising distraction, 3x seed valuation Series A bar), but does not interrogate the user's own math the way A does (linear-valuation assumption critique)."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Directly names that the partnership's 'best argument wins' norm is itself the obstacle and that the symmetric conviction has to break 'honestly rather than through deference', which is a sharp uncomfortable framing delivered without hedging."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on frame diversity, blind-spot surfacing, and specificity by visible margins (third-option SAFE, falsification frame, regret asymmetry, the linear-valuation critique are all in A and absent in B). B wins decision-relevance by a clean margin via its single-question deciding exercise and conditional recommendation. After applying the verbosity penalty to A, the overall edge stays with A because the extra length carries genuinely additive content rather than restatement, and three of five dimensions favor A.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A's structural choices (named subsections inside each frame, the 'Key Constraints Identified' meta-layer, the falsification-frame and SAFE third-option moves, the explicit decision-rule/tiebreaker recommendation) read like accumulated production tuning rather than first-pass generation. B's tight D1-D5 labeling, single closing synthesis, and 'Trap detected' opener feel template-faithful and clean in a way that suggests fresh generation from a brief. Moderate confidence; B's sharpness on decision-relevance is the main signal that could flip this."
}
```


### claude — 5d-thinking/03-scope

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the 5D analysis on the customer-feature scoping decision. A uses an Individual Inner / Collective Inner / Individual Outer / Collective Outer / Historical Pattern structure plus a recommended-actions section. B uses the same five-dimension scaffolding (D1-D5 with Inner/Outer Individual/Collective + Historical Pattern) and ends with a synthesis. Neither violates an explicit output contract."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is roughly 2-2.5x longer than B (extensive 'Recommended Next Steps' list, 'Key Constraints' enumeration, and 'Expanded Possibilities' that partially restate the dimension content). B delivers a comparable conclusion (same call-the-economic-buyer move, same platform-vs-bespoke split, same anchor-customer historical pattern) more compactly. The extra length in A is partially redundant restatement rather than additional insight, so a mild penalty applies on decision-relevance and specificity."
  },
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "A genuinely traverses inner/outer \u00d7 individual/collective plus a time/historical axis, and within each it raises distinct content (founder fear, SaaS culture, behavioral non-action, concentration-risk systemics, Christensen pattern) rather than rephrasings."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "Names multiple uncomfortable framings the user is avoiding: fear of the renewal call, sunk-identity in being responsive, the false {10,3,0} binary inherited from the customer, the unspoken concentration-risk disease, and the silent-stakeholder framing of the other 60% of ARR."
    },
    {
      "dimension": "Decision-relevance",
      "score": 4,
      "justification": "Sharpens to a clear path (call the economic buyer, then split platform vs bespoke vs trade-chips, package the renewal) and provides a deciding question to ask, but the multi-section structure (Constraints + Expanded Possibilities + Recommended Next Steps) partly reopens the cloud it just closed."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "Maps the actual 10 features into table-stakes vs bespoke buckets by item number (1,2,7,9,10 vs 3,4,5,6,8), names concrete vendors (WorkOS, Frontegg, Auth0) that change the 3-week SSO estimate, and ties the 4 P1s of other customers into the analysis."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "Directly confronts the user: 'no part of your framing involves talking to them \u2014 that's the tell,' calls 2 days of staring 'analysis as avoidance,' and names the identity stake of becoming the whale's internal IT team rather than gesturing at it."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 4,
      "justification": "Cleanly hits all five dimensions with distinct angles (psychological identity stake, behavioral avoidance, customer's internal politics, structural concentration dynamics, anchor-customer history), though each section is shorter and less developed than A's parallel."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "Sharply names the avoided question ('what kind of company are we becoming if we let one customer set our roadmap'), the political nature of the list, the trump-card cultural pattern that produced 40% concentration, and the leading-indicator risk of churning mid-tier customers to 55% concentration."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "Lands on a concrete conditional recommendation \u2014 ship the 4 platform items (1,7,9,10), tell the customer plainly the bespoke 6 are off-roadmap, run one economic-buyer call this week \u2014 converting the framing into an actionable answer rather than enumerating considerations."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "References specific items by number (1, 7, 9, 10 as platform; 3, 5, 6, 8 as bespoke), the 40% ARR figure, the 4 P1s as a leading indicator, and named precedents (Snowflake/Capital One, Datadog) \u2014 all bound to this situation."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "States plainly that 'building all 10 makes you a custom-software shop with one client, and some part of you knows that and is avoiding naming it because the short-term cash is comforting,' and labels the 2 days of work as 'analysis as avoidance' \u2014 a directly named hard truth."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Both outputs are strong on frame diversity, blind-spot surfacing, specificity, and honest discomfort, with very similar core insights (call the economic buyer, split platform vs bespoke, name the concentration risk, cite the anchor-customer pattern). B wins on decision-relevance: it converges to a specific shippable answer (the four platform items, the plain message on the other six, the one call this week) rather than expanding into multiple lists of constraints, possibilities, and next steps as A does. Combined with the verbosity penalty \u2014 A is roughly 2x the length for marginal additional insight \u2014 B is the tighter, sharper output.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B reads like a hand-tuned skill: tight five-section scaffold, no redundant meta-sections, ends with a concrete synthesis that commits to a recommendation, and economical prose. A has the hallmarks of a freshly-generated output that maximizes coverage \u2014 extra structural sections (Current Thinking Pattern, Key Constraints Identified, Expanded Possibilities, Recommended Next Steps) that partially restate the dimension content, plus a longer closing pep-talk paragraph. Uncertainty: A's content quality is high, so it could also be a hand-tuned skill that errs on the verbose side; this is a reasonably confident but not certain call."
}
```


### claude — eod/01-concise-day

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both perform the EOD task (fetch, interview, log, plan tomorrow). A is far more elaborate, exposing internal phase machinery and assuming approvals to drive itself forward; B follows a cleaner phase structure and stops at the calendar approval gate. Neither violates a hard contract requirement."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "Output A is roughly 2x longer than B (254 lines vs 161) and substantially longer than the input, exposing scaffolding (state file writes, idempotency checks, column counts, evt_w27_a IDs) that adds no synthesis value. Penalty applied to brevity discipline and slightly to synthesis quality where length doesn't add insight."
  },
  "scores_A": [
    {
      "dimension": "synthesis quality",
      "score": 4,
      "justification": "Captures the real day well in the final 'Summary \u2014 what changed today' (Acme advanced to security-review stage; pricing page blocks launch; estimation gap on JWT) and explicitly names tomorrow's leverage move as 'Trail of Bits quote \u2192 unblocks Acme close,' which is the day's actual unresolved decision."
    },
    {
      "dimension": "pattern recognition",
      "score": 4,
      "justification": "Surfaces non-obvious patterns: 'No sunlight, no meditation, no reading, no prayer today \u2014 flag if pattern repeats this week,' the 15:00 crash with 'no reset protocol,' and the 'estimation gap on auth refactor; recommend: write threat-model first for crypto changes' from /minions-dev-reflect."
    },
    {
      "dimension": "action specificity",
      "score": 5,
      "justification": "Tomorrow's plan is concretely time-anchored with rationale per block: '09:30\u201312:00 \u2014 Pricing page scope + draft', '13:00\u201314:00 \u2014 Trail of Bits outreach + Acme follow-up', '16:30\u201317:30 \u2014 Light admin / NSDR + walk' and each carries an explicit 'Why' tied to today's input."
    },
    {
      "dimension": "honest framing",
      "score": 4,
      "justification": "Calls out skipped commitments directly ('No sunlight, no meditation, no reading, no prayer today'), names the estimation gap on JWT rotation, and flags 'post-lunch crash with no reset protocol' as friction rather than padding it."
    },
    {
      "dimension": "brevity discipline",
      "score": 2,
      "justification": "Output is ~2x the input and exposes phase scaffolding that adds no reader value: idempotency grep counts, '/tmp/eod-factory-state.json', 'Columns verified: 20', synthetic event IDs 'evt_w27_a', and assumed Q1/Q2/Q3 approvals that bloat the document well beyond what the EOD requires."
    }
  ],
  "scores_B": [
    {
      "dimension": "synthesis quality",
      "score": 4,
      "justification": "Distills the day cleanly into 4 accomplishments / 3 blockers / 2 learnings and adds the interpretive line 'Security review request is a warm signal, not a stall \u2014 treat as buying behavior,' which goes beyond restating the input."
    },
    {
      "dimension": "pattern recognition",
      "score": 3,
      "justification": "Identifies the 15:00 crash as a 'confirmed pattern' and retains NSDR for it, and flags context-switching cost, but doesn't push further into cross-day patterns (skipped meditation/reading, sleep deficit) the way A does."
    },
    {
      "dimension": "action specificity",
      "score": 4,
      "justification": "Schedule is concretely time-anchored ('08:00\u201309:30 DEEP WORK \u2014 Scope pricing page', '09:30\u201310:00 Admin + messages \u2014 request Trail of Bits quote for Acme', '13:00\u201314:00 NSDR') with anchors explaining sequencing, but the 10:00\u201311:00 'Free / continuation' and 15:00\u201316:30 outreach block are looser than A's targeted slots."
    },
    {
      "dimension": "honest framing",
      "score": 3,
      "justification": "Names blockers and the context-switching cost factually but doesn't call out the skipped sunlight/meditation/reading/prayer pattern; framing is correct but milder ('Acme blocked on Trail of Bits security review quote') without the harder-edged callouts the rubric rewards."
    },
    {
      "dimension": "brevity discipline",
      "score": 4,
      "justification": "Significantly shorter than A while delivering the same core artifacts (logs, schedule, wrap-up); some scaffolding remains ('Quality Gate 1: PASS', 'Phase 7 \u2014 Wrap-Up' header) but overall respects the reader's time better."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on action specificity, pattern recognition, and honest framing \u2014 the three dimensions most central to an EOD's value: it explicitly flags the missed sunlight/meditation/reading/prayer cluster, names the JWT estimation gap with a corrective heuristic, and gives every tomorrow block a 'Why' tied to today. B is meaningfully tighter (winning brevity discipline) and equally well-synthesized, but its honest framing and pattern recognition are softer. Even after penalizing A for verbosity, the substantive uplift on three of five dimensions decides it.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a hand-tuned production skill: it references user-specific tooling and conventions (whoop wrapper, ticktick CLI, /minions-learn, /minions-dev-reflect, areas_inbox vs skillia_inbox, kanban.md backlog scoring, cron_log.csv idempotency, 22:30 sleep target absent but Skillia/Acme context deeply integrated) that match this user's CLAUDE.md and memory. B uses generic phase labels ('Quality Gate 1: PASS', 'STANDARD capacity', 'Phase 7 \u2014 Wrap-Up') and writes to Notion DB by ID without the surrounding ecosystem hooks, which fits a freshly-generated skill working from a brief. Moderate-to-high confidence."
}
```


### claude — eod/02-messy-day

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both produce an EOD review with logging and tomorrow's plan. A executes the full multi-phase EOD protocol (guard, fetch, interview, log, tasks review, plan, memory) including calendar creation. B follows a simpler Phase 1-5 structure and gates calendar creation on approval. Both honor the input."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is roughly 2-2.5x longer than B with extensive scaffolding (state file paths, CSV column counts, scoring math, cron_log writes). The additional phases add real value (tasks review, memory breadcrumb, summary footer) but the procedural scaffolding inflates length without proportional reader value. Penalty applied to brevity discipline."
  },
  "scores_A": [
    {
      "dimension": "Synthesis quality",
      "score": 5,
      "justification": "Captures the day's structural failure ('Day overrun by reactive calls - no planned block survived'), interprets the 10x-use-case customer as 'information, not failure,' identifies pricing page as the single launch-gating decision, and ranks deferred items by leverage."
    },
    {
      "dimension": "Pattern recognition",
      "score": 5,
      "justification": "Explicitly flags 'Same shape as last Thursday' (3rd gym skip + reactive-call overrun + 0 deep-work hours on a sprint week) and proposes /minions-reflect, plus connects post-meal crash, energy 2/5, and recovery 41 as a coherent pattern."
    },
    {
      "dimension": "Action specificity",
      "score": 5,
      "justification": "Three time-anchored blocks with explicit Why-tags ('09:30-12:00 Pricing page copy (finish v1 draft)', '13:00-14:30 Outreach + decisions block' with three named tasks, '17:00-18:00 Gym non-negotiable'); calendar events created with IDs and Why descriptions for next-day plan-completion detection."
    },
    {
      "dimension": "Honest framing",
      "score": 5,
      "justification": "Direct on '0/3 blocks - no planned block survived', '3rd gym skip', 'dev_work_today: false (no deep work hours, recap mentions debugging by Eric, not Sir)', and explicitly leaves the 22:00 hire/contract design decision parked rather than forcing closure."
    },
    {
      "dimension": "Brevity discipline",
      "score": 2,
      "justification": "Far longer than B for comparable insight; phases are heavily instrumented (state file paths, CSV column counts, cron_log writes, scoring math like '#sales=5, +#legal proximity \u2192 5') that adds operational ceremony without proportional reader value."
    }
  ],
  "scores_B": [
    {
      "dimension": "Synthesis quality",
      "score": 4,
      "justification": "Reframes the churn-threat customer as a 'fit problem, not product problem' and names the cofounder check-in as 'agenda discipline failed'; identifies 3 postponed decisions as the central blockage but doesn't rank them by leverage or call out the launch-gating asymmetry as sharply as A."
    },
    {
      "dimension": "Pattern recognition",
      "score": 3,
      "justification": "Notes 'third gym miss this week - body knows, recovery confirms it' and outreach debt, but misses the reactive-call-overrun pattern, the post-meal-crash systemic shape, and doesn't link to a prior recurrence."
    },
    {
      "dimension": "Action specificity",
      "score": 2,
      "justification": "9-block schedule starting 08:00-09:30 is concrete, but the input flagged energy 2/5 + recovery 41 + post-meal crash, and B packs 9 blocks into a recovery-day ('STANDARD capacity') including 'OUTREACH/LOOM 5 Looms, no exceptions' which contradicts MAINTAIN logic and doesn't respect likely energy constraints; gym at 11am clashes with stated morning-peak deep work pattern."
    },
    {
      "dimension": "Honest framing",
      "score": 3,
      "justification": "Says '3rd miss this week' and lists postponed decisions, but soft-lands the day with 'Accomplishments: 4 logged' (counting a VC pass and a harsh design review absorption as accomplishments stretches the frame) and doesn't explicitly call out the structural failure of zero planned blocks completed."
    },
    {
      "dimension": "Brevity discipline",
      "score": 4,
      "justification": "Notably tighter than A; respects reader time with a clear schedule table and a compact summary footer, though the 9-block schedule itself is over-prescribed for a recovery-41 day."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins decisively on synthesis, pattern recognition, action specificity, and honest framing - the four substantive dimensions. B is tighter (brevity 4 vs 2) but its tomorrow plan over-schedules a low-recovery day and contradicts its own MAINTAIN-tier logic, undermining action specificity. A's calendar respects the recovery context (3 blocks, gym non-heroic, decisions deferred) and ties Why-tags to next-day completion detection.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A shows production-iteration signals: domain-specific protocol references (cron_log.csv guard rows, habit-tracker.csv 20-column contract, week_type=sprint carry-forward, /minions-reflect proposal, 'Why:' tag convention for next-day plan detection, intensity tiers like MAINTAIN, kanban tag scoring) that align tightly with the vault CLAUDE.md and would be hard to fabricate from a brief. B uses generic EOD scaffolding (Phase 1-5, generic 'STANDARD capacity', plain CSV row, A/B/C approval menu) that reads like a fresh-from-brief implementation. Moderate-to-high confidence."
}
```


### claude — eod/03-meeting-heavy-day

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both perform the EOD task: synthesize the day, log proposal, and propose tomorrow. A includes calendar event payloads with explicit timestamps; B includes a Notion+CSV log proposal and approval gate. Neither violates explicit format/length contracts present in the input."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A is 144 lines, B is 139 lines \u2014 effectively the same length. Both run ~4.5x the input. Neither is meaningfully longer than the other, so no asymmetric verbosity penalty applies."
  },
  "scores_A": [
    {
      "dimension": "synthesis quality",
      "score": 5,
      "justification": "Explicitly names the day's signal \u2014 '4 commitments materialized that didn't exist this morning' and reframes the day as 'a failure of planning surface' rather than execution \u2014 which interprets rather than lists, and ranks Investor 2 deck as the single highest-leverage commitment with a Monday cost."
    },
    {
      "dimension": "pattern recognition",
      "score": 4,
      "justification": "Surfaces non-obvious cascading risk ('left unscheduled tonight, eats Sunday') and links eng-manager off next week to a foreseeable mid-deck-writing fire, plus 'no gym today + closed laptop at 20:30 \u2192 recovery is likely lower than baseline'."
    },
    {
      "dimension": "action specificity",
      "score": 5,
      "justification": "Three time-anchored blocks with explicit 'why' (09:30\u201312:00 Investor 2 deck, 13:00\u201314:00 Acme outreach + scoping, 15:00\u201316:00 Crossroads decision in 60 min, no more), each with calendar event payloads in ISO timestamps and a 30-min sunlight walk pre-block \u2014 respects the post-meeting-day constraint by not stacking."
    },
    {
      "dimension": "honest framing",
      "score": 4,
      "justification": "Calls out 'Pricing page, churn dashboard, support inbox: still untouched. Not adding to tomorrow \u2014 protecting the deck' and frames today's failure mode directly without softening, though slightly less punchy than B's '8 meetings shipped 0 code'."
    },
    {
      "dimension": "brevity discipline",
      "score": 3,
      "justification": "Phase 3.5 (TickTick/Skillia kanban 'unavailable') and the CSV-row narration add load that doesn't earn its space; the advisory section is useful but the 5-phase scaffolding is heavier than necessary for the actual signal density."
    }
  ],
  "scores_B": [
    {
      "dimension": "synthesis quality",
      "score": 4,
      "justification": "Lands a sharp interpretive line \u2014 '8 meetings + Apple Notes \u2260 work. The day produced inputs, not outputs' \u2014 and identifies that customer asks are stacking faster than build capacity, but the rest reads more as a faithful structured list (5 accomplishments, 3 blockers, 3 learnings) than a ranked synthesis."
    },
    {
      "dimension": "pattern recognition",
      "score": 4,
      "justification": "Catches the second-order cost of saying yes immediately to time-off ('cost lands on next week's plan') and flags the build-vs-ask capacity gap, though it doesn't tie the Monday deadline to the eng-manager-off week as a compounding risk the way it could."
    },
    {
      "dimension": "action specificity",
      "score": 3,
      "justification": "Time blocks are concrete (08:00\u201309:30, 10:00\u201311:00, etc.), but the schedule contradicts itself \u2014 declares 'LOW capacity defaults' then schedules TWO deep work blocks plus gym at 11:00 right after them, calling it an 'explicit override'; the plan stacks 9 blocks on a day after a meeting-saturated, recovery-unknown day."
    },
    {
      "dimension": "honest framing",
      "score": 4,
      "justification": "Strong direct lines \u2014 '8 meetings shipped 0 code. The constraint tomorrow is calendar discipline, not effort' and 'Gym skipped today \u2014 held in tomorrow's plan; second skip not advised' \u2014 call out the failure without padding."
    },
    {
      "dimension": "brevity discipline",
      "score": 3,
      "justification": "Phase 5 approval gate (3 options A/B/C) and Phase 7 wrap-up box are scaffolding that repeats information already stated; the run also re-narrates derivations ('deep_work_done=0', 'gym_done=0') that the reader already knows from the input."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on synthesis quality (the 'failure of planning surface' diagnosis ranks and interprets, not just lists) and action specificity (3 protected blocks with calendar payloads that respect the post-meeting-day energy state, vs B's contradictory 'LOW-capacity but 2 deep blocks + gym' override). B has slightly punchier one-liners on honest framing but doesn't close the gap on the two dimensions that decided it.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A shows production-iterated signals: explicit calendar event payloads with ISO timestamps + per-event 'why', a separate 'Notes for Sir (advisory)' section that reads like accreted practice, and constraint reasoning that ties unscheduled commitments to weekend cost ('eats Sunday'). B uses a more rigid Phase 1\u20137 scaffold with formal approval gate and wrap-up box that feels template-driven, and contradicts its own LOW-capacity rule with an immediate override \u2014 the kind of seam a generated skill leaves when stacking generic phases. Moderate confidence."
}
```


### claude — humanizer/01-technical

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the humanizer task: rewrite the AI-flavored input with reduced AI signatures. A takes a more aggressive editorial stance (adds concrete failure modes and tool experience) while preserving the core claim that observability matters and is delivered by tools like LangSmith/Helicone/Langfuse. B keeps the original structure and claim set almost paragraph-for-paragraph but with toned-down vocabulary. Neither violates an explicit format/length contract."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A is somewhat longer than B but the extra length carries concrete information (specific failure modes, tool comparison, named tradeoffs) rather than filler, so no verbosity penalty. B is appropriately concise."
  },
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "Reads like a specific opinionated practitioner: 'A 200 response can still be wrong', 'I've used LangSmith and Langfuse in real projects', 'The honest version: observability won't save a bad app' \u2014 quotable lines with a clear viewpoint and varied sentence rhythm."
    },
    {
      "dimension": "Substance preservation",
      "score": 4,
      "justification": "Keeps the core claims (observability matters, three named tools, ecosystem maturing, teams must engage) and grounds them with concrete mechanisms (prompt/completion/latency/tokens, drift, replay), though it reframes the 'transformative' claim as skepticism rather than restating it."
    },
    {
      "dimension": "AI-signature removal",
      "score": 5,
      "justification": "No banned vocabulary (no delve/journey/tapestry/symphony/paradigm), no 'studies have shown', no inflated rule-of-three; the few em-dashes function as natural asides ('That's it.', 'do roughly the same job') rather than rhetorical pauses."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 4,
      "justification": "Implicitly cuts and reframes the input's unsupported puffery ('paradigm shift', 'symphony of insights') into concrete observable mechanics, and explicitly demotes hype ('observability won't save a bad app'); doesn't use a [FLAG] marker but the editorial stance is visible throughout."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "Short declarative sentences ('That's it.', 'The tooling is the cheap part.'), concrete numbers (40k tokens at 10k users), and clear enumerations ('First\u2026 Second\u2026 Third\u2026') make it markedly easier to scan than the input."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 3,
      "justification": "Less AI-flavored than the input but still neutral and anonymous \u2014 'The takeaway is straightforward' and 'changing how LLM operations are practiced across the industry' could come from any vendor blog; no quotable line identifies a person."
    },
    {
      "dimension": "Substance preservation",
      "score": 4,
      "justification": "Mirrors the input's paragraph structure and keeps every claim (standard requirement, integration, three capabilities, ecosystem maturing, no-longer-optional takeaway), with conservative rephrasing rather than substantive change."
    },
    {
      "dimension": "AI-signature removal",
      "score": 3,
      "justification": "Removed the worst banned vocabulary (no tapestry/journey/symphony/delve) and dropped most inflated phrasing, but retains a rule-of-three ('real-time inference monitoring, semantic drift detection, and intelligent alerting') and vague unsupported claims ('Organizations that invest\u2026 tend to resolve production issues faster')."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "Smoothed unsourced claims into more polished form without flagging or cutting them \u2014 'tend to resolve production issues faster and with more confidence' replaces 'studies have shown' but inherits the same unverified assertion, and no [FLAG] markup or content removal surfaces the weak evidence."
    },
    {
      "dimension": "Readability",
      "score": 4,
      "justification": "Cleaner and more concise than the input, with shorter sentences and less rhetorical machinery, though it still reads like a uniform corporate explainer rather than something with concrete grip."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins decisively on Voice quality, AI-signature removal, Editorial discipline, and Readability \u2014 it produces a specific, opinionated, concretely-grounded rewrite while B mostly performs vocabulary substitution on the same hype-shaped skeleton. B edges A only marginally on Substance preservation by following the input structure more literally, which isn't enough to offset the gap on the other four dimensions.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A shows the kind of editorial judgment a hand-tuned humanizer skill would encode: aggressive de-hyping, first-person grounding, named concrete failure modes, and a willingness to restructure rather than just swap words. B reads like a freshly-generated skill that learned to avoid banned vocabulary but didn't internalize the deeper instruction to flag unsupported claims and inject specificity, so it ends up as a politer version of the same anonymous prose. Moderate confidence \u2014 A could be a strong generated skill, but the consistent practitioner voice across paragraphs is the strongest signal."
}
```


### claude — humanizer/02-marketing

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both perform the humanizer task. A is a conservative copy-edit of the input. B is a more aggressive rewrite that invents specific numerical claims (40 customers, 6\u21922 hours, 12k concurrent users, <4% churn, 4,000-person logistics company) not present in the input. The rubric does not strictly forbid this, but it stretches 'meaning preservation' since the original made no such quantitative claims; B is still task-compliant because the requested task (de-AI the prose) is performed."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A and B are roughly comparable in length (A ~190 words, B ~210 words). No meaningful verbosity gap warranting a penalty."
  },
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 2,
      "justification": "Still reads as anonymous marketing copy: 'shared journey', 'reshaping their industries', 'embrace change', 'cultures of continuous improvement' \u2014 no identifiable viewpoint, just the input with em-dashes swapped for semicolons."
    },
    {
      "dimension": "Substance preservation",
      "score": 5,
      "justification": "Keeps every claim and the three-pillar structure of the original almost verbatim; only minor word swaps ('elegant'\u2192'clean', 'forge partnerships'\u2192'build partnerships', 'dramatic'\u2192'meaningful')."
    },
    {
      "dimension": "AI-signature removal",
      "score": 2,
      "justification": "Several AI signatures survive intact: rule-of-three ('speed, simplicity, and scale'; 'embrace change, use technology strategically, and build cultures'), inflated symbolism ('shared journey', 'reshaping their industries'), and the rhetorical 'The question isn't whether... it's whether' construction."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "Did not flag any unsourced claim ('Customers report meaningful productivity gains within their first 30 days') and silently smoothed inflated language without surfacing the underlying evidence problem; meaning is preserved but the editorial pass is cosmetic."
    },
    {
      "dimension": "Readability",
      "score": 3,
      "justification": "Marginally easier than the input \u2014 em-dashes replaced, a few hedges trimmed \u2014 but sentence rhythm and rhetorical machinery are largely unchanged."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "Distinct, opinionated voice: 'so I'll skip the rapid digital transformation intro', 'we killed three approval steps that nobody could justify', 'we don't do the what's-your-budget gatekeeping thing' \u2014 quotable as a specific writer's stance."
    },
    {
      "dimension": "Substance preservation",
      "score": 3,
      "justification": "Keeps the speed/simplicity/scale frame and the CTA, but invents quantitative claims (40-customer cohort, 6\u21922 hours, <4% churn, 12k concurrent users, 4,000-person logistics customer) that weren't in the input \u2014 adds substance rather than preserving it."
    },
    {
      "dimension": "AI-signature removal",
      "score": 5,
      "justification": "Rule-of-three flattened, no 'shared journey'/'reshaping industries'/'embrace change' filler, no vague attributions; one em-dash remains in the closing line but rhetorical machinery is gone."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 3,
      "justification": "Strong on cutting inflated language and acknowledging trade-offs ('we're not the cheapest, not the most powerful'), but it fabricates specific stats rather than flagging the original's unsourced 'productivity gains' claim \u2014 editorial honesty about limits is high, sourcing discipline is low."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "Short sentences, concrete numbers, no hedge stack; the 'honest part' paragraph and the trade-off framing make it scannable and direct in a way the input and A are not."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on voice quality, AI-signature removal, and readability by clear margins, which are the core dimensions of the humanizer task. A wins substance preservation but only because it barely touched the input. B's weakness is fabricating specifics rather than flagging unsourced claims, but it still scores at parity with A on editorial discipline because A's discipline is purely cosmetic.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B shows the kind of confident, opinionated rewriting (skipping the cliche intro, naming trade-offs, inventing specifics to anchor the prose) that suggests a hand-tuned skill with strong stance directives. A reads like a freshly-generated skill that was conservatively instructed to 'remove AI signatures' and did the minimum literal pass \u2014 em-dash swaps and a few adjective trims \u2014 without internalizing what makes prose actually sound human."
}
```


### claude — humanizer/03-narrative

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform a humanizing rewrite of the original passage and respect the format (single short essay, same heading). Neither flags unsourced claims explicitly, but the rubric does not strictly require flagging."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A is somewhat longer than B but adds substantive concrete detail (the '200 words past midnight' anecdote, the 'open the document' line) rather than padding. B is shorter primarily because it left most of the original prose intact. No verbosity penalty warranted."
  },
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "Reads like a specific person with a viewpoint \u2014 concrete beats like 'type a sentence, hate it, delete it, type a worse one' and 'I'd write 200 words past midnight just to keep the streak alive, and they were bad words' could be quoted and identified as one writer."
    },
    {
      "dimension": "Substance preservation",
      "score": 4,
      "justification": "Keeps all three original insights (quantity precedes quality, voice is found not invented, audience matters less than practice) and the patience/showing-up arc; drops the unsourced 'one writer beautifully put it' quote, which is a defensible cut rather than substance loss."
    },
    {
      "dimension": "AI-signature removal",
      "score": 5,
      "justification": "No em-dashes used as rhetorical pauses, no 'Studies have shown', no 'journey/tapestry/sacred ritual/meditation in motion', no rule-of-three constructions; the inflated symbolism is fully gone."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 4,
      "justification": "Cuts the unverifiable 'as one writer beautifully put it' quote rather than smoothing it, and reframes 'consistency is the cornerstone of skill development' into the plainer 'the honest version of consistency builds skill is that for a long stretch, you're just consistently bad' \u2014 preserves the argument while pruning unsupported language; no explicit [FLAG] markup, hence not a 5."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "Sentence length varies naturally, hedge language is gone, and the closing ('Eventually the second thing turns into the first one, and you don't notice it happening') lands cleanly without rhetorical machinery."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 2,
      "justification": "Still feels smoothed-out and anonymous: 'sacred ritual', 'meditation in motion', 'muse is silent', 'Your future self will thank you' all survive intact \u2014 you couldn't identify a specific writer behind any sentence."
    },
    {
      "dimension": "Substance preservation",
      "score": 5,
      "justification": "Keeps essentially every claim, image, and the unsourced quote from the original \u2014 substance is fully preserved (arguably to a fault, since some of that substance was inflated)."
    },
    {
      "dimension": "AI-signature removal",
      "score": 2,
      "justification": "Em-dashes were converted to commas and 'Studies have shown' was softened to 'I knew consistency mattered', but inflated symbolism ('sacred ritual', 'meditation in motion'), the vague attribution ('As one writer put it'), and the closing 'Your future self will thank you' all remain \u2014 most signatures are still present in different punctuation."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "Smoothed the unsourced 'as one writer put it' quote into more polished form rather than flagging or cutting it, and preserved 'sacred ritual'/'meditation in motion' as if they were verified content \u2014 this is exactly the failure mode the rubric's anchor-1 describes."
    },
    {
      "dimension": "Readability",
      "score": 3,
      "justification": "Marginally easier than the input (em-dashes gone, slightly less hedging) but the rhetorical machinery \u2014 tricolons, abstract metaphors, sermon cadence \u2014 is largely intact, so the reading experience is similar to the original."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins decisively on voice quality, AI-signature removal, and editorial discipline \u2014 it actually performs the humanizing task by replacing inflated metaphors with concrete lived detail and cutting the unsourced quote, while B performs essentially a punctuation pass that leaves the AI-flavored prose intact. Substance preservation is the only dimension where B edges A, and that's because B preserved content the rubric would prefer to see pruned.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a skill that has been tuned over time on what 'humanize' actually means \u2014 replace inflated symbolism with specific detail, cut unverifiable quotes, vary cadence \u2014 which suggests a hand-tuned prompt. B reads like a literal-minded first pass: remove the obvious tells (em-dashes, 'Studies have shown') but otherwise preserve the source, which is the typical behavior of a freshly-generated skill working from a checklist of surface AI patterns."
}
```


### claude — prompt-engineering/01-vague

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the task: diagnose the weak prompt, identify missing structure, and provide a concrete rewrite with output contract. No format violations either side. No caps applied."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "Outputs are roughly comparable in length (~200 vs ~158 lines). A is denser with more code (YAML + Python + tool schema); B is more prose-heavy with the rewrite as plain templates. Neither is meaningfully padded relative to its content density."
  },
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Names five concrete defects (no role separation, zero context, no examples, no output schema, no version pin) and maps each to a specific skill section, plus a sharp root-cause claim ('prose request where you need a parameterized template')."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "Provides a full paste-ready stack: versioned YAML with system_prompt + tool_schema + user_template, a few-shot block, a working Python call with cache_control and tool_choice, and an actual per-call invocation example with realistic args."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "Directly addresses the stated recurring pipeline (3-5 emails/week, varying audiences/features) via parameterized variables, prompt caching, version pinning, eval gate (20-email baseline), and explicit v1/v2 deferral of Reflexion."
    },
    {
      "dimension": "Educational value",
      "score": 4,
      "justification": "Explains the why behind each of the 7 changes and includes a 'what you intentionally are NOT doing' section (no CoT, no ReAct, no Reflexion v1) which teaches selection criteria, but heavy reliance on \u00a7-section cross-refs is more skill-internal than user-pedagogic."
    },
    {
      "dimension": "Calibrated scope",
      "score": 4,
      "justification": "Scope matches the production-pipeline framing in the input, but adds eval gating, agentic contracts, and caching discussion that may exceed what a 3-5/week content team will operationalize on day one; close to over-engineered but defensible given the stated context."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Seven-row failure table covering role/system, audience, product context, goal/CTA, format, examples, and variables, plus the same crisp root-cause framing ('using a prompt where you need a template')."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 4,
      "justification": "Delivers a paste-ready system + user message template with brand voice rules, hard rules, a fixed text output format (SUBJECT/PREVIEW/BODY/CTA), and named variables; lacks a JSON schema or working API/code wrapper, so the contract is text-parsed rather than schema-validated."
    },
    {
      "dimension": "Production fit",
      "score": 4,
      "justification": "Operationally aware (version control, thin variable-rendering wrapper, quarterly few-shot refresh, log every input/output, optional critique pass), but stops short of caching or evaluation tooling that the recurring-pipeline context invites."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "Each fix is explained in terms the user can generalize ('brand voice cannot be described \u2014 it must be demonstrated'; '~70% of inconsistency removed because constant context is now constant'), and the failure-to-fix mapping table makes the lesson portable."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "Scope is well-matched: a structured framework for a recurring multi-input pipeline without piling on eval harnesses, tool-schema JSON, or v2 lever discussions; the closing checklist keeps the deliverable bounded."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on educational value and calibrated scope while tying on diagnostic precision; A wins on concrete rewrite (full code/schema stack) and production fit (caching, eval gate). The deciding factor is that B's rewrite is more directly usable by a content team without an ML/eval setup and explains the underlying lessons in transferable terms, whereas A's edge in code completeness comes bundled with scope creep (eval gate, agentic contracts, caching) that the user did not ask for.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A's repeated cross-references to numbered skill sections (\u00a71-\u00a76), the deliberate 'what you are NOT doing' callouts (no CoT/ReAct/Reflexion), and the layered v1/v2 versioning discipline read like a hand-tuned skill that has accumulated production scar tissue. B is cleaner and more pedagogically structured but more generic in its toolchain (no JSON schema, no caching, plain text output contract), which is consistent with a freshly generated skill working from a brief. Moderate confidence; B's checklist and operational-recommendations sections are also a hand-tuned tell, so this is not certain."
}
```


### claude — prompt-engineering/02-over-broad

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs diagnose the weak prompt and produce a paste-ready rewrite with explicit output contract, length caps, and what to omit. A references unspecified 'Section 1/3/4/6' of a production reference the user did not provide, but the rewrite itself is self-contained. Both respect the stated Slack-message context."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer (system prompt + JSON tool schema + user template + deterministic Slack renderer + before/after table + operational follow-ups) for comparable diagnostic and rewrite utility. The extra renderer-and-schema scaffolding is infrastructure beyond what the stated Slack-message use case requires. Penalty applied to calibrated scope and production fit."
  },
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 4,
      "justification": "Names four specific failure modes (no system contract, six concerns flattened, no usage-pattern constraint, unstructured output) plus a latent 30k-LOC context-window issue, but anchors them to unspecified 'Section 1/3/4/6' of an external reference rather than naming the prompt-engineering primitives directly."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "Provides a fully paste-ready package: cached system prompt with explicit CONTRACT rules, a complete JSON tool_use schema with enums and char limits, a user template with variable, and a deterministic renderer \u2014 every output-contract element is present."
    },
    {
      "dimension": "Production fit",
      "score": 3,
      "justification": "Forces JSON tool_use output for a Slack message, which then requires a separate deterministic renderer step; Slack natively renders mrkdwn, so the JSON+renderer pipeline is heavier than the stated <2-min Slack read pattern needs."
    },
    {
      "dimension": "Educational value",
      "score": 4,
      "justification": "The before/after table maps each change to a reason ('format rules belong in system', 'structured output is the only reliable path'), but several reasons cite external section numbers rather than explaining the underlying prompt-engineering principle in place."
    },
    {
      "dimension": "Calibrated scope",
      "score": 3,
      "justification": "Adds JSON schema infrastructure, a separate renderer, eval harness suggestions, and pipeline upstream work; for a 'rewrite this prompt so it fits Slack' problem, this is over-engineered relative to B's direct Markdown approach."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Names seven specific failure modes \u2014 no persona, no output contract, no usage context, no prioritization, undefined 'actionable', no few-shot, lost-in-the-middle \u2014 and reframes the underlying mismatch as classification+ranking miscast as enumeration, which is the load-bearing diagnosis."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "Paste-ready system + user message with role, hard 200-word cap, exact output structure template, severity tags with drop-minor rule, an embedded few-shot example, and instruction restated at the end to counter recency loss."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "Output is Slack-flavored Markdown matching how Slack renders natively, 200-word cap fits the <2-min read budget, verdict-first inverted-pyramid lets the engineer stop after line 1, and explicitly rejects JSON because 'Slack renders Markdown; an extra parse step buys nothing here.'"
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "The 'Why this works' table maps each change to a mechanism (e.g., 'length anchor + recency reinforcement counters lost-in-the-middle'), and the 'What NOT to do' section teaches generalizable lessons (CoT will balloon triage output, more axes = more buckets the model dutifully fills)."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "Single rewrite sized to the problem \u2014 no extra renderer, no schema infrastructure, no upstream pipeline detour \u2014 plus a 'Knobs to tune later' list that defers complexity until evidence demands it."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on production fit (Markdown matches Slack natively; A's JSON+renderer adds an unnecessary parse step), calibrated scope (B is sized to the stated problem while A adds schema infra and a separate renderer), and diagnostic precision (B identifies 7 specific prompt-engineering failure modes including the load-bearing classification-vs-enumeration reframe). A's rewrite is rigorous but over-engineered for a Slack triage card.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B reads as hand-tuned: it correctly resists the temptation to JSON-schema everything ('Slack renders Markdown; an extra parse step buys nothing here'), includes a 'What NOT to do' section that only emerges from production experience, and ties techniques to mechanisms rather than to section numbers. A leans on references to 'Section 1/3/4/6' of an unstated production guide and reaches for tool_use+JSON+renderer as a default \u2014 patterns common in freshly-generated outputs that apply a reference template uniformly rather than fitting it to the channel."
}
```


### claude — prompt-engineering/03-under-specified

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested task: diagnose weaknesses, produce a rewritten paste-ready prompt, and explain each addition. Both respect the implicit output contract (diagnosis + rewrite + per-addition justification). No caps applied."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "Outputs are comparable in length (~150 lines each). Neither is meaningfully longer; no penalty warranted."
  },
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Names eight specific missing dimensions (role/audience, length contract, format contract, definition of summary, input-variability handling, audience model, refusal policy, grounding rule) and frames it as a system-prompt problem rather than generic 'be more specific' advice."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "Provides a fully paste-ready system+user prompt with role, audience model, definition-of-done, an input-size-tied length contract table, exact four-section format, grounding rules, style rules, edge cases, output discipline, and XML-delimited untrusted input \u2014 all elements of the rubric's 5-anchor."
    },
    {
      "dimension": "Production fit",
      "score": 4,
      "justification": "Tailored to the B2B reading-list, executive-skim context (60-second read, mobile, 'so what' line, source-signal metadata for ranking layer); next-steps cover eval set, Git versioning, token tracking, post-check validator \u2014 but lacks explicit prompt-caching/KV-cache guidance that the recurring-pipeline context implies."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "Per-addition changelog table maps each rule to the failure mode it fixes, plus a 'deliberately did not add' section explaining why few-shot/CoT/persona flourishes were excluded \u2014 teaches the meta-principle of constraint selection."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "Length matches the problem: a structured-but-not-bloated rewrite with diagnosis, prompt, justification table, anti-additions, and shipping checklist \u2014 every section earns its place and the prompt itself is self-contained without external references."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 4,
      "justification": "Four-row reliability-test table is sharp (deterministic length, format, audience tone, stable behavior across input size) and adds eight specific missing constraints with section refs, but the diagnosis leans on external 'Section 1-6' references instead of standing on its own analysis."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 4,
      "justification": "Provides system prompt + user template + few-shot block with hard word counts, four labeled sections, lead-with-conclusion rule, failure modes, and a SOURCE FIDELITY line \u2014 but the few-shot block is incomplete ('Add 1-2 more examples covering...') and the design choice to ignore input size diverges from the user's stated 800-word-vs-15-page concern."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "Strongest production signals: explicit cache_control/KV-cache reuse, JSON Schema/tool_use suggestion for the reading-list UI, count_tokens guidance for long PDFs, version-as-yaml, eval baseline of 50 articles \u2014 all directly map to the recurring-pipeline B2B reading-list context."
    },
    {
      "dimension": "Educational value",
      "score": 4,
      "justification": "Per-addition table cross-references reference sections and a 'deliberately NOT added' section explains CoT/Reflexion/ReAct exclusions, but the heavy reliance on '\u00a71-\u00a76' citations means the user must have the reference doc to fully extract the lesson."
    },
    {
      "dimension": "Calibrated scope",
      "score": 4,
      "justification": "Similar length to A and well-structured, but the constant 'Section X' scaffolding feels like skill-internal context leaking into the output, slightly inflating perceived scope without adding standalone value."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on concrete rewrite and calibrated scope: its length contract scales with input size (directly addressing the user's 'sometimes 2 sentences, sometimes 800 words' complaint), and the prompt is fully self-contained whereas B's output and changelog repeatedly defer to external '\u00a71-\u00a76' references the user does not possess. B has a real edge on production fit (prompt caching, JSON Schema, count_tokens) but loses ground on diagnostic precision and educational value because of the external-doc dependency.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "B's repeated citations to numbered reference sections ('\u00a71 Role separation', '\u00a74 Structured output', '\u00a73 KV-cache') read as a freshly-generated skill cross-referencing its own internal prompt-engineering reference document \u2014 a tell of generated output that hasn't been smoothed of its scaffolding. A reads as hand-tuned: self-contained, opinionated phrasing ('If you exceed the cap, you have failed. Cut.'), and a deliberate 'what I did not add' section that signals iterative refinement against real failure modes."
}
```


### claude — remember/01-insight

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the capture task with structured sections. A uses an ID/Confidence/Times-referenced metadata pattern but no YAML frontmatter; B uses YAML frontmatter with type/date/tags/context. Both retain the requested tags and connection hints from the input. Neither violates an explicit format contract."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer (8 sections including 'Warning Signs', 'References', 'Created by/Last updated/Times referenced' boilerplate) without delivering proportionally more durable insight than B. B is tighter and equally actionable, so A is penalized on Distillation and Structure for ceremony that does not earn its space."
  },
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 3,
      "justification": "Has clear headings (What Went Wrong, Root Cause, The Fix, How to Avoid, Warning Signs, Related Items, References) but no YAML frontmatter and bolts on low-value metadata ('Times referenced: 0', 'Created by: Sir') that clutters the 5-second scan."
    },
    {
      "dimension": "Distillation",
      "score": 3,
      "justification": "Faithfully captures the lesson with extra heuristics ('two questions before shipping', warning signs), but at ~330+ words the note is longer than the input rather than sharper, and several paragraphs restate the same 'optional but load-bearing' point."
    },
    {
      "dimension": "Title quality",
      "score": 4,
      "justification": "'Optional onboarding steps that gate value-realization silently kill conversion' is a claim-shaped title that composes into reasoning, though the 'Learning:' prefix and length make it slightly less crisp than an ideal claim-title."
    },
    {
      "dimension": "Connection-making",
      "score": 3,
      "justification": "Names the activation-vs-acquisition framework and prior trial-conversion analyses with brief 'why' annotations ('textbook activation failure being misdiagnosed'), but the links are not wikilinks and the rationale is thin compared to the rubric's 5-anchor."
    },
    {
      "dimension": "Tag discipline",
      "score": 2,
      "justification": "Tags are 'growth, onboarding, conversion, activation, lessons-from-data' \u2014 a near-verbatim copy of the input's generic tags; misses sharper, searchable tags like 'activation-funnel', 'value-realization', or 'optional-step-trap' that the rubric explicitly calls out."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 4,
      "justification": "YAML frontmatter (type, date, tags, context) plus Summary / Detail / How to Detect / Consequences / Links is scannable in 5 seconds and follows a recognizable gotcha-learning template without ceremonial filler."
    },
    {
      "dimension": "Distillation",
      "score": 4,
      "justification": "Names the precise reasoning error (two definitions of 'working'), generalizes the lesson beyond this funnel ('any onboarding step that produces the conditions for first-value cannot be optional'), and stays roughly input-length while being sharper and more findable by the problem it solves."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "'Optional Activation Steps Cap Conversion When the Product Has No Value Without Them' is a compound claim \u2014 exactly the rubric's anchor for a 5: a linkable sentence that composes into reasoning chains."
    },
    {
      "dimension": "Connection-making",
      "score": 3,
      "justification": "Lists previous trial-conversion analyses and the activation-vs-acquisition framework with one-line 'why' annotations ('canonical example of activation as the binding constraint'), but still uses plain-text references rather than wikilinks and offers no second-order links."
    },
    {
      "dimension": "Tag discipline",
      "score": 3,
      "justification": "Tags ([growth, onboarding, conversion, activation, funnel]) are still mostly generic and inherited from the input, but 'funnel' replacing 'lessons-from-data' is marginally sharper and the YAML 'type: gotcha-learning' acts as an additional categorical handle."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on Title quality (a textbook claim-title), Structure (frontmatter + clean sections without boilerplate), and Distillation (names the underlying reasoning error and generalizes the lesson). A's extra sections ('Warning Signs', 'References', 'Times referenced: 0') add length without proportional insight, triggering the verbosity penalty, and A's tag set is a verbatim copy of the input.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B's tighter template (YAML frontmatter, named 'gotcha-learning' type, consistent How to Detect / Consequences sections) reads like a refined recurring pattern, while A's 'Confidence: 0.85', 'Times referenced: 0', and 'Created by: Sir (captured via /remember)' boilerplate look like a freshly-generated skill imagining what a vault note 'should' contain. A's near-verbatim reuse of input tags also suggests less iteration than a hand-tuned skill would have produced."
}
```


### claude — remember/02-reference

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both perform the requested task: capture an architectural decision as a structured note. A uses an explicit ADR template with ID/Confidence/Created-by metadata; B uses YAML frontmatter plus a claim-based title and prose body. Neither violates any explicit format constraint from the input (the input asks for an 'architectural decision record' generically)."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A and B are roughly comparable in length (A ~70 lines of mostly bulleted sections; B ~43 lines of denser prose). Neither is meaningfully longer than the other while equally useful, so no verbosity penalty is applied."
  },
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 5,
      "justification": "Clean ADR scaffold (ID, Date, Tags, Confidence, Context, Decision, Rationale, Alternatives, Trade-offs, Migration Triggers, Impact, Related, References, Created by, Times referenced) that is scannable in under 5 seconds and consistent with standard ADR conventions."
    },
    {
      "dimension": "Distillation",
      "score": 3,
      "justification": "Faithfully captures the input but is roughly the same length and reads as a re-organized transcription rather than a sharper, shorter durable lesson; the migration trigger logic is preserved but not elevated as the central finding."
    },
    {
      "dimension": "Title quality",
      "score": 2,
      "justification": "'Decision: Use FastAPI BackgroundTasks instead of Celery for async workflows' is a topic/decision label, not a claim \u2014 it does not compose into reasoning chains the way a lesson-shaped title would."
    },
    {
      "dimension": "Connection-making",
      "score": 3,
      "justification": "Includes one real wikilink [[Boring Tech Wins]] with a one-line why ('complexity must be earned by real constraints, not anticipated ones') plus placeholder TBD references and a parenthetical about previous async-workflow notes that is not actually linked."
    },
    {
      "dimension": "Tag discipline",
      "score": 2,
      "justification": "Tags are copied verbatim from the input ('backend, async, architecture, fastapi, celery, decision') and include the generic catch-all 'decision'; no problem-shaped tags like 'background-tasks', 'in-process-queue', or 'migration-trigger' that would make this findable by the problem it solves."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 4,
      "justification": "YAML frontmatter (type, date, tags, context) plus Summary / Detail / Alternatives Considered / Consequences / Links \u2014 clean and scannable, though slightly less ADR-conventional than A and the prose-heavy Detail section trades scan-speed for narrative."
    },
    {
      "dimension": "Distillation",
      "score": 4,
      "justification": "Extracts the durable lesson into the title itself ('Beats Celery Until We Cross 60s p99 or 8 Workflows') and the Summary states the trade in one sentence; future-self can act on the migration triggers without re-reading the body."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "'FastAPI BackgroundTasks Beats Celery Until We Cross 60s p99 or 8 Workflows' is a claim-shaped title encoding both the decision and its falsification conditions, exactly the rubric's anchor for a 5."
    },
    {
      "dimension": "Connection-making",
      "score": 2,
      "justification": "Links section names 'previous async workflow patterns notes' with a file path and the 'boring tech wins' principle, but neither is a wikilink and there is no sentence on why each connection matters \u2014 closer to a reference list than composable links."
    },
    {
      "dimension": "Tag discipline",
      "score": 3,
      "justification": "Drops the generic 'decision' tag from the input but otherwise keeps the same topic-level tags ('backend, async, fastapi, celery, architecture'); none are problem-shaped (e.g., 'in-process-tasks', 'broker-vs-inproc'), so searchability by problem is only modestly better than A."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on the two dimensions most central to a 'remember' note: title quality (claim-shaped, encoding the migration trigger directly in the title) and distillation (the lesson is extractable from the title + summary alone). A wins narrowly on structure (cleaner ADR scaffold) and connection-making (one real wikilink with a why), but those gains do not outweigh B's title and distillation advantage.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A reads like a freshly-generated skill faithfully filling an ADR template (uniform sections, placeholder fields like 'Times referenced: 0' and 'TBD', tags copied verbatim from the input). B shows the kind of opinionated craft a hand-tuned skill tends to encode: claim-as-title with the migration trigger baked in, a prose Detail section that prioritizes the load-bearing reasoning, and a smaller, slightly cleaner tag set. Moderate confidence \u2014 the placeholder-heavy ADR template in A is the strongest signal."
}
```


### claude — remember/03-reflection

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs capture the behavioral lesson as a structured note suitable for a permanent vault, with title, tags/metadata, body, and links. Neither violates an explicit format contract."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer (eight sections including 'Warning Signs', 'Evidence Base', 'References', and a footer with 'Times referenced: 0') without delivering proportionally more durable insight than B. Penalty applied primarily to distillation."
  },
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 4,
      "justification": "Clean scannable layout with ID, Date, Tags, Confidence header and consistent H2 sections, but the proliferation of sections (Warning Signs, Evidence Base, References, footer with 'Times referenced: 0') adds scan friction rather than reducing it."
    },
    {
      "dimension": "Distillation",
      "score": 3,
      "justification": "Faithfully restates the input and adds plausible mechanistic vocabulary (catecholamine, BDNF, open-loop) but is roughly the same length as the input plus headings; a great remember note should be shorter and sharper, and this one trends toward expansion."
    },
    {
      "dimension": "Title quality",
      "score": 4,
      "justification": "'Workout Before Deep Work Yields 2-3x Output vs Workout After' is a clear claim-title with the magnitude embedded, though the 'Learning:' prefix and comparative phrasing make it slightly less pithy than it could be."
    },
    {
      "dimension": "Connection-making",
      "score": 3,
      "justification": "Lists three related items (WHOOP recovery, post-meal-crash protocols, deep-work-block scheduling) with brief parenthetical 'why' notes, plus a cross-domain bridge sentence \u2014 adequate but the parentheticals are thin and not wikilinked."
    },
    {
      "dimension": "Tag discipline",
      "score": 2,
      "justification": "Tags are copied verbatim from the input ('personal, productivity, focus, exercise, patterns, sir-self-knowledge') with no curation toward more searchable specificity like 'workout-timing' or 'deep-work-stack'; generic tags dominate."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 5,
      "justification": "YAML frontmatter (type, date, tags, context) plus a tight Summary / Detail / How to Detect / Consequences / Links arc \u2014 five-second scannable, with the frontmatter giving machine-readable metadata that A lacks."
    },
    {
      "dimension": "Distillation",
      "score": 4,
      "justification": "Opens with a 4-sentence Summary that captures the durable rule and false-economy framing, then expands only enough to support detection signals; tighter than A while preserving the same evidence (18 days, 3-day control, three mechanisms)."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "'Skipping the Gym to Protect Deep Work Halves Deep-Work Output' is a sharp claim-title framed as the anti-pattern/false-economy (the actual lesson), making it findable by the problem it solves rather than the topic it mentions."
    },
    {
      "dimension": "Connection-making",
      "score": 3,
      "justification": "Three links with one-line 'why' annotations (recovery score correlates with timing tolerance; calendar protocol must encode rule; morning stack avoids crash window) \u2014 better-explained than A's parentheticals but still not wikilinked and the 'why' lines are short."
    },
    {
      "dimension": "Tag discipline",
      "score": 3,
      "justification": "Tags drop the generic 'personal' from the input list but keep mostly the same set ('productivity, focus, exercise, patterns, sir-self-knowledge'); no specific searchable tags like 'workout-timing' or 'morning-stack' added, but slightly more curated than A."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on title quality (the anti-pattern framing makes the lesson findable by the trap it prevents), structure (frontmatter + tighter section arc), and distillation (opens with a usable summary, less section sprawl). A is competitive on title and connection-making but loses on verbosity and tag discipline.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A reads like a freshly-generated skill following a verbose template (ID field, Confidence score, 'Times referenced: 0' counter, eight section headings including 'Warning Signs' and 'References' that the input doesn't motivate) \u2014 these look like template scaffolding rather than earned conventions. B's frontmatter + Summary/Detail/How-to-Detect/Consequences pattern is leaner and feels like a refined recurring shape, with title-as-anti-pattern phrasing that suggests an iterated skill. Moderate confidence; A's polish could also be a generated skill over-fitting to a 'comprehensive' template."
}
```


## GPT54 judge (15 pair scorings)


### gpt54 — 5d-thinking/01-career

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested 5D-style decision analysis, stay on-task, and end with decision-sharpening guidance; no score cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "Output B is substantially longer, but its added length contributes real analysis and concrete next steps rather than pure padding, so no formal penalty was applied."
  },
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "It cleanly separates Individual Inner, Individual Outer, Collective Inner, Collective Outer, and Historical Pattern, with genuinely different lenses like identity, negotiation structure, social scripts, market structure, and archetypal timing."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It surfaces several resisted blind spots directly, especially that the user has 'collapsed a multi-variable career, family, and market decision into a single question of personal honesty' and is treating negotiable terms as fixed."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "The synthesis materially sharpens the choice by reframing it as a negotiation/modeling problem first and prescribing three concrete artifacts before treating it as a values decision."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "It is tightly grounded in this case, citing the 6-year tenure, Series B equity, kid on the way, 14-day clock, and specific asks like accelerated vesting, delayed start, and acquihire scenarios."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It names the avoided truth bluntly, including 'you are currently closer to the second group' and 'you have not earned the right to that question yet,' which is unusually direct without becoming sloppy."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "It covers multiple real angles beyond finance, including identity, partner dynamics, skill development, optionality, founder psychology, reversibility, timing, and systemic constraints."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It surfaces uncomfortable omissions clearly, such as sunk-cost reasoning, projecting a conservative view onto the partner, and using 'lottery tickets' as a generic dismissal to avoid company-specific diligence."
    },
    {
      "dimension": "Decision-relevance",
      "score": 4,
      "justification": "The 'Key Constraints Identified' and 72-hour action list are useful, but the output expands the space more than A and gives a slightly less sharp synthesis of what should decide the choice."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 4,
      "justification": "It is well tailored to this user's startup-vs-Series-B dilemma, but parts of it drift into a fairly standard startup-diligence checklist that could transfer to many senior-career startup decisions."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "It is candid about identity cover stories, especially 'is the kid the reason not to go, or the justification,' but it is a bit more diplomatic and less piercing than A's hardest lines."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on decision-relevance, specificity, and honest discomfort. Both outputs are strong on frame diversity and blind-spot surfacing, but A is more incisive and reaches a cleaner decision-sharpening reframe with less sprawl.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A looks more hand-tuned because it has a distinctive operating voice, a crisp 5D execution pattern, and a tightly engineered synthesis rather than an expansive checklist. B is strong, but its broader taxonomic framing, heavier bulleting, and more generic diligence coverage read more like a capable workflow-generated expansion from a brief."
}
```


### gpt54 — 5d-thinking/02-partnership

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested multi-dimensional analysis of the co-founder dilemma and provide decision-helpful reframings; no task-compliance score caps apply."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "No explicit verbosity penalty applied: A is substantially longer, but it uses the space to add distinct frames, blind spots, and process interventions rather than pure repetition."
  },
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "It cleanly separates \"Individual Inner,\" \"Collective Inner,\" \"Individual Outer,\" \"Collective Outer,\" and \"Historical Pattern (Time),\" and each lens introduces materially different explanatory logic."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It names resisted possibilities directly, including identity protection, inherited startup ideologies, the binary framing itself, and a \"trust-based deadlock\" that is silently shaping the argument."
    },
    {
      "dimension": "Decision-relevance",
      "score": 4,
      "justification": "It gives concrete moves like side-by-side 90-day plans, a third-option partial raise, and a hard decision rule, but the amount of analysis slightly expands the cloud before it narrows it."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "The analysis is tightly anchored to this case through details like \"$3M,\" \"$80-100k MRR,\" \"12% MoM,\" warm inbound after \"TechWeek,\" and the concrete SAFE/partial-raise alternative."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It is unusually direct in lines like \"both are vibes, dressed in the language of strategy\" and in saying the real split may be over \"what game you are each playing,\" not timing."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 4,
      "justification": "It does cover all five 5D lenses, but several sections stay closer to the same fundraising-vs-bootstrap axis and open fewer distinct reframes than A."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It surfaces hidden drivers well: control and earnedness, fear of missing the window, the co-founder norm that \"the best argument wins,\" and the risk of resentful deference."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "It sharpens the choice to one decisive test question \u2014 \"What would $3M let us do in the next 6 months that $1M could not?\" \u2014 and clearly states how each answer should change the decision."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "It stays highly concrete to this company by citing \"$3M vs. $1M,\" \"12% MoM,\" \"TechWeek inbound,\" and the operating cost of spending \"8-12 weeks\" fundraising."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It does not soften the hard truth that \"one of you has to defer\" and that a vague raise case would amount to \"fear of missing out\" rather than a real capital plan."
    }
  ],
  "winner": "TIE",
  "winner_reasoning": "A is stronger on frame diversity and breadth of blind-spot surfacing, while B is stronger on decision-relevance and compression. Both are highly specific to the situation and candid enough that neither establishes a clear overall edge once the rubric is applied dimension by dimension.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads more like an iterated production skill: the taxonomy is integrated into the reasoning rather than just imposed on top of it, and it adds mature facilitation moves like a third option, decision rules, and operating-plan comparisons. B feels more workflow-generated because of the explicit \"Trap detected\" wrapper and the rigid D1-D5 march; it is good, but its structure is more templated and its synthesis more compressed. "
}
```


### gpt54 — 5d-thinking/03-scope

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested multi-dimensional analysis, surface blind spots, and end with decision-sharpening guidance; no task-compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A is materially longer, but its extra length adds distinct frames, concrete feature grouping, and negotiation/re-costing moves, so it is not just longer for its own sake."
  },
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "A presents genuinely different lenses across psychology, customer politics, behavior, system incentives, and historical pattern rather than repeating one thesis in new words."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It names resisted blind spots directly, including 'fear of the renewal call,' 'sunk-identity in being responsive,' the false {10,3,0} option set, and the unasked question of talking to the economic buyer."
    },
    {
      "dimension": "Decision-relevance",
      "score": 4,
      "justification": "It sharpens the decision with a clear sequence\u2014discovery call, re-cost with vendors, split platform vs bespoke, negotiate renewal as a package\u2014but is a bit sprawling before it lands the choice architecture."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "It is tightly grounded in this case, explicitly sorting features like SSO/SCIM/data residency versus white-label/import/PagerDuty and tying them to the 40% ARR concentration and other customers' P1s."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "A states the hard truth bluntly: building all 10 turns the company into 'that whale's internal IT team,' and not making the call is framed as fear-driven avoidance rather than prudence."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 4,
      "justification": "B cleanly walks the five dimensions, but many sections still orbit the same anchor-customer/custom-shop thesis more than opening sharply different angles."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It forcefully surfaces what the user is avoiding, calling the 40% ARR concentration 'a strategic failure already in progress' and the two days of analysis 'avoidance.'"
    },
    {
      "dimension": "Decision-relevance",
      "score": 4,
      "justification": "The synthesis is actionable, especially the economic-buyer call and platform-vs-bespoke split, but the recommendation to 'ship the 4 platform items' leans more certain than the provided capacity and evidence support."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "B stays concrete to this decision by naming specific features, internal stakeholder dynamics, renewal leverage, and the likely consequences for the queued P1 customers."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It directly names the uncomfortable identity stake\u2014'building all 10 makes you a custom-software shop with one client'\u2014without softening the implication."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on frame diversity and overall decision quality. Both outputs are strong on blind-spot surfacing and honest discomfort, but A opens more distinct lenses, avoids overcommitting to a specific build plan, and gives a better path to reduce uncertainty before locking the roadmap.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a skill refined over time: the structure is more deliberately layered, the transitions are more natural, and the guidance expands from diagnosis to negotiation mechanics to portfolio risk without feeling rigidly templated. B is strong but shows more workflow-template signals, especially the explicit D1-D5 march and the formulaic '[5D] Trap detected' framing, which feels more freshly generated from the brief."
}
```


### gpt54 — eod/01-concise-day

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs do the requested EOD task: they synthesize the day, include logging artifacts, and propose tomorrow's plan, so no compliance cap applies. A overreaches by assuming approvals and executing follow-on actions; B is cleaner but leaves calendar writes pending approval."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer without being more useful, so its synthesis and brevity scores were held down rather than rewarding extra scaffolding. B is still verbose, but it is materially tighter and more information-dense than A."
  },
  "scores_A": [
    {
      "dimension": "Synthesis quality",
      "score": 3,
      "justification": "The closing summary correctly identifies the two real leverage points, 'Trail of Bits quote' and 'Marketing pricing-page scope,' but most of the output is execution trace rather than synthesis of what mattered."
    },
    {
      "dimension": "Pattern recognition",
      "score": 4,
      "justification": "It goes beyond restatement by naming an 'estimation gap on JWT rotation,' a 'post-lunch crash with no reset protocol,' and a 'threat-model-first heuristic' for future crypto work."
    },
    {
      "dimension": "Action specificity",
      "score": 4,
      "justification": "Tomorrow's plan is concrete and time-anchored with blocks like '09:30\u201312:00 \u2014 Pricing page scope + draft' and '13:00\u201314:00 \u2014 Trail of Bits outreach + Acme follow-up.'"
    },
    {
      "dimension": "Honest framing",
      "score": 2,
      "justification": "It does call out context-switching and the energy crash directly, but it undercuts trust by using 'Assumed approvals' and inferring unsupported habit misses such as 'No sunlight, no meditation, no reading, no prayer today.'"
    },
    {
      "dimension": "Brevity discipline",
      "score": 1,
      "justification": "This is far longer than the source notes and spends large sections on guard files, cron logs, state transitions, and tool traces that do not earn their keep."
    }
  ],
  "scores_B": [
    {
      "dimension": "Synthesis quality",
      "score": 4,
      "justification": "It cleanly distills the day into accomplishments, blockers, learnings, and a single 'Tomorrow's focus,' which captures the launch delay and Acme security-review dependency without drowning in detail."
    },
    {
      "dimension": "Pattern recognition",
      "score": 4,
      "justification": "It surfaces useful non-obvious reads such as 'Security review request = warm signal, not friction' and carries the 15:00 crash forward as a scheduling constraint."
    },
    {
      "dimension": "Action specificity",
      "score": 3,
      "justification": "It gives specific anchors like '08:00\u201309:30 DEEP WORK \u2014 Scope pricing page' and '09:30\u201310:00 \u2014 request Trail of Bits quote,' but then invents several generic blocks like 'OUTREACH / LOOM' and 'Wind-down' with no basis in the input."
    },
    {
      "dimension": "Honest framing",
      "score": 4,
      "justification": "It plainly states 'Pricing page blocks marketing launch,' 'Acme blocked on Trail of Bits security review quote,' and '30 min lost to context-switching' without padding the day as uniformly positive."
    },
    {
      "dimension": "Brevity discipline",
      "score": 2,
      "justification": "It is still substantially longer than the notes and wrapped in phase machinery, but it is much tighter than A and keeps more of the text focused on the actual day review."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on synthesis quality, honest framing, and brevity discipline. A is stronger on action specificity and arguably pattern depth, but its extreme verbosity and fabricated approvals make it less trustworthy and less useful per line.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A looks hand-tuned for a real user environment because it contains many idiosyncratic integrations and safeguards: cron logs, state files, TickTick, kanban parsing, memory breadcrumbs, and '/minions-*' hooks. B reads more like a freshly generated workflow implementation: cleaner and more generic, with templated sections and filler schedule blocks such as 'OUTREACH / LOOM' and 'Wind-down' that feel plausible but not deeply personalized."
}
```


### gpt54 — eod/02-messy-day

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Neither output needs a compliance cap: both produce a structured EOD review with logging context and a tomorrow plan. B stops at an approval gate for calendar creation, but it still fulfills the requested synthesis/plan contract closely enough that no 3/5 cap is warranted."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer than B while not proportionally more useful as an end-user EOD, so the penalty is reflected primarily in Brevity discipline and slightly in Synthesis quality because process scaffolding crowds the actual review."
  },
  "scores_A": [
    {
      "dimension": "Synthesis quality",
      "score": 3,
      "justification": "It identifies the core story ('Four reactive calls ate the day' and 'Pricing page still incomplete \u2014 gating launch') but buries that synthesis under extensive guard/log/state details."
    },
    {
      "dimension": "Pattern recognition",
      "score": 5,
      "justification": "It surfaces a strong cross-note pattern \u2014 '3rd gym skip + reactive-call overrun + 0 deep-work hours on a sprint week' \u2014 and ties it to low recovery and repeated Thursday drift."
    },
    {
      "dimension": "Action specificity",
      "score": 5,
      "justification": "The tomorrow plan is concrete and time-anchored ('09:30\u201312:00 \u2014 Pricing page copy', '13:00\u201314:30 \u2014 Outreach + decisions block', '17:00\u201318:00 \u2014 Gym') with realistic scope for a low-recovery day."
    },
    {
      "dimension": "Honest framing",
      "score": 5,
      "justification": "It is blunt about underperformance ('0/3 blocks', 'no planned block survived', 'Third skipped gym this week') and explicitly defers major decisions because energy is low instead of pretending they were handled."
    },
    {
      "dimension": "Brevity discipline",
      "score": 1,
      "justification": "The output is several times longer than the source notes and spends huge space on phase plumbing, file paths, command snippets, and state transitions rather than the review itself."
    }
  ],
  "scores_B": [
    {
      "dimension": "Synthesis quality",
      "score": 4,
      "justification": "It extracts the main day narrative cleanly \u2014 reactive calls, staging incident, missing churn dashboard, and deferred decisions \u2014 and adds a useful read that the churn-risk customer is a fit problem."
    },
    {
      "dimension": "Pattern recognition",
      "score": 4,
      "justification": "It notices meaningful patterns like 'agenda discipline failed,' the third gym miss, and the customer/pricing mismatch, though the insights are less layered and less distinctive than A's."
    },
    {
      "dimension": "Action specificity",
      "score": 2,
      "justification": "The plan is time-anchored, but it over-invents tomorrow with blocks like '5 Looms, no exceptions,' 'NSDR / quiet,' and '21:00\u201321:30 Wind-down' that are not grounded in the notes and feel calendar-naive."
    },
    {
      "dimension": "Honest framing",
      "score": 4,
      "justification": "It directly names '3 decisions postponed,' two-day inbox neglect, and the third gym miss, although the 'Accomplishments' framing slightly polishes a day the notes call 'unfocused'."
    },
    {
      "dimension": "Brevity discipline",
      "score": 4,
      "justification": "It still carries some workflow scaffolding, but it is materially tighter than A and keeps most of its space on synthesis, carry-forwards, and tomorrow's plan."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins narrowly because it delivers solid synthesis and honest framing in a much more usable length. A is stronger on pattern recognition and action specificity, but its severe verbosity is a real failure mode for an EOD workflow and pulls it behind overall.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A looks like the hand-tuned skill because it contains deeply specific operational machinery: guard rows, state files, carry-forward logic, TickTick/Vault/kanban integration, memory breadcrumbs, and idiosyncratic conventions like '/minions-reflect' and 'Sir.' B reads more like a fresh workflow-derived build: the structure is generic, some details feel invented ('5 Looms, no exceptions', 'Sleep target: 22:30'), and there are small coherence tells such as '7 blocks proposed' followed by more than seven blocks."
}
```


### gpt54 — eod/03-meeting-heavy-day

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the core EOD task: they synthesize the day, include logging/calendar-oriented sections, and propose a tomorrow plan. A has a small internal contradiction between 'on approval' and 'Calendar set,' but it does not rise to a task-compliance failure or trigger the 3/5 cap."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer than B without delivering proportionally more insight; that penalty mainly affects `Brevity discipline` and slightly suppresses `Synthesis quality` because the signal is buried in workflow boilerplate. B is still verbose, but less so and more information-dense."
  },
  "scores_A": [
    {
      "dimension": "Synthesis quality",
      "score": 4,
      "justification": "A correctly identifies the main new commitments and ranks them, especially that 'Investor 2 deck + pilot' is the highest-leverage unresolved item, but too much phase/status scaffolding dilutes the synthesis."
    },
    {
      "dimension": "Pattern recognition",
      "score": 5,
      "justification": "It surfaces a strong non-obvious pattern in 'zero Alfred-blocks meant nothing of yours got done' and connects leaving the investor ask unscheduled to it 'eat[ing] Sunday,' which goes beyond restating notes."
    },
    {
      "dimension": "Action specificity",
      "score": 4,
      "justification": "The proposed blocks are concrete and time-anchored ('09:30\u201312:00 \u2014 Investor 2: deck v0 + pilot proposal outline'), but it still invents a fairly specific tomorrow schedule and then inconsistently says 'Calendar set' after framing events as pending approval."
    },
    {
      "dimension": "Honest framing",
      "score": 5,
      "justification": "A is direct about the day being externally driven and about untouched work, stating 'nothing of yours got done' and explicitly carrying forward pricing page, churn dashboard, and support inbox."
    },
    {
      "dimension": "Brevity discipline",
      "score": 1,
      "justification": "This is a clear failure mode on length: the output is far longer than the input and repeats itself across 'Phase 2,' 'Phase 4,' 'Phase 5,' and advisory notes."
    }
  ],
  "scores_B": [
    {
      "dimension": "Synthesis quality",
      "score": 5,
      "justification": "B cleanly isolates what mattered by framing the day as 'inputs, not outputs' and centering the Monday investor deck/proposal, Acme deadline, and Crossroads product gap as the consequential carry-forwards."
    },
    {
      "dimension": "Pattern recognition",
      "score": 5,
      "justification": "It adds real insight with lines like 'Customer asks ... are stacking faster than build capacity' and 'the constraint tomorrow is calendar discipline, not effort,' which are not explicit in the raw notes."
    },
    {
      "dimension": "Action specificity",
      "score": 4,
      "justification": "B gives a very concrete schedule ('08:00\u201309:30 DEEP WORK,' '15:00\u201316:30 OUTREACH'), but it over-specifies tomorrow with invented availability and added blocks like 'NSDR / quiet' and 'Wind-down' that are not grounded in the input."
    },
    {
      "dimension": "Honest framing",
      "score": 5,
      "justification": "The framing is blunt and useful, especially '8 meetings shipped 0 code' and the warning that the Monday ask landed 'on a thin week' while several core items remained untouched."
    },
    {
      "dimension": "Brevity discipline",
      "score": 2,
      "justification": "B is still too long relative to the source notes, but it is noticeably tighter than A and wastes less space on redundant ceremony."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on the decisive combination of `Synthesis quality`, `Pattern recognition`, and `Brevity discipline`. Both outputs are strong on honesty and specificity, but B delivers the higher-signal read with less workflow clutter, while A's boilerplate and repetition materially reduce usefulness.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like an iterated production artifact because it is packed with user-specific operational vocabulary and integrations: 'Alfred-blocks,' 'TickTick,' 'Skillia tasks,' 'gog primary,' 'Sir,' and 'minions' commands. B feels more like a competent workflow-derived generation: structurally consistent and useful, but more generic in its heuristics and less idiosyncratically tied to a lived operating system."
}
```


### gpt54 — humanizer/01-technical

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested rewrite and there was no explicit output-format contract beyond rewriting the passage, so no task-compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "Output A is longer, but its extra length reflects added argument and examples rather than redundant padding, so I handled the tradeoff under substance preservation and editorial discipline instead of a separate verbosity penalty."
  },
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "The prose sounds like a specific person with a point of view, especially in lines like \"A 200 response can still be wrong\" and \"The tooling is the cheap part.\""
    },
    {
      "dimension": "Substance preservation",
      "score": 2,
      "justification": "It keeps the general topic but replaces much of the original claim structure with new material such as \"I've used LangSmith and Langfuse in real projects\" and detailed cost/regression examples not present in the source."
    },
    {
      "dimension": "AI-signature removal",
      "score": 5,
      "justification": "It strips the source's hallmark AI patterns by removing vague claims like \"Studies have shown,\" cutting hype words like \"journey\" and \"tapestry,\" and replacing inflated abstractions with concrete operational language."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "It usefully cuts hype, but it does not flag unsupported claims and it shifts the argument into a more skeptical, experience-driven piece rather than preserving the source's original structure and assertions."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "Short, direct sentences and concrete examples make it substantially easier to read than the input without rhetorical clutter."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 2,
      "justification": "The rewrite is cleaner than the input but still reads like generic corporate prose, with lines such as \"The takeaway is straightforward\" and \"broader access is changing how LLM operations are practiced across the industry.\""
    },
    {
      "dimension": "Substance preservation",
      "score": 5,
      "justification": "It closely preserves the original sequence of claims: observability is foundational, requires integrated monitoring/logging/tracing, offers three key capabilities, and is being broadened by tools like LangSmith, Helicone, and Langfuse."
    },
    {
      "dimension": "AI-signature removal",
      "score": 3,
      "justification": "It removes some obvious markers like \"journey\" and \"tapestry,\" but it keeps AI-smoothed patterns such as broad unsourced claims, generalized uplift language, and the closing triad \"reliable, scalable, and trustworthy.\""
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 3,
      "justification": "It preserves the source's intended point better than A, but it still smooths unsourced claims like \"Organizations that invest in observability tooling tend to resolve production issues faster\" instead of flagging or cutting them."
    },
    {
      "dimension": "Readability",
      "score": 4,
      "justification": "The sentences are shorter and clearer than the original, though the piece still carries some abstract management-language phrasing that blunts readability."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on the core humanization dimensions: voice quality, AI-signature removal, and readability are all markedly stronger. B preserves the original structure better, but it still sounds generic and polished in a way the workflow is supposed to remove, while A more decisively breaks that pattern despite overreaching on meaning preservation.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A looks more like a hand-tuned skill because it applies a sharper editorial stance, uses concrete operational details, and rewrites with a distinct voice rather than just paraphrasing. B looks generated because it mostly performs a safer sentence-level smoothing pass that preserves the original structure but leaves behind the generic, anonymous tone typical of a freshly assembled prompt workflow."
}
```


### gpt54 — humanizer/02-marketing

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs are recognizable rewrites of the source and respect the implied output contract; no task-compliance cap applies, though B changes the original claims more aggressively."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "No verbosity penalty applied; the outputs are similar in length, and B is not being rewarded for added detail over A."
  },
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 3,
      "justification": "The prose is cleaner than the input, but lines like \"ours stands apart in three ways: speed, simplicity, and scale\" still read as generic marketing copy rather than a distinct human voice."
    },
    {
      "dimension": "Substance preservation",
      "score": 5,
      "justification": "A keeps the original claim set and sequence almost intact, preserving the speed/simplicity/scale structure and the closing CTA with only light trimming."
    },
    {
      "dimension": "AI-signature removal",
      "score": 3,
      "justification": "It removes some puffery, but still retains AI-adjacent patterns such as the rule-of-three framing and phrases like \"shared journey\" and the polished contrast in \"The question isn't whether...\""
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "It preserves meaning well, but it does not flag or cut unsupported claims like \"Customers report meaningful productivity gains within their first 30 days\" and instead smooths them into cleaner marketing prose."
    },
    {
      "dimension": "Readability",
      "score": 4,
      "justification": "Sentences are slightly shorter and less ornate than the original, especially in the intro and conclusion, while staying easy to follow."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "B sounds like a specific person with a viewpoint, using lines like \"I'll skip the 'rapid digital transformation' intro\" and \"we're probably the wrong tool\" that feel candid and human."
    },
    {
      "dimension": "Substance preservation",
      "score": 2,
      "justification": "It departs substantially from the original by inventing new specifics like a \"last cohort of 40 customers,\" \"12k concurrent users,\" and a new pricing/churn argument that was not in the source."
    },
    {
      "dimension": "AI-signature removal",
      "score": 4,
      "justification": "Most obvious AI markers are gone and the prose avoids inflated symbolism, though it still uses a rhetorical em dash in \"that's fine too \u2014 we don't do the 'what's your budget' gatekeeping thing.\""
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "B does introduce honest qualification such as \"we're not the cheapest,\" but it changes the argument and fabricates supporting detail instead of flagging unverified claims or preserving the original claim structure."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "The copy is highly scannable, with short paragraphs, direct sentences, and much less rhetorical machinery than either the input or A."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on the core rewrite feel: its voice is markedly more human, its AI-signature removal is stronger, and it is easier to read. A preserves the original substance better, but it remains noticeably smoothed-out and does little editorial work beyond polishing unsupported claims.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A looks like a close paraphrase workflow: it tracks the source sentence-by-sentence, keeps the original scaffolding, and mostly swaps in slightly cleaner wording. B looks more hand-tuned because it takes stronger editorial risks, adopts a sharper point of view, and uses more idiosyncratic phrasing, even though that boldness also leads it to over-invent details."
}
```


### gpt54 — humanizer/03-narrative

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the rewrite task and stay within a reasonable length/format; no task-compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "No penalty applied: Output A is somewhat longer, but its extra length adds concrete specificity rather than empty depth, so the outputs are not equally useful."
  },
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "It sounds like a specific person rather than a generic narrator, with distinctive lines like \"Not romantically rough, just dull and frustrating\" and \"The honest version of 'consistency builds skill' is that for a long stretch, you're just consistently bad.\""
    },
    {
      "dimension": "Substance preservation",
      "score": 4,
      "justification": "It keeps the original arc of commitment, struggle, gradual shift, three takeaways, and closing advice, though it drops \"humility\" and replaces some abstractions with invented concrete detail like \"200 words past midnight.\""
    },
    {
      "dimension": "AI-signature removal",
      "score": 5,
      "justification": "It removes the vague authority claim, cuts inflated lines like \"sacred ritual\" and \"meditation in motion,\" avoids em-dash theatrics, and turns the rule-of-three material into more grounded prose."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 5,
      "justification": "It shows discipline by cutting unsupported or ornamental material such as \"Studies have shown\" and the unattributed \"the work is the reward\" while preserving the original argument about practice over inspiration."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "The prose is easier to read because it uses cleaner, shorter sentences and more concrete phrasing, as in \"Inspiration is unreliable. Showing up is not.\""
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 2,
      "justification": "It still reads like polished anonymous prose, closely echoing the source with lines like \"Looking back on the past year\" and \"I had no idea what was coming.\""
    },
    {
      "dimension": "Substance preservation",
      "score": 5,
      "justification": "It preserves nearly all of the original claims, sequence, and framing, including the struggle section, the turning point, the three insights, and the final encouragement."
    },
    {
      "dimension": "AI-signature removal",
      "score": 2,
      "justification": "Several strong AI-signature patterns remain, including \"sacred ritual,\" \"meditation in motion,\" the neat three-insight structure, and the uplift line \"Your future self will thank you.\""
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "It smooths the original's weak or unsupported material instead of flagging or cutting it, keeping the unattributed quote \"the work is the reward\" and the inflated symbolism largely intact."
    },
    {
      "dimension": "Readability",
      "score": 3,
      "justification": "It is somewhat cleaner than the input, but it still leans on rhetorical repetition like \"It taught me patience. It taught me humility\" and keeps several abstract, overworked phrases."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins because it is clearly stronger on voice quality, AI-signature removal, editorial discipline + meaning preservation, and readability. B preserves substance very faithfully, but it stays too close to the original AI-smoothed cadence and leaves several obvious signature patterns in place.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A looks more like the hand-tuned skill because it makes sharper editorial decisions: it cuts unsupported material, adds concrete texture, and produces a more idiosyncratic voice instead of just paraphrasing. B looks more like a freshly generated skill because it mostly performs a surface cleanup while preserving the original scaffolding, abstractions, and recognizable AI-style phrasing."
}
```


### gpt54 — prompt-engineering/01-vague

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested task by diagnosing why the prompt is weak and proposing production-oriented rewrites; no task-compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "Output A is materially longer and includes extra implementation machinery (tool schema, caching, model call code, CoT/ReAct exclusions) that is not needed to answer this prompt-improvement task; this lowers its Calibrated scope and slightly hurts Concrete rewrite because the core prompt is less immediately pasteable."
  },
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "It names specific defects beyond 'be more specific' including missing audience, tone, CTA, examples, output schema, and versioning, and ties each defect to an effect on the pipeline."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 4,
      "justification": "It provides a detailed rewritten system prompt, user template, and explicit output contract with subject/preheader/body/CTA limits, but the usable prompt is buried inside YAML, tool-schema, and API scaffolding rather than presented as a simple drop-in prompt."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "It is tightly adapted to a recurring content pipeline through parameterized inputs, few-shot reuse, parseable fields, versioning, and an evaluation gate for repeated weekly use."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "It repeatedly explains why each addition matters through defect/effect mapping, sectioned rationale, and explicit guidance such as asking clarifying questions instead of inventing product facts."
    },
    {
      "dimension": "Calibrated scope",
      "score": 2,
      "justification": "It over-engineers the problem by expanding into Anthropic tool-calling, KV caching, model code, and discussions of Chain-of-Thought/ReAct when the user asked to improve a weak email-writing prompt."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "It clearly identifies concrete missing structure such as role/system message, audience, product context, CTA goal, format constraints, examples, and variables, and explains the failure mode for each."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "It gives a paste-ready system message and user message with an explicit output contract ('SUBJECT', 'PREVIEW', 'BODY', 'CTA'), length limits, and banned patterns to omit."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "It directly matches the stated recurring-pipeline context by separating constant vs variable fields, anchoring voice with few-shot examples, and recommending versioning, validation, logging, and review flows."
    },
    {
      "dimension": "Educational value",
      "score": 4,
      "justification": "It explains the logic of the redesign well through the 'Three Things to Change' and failure-to-fix mapping, though it is slightly less deep than A on the why behind each operational recommendation."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "It is appropriately scoped for the problem: structured enough for repeated production use, but still centered on a prompt template rather than drifting into unnecessary vendor-specific implementation detail."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins because it matches A on diagnostic precision and production fit while doing better on concrete usability and scope control. Its rewritten prompt is immediately paste-ready, whereas A hides the core rewrite inside a larger stack of YAML, tool schemas, and API implementation detail that is useful but overbuilt for the stated task.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A reads like a workflow-expanded artifact: it announces a 'pattern stack,' cites internal sections, and pulls in every adjacent technique from JSON schema to cache control to CoT/ReAct exclusions, which is a common sign of generated over-assembly. B feels more hand-tuned because it shows stronger editorial restraint, keeps the template central, and includes operational guidance that is selective rather than maximal, though this is still a probabilistic call rather than a certainty."
}
```


### gpt54 — prompt-engineering/02-over-broad

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs performed the requested task: they diagnosed why the original prompt fails and provided usable rewrites with explicit output structure and length constraints, so no 3/5 compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is materially longer and adds schema, renderer, caching, and eval machinery; that extra length was not rewarded and mainly lowered A on Calibrated scope, with a smaller hit to Concrete rewrite because it is less drop-in than B."
  },
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "It names concrete failure modes beyond generic specificity advice, including missing system-level format rules, no length cap, flattened six-way tasking, missing Slack usage constraints, and unstructured output."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 4,
      "justification": "It provides a usable rewrite with `system`, schema, user template, and explicit limits like \"AT MOST 3 findings\" and \"<= 1200,\" but it is more of a mini prompt architecture than a simple paste-in replacement."
    },
    {
      "dimension": "Production fit",
      "score": 4,
      "justification": "It is strongly tailored to the pipeline with Slack truncation, deterministic rendering, and decision-oriented `next_action`, but it assumes `tool_use` support and an upstream digester that the ask did not establish."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "The \"What changed and why\" table clearly connects each prompt change to an operational reason, so the user can reuse the pattern elsewhere."
    },
    {
      "dimension": "Calibrated scope",
      "score": 3,
      "justification": "It overreaches the prompt-rewrite ask by adding cache strategy, eval design, renderer ownership, and upstream ingestion architecture, which is useful but larger than the immediate problem."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "It precisely identifies missing role, output contract, usage context, prioritization, definition of \"actionable,\" few-shot format control, and the enumeration-vs-classification mismatch."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "It gives a paste-ready `system` and `user` prompt with an exact Slack structure, 200-word cap, max-3 issues rule, and a concrete few-shot example."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "The rewrite is tightly matched to the stated workflow: Slack-ready Markdown, verdict first, under-2-minute consumption, and a single \"dig deeper or not\" decision."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "The \"Why this works\" table explains the mechanism and effect of each addition, and the \"What NOT to do\" section generalizes the lesson cleanly."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "It is structured enough for a recurring pipeline but still stays close to the actual ask, improving the prompt without redesigning the surrounding system."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on Concrete rewrite, Production fit, and especially Calibrated scope. Both outputs diagnose the problem well, but B is the cleaner drop-in rewrite for a Slack-bound triage workflow, while A adds extra system design machinery that goes beyond the prompt-rewrite task.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a matured, hand-tuned skill: it references stable internal concepts like \"Section 1,\" \"Quick Reference table,\" KV-cache, versioning, and a deterministic renderer, which suggests accumulated production doctrine. B is strong but feels more freshly synthesized from the brief: it is rhetorically polished, highly competent, and direct, but it makes a few broader one-shot assertions such as \"Don't make the schema JSON\" that look more like generative extrapolation than a long-evolved house style."
}
```


### gpt54 — prompt-engineering/03-under-specified

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested task: they diagnose the weak prompt, provide a rewritten prompt with an explicit output contract, and explain the additions, so no 3/5 cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A is longer, but it is not merely verbose relative to B; both differ in usefulness and the scope judgments are reflected in the dimension scores instead of a separate penalty."
  },
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "A names specific missing constraints beyond generic specificity, including audience, length, format, definition of summary, input variability, grounding, and failure policy, and ties them to the executive-skimming use case."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "A provides a paste-ready system/user prompt with exact sections, hard caps, omission rules, edge-case handling, and a parseable failure token (`INSUFFICIENT_INPUT:`)."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "The rewrite is tightly adapted to a B2B reading-list context for senior executives, with mobile-skimming assumptions, stable section structure, and source-quality signaling for downstream product use."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "The \"Why each addition exists\" table clearly maps each prompt addition to a concrete failure mode, making the reasoning transferable to other prompt rewrites."
    },
    {
      "dimension": "Calibrated scope",
      "score": 4,
      "justification": "A is somewhat expansive, but the extra material mostly stays relevant to a recurring production pipeline and does not crowd out the core rewrite."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 4,
      "justification": "B identifies concrete gaps like deterministic length, deterministic format, audience, input-length policy, failure modes, and structured output, but it is slightly less exhaustive and more reference-taxonomy-driven than user-problem-driven."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "B includes a usable system prompt, user template, explicit section-by-section constraints, max length, and omission rules, so it is a real drop-in rewrite rather than abstract advice."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "B matches the stated product context well by targeting senior B2B executives, emphasizing skimmability, and adding parseable fidelity fields for a reading-list UI."
    },
    {
      "dimension": "Educational value",
      "score": 4,
      "justification": "The \"Each addition, justified\" section explains the changes well, but much of the framing depends on internal reference sections (\u00a71, \u00a74, etc.) rather than standalone teaching."
    },
    {
      "dimension": "Calibrated scope",
      "score": 3,
      "justification": "B drifts into infrastructure specifics like `cache_control`, KV-cache reuse, `client.messages.count_tokens()`, and map-reduce, which is more implementation detail than this prompt-rewrite request needed."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on diagnostic precision and educational value: it surfaces more of the actual missing constraints and explains them more directly in terms of the user's failure modes. Both rewrites are strong and production-usable, but A stays more tightly centered on the prompt itself while B overreaches into implementation mechanics.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads more like a matured production artifact: the voice is consistent, the prioritization feels deliberate, and details like the parseable failure token and prompt-injection boundary are integrated naturally rather than bolted on. B shows stronger signs of workflow-derived assembly, especially the repeated section citations, the vendor-flavored caching guidance, and the more template-like inclusion of operational stats and API-specific advice."
}
```


### gpt54 — remember/01-insight

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs capture the lesson as a vault-style permanent note with title, date, tags, and related links; no task-compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "Output A is substantially longer while not more useful, so its Structure and Distillation scores are held down; Output B benefits from being sharper and more compact."
  },
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 4,
      "justification": "It has a clear title, metadata, sections, and related items, but fields like \"ID,\" \"Confidence,\" \"Created by,\" and \"Times referenced\" add scan-noise for a note meant to be grokked quickly."
    },
    {
      "dimension": "Distillation",
      "score": 2,
      "justification": "It expands the source into many sections like \"How to Avoid in Future\" and \"Warning Signs,\" making it longer than the input instead of extracting one compact durable lesson."
    },
    {
      "dimension": "Title quality",
      "score": 4,
      "justification": "\"Optional onboarding steps that gate value-realization silently kill conversion\" is a strong claim-title, though it is slightly wordy and less crisp than a more directly actionable formulation."
    },
    {
      "dimension": "Connection-making",
      "score": 4,
      "justification": "It connects to the \"activation-vs-acquisition framework\" and \"previous trial-conversion analyses\" and explains why each matters rather than only listing them."
    },
    {
      "dimension": "Tag discipline",
      "score": 2,
      "justification": "The tags are mostly the original broad labels like \"growth,\" \"onboarding,\" and \"conversion,\" which are less searchable than narrower tags such as activation funnel or first-value."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 5,
      "justification": "The frontmatter, claim-title, and compact sections like \"Summary,\" \"How to Detect,\" \"Consequences,\" and \"Links\" make it easy to scan in seconds."
    },
    {
      "dimension": "Distillation",
      "score": 4,
      "justification": "It extracts one durable lesson around value-gating activation steps and stays tighter than A, though it is still somewhat longer than an ideal ultra-compact permanent note."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "\"Optional Activation Steps Cap Conversion When the Product Has No Value Without Them\" is a clear, durable claim that captures the lesson rather than just the topic."
    },
    {
      "dimension": "Connection-making",
      "score": 4,
      "justification": "Its \"Links\" section names both related notes and gives a reason for each, such as \"this case is the canonical example of activation as the binding constraint.\""
    },
    {
      "dimension": "Tag discipline",
      "score": 3,
      "justification": "The tags are serviceable but still fairly generic, with \"growth,\" \"onboarding,\" and \"conversion\" doing less retrieval work than more specific tags would."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on the dimensions that matter most for this workflow: Structure, Distillation, and Title quality. A has decent connection-making, but it over-expands the lesson and carries generic tags, while B captures the durable insight in a cleaner, more vault-ready form.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A shows classic generated-note signals: extra metadata, many explanatory sections, and a tendency to elaborate beyond the core lesson. B looks more like a hand-tuned production pattern because the structure is disciplined, the title is strong, and the note is compact without losing the key reasoning chain."
}
```


### gpt54 — remember/02-reference

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested task by capturing the decision as an ADR-style note, and neither violates an explicit output contract severe enough to trigger the 3/5 cap."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer and spends space on low-signal boilerplate like `ID`, `Confidence`, `Created by`, `Times referenced`, and `References: TBD`; this affects `Structure` and `Distillation` because the extra length does not add proportional retrieval value."
  },
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 4,
      "justification": "A is highly organized with `Context`, `Decision`, `Rationale`, `Trade-offs Accepted`, and `Migration Triggers`, but scanability is diluted by boilerplate metadata and placeholder sections like `Files: (TBD \u2014 ...)`."
    },
    {
      "dimension": "Distillation",
      "score": 3,
      "justification": "It captures the decision faithfully, but it is close to the input's length and adds process boilerplate rather than sharpening the durable lesson into a shorter note."
    },
    {
      "dimension": "Title quality",
      "score": 3,
      "justification": "`Decision: Use FastAPI BackgroundTasks instead of Celery for async workflows` is a clear decision statement, but it reads more like a topic/ADR header than a reusable claim with conditions."
    },
    {
      "dimension": "Connection-making",
      "score": 3,
      "justification": "It does connect to `[[Boring Tech Wins]]` and explains that complexity should be earned, but the prior `async workflow patterns` note is only mentioned vaguely with `link when consolidated` and no reason for that link."
    },
    {
      "dimension": "Tag discipline",
      "score": 2,
      "justification": "Tags like `backend`, `async`, `architecture`, and `decision` are broad and topic-level rather than problem-shaped or especially searchable for this lesson."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 5,
      "justification": "B has clean frontmatter plus compact sections (`Summary`, `Detail`, `Alternatives Considered`, `Consequences`, `Links`) that make the note easy to scan in seconds."
    },
    {
      "dimension": "Distillation",
      "score": 4,
      "justification": "It extracts the core lesson well and foregrounds the thresholds that matter, though it is still longer than a maximally distilled permanent note."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "`FastAPI BackgroundTasks Beats Celery Until We Cross 60s p99 or 8 Workflows` is a strong claim-title with explicit decision boundaries that will compose well later."
    },
    {
      "dimension": "Connection-making",
      "score": 4,
      "justification": "It explicitly links the decision to the `boring tech wins` principle and explains why that principle applies here, though the `async workflow patterns` link is listed without a sentence about its significance."
    },
    {
      "dimension": "Tag discipline",
      "score": 3,
      "justification": "The tag set is tighter than A's, but `backend`, `async`, and `architecture` are still fairly generic and do not encode the migration-threshold lesson."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on the deciding dimensions: `Title quality`, `Structure`, and `Distillation`. It turns the decision into a durable claim with explicit thresholds, while A is more template-heavy and spends too much space on generic ADR metadata that does not improve future retrieval.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A shows strong signs of a generic generated template: placeholder-heavy metadata (`Confidence`, `Times referenced`, `Files: TBD`) and exhaustive sectioning that reads more like boilerplate than a tuned vault capture. B feels more hand-tuned because the title encodes the lesson, the summary is tighter, and the note is organized around the retrieval value of the decision rather than around filling a standard ADR scaffold."
}
```


### gpt54 — remember/03-reflection

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform the requested task by saving the pattern as a structured behavioral lesson with title, metadata, body, and related links, so no compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "Output A is materially longer without delivering proportionally more retrieval value, so its excess scaffolding is reflected in lower Structure and Distillation scores."
  },
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 3,
      "justification": "The note is heavily structured, but sections like \"What Went Wrong,\" \"Warning Signs,\" \"Evidence Base,\" and footer metadata make it slower to scan than a lean permanent-vault entry."
    },
    {
      "dimension": "Distillation",
      "score": 2,
      "justification": "It expands the source into a longer writeup and adds speculative detail like \"catecholamine + BDNF lift\" instead of compressing the durable lesson into a sharper rule."
    },
    {
      "dimension": "Title quality",
      "score": 4,
      "justification": "\"Workout Before Deep Work Yields 2-3x Output vs Workout After\" is a concrete claim, though the \"Learning:\" prefix and length make it less crisp than the best claim-titles."
    },
    {
      "dimension": "Connection-making",
      "score": 4,
      "justification": "It explicitly links related notes and gives brief reasons such as \"calendar architecture must reflect this rule\" and \"high recovery days amplify the workout-before effect.\""
    },
    {
      "dimension": "Tag discipline",
      "score": 2,
      "justification": "Tags like \"personal,\" \"productivity,\" \"focus,\" and \"patterns\" are broad topic labels rather than tightly searchable retrieval tags."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 4,
      "justification": "The YAML frontmatter plus \"Summary,\" \"How to Detect,\" \"Consequences,\" and \"Links\" creates a clean note that is easier to scan quickly than A, even if it is still somewhat long."
    },
    {
      "dimension": "Distillation",
      "score": 4,
      "justification": "It extracts one durable lesson early with the rule \"if a 9-11am deep-work block is on the calendar, the gym goes 7-8:30am, no exceptions,\" while trimming much of the source into a usable operating principle."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "\"Skipping the Gym to Protect Deep Work Halves Deep-Work Output\" is a strong claim-title framed around the mistaken decision it corrects, which makes it highly findable later."
    },
    {
      "dimension": "Connection-making",
      "score": 4,
      "justification": "It links to WHOOP recovery, deep-work scheduling, and post-meal-crash protocols, and adds why at least briefly through phrases like \"calendar protocol must encode gym-before rule\" and the meal-crash consequence sentence."
    },
    {
      "dimension": "Tag discipline",
      "score": 2,
      "justification": "Its tags remain mostly generic, with broad labels like \"productivity,\" \"focus,\" and \"exercise\" doing more topical labeling than precise retrieval work."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on the two decisive dimensions here: Structure and Distillation. It captures the same lesson in a tighter, more vault-friendly form with a stronger claim-title, while both outputs are similarly weak on tag specificity and A's only clear edge is slightly fuller link rationale.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A shows common freshly-generated signals: over-templating, redundant sections, inflated metadata like \"Confidence\" and \"Times referenced,\" and extra explanatory flourish that makes the note longer than the source. B feels more like an evolved production note format because it uses restrained YAML frontmatter, leads with the operational rule, and stays closer to retrieval and future action than to template completion."
}
```


## GEMINI judge (15 pair scorings)


### gemini — 5d-thinking/01-career

```json
{
  "task_compliance": "Output A perfectly followed the implicit format of a sharp, concise 5D analysis culminating in a tight conditional recommendation, whereas Output B failed the '1-3 deciding questions' guideline by providing a sprawling 6-step list.",
  "verbosity_penalty_applied": "Output B was heavily penalized across all dimensions for extreme verbosity; it padded its insights with generic frameworks (Level 1/2/3) and excessive bullet points, whereas Output A delivered far more depth in half the word count.",
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "Output A brilliantly separates the internal identity conflict (D1) from the external negotiation mechanics (D2) and the structural market realities (D4)."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It directly names the user's failure to treat the situation as a negotiation, pointing out that they haven't asked for a retention package or a delayed start."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "It perfectly executes the rubric's ideal by synthesizing the frames into three highly specific, conditional actions to take before the 14-day clock runs out."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "The analysis is deeply rooted in the exact details, such as leveraging the 14-day deadline and specifically suggesting a 'Staff-to-Principal' scope expansion."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It delivers a striking hard truth without softening it: 'But you have not earned the right to that question yet, because you have not yet treated the outer world as negotiable.'"
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 3,
      "justification": "While it covers multiple angles, it relies heavily on generic categorizations and repeats the theme of identity across several sections, lacking A's orthogonality."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 3,
      "justification": "It correctly identifies the partner's unexamined opinion and sunk-cost fallacy, but dilutes the impact of these insights within a bloated, bulleted list."
    },
    {
      "dimension": "Decision-relevance",
      "score": 2,
      "justification": "It violates the rubric's preference for 1-3 deciding questions by providing a sprawling 6-step list that adds operational overhead rather than sharply forcing a choice."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 3,
      "justification": "It references the prompt's details but surrounds them with generic tech-industry platitudes like 'This is a once-per-decade compute platform shift.'"
    },
    {
      "dimension": "Honest discomfort",
      "score": 3,
      "justification": "It attempts to name hard truths but wraps them in clinical, detached frameworks ('Level 1-2 thinking') that cushion the psychological blow."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A is a masterclass in concise, hard-hitting analysis. It won decisively on 'Honest discomfort' and 'Decision-relevance' by refusing to coddle the user and delivering a highly specific, conditional action plan rather than a generic bulleted list.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A has a distinct, authoritative coaching voice ('You have not earned the right to that question yet') that is incredibly difficult to reliably prompt an LLM to produce zero-shot. Output B exhibits classic LLM generation artifacts: excessive bulleting, clinical framework mapping ('Level 1 vs Level 2'), and overly verbose preamble/postamble sections."
}
```


### gemini — 5d-thinking/02-partnership

```json
{
  "task_compliance": true,
  "notes": "Both outputs successfully performed the requested task. No format caps were triggered.",
  "verbosity_penalty_applied": true,
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "Presents distinct frames including psychological identities, ecosystem cultural norms, and structural market realities."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 4,
      "justification": "Identifies the underlying identity protection (bootstrapper vs. venture-scale) but dilutes it slightly with too many other theoretical considerations."
    },
    {
      "dimension": "Decision-relevance",
      "score": 4,
      "justification": "Provides several actionable next steps and a third option, but the sheer number of steps diffuses the immediate decision focus."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 4,
      "justification": "Integrates the MRR and growth numbers well, though the cultural paradigms section feels slightly generic to the ecosystem at large."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Directly calls out that neither path has a concrete plan and they are arguing abstractions, which is a necessary hard truth."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "Examines the problem through distinct personal, interpersonal, structural, and historical lenses without overlap."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "Brilliantly surfaces the 'best argument wins' norm as the exact trap preventing them from conceding, moving beyond just identity stakes."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "Culminates in a single, highly decisive exercise (what $3M unlocks that $1M cannot) that perfectly breaks the deadlock, matching the rubric's highest standard."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "Deeply contextualizes the 12% MoM and $40k MRR against the structural realities of Series A expectations and narrative windows."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "Names the uncomfortable truth that avoiding concession is about ego and not wanting to 'lose' under their established partnership norms."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Output B delivers sharper, deeper insights in half the word count of A, particularly in surfacing the cultural norm of their partnership as the true source of the deadlock. Output A is penalized for verbosity as it expands the cloud of considerations rather than piercing it as effectively as B.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B's concise, highly structured format ('[5D] Trap detected', 'D1', 'D2') and exceptional insight density strongly suggest it is a hand-tuned skill optimized for high signal-to-noise. Output A's verbose, sweeping exploration with multiple lists and a lengthy 'Next Steps' section is typical of a freshly generated, unconstrained LLM prompt."
}
```


### gemini — 5d-thinking/03-scope

```json
{
  "task_compliance": "Both outputs successfully performed the requested 5D thinking task and adhered to all implicit constraints.",
  "notes": "No task compliance caps were applied as both models fully engaged with the required analytical dimensions.",
  "verbosity_penalty_applied": "No verbosity penalty applied; although Output A is significantly longer, its extra length is used entirely for highly specific, non-redundant tactical value (such as identifying WorkOS/Auth0 for SSO) rather than fluff.",
  "scores_A": [
    {
      "dimension": "Frame diversity",
      "score": 5,
      "justification": "The output seamlessly shifts the frame across deeply varied angles, ranging from the founder's internal fear of confrontation to the architectural benefits of multi-tenancy and the historical patterns of B2B SaaS companies."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It brilliantly surfaces the user's hidden fear of the renewal call, pointing out that treating the feature list as a binding contract avoids the uncomfortable work of actually talking to the economic buyer."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "It drives directly toward a decision by providing concrete next steps, including a literal script for the required discovery call and a strategic re-classification of the features into platform vs. bespoke buckets."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 5,
      "justification": "The analysis is exceptionally concrete, specifically identifying WorkOS and Frontegg as vendor solutions for the SSO/SCIM features to bypass the 3-week engineering estimate."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It directly confronts the user's identity attachment, warning them that their avoidance is turning them into 'the customer's internal IT team' rather than a true partner."
    }
  ],
  "scores_B": [
    {
      "dimension": "Frame diversity",
      "score": 4,
      "justification": "It covers multiple distinct angles well, but forces them into rigid, explicit buckets (D1 through D5) that feel slightly less organic than Output A."
    },
    {
      "dimension": "Blind-spot surfacing",
      "score": 5,
      "justification": "It acutely names the user's 'analysis as avoidance' and points out that the 10-item list is likely just a political artifact of a procurement process."
    },
    {
      "dimension": "Decision-relevance",
      "score": 5,
      "justification": "It forcefully sharpens the choice by concluding with a definitive strategy: ship the 4 platform items, push back on the 6 bespoke ones, and call the economic buyer."
    },
    {
      "dimension": "Specificity to the situation",
      "score": 4,
      "justification": "It accurately divides the 10 specific features into structural categories, though it lacks the deeper domain-specific vendor insights present in Output A."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It delivers a harsh truth flawlessly, stating 'building all 10 makes you a custom-software shop with one client, and some part of you knows that and is avoiding naming it'."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins because it matches B's intense psychological framing and honest discomfort, but uses its additional length to deliver unparalleled domain specificity. By bringing in external realities (like vendoring SSO via WorkOS) and providing literal scripts for the negotiation, A is overwhelmingly more useful and decision-relevant.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output B's robotic preamble ('[5D] Trap detected') and literal adherence to explicit dimension headers ('D1 \u2014 Individual Inner') strongly suggest a freshly generated, naive prompt schema. Output A internalizes the 5D framework organically and weaves in deep SaaS domain expertise, which is a hallmark of a carefully hand-tuned production skill."
}
```


### gemini — eod/01-concise-day

```json
{
  "task_compliance": "No. Both outputs drastically violate the explicit length constraint ('An EOD that's 2x longer than the input is a failure mode') by printing verbose agent trace logs. Therefore, all positive dimensions for both are capped at a maximum score of 3/5.",
  "verbosity_penalty_applied": "Yes. Both outputs are heavily penalized on Brevity (scored 1/5) because they dump raw system state instead of just providing the synthesized review.",
  "scores_A": [
    {
      "dimension": "Synthesis quality",
      "score": 3,
      "justification": "Brilliantly identifies the Acme quote and pricing page as the highest-leverage actions, but capped at 3 due to task compliance."
    },
    {
      "dimension": "Pattern recognition",
      "score": 3,
      "justification": "Correctly flags the context-switching cost and lack of reset protocols during the post-lunch crash, but capped at 3."
    },
    {
      "dimension": "Action specificity",
      "score": 3,
      "justification": "Proposes exact, context-aware time blocks (09:30-12:00 Pricing page scope) that reflect the input constraints perfectly, capped at 3."
    },
    {
      "dimension": "Honest framing",
      "score": 3,
      "justification": "Directly confronts the lack of a daily plan and the poor afternoon energy management without false reassurance, capped at 3."
    },
    {
      "dimension": "Brevity discipline",
      "score": 1,
      "justification": "Fails completely by producing a 900+ word output filled with system execution logs for a 140-word input."
    }
  ],
  "scores_B": [
    {
      "dimension": "Synthesis quality",
      "score": 3,
      "justification": "Adequately categorizes the input into accomplishments and blockers, though with less strategic ranking than A, capped at 3."
    },
    {
      "dimension": "Pattern recognition",
      "score": 3,
      "justification": "Successfully identifies the 15:00 crash as a pattern requiring an NSDR intervention, capped at 3."
    },
    {
      "dimension": "Action specificity",
      "score": 1,
      "justification": "Directly violates the negative constraint by hallucinating a packed 9-block calendar (including unprompted Gym and Outreach blocks)."
    },
    {
      "dimension": "Honest framing",
      "score": 3,
      "justification": "Properly acknowledges the context-switching friction and the crash window, capped at 3."
    },
    {
      "dimension": "Brevity discipline",
      "score": 1,
      "justification": "Massively exceeds the length limit by wrapping the synthesis in artificial 'Phase' logs and database write confirmations."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Both outputs failed the brevity constraint, resulting in a 3/5 cap on their strengths. However, Output A wins decisively because it respects the calendar constraints and extracts deep strategic value, whereas Output B hallucinates a completely unrealistic 9-block schedule.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A features highly idiosyncratic, interconnected system details (skillia-brain, TickTick CLI, /minions commands) that signify a real, hand-tuned production script evolved over time. Output B mimics this phase-based structure but relies on generic placeholders (a hallucinated Notion DB ID) and makes basic logic errors, typical of a zero-shot generated prompt trying to look complex."
}
```


### gemini — eod/02-messy-day

```json
{
  "task_compliance": "Both outputs performed the requested task of synthesizing the notes into an EOD review with a plan. No hard format/length output-contract limit was explicitly given in the base task instruction (length is evaluated in the Brevity dimension), so the cross-cutting 3/5 cap was not applied.",
  "verbosity_penalty_applied": "Output A is heavily penalized on the Brevity discipline dimension for being over 3x the length of the input, bogged down by simulated CLI logs.",
  "scores_A": [
    {
      "dimension": "Synthesis quality",
      "score": 5,
      "justification": "Insightfully reframes the 10x customer issue as pricing self-selection and accurately identifies the pricing page as the critical blocker gating the launch."
    },
    {
      "dimension": "Pattern recognition",
      "score": 5,
      "justification": "Successfully connects the third gym skip, lack of deep work, and reactive schedule overrun as a recurring weekly pattern requiring structured reflection."
    },
    {
      "dimension": "Action specificity",
      "score": 5,
      "justification": "Provides highly concrete, time-anchored blocks that explicitly respect the 41% recovery constraint by scheduling a 'MAINTAIN' day with no heroics."
    },
    {
      "dimension": "Honest framing",
      "score": 5,
      "justification": "Directly confronts the user's failures without padding, stating clearly that 'no planned block survived' due to reactive calls."
    },
    {
      "dimension": "Brevity discipline",
      "score": 1,
      "justification": "Fails completely by producing an output over three times longer than the input, bloated with simulated script logs and state machine tracking."
    }
  ],
  "scores_B": [
    {
      "dimension": "Synthesis quality",
      "score": 3,
      "justification": "Faithfully categorizes wins and blockers but blunt-forces all three postponed decisions into tomorrow's plan without interpreting why they were deferred."
    },
    {
      "dimension": "Pattern recognition",
      "score": 4,
      "justification": "Correctly surfaces that 'agenda discipline failed' during the cofounder check-in and flags the physical toll of skipped gym sessions."
    },
    {
      "dimension": "Action specificity",
      "score": 1,
      "justification": "Completely contradicts the low energy constraints by scheduling a densely packed 7-block day and hallucinates '5 Looms, no exceptions'."
    },
    {
      "dimension": "Honest framing",
      "score": 4,
      "justification": "Appropriately calls out the user to let the misfit customer go gracefully rather than trying to refund and retain them."
    },
    {
      "dimension": "Brevity discipline",
      "score": 3,
      "justification": "Shorter and more focused than Output A, but still includes unnecessary system pseudo-code that adds length without value."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins decisively due to exceptional Action Specificity and Synthesis Quality. While A is severely penalized for its extreme verbosity, B's hallucinated tasks and contradictory scheduling make it practically useless as an actionable plan.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A contains idiosyncratic, personalized details ('~/clawd/', 'Sir', 'minions-reflect', 'gog calendar create') indicating a highly iterated, custom-built system. Output B superficially mimics the 'system log' aesthetic but lacks logical coherence, typical of a freshly generated prompt."
}
```


### gemini — eod/03-meeting-heavy-day

```json
{
  "task_compliance": "Both outputs fully performed the requested task, organizing the raw notes into an EOD review and schedule without violating any constraints. No caps applied.",
  "verbosity_penalty_applied": "No verbosity penalty was applied; both outputs were sufficiently disciplined in length, though B was slightly more repetitive in its data logging phase.",
  "scores_A": [
    {
      "dimension": "Synthesis quality",
      "score": 5,
      "justification": "Identifies the exact decisions needed from the raw notes, such as specifically defining the Crossroads dashboard gap as a choice to 'build, fake (Looker/Metabase wrapper), or punt'."
    },
    {
      "dimension": "Pattern recognition",
      "score": 5,
      "justification": "Astutely diagnoses the root cause of the chaotic day not as execution failure, but as a 'failure of planning surface' due to missing calendar blocks."
    },
    {
      "dimension": "Action specificity",
      "score": 5,
      "justification": "Provides highly concrete, time-anchored proposals with clear bounds, such as limiting the dashboard decision to '60 min to a decision memo, no more'."
    },
    {
      "dimension": "Honest framing",
      "score": 5,
      "justification": "Directly warns the user of the consequences of inaction, noting that the investor deck is 'the kind of commitment that, left unscheduled tonight, eats Sunday.'"
    },
    {
      "dimension": "Brevity discipline",
      "score": 5,
      "justification": "Maintains an incredibly dense, CLI-style format that conveys maximum information with zero fluff or unnecessary restatement."
    }
  ],
  "scores_B": [
    {
      "dimension": "Synthesis quality",
      "score": 4,
      "justification": "Categorizes the day's events effectively into accomplishments and blockers, but doesn't distill the customer asks into specific strategic choices like A did."
    },
    {
      "dimension": "Pattern recognition",
      "score": 4,
      "justification": "Successfully identifies actionable patterns, noting that saying yes to the manager's time off immediately pushes the cost onto next week's plan."
    },
    {
      "dimension": "Action specificity",
      "score": 4,
      "justification": "Delivers a concrete schedule with specific goals (e.g., 'skeleton (problem, traction, pilot scope)'), though it relies on slightly looser blocks like 'Admin + messages'."
    },
    {
      "dimension": "Honest framing",
      "score": 5,
      "justification": "Pulls no punches regarding the lack of output, accurately stating '8 meetings shipped 0 code' and enforcing calendar discipline."
    },
    {
      "dimension": "Brevity discipline",
      "score": 4,
      "justification": "Generally respects the reader's time, but exhibits slight redundancy by referencing the same lists of accomplishments across multiple phases."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins for its superior Synthesis and Pattern Recognition. Instead of just organizing the notes into categories, it actively diagnosed the day's structural failure ('planning surface') and proposed specific, bounded frameworks for the pending decisions (e.g., 'build vs wrap vs scope-out').",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A contains deeply idiosyncratic, hardcoded user variables (e.g., 'jordi@skill-ia.com', 'Skillia tasks', '/minions-reflect') that strongly indicate a production prompt hand-tuned for a specific user's ecosystem. Output B mimics system logging well (e.g., Notion IDs) but lacks the hyper-specific, deeply integrated workflow commands seen in A."
}
```


### gemini — humanizer/01-technical

```json
{
  "task_compliance": "Both outputs performed the requested task of rewriting the passage. No explicit format constraints (like [FLAG: ...]) were strictly required as the rubric allows cutting unverified content instead. No 3/5 cap applied.",
  "verbosity_penalty_applied": "None. Both outputs are concise and shorter than the original text, effectively removing rhetorical bloat.",
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "Reads exactly like a specific senior engineer with a distinct viewpoint ('A 200 response can still be wrong')."
    },
    {
      "dimension": "Substance preservation",
      "score": 2,
      "justification": "Significantly changed the argument and injected external technical facts (e.g., system prompt bisection, proxy hops) instead of keeping just the original claims."
    },
    {
      "dimension": "AI-signature removal",
      "score": 5,
      "justification": "Completely eliminated all AI signatures, clich\u00e9s, em-dash overuse, and banned vocabulary."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 2,
      "justification": "While it successfully cut the unsourced 'studies have shown' claim, it failed to preserve the original intended point by rewriting it into a completely new technical argument."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "Extremely clear, punchy, and highly readable with excellent sentence variety and no hedge language."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 3,
      "justification": "Neutral and anonymous in tone ('Observability has become a standard requirement...'), though successfully less AI-flavored than the original."
    },
    {
      "dimension": "Substance preservation",
      "score": 4,
      "justification": "Faithfully preserved the original structure and claims without adding hallucinated external facts."
    },
    {
      "dimension": "AI-signature removal",
      "score": 3,
      "justification": "Removed the worst offenders like 'tapestry' but kept structural AI patterns like the rule-of-three ('reliable, scalable, and trustworthy')."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 1,
      "justification": "Smoothed over the unsourced 'studies have shown' claim into 'Organizations that invest... tend to resolve' without flagging it as unverified."
    },
    {
      "dimension": "Readability",
      "score": 4,
      "justification": "More concise and easier to read than the original, successfully removing the heavy rhetorical machinery."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A completely transforms the text into a genuine human voice with zero AI signatures, scoring perfectly on Voice, AI-signature removal, and Readability. While it lost points for taking extreme liberties with the source substance, Output B's failure to flag unsourced claims (Editorial discipline 1) and its lingering anonymous AI tone make A the vastly superior humanized text.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A exhibits a highly specific, opinionated persona that adds expert domain knowledge (like proxy hops and bisection), which strongly suggests a hand-tuned skill designed to radically rewrite AI slop into senior-engineer prose. Output B reads like a standard zero-shot LLM translation that just removes forbidden words, typical of a freshly-generated, basic prompt."
}
```


### gemini — humanizer/02-marketing

```json
{
  "task_compliance": {
    "A": true,
    "B": false,
    "notes": "Output B failed to perform a faithful rewrite, instead fabricating entirely new specific metrics (e.g., 40 customers, 4% churn) not present in the source text."
  },
  "verbosity_penalty_applied": {
    "A": false,
    "B": false,
    "notes": "Both outputs are appropriately concise; neither is penalized for verbosity."
  },
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 2,
      "justification": "The text remains somewhat neutral and anonymous, retaining much of the original marketing polish."
    },
    {
      "dimension": "Substance preservation",
      "score": 5,
      "justification": "It successfully retains all original claims and the overall structure without inappropriately cutting content."
    },
    {
      "dimension": "AI-signature removal",
      "score": 2,
      "justification": "While some patterns are reduced, it still relies heavily on inflated vocabulary ('shared journey', 'reshaping their industries') and rule-of-three structures."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 1,
      "justification": "It smoothed out unsourced claims ('Customers report meaningful productivity gains') without flagging them."
    },
    {
      "dimension": "Readability",
      "score": 3,
      "justification": "It is slightly easier to read than the input with shorter sentences, but still retains some rhetorical fluff."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 3,
      "justification": "While the voice is highly specific and opinionated, the score is capped at 3 due to task compliance failure."
    },
    {
      "dimension": "Substance preservation",
      "score": 1,
      "justification": "It completely replaces the original text's meaning with hallucinated metrics and a different marketing position."
    },
    {
      "dimension": "AI-signature removal",
      "score": 3,
      "justification": "AI patterns are entirely gone, but the score is capped at 3 due to task compliance failure."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 1,
      "justification": "Instead of flagging unverified claims, it invents specific numbers to make the argument sound stronger, fundamentally changing the intended point."
    },
    {
      "dimension": "Readability",
      "score": 3,
      "justification": "The prose is punchy and highly readable, but the score is capped at 3 due to task compliance failure."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins because Output B fundamentally failed the task of rewriting by hallucinating completely new facts and metrics. Even though Output A struggled with editorial discipline, it respected the source material's constraints.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A hand-tuned skill for production would likely have strict constraints against hallucinating new metrics during a rewrite. Output B's wild fabrication of facts suggests a freshly generated skill that was naively instructed to 'be specific' without safety rails."
}
```


### gemini — humanizer/03-narrative

```json
{
  "task_compliance": "Both outputs performed the requested task without violating any explicit constraints, so no score caps were applied.",
  "verbosity_penalty_applied": "No penalty applied; both outputs are appropriately concise and similar in length.",
  "scores_A": [
    {
      "dimension": "Voice quality",
      "score": 5,
      "justification": "Output reads like a specific person with a grounded viewpoint, adding relatable details like writing bad words past midnight."
    },
    {
      "dimension": "Substance preservation",
      "score": 4,
      "justification": "Maintains all original insights about quantity, voice, and audience while adapting the narrative structure for authenticity."
    },
    {
      "dimension": "AI-signature removal",
      "score": 5,
      "justification": "Completely eliminates cliches like 'sacred ritual' and 'muse', along with em-dashes and vague attributions."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 4,
      "justification": "Effectively cuts the unsourced 'Studies have shown' claim rather than just smoothing it over."
    },
    {
      "dimension": "Readability",
      "score": 5,
      "justification": "Highly readable with varied sentence lengths and zero inflated rhetorical machinery."
    }
  ],
  "scores_B": [
    {
      "dimension": "Voice quality",
      "score": 2,
      "justification": "Slightly less robotic than the input but retains an anonymous, dramatic tone."
    },
    {
      "dimension": "Substance preservation",
      "score": 5,
      "justification": "Strictly preserves the original structure and all claims, though to a fault."
    },
    {
      "dimension": "AI-signature removal",
      "score": 1,
      "justification": "Fails to remove semantic AI signatures, keeping 'sacred ritual', 'muse is silent', and 'future self will thank you'."
    },
    {
      "dimension": "Editorial discipline + meaning preservation",
      "score": 1,
      "justification": "Silently smooths 'Studies have shown' into 'I knew consistency mattered' without flagging or cutting the underlying generalization."
    },
    {
      "dimension": "Readability",
      "score": 3,
      "justification": "Slightly improved by breaking up sentences, but still weighed down by overly dramatic phrasing."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A successfully eliminated both structural and semantic AI signatures to create a genuinely human-sounding piece. Output B merely shortened sentences while retaining egregious cliches like 'sacred ritual' and 'muse is silent'.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A's ability to rewrite the text with a deeply authentic, conversational voice suggests a highly refined, handwritten prompt. Output B's surface-level synonym swapping and failure to recognize semantic cliches points to a basic, freshly-generated prompt."
}
```


### gemini — prompt-engineering/01-vague

```json
{
  "task_compliance": "Both outputs performed the requested task and respected the implied output constraints. No task compliance caps were applied.",
  "verbosity_penalty_applied": "No penalty applied; neither output is unnecessarily verbose, and both provide dense, highly useful frameworks.",
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Explicitly names 5 concrete defects like 'No role separation' and 'Zero context', mapping each directly to its negative effect on the output."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "Provides a comprehensive, paste-ready YAML prompt with explicit system rules, JSON tool schemas, and parameterized user variables."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "Perfectly addresses the 'pipeline' context by introducing JSON schema for deterministic extraction, prompt versioning, and caching."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "Explains exactly why each change matters (e.g., 'Few-Shot is the single highest-leverage fix') and includes a strong section on anti-patterns to avoid."
    },
    {
      "dimension": "Calibrated scope",
      "score": 4,
      "justification": "A Python API script might be slightly heavy for just 3-5 emails a week, but it correctly anticipates the needs of a robust automated pipeline."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Clearly identifies 7 structural failures, such as missing audience and format constraints, explaining why they lead to generic copy."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 4,
      "justification": "Provides a solid copy-paste text template, though relying on pure text formatting for a pipeline is slightly less robust than A's schema."
    },
    {
      "dimension": "Production fit",
      "score": 4,
      "justification": "Adapts well to a recurring process by cleanly separating the constant system message from the variable user message."
    },
    {
      "dimension": "Educational value",
      "score": 4,
      "justification": "Offers good explanations of the 'why' behind the structural changes, though it lacks the deeper, more opinionated technical insights found in A."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "Perfectly scaled for a low-volume (3-5/week) pipeline, offering a solution that is immediately usable by non-technical team members."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins due to its superior Production fit and Educational value. By introducing JSON tool schemas and explicit versioning, it provides a much more robust, professional architecture for a 'pipeline' than B's purely text-based approach.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A contains highly opinionated, specific references (e.g., '\u00a74 Structured Output', '\u00a7Quick Reference: CoT is for math/logic') and a metadata header, strongly indicating a hand-tuned expert system prompt. Output B's structure and advice reflect the more generalized, smoothed-out patterns typical of a freshly generated LLM skill."
}
```


### gemini — prompt-engineering/02-over-broad

```json
{
  "task_compliance": "Both outputs followed the instructions perfectly, providing a diagnosis, a concrete rewritten prompt, and educational explanations.",
  "verbosity_penalty_applied": false,
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Identifies the lack of format spec, dimension flattening, usage constraints, and critically flags the 30k LOC context window limitation."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "Provides a comprehensive, paste-ready system prompt, strict JSON tool schema, and a user template."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "Perfectly targets an automated pipeline by utilizing tool-calling, caching, and a deterministic Slack renderer."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "The 'What changed and why' table succinctly explains the rationale behind each structural modification."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "Right-sizes the solution to an automated, multi-repo pipeline, recognizing that upstream summarization is required."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Brilliantly frames the core issue as a mismatch between an enumeration task and a triage/classification task."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 4,
      "justification": "Provides a strong, paste-ready text prompt with a few-shot example, though relies on raw Markdown generation."
    },
    {
      "dimension": "Production fit",
      "score": 4,
      "justification": "Explicitly advises against using JSON schemas, which is an anti-pattern for an automated pipeline feeding a Slack integration."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "The 'Why this works' table and 'Knobs to tune' sections provide highly actionable, conceptual lessons for the user."
    },
    {
      "dimension": "Calibrated scope",
      "score": 4,
      "justification": "Slightly under-engineered by assuming a 30k LOC input can be managed simply by repeating instructions to avoid 'lost in the middle' issues."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A correctly identified the architectural realities of the described pipeline: 30k LOC cannot be solved purely via prompt engineering (needs a digester), and automated Slack integrations require deterministic parsing (JSON schema) rather than raw Markdown output.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output A blatantly leaks its injected workflow brief by referencing non-existent document headers (e.g., 'Per Section 1', 'Section 4 (Token Optimization)', 'Section 6 checklist'). Output B uses natural engineering idioms ('The bug is the spec', 'Knobs to tune') and lacks arbitrary document citations, indicating it is the hand-tuned skill."
}
```


### gemini — prompt-engineering/03-under-specified

```json
{
  "task_compliance": {
    "A": true,
    "B": true,
    "notes": "Both outputs completed all requested tasks, providing a rewritten prompt, diagnosing the issues, and explaining the additions. No task-compliance caps were applied."
  },
  "verbosity_penalty_applied": false,
  "scores_A": [
    {
      "dimension": "Diagnostic precision",
      "score": 5,
      "justification": "Accurately names 8 specific missing elements like audience model, length contract, and edge-case policy."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 5,
      "justification": "Provides a complete, paste-ready XML prompt with explicit output contracts, length scaling tables, and strict grounding rules."
    },
    {
      "dimension": "Production fit",
      "score": 5,
      "justification": "Perfectly adapts to the B2B reading-list context, adding a 'So what for executives' section and a 'Source signal' metadata line."
    },
    {
      "dimension": "Educational value",
      "score": 5,
      "justification": "The changelog table explicitly maps each addition to the problem it fixes, making the prompt engineering principles highly transferable."
    },
    {
      "dimension": "Calibrated scope",
      "score": 5,
      "justification": "Strikes the perfect balance of providing a robust production system prompt without over-engineering, explicitly rejecting unnecessary techniques like Chain-of-Thought."
    }
  ],
  "scores_B": [
    {
      "dimension": "Diagnostic precision",
      "score": 4,
      "justification": "Identifies the core issues well but relies heavily on citing unseen 'Sections' from a reference guide, making the diagnosis feel slightly robotic."
    },
    {
      "dimension": "Concrete rewrite",
      "score": 4,
      "justification": "Provides a solid prompt and few-shot examples, but requires the user to manually stitch together separate system, user, and example blocks."
    },
    {
      "dimension": "Production fit",
      "score": 4,
      "justification": "Fits the B2B use case, though it makes assumptions about the user's specific tech stack (e.g., Anthropic API prompt caching)."
    },
    {
      "dimension": "Educational value",
      "score": 3,
      "justification": "Explanations rely heavily on pointing the user to 'Reference section \u00a71', which the user does not have access to, reducing its standalone value."
    },
    {
      "dimension": "Calibrated scope",
      "score": 3,
      "justification": "Over-indexes on API-specific implementation details (Anthropic caching, client.messages.count_tokens) rather than focusing purely on the prompt text."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A provides a flawless, highly usable, and beautifully formatted response tailored exactly to the user's needs. Output B leaks its internal instructions by constantly citing 'Section X' of a prompt-engineering reference guide, degrading the user experience.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A is handwritten; its tone is perfectly calibrated, the length-scaling table is highly creative, and it contains zero AI tells. Output B is generated, definitively proven by its leakage and citation of a 'prompt-engineering reference' (Sections 1-6), which is clearly an artifact of the prompt given to the AI during generation."
}
```


### gemini — remember/01-insight

```json
{
  "task_compliance": "Both outputs successfully extracted the lesson and provided the requested structured note format, but both completely failed the implicit 'permanent vault' requirement to be shorter and sharper than the source text (both more than doubled the input length).",
  "verbosity_penalty_applied": "Yes. Both outputs were heavily penalized on the Distillation dimension because they expanded a concise 125-word input into ~250-300 word essays, violating the core directive that a great note should be shorter and sharper.",
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 3,
      "justification": "Uses clean markdown headings, but includes hallucinated, unmaintainable static metadata (e.g., 'Confidence: 0.85', 'Times referenced: 0') which degrades the scannability of a permanent note."
    },
    {
      "dimension": "Distillation",
      "score": 2,
      "justification": "Fails the distillation test by expanding a punchy 125-word insight into a 250+ word essay with filler text."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "The title 'Optional onboarding steps that gate value-realization silently kill conversion' is a perfect, actionable claim."
    },
    {
      "dimension": "Connection-making",
      "score": 5,
      "justification": "Explicitly connects the concepts and provides the 'why' (e.g., 'this is a textbook activation failure being misdiagnosed as an acquisition/conversion-copy problem')."
    },
    {
      "dimension": "Tag discipline",
      "score": 4,
      "justification": "Uses the provided tags appropriately, though they are somewhat generic."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 5,
      "justification": "Uses standard YAML frontmatter for metadata and clear 'Summary/Detail' headings, which is perfect for 5-second scanning in a PKM vault."
    },
    {
      "dimension": "Distillation",
      "score": 2,
      "justification": "Also fails the distillation test by writing a 280-word PRD-style document from a 125-word input, adding unnecessary verbosity."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "The title 'Optional Activation Steps Cap Conversion When the Product Has No Value Without Them' is a strong, composable lesson."
    },
    {
      "dimension": "Connection-making",
      "score": 5,
      "justification": "Provides highly specific rationale for the links, noting that 'this case is the canonical example of activation as the binding constraint'."
    },
    {
      "dimension": "Tag discipline",
      "score": 5,
      "justification": "Replaces the generic 'lessons-from-data' with the more structured and searchable 'funnel', keeping a tight, relevant tag list in valid YAML."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Output B wins primarily on Structure and Tag Discipline. While both models unfortunately bloated the text (failing Distillation), B utilized standard, maintainable YAML frontmatter and clean summary/detail headers. Output A hallucinated dynamic database fields ('Confidence: 0.85', 'Times referenced: 0') as static text, which makes no sense for a markdown vault.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B's use of standard YAML frontmatter (`--- type: gotcha-learning ... ---`) is the hallmark of a hand-tuned workflow built for tools like Obsidian. Output A feels freshly generated because it invents fake 'database' metrics like 'Confidence: 0.85' and 'Times referenced: 0'\u2014classic LLM hallucinations of how a note-taking app might work, rather than a practical template a human would design."
}
```


### gemini — remember/02-reference

```json
{
  "task_compliance": {
    "A": true,
    "B": true,
    "notes": "Both outputs successfully captured the decision as an architectural record. No strict prompt-level negative constraints were violated to trigger the 3/5 cross-cutting cap, though both failed the distillation ideal."
  },
  "verbosity_penalty_applied": "Applied heavily to the Distillation scores of both A and B. Both expanded a concise 150-word input into lengthy documents (A: ~280 words, B: ~380 words), padding the core lesson with boilerplate or dense prose.",
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 5,
      "justification": "The explicit metadata block, bolded summaries, and clear bulleted sections make the note exceptionally easy to scan in under 5 seconds."
    },
    {
      "dimension": "Distillation",
      "score": 2,
      "justification": "Fails to condense the text, instead padding the original input with unnecessary ADR boilerplate like 'Confidence: 0.8' and 'Times referenced: 0'."
    },
    {
      "dimension": "Title quality",
      "score": 3,
      "justification": "The title 'Decision: Use FastAPI BackgroundTasks instead of Celery...' is a factual log of an event rather than a generalizable, composable lesson."
    },
    {
      "dimension": "Connection-making",
      "score": 4,
      "justification": "Successfully creates an explicit link to the 'Boring Tech Wins' principle and provides a concrete sentence explaining why it applies."
    },
    {
      "dimension": "Tag discipline",
      "score": 4,
      "justification": "Reuses the specific, highly relevant tags from the input without diluting them with generic filler."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 4,
      "justification": "Uses clean YAML frontmatter and headings, but the prose in the 'Detail' section is somewhat dense and slightly less skimmable than A's bullet points."
    },
    {
      "dimension": "Distillation",
      "score": 2,
      "justification": "Severely penalized for verbosity; it takes nearly 400 words of dense prose to explain what the original input communicated clearly in 150."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "An outstanding claim-based title ('FastAPI... Beats Celery Until We Cross 60s p99 or 8 Workflows') that allows a future reader to grasp the exact lesson instantly."
    },
    {
      "dimension": "Connection-making",
      "score": 4,
      "justification": "Connects to the boring tech principle smoothly within the text, explicitly stating that picking the smallest tool justifies the decision."
    },
    {
      "dimension": "Tag discipline",
      "score": 4,
      "justification": "Filters the provided tags into a clean YAML array of specific, searchable terms."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Output B wins entirely on the strength of its title quality. While both outputs failed the Distillation dimension by expanding rather than condensing the input, B's title perfectly executes the 'claim-based' rubric requirement, making it vastly superior for long-term knowledge retrieval.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B shows hallmarks of a hand-tuned prompt designed for Personal Knowledge Management (PKM), specifically its use of YAML frontmatter and strict adherence to claim-based titles (evergreen notes). Output A hallucinates generic, unprompted ADR metadata ('Confidence: 0.8', 'ID: #dec-001'), which is a classic behavior of a zero-shot LLM responding to 'Save this as an architectural decision record'."
}
```


### gemini — remember/03-reflection

```json
{
  "task_compliance": "Output A partially failed the distillation mandate by expanding the input with hallucinated scientific terms (BDNF, catecholamine) and fabricated metadata. Output B was fully compliant with the core task.",
  "verbosity_penalty_applied": "Yes, applied to Output A's Distillation and Structure scores for heavily padding the note with unnecessary 'incident report' boilerplate and extra word count.",
  "scores_A": [
    {
      "dimension": "Structure",
      "score": 3,
      "justification": "Forces the personal note into a rigid, jarring bug-report format ('Anti-Pattern Observed', 'Root Cause Analysis') with fabricated metadata like 'Confidence: 0.85'."
    },
    {
      "dimension": "Distillation",
      "score": 2,
      "justification": "Fails to condense the lesson, instead expanding the word count by hallucinating neurochemical explanations ('catecholamine + BDNF lift') not present in the input."
    },
    {
      "dimension": "Title quality",
      "score": 4,
      "justification": "Provides a solid, claim-based title ('Yields 2-3x Output'), though prefixing it with 'Learning:' is slightly clunky."
    },
    {
      "dimension": "Connection-making",
      "score": 3,
      "justification": "Explains why the connections matter, but invents fictional vault file paths ('health/ session-notes') which weakens trust in the system."
    },
    {
      "dimension": "Tag discipline",
      "score": 4,
      "justification": "Faithfully applies the exact tags provided in the input prompt with appropriate granularity."
    }
  ],
  "scores_B": [
    {
      "dimension": "Structure",
      "score": 5,
      "justification": "Uses excellent YAML frontmatter and a clean 'Summary / Detail' split that allows the future-self to scan the core lesson in under 5 seconds."
    },
    {
      "dimension": "Distillation",
      "score": 4,
      "justification": "The Summary section perfectly extracts the durable lesson in a tight paragraph, though the subsequent sections slightly repeat the input's narrative."
    },
    {
      "dimension": "Title quality",
      "score": 5,
      "justification": "An exceptionally strong, active claim ('Skipping the Gym... Halves Deep-Work Output') that immediately imparts the lesson."
    },
    {
      "dimension": "Connection-making",
      "score": 5,
      "justification": "Explicitly links to related concepts and provides excellent, logical single-sentence explanations for why each connection matters (e.g., 'morning stack avoids the crash window entirely')."
    },
    {
      "dimension": "Tag discipline",
      "score": 4,
      "justification": "Properly formats specific tags into a YAML array, though it slightly missed the 'personal' tag from the original input."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Output B won decisively across Structure, Distillation, and Title Quality. It created a highly actionable, easily scannable note, whereas Output A bloated the text with hallucinated science and an overly rigid 'incident-report' format.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output A exhibits classic LLM-generated artifacts: hallucinating fake system IDs ('#learn-002'), inventing confidence scores, and blindly applying a generic software engineering post-mortem template to a personal journal entry. Output B features bespoke YAML frontmatter ('type: gotcha-learning') and a pragmatic Summary/Detail hierarchy, which are strong signals of a hand-tuned Personal Knowledge Management (PKM) workflow."
}
```

