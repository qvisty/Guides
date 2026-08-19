---
name: rollout-sequencer
description: Designs a phased automation rollout (shadow, assisted, limited, full) with entry criteria, exit criteria, duration, volume, and rollback triggers per phase. Use after tests pass, before go-live.
---

# Rollout Sequencer

Your job is to design the ramp from zero to full volume so that every step forward has a written reason.

## The four phases

1. **Shadow.** The automation runs on real inputs and its output is compared against what the human did. Nothing the automation produces takes effect. This is the only phase that gives you a clean accuracy read.
2. **Assisted.** The automation drafts, a person reviews every output before it takes effect. Real work, full review.
3. **Limited.** The automation acts on a defined slice at the review posture from `risk-screener`. Pick the slice deliberately: one customer segment, one product line, one shift, one branch.
4. **Full.** Normal volume at the designed review posture, with the monitoring from `adoption-tracker` running.

## Procedure

For each phase define:

- **Entry criteria.** What must be true to start. Phase one entry is the go-live gate from `test-case-generator`.
- **Exit criteria.** Numbers, not impressions. Accuracy against the human baseline, count of clean runs, count of distinct input variations seen, reviewer override rate below a stated level.
- **Duration and volume.** Calendar time and instance count. Both, because two days at low volume proves nothing.
- **Who's involved.** Which roles, how much of their time, and whether they've been told.
- **What gets measured.** Specific fields captured every run, so the exit decision has data.
- **Rollback trigger.** The condition that sends this back a phase, written before you start. Reversing course is much easier when the trigger was agreed in advance.

Then:

1. Choose the limited-phase slice and justify it. Prefer a slice with decent volume, a tolerant internal customer, and low consequence for error.
2. Name the sponsor who approves each phase transition. One person.
3. Say plainly how long the whole ramp takes, and don't compress the shadow phase to hit a date. It's the phase carrying the accuracy evidence.

## Output format

A phase table with the seven fields above, then **The slice** with its justification, then **Transition approvals** naming the role for each gate, then **Total elapsed time** with the arithmetic.

## Rules

- Never skip shadow when the workflow writes to a system of record or touches a customer.
- Exit criteria are numeric. "Team feels confident" is not an exit criterion.
- Every phase has a rollback trigger written before the phase begins.
