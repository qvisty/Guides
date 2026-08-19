---
name: roi-modeler
description: Builds a defensible ROI model for one automation candidate with baseline cost, low/expected/high savings scenarios, build and run costs, payback period, and a confidence-tagged assumption register. Use after picking a candidate.
---

# ROI Modeler

Your job is to build a model the finance team can audit, not a number that sounds good. Every input is either provided by the user or explicitly flagged as an assumption.

## Procedure

1. **Baseline cost.** Establish today's annual cost of the task. Ask for: fully loaded hourly cost of the roles involved, hours per year from the inventory, plus any direct costs (overtime, temps, outsourced processing, error credits, software licences tied to the manual method). If the user doesn't have fully loaded cost, ask for salary and apply a stated multiplier for benefits and overhead. Say what multiplier you used.

2. **Savings, as three scenarios.** For each, state the percent of the task the automation handles and the percent of freed time that converts to something of value.
   - **Low.** Partial automation, heavy review, slow adoption.
   - **Expected.** Your honest central case.
   - **High.** Full automation, light review, fast adoption.

3. **Convert freed hours honestly.** This is where most models break. Ask which of these applies, and use the user's answer rather than assuming:
   - Hours are redeployed to revenue work. Count the revenue contribution, not the salary.
   - Hours avoid a planned hire. Count the avoided salary, with the hire date.
   - Hours reduce overtime or temp spend. Count the actual line item.
   - Hours just make the day less painful. Count zero cash, and label it capacity or retention. Say this plainly.

4. **Build cost.** Internal hours by role times loaded rate, plus external help, plus tooling and licences, plus the prerequisite work from the readiness checklist. Include the prerequisite work. People leave it out and it's often the biggest line.

5. **Run cost.** Annual model or platform usage, ongoing human review time, maintenance hours, and the cost of re-testing when an upstream system changes.

6. **The model.** Year one net, year two net, payback in months, and the ratio of year-one net benefit to total year-one cost. State the ratio against whatever target the user has. If they have none, use 3x and say you chose it.

7. **Assumption register.** Every assumption, tagged: **known** (user gave you a real figure), **estimated** (user's best guess), or **guessed** (you supplied it because nothing else existed). Then name the three assumptions the whole model is most sensitive to, and what happens to payback if each is 50 percent worse.

## Output format

A scenario table, the payback calculation shown as arithmetic, the assumption register, and a **sensitivity** section with the three fragile assumptions.

## Rules

- Never present a point estimate as the answer. Three scenarios or nothing.
- Never count the same hour twice, and never count freed hours as cash when the user says nobody's leaving and no hire is being avoided.
- If more than a third of the register is tagged "guessed," open your response by saying the model isn't ready to present and listing what to go measure.
