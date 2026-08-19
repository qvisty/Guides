---
name: sop-rewriter
description: Rewrites a standard operating procedure so an automation is embedded in it, covering the human's new role, review duties, exception handling, and the manual fallback. Use during rollout, before full volume.
---

# SOP Rewriter

Your job is to rewrite the written procedure so someone hired next month learns the new way, not the old one.

## Procedure

1. Get the current procedure. If none exists in writing, say that plainly, then write the new one from the runtime spec and note that there's no prior version to compare against.

2. Mark every step in the old procedure as: unchanged, now automated, changed for the human, or removed.

3. Write the new procedure, ordered as the work now happens. For every step where the human interacts with the automation, cover:
   - What the automation produces and where it appears.
   - What the human is checking. Be specific about the fields and the failure modes worth looking for. "Review for accuracy" trains nobody.
   - How long the check should take. If a reviewer is spending as long checking as they used to spend doing, the design needs revisiting and someone should hear about it.
   - What to do when something's wrong: correct it, reject it, escalate it, and where the correction gets recorded so the workflow can be improved.

4. Write the **exception procedure** as its own section: what to do when the automation refuses, when confidence is low, when a source system is down, and when the item is genuinely unusual.

5. Write the **manual fallback** as its own section. Full instructions for completing the work without the automation, written for someone who has never done it that way. This section is why the workflow survives an outage.

6. Write the **change summary** for the affected roles: what you no longer do, what you now do instead, what you're accountable for, and where the time goes. Address the status question directly and without spin. People read a new SOP looking for whether their job got smaller.

## Output format

- **The new procedure**, numbered, with the exception and fallback sections.
- **Change table:** Old step, Status, New step, Who's affected.
- **Training note**, half a page, written to the affected roles in plain language.
- **Documents to update elsewhere.** Job descriptions, onboarding checklists, quality scorecards, and any other place the old procedure is referenced.

## Rules

- Write for the person doing the job, not for an auditor.
- Never write "review the output" without saying what to look for.
- The manual fallback is required. A workflow with no documented manual path is a single point of failure with a nice interface.
