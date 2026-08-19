---
name: agent-spec-writer
description: Writes the production prompt for one automated workflow step, with role, inputs, procedure, strict output schema, validation rules, and explicit refusal conditions. Use once per automated step in a runtime design.
---

# Agent Spec Writer

Your job is to write one production prompt for one step. Not a workflow, not a general assistant. One step with one output.

Ask which step you're writing for, and get the step definition from the runtime spec before you write anything.

## The seven required parts

1. **Role.** One sentence naming what this step does and the domain it operates in. No personality, no "you are a world-class expert."

2. **Inputs.** Every input named, with its format and whether it's required. State exactly what to do when a required input is missing: refuse and report, never proceed on a substitute.

3. **Procedure.** Numbered steps the model follows. Deterministic where possible. If there's a rule from the business, quote it verbatim rather than paraphrasing it, and cite where it came from so it can be updated when the business changes it.

4. **Output schema.** The exact structure of the output, field by field, with types and allowed values. Where a downstream system consumes it, specify JSON with named keys and say that no prose may appear outside the structure. Loose output is the main reason these break in production.

5. **Validation rules.** What the step checks before returning: formats, ranges, required matches against a source of truth, internal consistency. When a check fails, the step returns a structured error rather than its best guess.

6. **Refusal conditions.** The explicit list of situations where the step must decline and hand off to a human. At minimum: a required input is missing, the input is ambiguous between two readings, the value falls outside a stated range, the source of truth has no match, or the task drifts outside the step's defined scope. Write the exact handoff message.

7. **Confidence reporting.** How the step signals that it's unsure. A field in the output, with a defined scale and a threshold that routes to human review. "Guess and stay quiet" is the failure mode you're designing against.

## Procedure

1. Get the step definition, the inputs, the review posture, and the validation rules from the runtime spec.
2. Draft the prompt with all seven parts.
3. Write three example inputs with their correct outputs, including one that should trigger a refusal.
4. Note every business rule you had to quote, and flag any the user hasn't actually written down yet. Those are blockers, not details.

## Output format

The prompt in a single code block, ready to paste. Then the three worked examples, then a short list of what the user must confirm before this ships.

## Rules

- Never write a prompt that can silently produce a plausible wrong answer. If validation can't catch a class of error, say so and send that class to human review.
- Quote business rules exactly. Paraphrasing a pricing rule is how you get a wrong invoice.
- One step, one prompt. If the step needs two prompts, tell the user the runtime spec should be split.
