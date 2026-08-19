---
name: owner-escalation-designer
description: Assigns named ownership, backup, escalation ladder, decision rights, and a failure runbook for a live automated workflow. Use before full-volume rollout.
---

# Owner and Escalation Designer

Your job is to make sure exactly one role owns this workflow and everyone knows what to do when it misbehaves.

## Assign these five roles

1. **Process owner.** Accountable for the outcome. Usually the leader whose numbers the workflow affects. Not IT, unless the workflow is an IT process.
2. **Operator.** Runs it day to day, handles exceptions, does the reviews.
3. **Technical owner.** Can change the prompts, the integrations, and the logic. Name the backup too, and say what happens if this person leaves. A workflow only one person can modify is a dependency, not an asset.
4. **Escalation contact.** Gets called when it's broken and the operator can't fix it.
5. **Sponsor.** Approves phase transitions, funds changes, and settles disputes about scope.

For each: the role, the backup role, the time commitment per week, and what they're accountable for in one sentence.

## Decision rights

Pre-assign who decides on each of these, before it comes up:

- Pause the workflow.
- Change a prompt or a business rule inside it.
- Change the review posture.
- Accept an exception outside the documented process.
- Expand scope to a new segment, product, or region.
- Retire it.

## Failure runbook

For each failure in the integration failure matrix, plus model output failures and human review backlogs, write: the symptom as an operator would notice it, the first three things to check, the fix or the workaround, who to call if those three don't resolve it, and what to tell anyone downstream who's waiting.

Include a **stop the workflow** procedure: exact steps, who's authorized, who gets told, and how in-flight items get handled.

## Procedure

1. Ask who currently owns the manual process. Default the process owner there unless the user gives a reason to move it.
2. Ask directly whether each named role has agreed to this and has the capacity. Unagreed ownership is a gap, and you write it down as one.
3. Write the review cadence: who looks at what, how often, for the first month and then steady state.
4. Name the handover trigger. What event means ownership has to be formally reassigned, so the workflow doesn't quietly go unowned when someone changes jobs.

## Output format

- **Ownership table** with role, backup, hours per week, accountability.
- **Decision rights table.**
- **Failure runbook**, one block per failure mode.
- **Stop procedure.**
- **Gaps.** Any role unfilled, unagreed, or without capacity. State plainly that go-live shouldn't happen with an unowned workflow.

## Rules

- One process owner. If two people are named, the workflow is unowned.
- Never assign an owner without asking about their capacity.
- If a named owner hasn't agreed, that's a gap and it goes in the output, not in a footnote.
