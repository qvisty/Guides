---
name: impact-scorer
description: Scores automation candidates on hours reclaimed, error cost, cycle-time reduction, and revenue exposure, requiring a stated basis for every score. Use after task inventory to rank candidates by value.
---

# Impact Scorer

Your job is to score the value side only. Feasibility, cost, and risk are scored by other skills. Keep them out of your reasoning here.

## The four dimensions

Score each 1 to 5. Every score needs a basis in one sentence, drawn from the inventory data or from something the user told you. A score with no basis is written as "unscored," not as 3.

1. **Hours reclaimed per year.** From the inventory: minutes per instance times instances per year, times the share of the task realistically automatable. Be conservative on that share and state it.
2. **Error cost.** What do mistakes in this task cost today, in rework, credits, write-offs, or customer churn? Use the cost-of-a-wrong-answer field from the inventory.
3. **Cycle-time reduction.** How much calendar time comes out, per the bottleneck analysis. A task with high touch time but no effect on cycle time scores low here, and that's correct.
4. **Revenue exposure.** Does this task sit between a customer and a purchase, a renewal, or a payment? Quote-to-cash and inbound response tasks score high. Internal reporting scores low.

## Procedure

1. Score each candidate on all four. State the basis for each.
2. Compute a total. Weight hours and error cost at 1.0, cycle time at 1.5, revenue exposure at 1.5, because in mid-market operations the constraint is usually speed and revenue capture rather than labor cost. Show the weighting so the user can change it and re-run.
3. Rank by weighted total.
4. Separate out the **annoyance trap**: candidates the user described with frustration but that score under 8 weighted. Name them and say plainly that they're irritating rather than expensive.
5. Name the top three and, in one sentence each, say what makes them valuable.

## Output format

A table: Candidate, Hours (score + basis), Error cost (score + basis), Cycle time (score + basis), Revenue exposure (score + basis), Weighted total.

Then **Top three**, **The annoyance trap**, and **Unscored**, listing what data would be needed to score them.

## Rules

- Never invent a volume, a rate, or a dollar figure. Unscored is an acceptable answer.
- Do not adjust a score because a candidate seems hard to build. That's the feasibility skill's job.
- If the user pushes for a favorite to rank higher, ask which input they want to change and re-run. Do not quietly re-weight.
