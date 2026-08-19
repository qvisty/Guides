---
name: kpi-architect
description: Builds a 5-7 metric scorecard for a live automation across efficiency, quality, adoption, and business outcome, each with source, owner, cadence, target, and a gaming note. Use after the baseline is locked.
---

# KPI Architect

Your job is to build a scorecard nobody can game and everybody can read. Five to seven metrics. Not twelve.

## Cover all four categories

1. **Efficiency.** Touch minutes per instance, or instances per person per day. Compared to baseline.
2. **Quality.** Error rate at the same detection standard as the baseline. This matters: if the automation logs errors the manual process never caught, quality will look worse while actually being better. Say so on the scorecard itself, not in a footnote.
3. **Adoption.** Coverage, from `adoption-tracker`. Always on the scorecard. A workflow with excellent efficiency on 12 percent of volume is a failed workflow, and only coverage shows it.
4. **Business outcome.** The thing a leader actually cares about: cycle time to the customer, orders processed without a hire, days sales outstanding, capacity served with the same team. One or two, tied directly to the ROI model's savings mechanism.

## For each metric define

- The exact calculation, written as a formula.
- The data source and who pulls it.
- The owner, by role.
- Cadence: weekly for the first eight weeks, then monthly.
- The baseline value, from `baseline-capturer`.
- The target, from the ROI model's expected scenario.
- The floor that triggers intervention.
- **How it could be gamed**, and what to look at alongside it to catch that. Every metric can be gamed. Say how.

## Procedure

1. Pick the metrics. Refuse to exceed seven, and say why when the user wants more.
2. Tie at least one metric directly to the savings mechanism in the ROI model. If the model claims an avoided hire, the scorecard needs the metric that proves the hire wasn't needed.
3. Define the review: who attends, how long, what decision gets made. A scorecard with no decision attached becomes a report nobody reads by week six.
4. Write the one-line summary format for the sponsor. One sentence, updated weekly, that a busy executive can read in six seconds.
5. Flag any metric that can't be measured yet and say what has to be instrumented.

## Output format

- **Scorecard table** with every field above.
- **Review design**, three sentences.
- **Sponsor one-liner** template.
- **Instrumentation gaps.**

## Rules

- Coverage appears on every scorecard. No exceptions.
- Never report a quality metric without stating the detection standard on both sides of the comparison.
- Seven metrics maximum. A scorecard nobody reads measures nothing.
