---
name: task-inventory
description: Breaks mapped process steps into individual tasks and classifies each as retrieve, transcribe, decide, judge, or communicate, with the cost of a wrong answer. Use after process mapping, before scoring automation candidates.
---

# Task Inventory

Your job is to decompose a process map into tasks and classify each one. Classification drives everything downstream, so be strict about it.

## The five task types

- **Retrieve.** Find and return existing information. Low judgment, high volume. Usually the safest automation.
- **Transcribe.** Move information from one format or system to another. Includes reading documents and typing into forms. Verifiable against a source, which makes it testable.
- **Decide.** Apply a written rule to inputs and produce an outcome. Automatable when the rule is genuinely written down. If the rule lives in someone's head, it's a judge task until it gets written.
- **Judge.** Weigh factors without a fixed rule. Requires human review, sometimes permanently. Assist rather than automate.
- **Communicate.** Draft or send something to a person. Drafting automates well. Sending without review rarely should.

## Procedure

1. Take the process map. For each step, list every discrete task inside it. A step usually holds two to five tasks. If a step yields one task, check whether the map was written at the task level already.

2. Assign exactly one type per task. When a task looks like two types, split it. "Review the invoice and approve it" is a retrieve plus a judge.

3. For each task, record: minutes per instance, instances per week, and whether the output is verifiable against a source of truth.

4. For each task, ask what a wrong answer costs. Use four levels: cosmetic, rework, customer-visible, regulatory or financial. Do not skip this. It decides the review posture later.

5. Flag every decide task where the rule is not written down anywhere. These are the most common false positives in AI scoping.

## Output format

A table: Task, Parent step, Type, Minutes per instance, Instances per week, Verifiable (yes/no), Cost of a wrong answer.

Then:

- **Weekly minutes by type.** Which type holds the most time.
- **Unwritten rules.** Every decide task with no documented rule, and who would need to write it.
- **Do not automate.** Judge tasks with customer-visible or regulatory consequences, listed plainly.

## Rules

- One type per task. No hybrids.
- Do not upgrade a judge task to a decide task because automating it would be convenient.
- If minutes or volumes are unknown, write unknown. Do not interpolate.
