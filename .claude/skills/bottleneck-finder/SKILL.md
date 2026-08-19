---
name: bottleneck-finder
description: Separates touch time from wait time in a mapped process, ranks where calendar time is actually lost, and distinguishes delays automation can fix from staffing or policy problems. Use after task inventory.
---

# Bottleneck Finder

Your job is to find where the process waits, not where it works. These are different problems with different fixes, and conflating them is how automation projects miss their target.

## Definitions

- **Touch time.** A person or system actively working on the item.
- **Wait time.** The item exists and nothing is happening to it. Queues, inbox backlogs, "waiting for approval," overnight batch gaps, someone on PTO.
- **Cycle time.** Touch plus wait, start to finish, in calendar hours.

## Procedure

1. From the map and inventory, total the touch time per instance.

2. Ask the user for actual cycle time, start to finish, in calendar hours or days. If they don't know, ask them to pull ten recent instances and check timestamps. Do not estimate this for them.

3. Wait time is cycle time minus touch time. Present the ratio.

4. Locate the wait. For each handoff between steps, ask how long items typically sit. Ask specifically about: single-approver dependencies, work that only moves during business hours, batch processes that run once a day, and steps where one person is the only one who can act.

5. Classify each delay by its actual cause:
   - **Capacity.** Not enough people for the volume. Automation helps if it removes touch time from the constrained role, and only then.
   - **Sequence.** Steps run one after another that could run at the same time. Redesign, not automation.
   - **Authority.** Waiting on a decision only one person can make. Delegation or a written rule, not automation.
   - **Availability.** The system or the person isn't reachable. Scheduling or integration.
   - **Rework.** The item goes backward. Fix the upstream quality problem first.

6. Rank delays by calendar hours lost per week.

## Output format

- **The ratio.** Touch time versus wait time per instance, with the arithmetic shown.
- **Ranked delays table:** Where it waits, Cause type, Hours lost per week, Would automation fix it (yes / partly / no), What would actually fix it.
- **The honest note.** If automating every touch-time task would cut cycle time by less than 20 percent, say so in one sentence at the top of your response. Do not bury it.

## Rules

- Never label a capacity problem as an automation opportunity without saying which role's hours get freed.
- If cycle time data doesn't exist, say the analysis is blocked and name the ten instances that need pulling. Don't guess a ratio.
