---
name: test-case-generator
description: Generates a full test set for an automated workflow, covering happy path, edge cases, adversarial inputs, integration failures, and refusal behavior, with expected outcomes and a go-live pass threshold. Use before go-live.
---

# Test Case Generator

Your job is to write the test set that has to pass before this workflow touches real work, and to define the threshold that counts as passing.

## The six categories

Generate cases across all six. Skew the count toward the last four, because that's where production failures live.

1. **Happy path.** The normal case, two or three variants.
2. **Edge cases.** Legitimate but unusual inputs: the biggest order anyone's placed, a customer with no history, a document with an odd layout, a field in an unexpected unit or currency, a name with characters outside the usual set, a date at a period boundary.
3. **Bad inputs.** Missing required fields, wrong format, empty file, duplicate submission, truncated document, two conflicting values for the same field.
4. **Adversarial inputs.** Content designed to make the step do something it shouldn't: instructions embedded in a document the step is reading, a value that would pass validation but be commercially wrong, a request that drifts outside the step's scope.
5. **Integration failures.** Each system unreachable, each credential expired, a timeout mid-run, a partial write, the same item processed twice.
6. **Refusal and handoff.** Every refusal condition from the step prompts, verified to actually trigger. Plus the human checkpoint stalling, so you can confirm the timeout path works.

## Procedure

1. Pull the validation rules and refusal conditions from the step prompts. Every single one gets at least one test.
2. Write each case as: number, category, input description, expected behavior, and how a person verifies the result.
3. Mark each case **blocking** or **non-blocking**. Blocking cases are ones where a failure means no go-live, no exceptions. Every case in categories 4, 5, and 6 that touches a customer or a system of record is blocking.
4. Ask the user for ten to twenty real historical instances to run as a regression set, including any known nightmare cases. Real data finds things invented cases don't.
5. Define the go-live gate: all blocking cases pass, plus a stated pass rate on the regression set, plus a named person who signs off. Make the sign-off a person, not a committee.

## Output format

- **Test table:** Number, Category, Input, Expected behavior, Verified how, Blocking (yes/no).
- **Regression set request.** Exactly what historical data to pull and how many instances.
- **Go-live gate**, written as a short paragraph the sponsor can approve.
- **Known gaps.** What you cannot test before go-live, and what to watch in the first two weeks instead.

## Rules

- Never write a test with a vague expected behavior. "Handles it gracefully" isn't testable. Say what the output should be.
- Every refusal condition gets a test. If a refusal was never verified, assume it doesn't work.
- If the user wants to launch with blocking cases failing, write down which ones and who decided. That record protects everyone.
