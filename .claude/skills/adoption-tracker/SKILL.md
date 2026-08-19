---
name: adoption-tracker
description: Defines usage signals, abandonment thresholds, and a weekly review agenda to detect whether a live automated workflow is actually being used or quietly worked around. Use from first go-live onward.
---

# Adoption Tracker

Your job is to make workaround behavior visible. Assume the workflow will be bypassed and design the signals that would show it.

## The five signal types

1. **Coverage.** What share of eligible instances actually went through the workflow? The denominator matters most: count every instance that could have used it, not just the ones that did. This is the signal that catches quiet abandonment.
2. **Completion.** Of the runs that started, how many finished without a human taking over mid-flight?
3. **Override.** How often does the reviewer change the output, and which fields do they change? A rising override rate on one field is a fixable design problem. A rising override rate everywhere means the reviewers don't trust it.
4. **Latency.** Time from trigger to completion, including the human review. Compare against the old cycle time. If the automation is slower end to end because reviews queue up, people will route around it and they'll be right to.
5. **Workaround.** Direct evidence of the old path still in use: manual entries created outside the workflow, the old spreadsheet still being edited, emails asking someone to "just do it the normal way," volume in the legacy queue.

## Procedure

1. For each signal, define the exact measure, where the data comes from, who pulls it, and how often.
2. Set a target and a floor for each. The floor is where you intervene.
3. Define **abandonment** explicitly for this workflow, as a condition in the data. For example, coverage below 60 percent for two consecutive weeks with no volume explanation. Write it down now, because after go-live everyone becomes an optimist.
4. Write the weekly review agenda: five questions, fifteen minutes, same time every week, with the process owner present. Include one question that requires talking to an actual operator rather than reading a number.
5. Design the **feedback loop.** Where do operators report that something's wrong, who reads it, and what's the commitment on response time? Silent frustration turns into workaround within about a month.
6. Set the cadence taper: weekly for the first eight weeks, then monthly, with a named trigger that puts it back to weekly.

## Output format

- **Signal table:** Signal, Measure, Source, Owner, Cadence, Target, Floor.
- **Abandonment definition**, one sentence, as a data condition.
- **Weekly review agenda**, five questions.
- **Feedback loop**, three sentences.
- **Escalation.** What happens when a signal breaches its floor, and who's told.

## Rules

- Coverage is the primary signal. Never report completion or accuracy without coverage next to it.
- Never define adoption purely by run count. A workflow running 200 times a month on 3,000 eligible instances has been abandoned.
- Always include one signal that requires talking to a human being.
