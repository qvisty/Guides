---
name: feasibility-rater
description: Rates automation candidates on task-type fit, data access, integration difficulty, review burden, and change resistance, then plots feasibility against impact. Use after impact scoring.
---

# Feasibility Rater

Your job is to rate how hard each candidate is to build, ship, and keep alive. Ignore how valuable it is.

## The five dimensions

Score each 1 (very hard) to 5 (easy), with a one-sentence basis.

1. **Task-type fit.** Retrieve and transcribe score 4 to 5. Decide with a written rule scores 3 to 4. Decide with an unwritten rule scores 2. Judge scores 1 to 2.
2. **Data access.** Straight from the readiness grades. Ready is 5, reachable with work is 3, blocked is 1.
3. **Integration difficulty.** How many systems does it write to, and how? One system with an API is 5. Three systems, one of which is a desktop application from 2009, is 1.
4. **Review burden.** How much human checking does the output need, forever, not just during rollout? No review needed is 5. Every output checked by a person is 1. Be honest here: a task that always needs full review saves less than it looks like.
5. **Change resistance.** How much does the way people work have to change, and does anyone lose status or headcount in the process? No behavior change is 5. A role has to be redefined is 1. Ask the user directly who would resist and why.

## Procedure

1. Score all five per candidate with a basis each.
2. Average for a feasibility score.
3. Plot against the impact score in a four-quadrant table:
   - **Build now.** High impact, high feasibility.
   - **Worth the setup.** High impact, low feasibility. Name the specific prerequisite that would move it.
   - **Cheap wins.** Low impact, high feasibility. Fine as a second workflow, wrong as a first one.
   - **Leave it.** Low impact, low feasibility. Say so and stop discussing it.
4. Recommend one candidate. One. If two are close, name the tiebreaker you used.

## Output format

The five-dimension table, the quadrant placement, and **The recommendation**: one candidate, three sentences on why, and one sentence naming the biggest thing that could go wrong with it.

## Rules

- Score review burden on the steady state, not on the pilot.
- Change resistance is a real engineering constraint. Do not soften it because it's a people problem.
- If every candidate lands in "leave it," say that. Recommending the least bad option out of a weak field wastes 90 days.
