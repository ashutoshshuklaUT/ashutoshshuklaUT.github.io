---
title: "git diff --two-years"
date: 2026-06-24
categories: []
tags: []
---
Two years ago I joined as a data scientist. I had strong technical instincts and a vague sense that good models were the point. I was wrong about that — at least about which part is hardest.

Here is what I actually learned.

---

## Dollar logic comes before code

The single most important shift in how I think: impact is not a story you tell after shipping. It is a precondition for starting.

Before any feature gets prioritized, I want a defensible dollar value attached to it. Not a vague business case, not a narrative about efficiency — an actual number, ideally one finance will stand behind. If I can't construct that logic upfront, I treat that as a signal the feature isn't ready to build yet, not that I need to work harder on selling it.

This changes how you prioritize. You stop building features because they're interesting or because a stakeholder asked for them. You build in order of expected dollar impact per unit of engineering effort, and you're honest about that math.

The corollary: I want to work where, if I work hard, it actually shows in numbers. That's not mercenary — it's the only way to know if you're pointing in the right direction.

---

## Adoption is a process problem, not a persuasion problem

The second big lesson, and the one that took longer to learn.

I spent time in my first year trying to convince people that the model was good. That's the wrong frame. You don't win adoption by arguing for your solution. You win it by building a process where the comparison is unavoidable and measurable.

What that looks like in practice:

**Deploy first, measure second.** Don't wait for the model to be perfect. Ship it, then instrument it. The feedback you get from real usage is worth more than another month of offline evaluation.

**Make rejection actionable.** When a solution gets rejected on the ground, my reflex used to be frustration. Now I treat it as a data collection problem. A criticism with no counter-solution isn't measurable, so I build the process that forces the counter-solution to exist. When a field team can't execute the model's output, they submit their own solution on the same input. That gives you two plans on identical inputs — now you can compare them against the metrics you actually care about.

**Release on a cadence.** Bi-weekly releases with a real change-management process: tool training, feedback workshops, structured rollouts. Technical debt is only taken on when adoption is trending in the right direction.

The deeper principle: you don't compare performance instance-by-instance. You compare distributions. One bad example doesn't disprove the model. The question is whether the distribution of outcomes is shifting.

---

## Alignment is Phase Zero, not an afterthought

A project should not enter engineering until a few things are locked down:

- Business buy-in from the people who will actually use it
- Finance alignment that can vouch for impact — not just "this seems valuable" but "if this metric moves, it hits our books"
- Committed leadership from every team the project's success depends on
- A measurement contract: what you'll track, how each metric ties to a business outcome, which team owns moving which number, and a baseline

Without this, you can ship technically impressive work and have it go nowhere. I know this because I've seen it happen. Two years of model development, zero percent adoption — the technical work was real, but the alignment infrastructure was missing.

Getting alignment right is harder than getting the model right. And it compounds. Every hour you spend in Phase Zero saves multiples downstream.

---

## Feedback is labeled data

This one reframed how I think about post-production.

Raw feedback from users is low signal. It's high volume, it's inconsistent, and it's hard to act on. But if you design your feedback-capture process correctly, every piece of feedback becomes a labeled example for back-testing.

The setup: when the model's solution can't be executed, the human completes the same task on the same input and submits their solution. Now you have a ground-truth label. You can run back-tests on it. You can measure whether, on average across that distribution, you're improving.

This is what separates a model that gets better over time from one that just accumulates complaints.

---

## The proof

These aren't abstractions. Over 24 weeks and 16 deployments, the playbook above moved the numbers I care about:

- **Compliance**: 10% → 87%
- **Adoption**: 0% → 60%
- **Projected value**: ~$10M in 2026

For the SLOT project specifically — which optimizes switch-list generation in freight rail yards — we ran a finance-led study to put a dollar figure on the cost pool. The work came down to two levers: labor (trainmaster time to generate switch lists) and quality (poor switch lists cause rework, extra pinpulls, non-compliant placements). We built a grading framework across experience levels and computed benefit as the cost delta between what a human at a given experience level would produce versus what SLOT produces. That framing — splitting the gain into compliance wins versus genuinely better solutions — matters, because a win that only came from breaking a rule isn't a win.

---

## What I'm still figuring out

I don't have a good cross-functional conflict story yet. The alignment principles exist, but I haven't written down a crisp case where two committed leaders disagreed and I had to navigate it. That's real work and it deserves a real account.

The collaboration story from building our exec dashboard also needs a proper arc. Right now I have the setup and the outcome but not the decision and the tradeoff in between. I'll write that when I've thought it through.

---

The through-line across all of this: optimize for leverage. Not for lines of code, not for model complexity, not for how technically interesting the problem is. For leverage — the decisions and systems that multiply the output of everyone around you. That's what two years in has taught me to care about.

