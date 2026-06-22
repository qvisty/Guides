# **The AI Operations Starter Pack: 28 Hooks, 12 Integrations, and 4 Role-Based Agents for Mid-Market Teams**

![Anthony.jpeg](attachment:174ae978-347c-4069-81f4-2157721f5418:Anthony.jpeg)

Hey, I'm Anthony Whitaker. I spent 10+ years building AI systems at Amazon, Salesforce, Google, and the NFL. Now I run 90-Day AI ROI Sprints for mid-market companies (50-500 employees) where the board's asking about AI and the team has zero capacity for a six-month consulting engagement.

I put this starter pack together because most mid-market AI projects fail in the same place: nobody can point to a live workflow on Day 30. They have a deck. They have a strategy. They don't have anything in production.

This pack is the documented version of what we hand clients on Day 1 of a Sprint. 28 operational hooks, 12 integration patterns, 15 production-ready prompts, and 4 role-based agent configurations. All in plain text. All deployable with Claude Code, n8n, or your stack of choice.

What you'll get out of it: a working blueprint your ops, finance, RevOps, or service team can clone and stand up against a real process this quarter.

> **Prefer to skip the DIY?**
> If your board is asking about AI and you'd rather have us ship the live workflows in 90 days with a 3x ROI guarantee, that's what the Sprint does.
> Book a 20-min fit call → [https://calendly.com/anthonywhitaker/discovery](https://calendly.com/anthonywhitaker/discovery)

---

### What's Inside

1. **How to use this pack** — The deployment model behind every hook (read this first)
2. **The 7 operational categories** — Where AI actually earns its keep in a mid-market business
3. **The 28 hooks** — Every hook with trigger, action, integration, and expected output
4. **The 12 integrations** — How each system connects and what data flows where
5. **The 15 production prompts** — Copy-paste prompts for the highest-leverage actions
6. **The 4 role-based agent packs** — Pre-bundled stacks for Ops, Finance, RevOps, and Service
7. **The 90-day deployment roadmap** — What to ship in weeks 1-4, 5-8, and 9-12
---

### 1. How to Use This Pack

The pack assumes one thing: you're not trying to put AI everywhere. You're trying to put it in the two or three processes where it actually moves the business.

That means three rules.

**Rule 1: Start where the money is.** Customer-facing first, then internal efficiency, then decision support. Customer-facing has the fastest ROI because the wins show up in deal velocity, win rate, or churn. Internal efficiency is next because the hours saved are real but harder to defend in a board meeting. Decision support is last because it sounds good and is the easiest to deprioritize.

**Rule 2: One process, end-to-end.** Don't deploy 12 hooks across 12 processes. Pick one process. Wire up the 4-6 hooks that own that process. Get it to production. Then move to the next process. Mid-market teams that skip this rule end up with 50 half-built workflows and zero ROI.

**Rule 3: Every hook needs an owner.** The person who owns the underlying business process owns the hook. Not IT. Not the AI vendor. The ops lead, the controller, the head of service. If nobody on the business side owns it, it will rot inside six weeks.

The hooks are organized by operational category, not by department, on purpose. A real workflow usually crosses departments. The hook that flags an invoice exception in NetSuite is owned by finance, but the resolution loop sits in ops. Build for the workflow, not the org chart.

---

### 2. The 7 Operational Categories

This is where production AI actually delivers measurable results in mid-market businesses, ranked by speed-to-ROI based on the patterns we see across Sprint engagements.

| # | Category | What it owns | Typical ROI driver |
| --- | --- | --- | --- |
| 1 | Customer & Revenue Ops | Inbound requests, leads, proposals, customer comms | Faster response, higher conversion |
| 2 | Sales Operations | CRM hygiene, deal updates, forecast support | Rep capacity, forecast accuracy |
| 3 | Service & Support | Ticket triage, case summaries, escalations | Resolution time, agent capacity |
| 4 | Finance & Accounting | Invoices, expenses, month-end, collections | Cycle time, error reduction |
| 5 | Executive Reporting | Board memos, KPI rollups, status reports | Leadership time, decision speed |
| 6 | Procurement & Contracts | Contract review, vendor research, POs | Cycle time, risk reduction |
| 7 | HR & People Ops | Resume screening, policy lookups, onboarding | Hiring throughput, ramp time |

Pick one. Read the 4 hooks underneath it in Section 3. Pick the 2 that solve a process you can name in one sentence. Build those first.

---

### 3. The 28 Hooks

Each hook has four parts: the trigger (what fires it), the action (what Claude does), the integration (where the data lands), and the expected output (what the human sees). Build them in this order inside any category and you'll usually find the first ROI hit on hook 2 or 3.

#### Category 1: Customer & Revenue Operations

**Hook 1.1 — Inbound RFP Triage**

- Trigger: Email lands in `rfp@` inbox or web form submission
- Action: Claude reads the RFP, extracts scope, budget signals, timeline, and decision criteria
- Integration: Salesforce or HubSpot
- Output: New opportunity created with a one-page summary in the notes field, routed to the right AE based on territory and segment
**Hook 1.2 — Customer Email Draft**

- Trigger: Inbound customer email categorized as "common question"
- Action: Claude pulls relevant answer from the knowledge base and drafts a reply
- Integration: Outlook or Gmail + internal KB (SharePoint, Notion, Confluence)
- Output: Drafted reply in the rep's inbox, never auto-sent, always human-reviewed
**Hook 1.3 — Lead Enrichment**

- Trigger: New lead created in CRM
- Action: Claude pulls company size, industry, recent news, tech stack, and key contacts
- Integration: Salesforce or HubSpot + LinkedIn or enrichment API
- Output: Lead record updated with structured firmographic data and a 3-bullet "why this matters" note
**Hook 1.4 — Win/Loss Summary**

- Trigger: Opportunity closed (won or lost) in CRM
- Action: Claude reviews call notes and email thread, drafts a structured win/loss summary
- Integration: Salesforce or HubSpot + Gong or call recording tool
- Output: Win/loss summary attached to the opportunity, tagged by reason category for monthly review
#### Category 2: Sales Operations

**Hook 2.1 — Call → Next Steps**

- Trigger: Sales call recording finishes
- Action: Claude transcribes, extracts next steps, identifies stakeholders mentioned, flags risks
- Integration: Gong or Fireflies + Salesforce
- Output: CRM updated with next steps, stakeholder map, and a risk flag if applicable
**Hook 2.2 — Deal Slip Alert**

- Trigger: Opportunity close date changes by more than 30 days
- Action: Claude reviews recent activity and drafts a "what's actually happening" summary
- Integration: Salesforce + Slack
- Output: Slack DM to the rep's manager with the summary and a recommended next action
**Hook 2.3 — Forecast Q&A**

- Trigger: Sales leader asks a forecast question in Slack
- Action: Claude pulls current pipeline state, applies the company's forecasting rules, returns an answer with the underlying data
- Integration: Salesforce + Slack
- Output: Threaded reply with the answer, supporting deals, and a confidence level
**Hook 2.4 — Stale Opportunity Re-engagement**

- Trigger: Opportunity has had no activity in 21 days
- Action: Claude drafts a context-specific re-engagement email based on the last meaningful interaction
- Integration: Salesforce + Outlook/Gmail
- Output: Draft email in the rep's outbox, scheduled to send after rep review
> **Two hooks in and already saving rep hours?**
> Most teams ship hooks 1.1, 1.3, and 2.1 in the first three weeks of a Sprint and recover 4-8 rep-hours per week. That's the easy ROI.
> Want the full deployment supervised, with a 3x ROI guarantee on the engagement?
> Book a 20-min fit call → [https://calendly.com/anthonywhitaker/discovery](https://calendly.com/anthonywhitaker/discovery)

#### Category 3: Service & Support

**Hook 3.1 — Ticket Triage**

- Trigger: New support ticket created
- Action: Claude classifies by issue type, urgency, customer segment, and routes to the right queue
- Integration: ServiceNow, Zendesk, or Jira Service Management
- Output: Ticket auto-routed and tagged, with a one-line summary in the description field
**Hook 3.2 — Case Resolution Summary**

- Trigger: Support ticket closed
- Action: Claude drafts a knowledge base article from the resolution thread if the issue type is recurring
- Integration: ServiceNow/Zendesk + internal KB
- Output: Draft KB article in review queue, tagged to the relevant product/feature
**Hook 3.3 — Escalation Brief**

- Trigger: Customer requests a manager or ticket flagged as escalation
- Action: Claude assembles a brief: customer history, recent tickets, account value, root cause of current issue
- Integration: ServiceNow/Zendesk + Salesforce or HubSpot
- Output: One-page brief delivered to the escalation manager before the customer call
**Hook 3.4 — Service Call Notes → Action Items**

- Trigger: Service call recording finishes
- Action: Claude extracts customer-promised follow-ups, parts ordered, and next-visit needs
- Integration: Call recording + service management system
- Output: Action items logged to the ticket, parts orders queued, calendar event drafted for next visit
#### Category 4: Finance & Accounting

**Hook 4.1 — Invoice Exception Flagging**

- Trigger: Invoice received via email or upload
- Action: Claude reads the invoice, matches against PO and contract terms, flags exceptions (price, quantity, terms)
- Integration: NetSuite or QuickBooks + email or AP inbox
- Output: Invoice queued in AP with exceptions highlighted, clean invoices auto-routed for approval
**Hook 4.2 — Expense Policy Check**

- Trigger: Expense report submitted
- Action: Claude reviews line items against the expense policy, flags violations with policy references
- Integration: Expensify or Concur + policy doc
- Output: Expense report returned to submitter or escalated, with specific cited violations
**Hook 4.3 — Month-End Variance Commentary**

- Trigger: Month-end close completes
- Action: Claude reads the variance report and drafts commentary on each material variance
- Integration: NetSuite or QuickBooks + reporting tool
- Output: Draft commentary sent to the controller for review, ready to drop into the board package
**Hook 4.4 — Collections Follow-Up**

- Trigger: Invoice ages past 30 days
- Action: Claude drafts a follow-up email tuned to the customer's payment history and current balance
- Integration: NetSuite or QuickBooks + Outlook/Gmail
- Output: Draft email queued in AR clerk's outbox, with a recommended next escalation step
#### Category 5: Executive Reporting

**Hook 5.1 — Board Memo Draft**

- Trigger: Board meeting scheduled (calendar invite or scheduled task)
- Action: Claude pulls financials, KPIs, and recent strategic notes, drafts a board memo against the standard agenda
- Integration: NetSuite + CRM + project management tool
- Output: Draft board memo in shared drive, ready for CEO/CFO review 5 days before the meeting
**Hook 5.2 — Weekly KPI Rollup**

- Trigger: Every Monday at 7am
- Action: Claude pulls KPIs from the source of truth for each metric, assembles a weekly scorecard
- Integration: Multiple (NetSuite, Salesforce, HubSpot, service management)
- Output: Slack post or email to the leadership team with the scorecard and 2-3 commentary bullets
**Hook 5.3 — Project Status Report**

- Trigger: Every Friday at 4pm
- Action: Claude reads project Slack channels, Jira tickets, and recent commits, drafts a status report
- Integration: Slack + Jira (or Asana/Monday)
- Output: Status report posted to the leadership channel, formatted by project
**Hook 5.4 — Investor Update Draft**

- Trigger: Quarter-end close completes
- Action: Claude pulls the quarter's financials, key wins/losses, and strategic notes, drafts the investor update
- Integration: NetSuite + CRM + executive notes
- Output: Draft investor update in shared drive for CEO review
#### Category 6: Procurement & Contracts

**Hook 6.1 — Contract Clause Review**

- Trigger: New contract uploaded to DocuSign or contract management system
- Action: Claude reviews against the standard playbook, flags non-standard clauses with risk levels
- Integration: DocuSign or Ironclad + legal playbook doc
- Output: Annotated contract sent to legal with a one-page risk summary
**Hook 6.2 — Vendor Comparison Matrix**

- Trigger: RFI received from procurement
- Action: Claude reviews vendor responses, builds a side-by-side comparison against your evaluation criteria
- Integration: SharePoint or shared drive + procurement tool
- Output: Comparison matrix drafted in the procurement folder, ready for review
**Hook 6.3 — PO Budget Validation**

- Trigger: Purchase order submitted
- Action: Claude validates against the department's remaining budget, flags overages
- Integration: NetSuite or QuickBooks + procurement tool
- Output: PO routed for approval or returned with budget context
**Hook 6.4 — Renewal Terms Summary**

- Trigger: Vendor contract 90 days from renewal
- Action: Claude reviews the current contract and any new vendor proposal, summarizes deltas
- Integration: DocuSign or Ironclad + procurement tool
- Output: Renewal brief to the contract owner, including price changes and term changes
#### Category 7: HR & People Ops

**Hook 7.1 — Resume Screen**

- Trigger: New application received
- Action: Claude screens against role criteria (skills, experience, location), scores fit, drafts a one-line note
- Integration: ATS (Greenhouse, Lever, Workable) + role spec
- Output: Application tagged with score and note, surfaced or filtered based on threshold
**Hook 7.2 — Policy Lookup**

- Trigger: Employee asks a policy question in Slack or HR portal
- Action: Claude answers from the handbook with a citation
- Integration: Slack + handbook (SharePoint, Notion, Confluence)
- Output: Threaded answer with the cited policy section, escalated to HR if uncertain
**Hook 7.3 — Onboarding Personalization**

- Trigger: New hire created in HRIS
- Action: Claude assembles a role-specific onboarding checklist from the master template
- Integration: BambooHR or Workday + project management tool
- Output: Personalized 30-60-90 plan in the new hire's onboarding workspace
**Hook 7.4 — Performance Review Draft**

- Trigger: Review cycle opens
- Action: Claude pulls the manager's notes, peer feedback, and the employee's accomplishments, drafts a structured review
- Integration: Performance management tool + Slack/email notes
- Output: Draft review in the manager's tool, ready for editing
---

### 4. The 12 Integrations

Twelve systems cover the operational stack for the vast majority of mid-market companies. The hooks above don't need all 12. They need the 4-6 that touch the process you're attacking.

| # | System | Category | What it owns in the stack |
| --- | --- | --- | --- |
| 1 | Salesforce | CRM | Opportunities, accounts, contacts, activity |
| 2 | HubSpot | CRM | Same as Salesforce, smaller end of mid-market |
| 3 | NetSuite | ERP/Finance | GL, AP/AR, financial reporting |
| 4 | QuickBooks | Finance | AP/AR, GL, smaller end of mid-market |
| 5 | Slack | Comms | Real-time team comms, alerts, status |
| 6 | Microsoft Teams | Comms | Same as Slack, Microsoft-shop equivalent |
| 7 | Outlook | Email | Inbound/outbound email, calendar |
| 8 | Gmail (Google Workspace) | Email | Same as Outlook, Google-shop equivalent |
| 9 | ServiceNow / Zendesk | Service | Tickets, cases, knowledge base |
| 10 | Jira / Asana | Project | Project tracking, engineering work, ops tasks |
| 11 | DocuSign / Ironclad | Contracts | Contract storage, signature, lifecycle |
| 12 | SharePoint / OneDrive / Google Drive | Documents | Policies, SOPs, knowledge base, file storage |

The integration pattern is the same for every hook: read a trigger from one system, run the prompt, write structured output to another. The diagram below shows the canonical flow.

event or scheduleread contextcontextstructured outputnotificationapprove or editTrigger SystemClaude AgentKnowledge SourceAction SystemHuman Reviewer

The human reviewer step is not optional. Every hook in this pack assumes a human in the loop. Drafts go to inboxes, not into the wild. That's not a limitation. That's the design.

---

### 5. The 15 Production Prompts

Copy-paste-ready. Each one is structured the same way: role, context, task, output format, constraints. That structure is what makes them work in production instead of just demos.

#### Prompt 1: Inbound RFP Triage

`You are an inbound RFP triage assistant for a mid-market B2B company.

Read the email or document below. Extract:
- Scope (1-2 sentences)
- Budget signals (any numbers, ranges, or implied capacity)
- Timeline (start date, decision date, go-live date)
- Decision criteria (in order, if listed)
- Decision maker(s) and influencers (names and titles)
- Disqualifying factors (geography, regulatory, technical fit)

Output format: JSON with the fields above. If a field is not present, return null. Do not infer.

Constraints: Use only information in the source. Do not assume budget or timeline based on company size.

Source:
{EMAIL_OR_DOCUMENT}`

#### Prompt 2: Customer Email Draft

`You are a customer support assistant. Draft a reply to the email below.

Use only the knowledge base content I provide. Do not invent product features or policies.

Tone: professional, warm, direct. Match the customer's level of formality.

If the question cannot be fully answered from the knowledge base, draft a holding reply that says we'll get back to them within X hours, and flag the gap.

Output format: subject line + email body.

Customer email:
{EMAIL}

Relevant knowledge base content:
{KB_CONTENT}`

#### Prompt 3: Lead Enrichment Summary

`You are a sales research assistant. Given the company name and domain below, produce a structured enrichment record.

Fields:
- Company size (employees, revenue range)
- Industry and sub-vertical
- Recent news (last 90 days) relevant to our product category
- Tech stack signals (if discoverable)
- Top 3-5 likely buyers (titles, not names unless found)
- A 3-bullet "why this matters" note for the rep

Output format: structured fields plus the 3-bullet note.

Constraints: Cite sources for any specific claim (recent news, tech stack). If you cannot verify, do not include.

Company: {COMPANY_NAME}
Domain: {DOMAIN}`

#### Prompt 4: Win/Loss Structured Summary

`You are a sales operations assistant. Review the opportunity record and call/email history below.

Produce a structured win/loss summary:
- Outcome (won/lost) and amount
- Decision driver (one sentence on what actually decided it)
- Competitive context (who else was evaluated)
- Stakeholders by role (champion, economic buyer, blocker, etc.)
- What would have changed the outcome (one sentence)
- Reason category (pick from: price, fit, timing, competitor, internal change, no decision)

Output format: structured fields plus a 2-3 sentence narrative summary.

Source:
{OPPORTUNITY_RECORD_AND_HISTORY}`

#### Prompt 5: Sales Call Next Steps

`You are a sales operations assistant. Read the call transcript below.

Extract:
- Next steps (verb + owner + due date if mentioned)
- Stakeholders mentioned (name, role, what was said about them)
- Risks raised (objections, concerns, blockers)
- Information requested by the prospect (what they asked us to send/do)
- Strength signal (1-5, based on engagement and commitment language)

Output format: structured fields.

Constraints: Only extract what was actually said. Do not infer next steps from "we should probably" type language unless a commitment was made.

Transcript:
{TRANSCRIPT}`

#### Prompt 6: Forecast Question Answer

`You are a sales forecast assistant.

Answer the question below using the pipeline data provided. Apply the company's forecasting rules:
{FORECAST_RULES}

Output format:
1. Direct answer to the question
2. Supporting deals (top 5 by amount, with stage, amount, close date, confidence)
3. Confidence level (high/medium/low) with one sentence on why

Constraints: Do not estimate or extrapolate beyond the data provided.

Question: {QUESTION}
Pipeline data: {PIPELINE}`

#### Prompt 7: Support Ticket Triage

`You are a support ticket triage assistant.

Classify the ticket below:
- Issue type (use the provided taxonomy: {TAXONOMY})
- Urgency (P1/P2/P3/P4 using the provided rules: {URGENCY_RULES})
- Customer segment (Enterprise/Mid-Market/SMB)
- Routing destination (which queue/team)
- One-line summary for the ticket description

Output format: structured fields.

Constraints: If urgency cannot be determined from the ticket content, default to P3 and flag for review.

Ticket: {TICKET}
Customer context: {CUSTOMER_RECORD}`

#### Prompt 8: Escalation Brief

`You are a customer success assistant. Draft a one-page escalation brief for a manager taking a customer call in the next hour.

Pull from the data provided:
- Customer name, segment, account value, tenure
- Recent ticket history (last 6 months, top 5 by severity)
- Current issue summary (3-4 sentences)
- Root cause analysis (1-2 sentences)
- What has been promised/attempted so far
- Recommended next step for the manager

Output format: one-page brief, scannable in 90 seconds.

Constraints: Stick to facts in the data. If something is unknown, say so.

Customer record: {CUSTOMER}
Ticket history: {TICKETS}
Current issue: {ISSUE}`

#### Prompt 9: Invoice Exception Detection

`You are an accounts payable assistant.

Compare the invoice below against the PO and contract terms provided. Identify exceptions:
- Price variance (line-item level)
- Quantity variance
- Terms variance (payment terms, delivery terms)
- Missing or extra line items
- Approval threshold breach

Output format: structured exceptions list with severity (block/flag/note) and recommended action.

Constraints: Do not approve. Do not reject. Surface exceptions for human review.

Invoice: {INVOICE}
PO: {PO}
Contract terms: {CONTRACT_TERMS}`

#### Prompt 10: Month-End Variance Commentary

`You are a financial reporting assistant. Draft variance commentary for the controller.

For each material variance (>5% or >$X, whichever is greater):
- Account name and amount
- Direction (favorable/unfavorable)
- Likely driver (pull from operational notes provided)
- One-sentence commentary suitable for the board package

Output format: structured by account, then a 2-paragraph overall summary.

Constraints: Only commentary that can be supported by operational notes. If no operational driver is documented, write "Driver under investigation" and flag for the controller.

Variance report: {VARIANCE_REPORT}
Operational notes: {OPS_NOTES}`

#### Prompt 11: Board Memo Draft

`You are an executive assistant drafting a board memo.

Use the standard agenda structure:
{BOARD_AGENDA_TEMPLATE}

Pull from:
- Financial summary: {FINANCIALS}
- KPI dashboard: {KPIS}
- Strategic notes: {STRATEGIC_NOTES}
- Risk register: {RISKS}

Output format: full board memo, in the standard template structure, ready for CEO/CFO review.

Constraints:
- No new claims that aren't in the source material.
- Variances and risks must reference the supporting data point.
- Strategic notes are pulled verbatim or paraphrased, not invented.
- Length: target 4-6 pages.`

#### Prompt 12: Contract Clause Review

`You are a contract review assistant. Review the contract below against the standard playbook.

For each clause that does not match the playbook:
- Section reference (e.g., "5.2 Indemnification")
- The non-standard language (verbatim)
- The playbook standard for that section
- Risk level (low/medium/high) with one-sentence reasoning
- Suggested redline (optional, only if confident)

Output format: structured exceptions list, sorted by risk level.

Constraints: Do not approve. Surface for legal review. If a clause is ambiguous, flag at medium risk for legal interpretation.

Contract: {CONTRACT}
Playbook: {PLAYBOOK}`

#### Prompt 13: KPI Rollup Commentary

`You are an executive reporting assistant. Generate a weekly KPI scorecard.

For each KPI provided:
- Current value
- Variance vs. last week and vs. plan
- One-sentence commentary on the variance (only if material)

Then write a 2-3 bullet overall summary covering:
- What's on track
- What's at risk
- What needs leadership attention this week

Output format: scorecard table + summary bullets.

Constraints: Commentary must reference the underlying data, not aspirational language.

KPI data: {KPIS}
Plan: {PLAN}`

#### Prompt 14: Resume Screen Against Role Spec

`You are a recruiting assistant.

Score the resume below against the role spec provided. Use these criteria:
- Required skills (must-have)
- Preferred skills (nice-to-have)
- Experience level
- Industry/domain fit
- Location/timezone match

Output format:
- Overall score (1-10) with one-sentence rationale
- Skill match table (required and preferred, with hit/miss)
- Flags (red flags, gaps, exceptional strengths)
- Recommendation (advance/hold/pass)

Constraints: Do not infer demographic information. Do not consider anything outside the job-relevant criteria.

Resume: {RESUME}
Role spec: {ROLE_SPEC}`

#### Prompt 15: Onboarding 30-60-90 Personalization

`You are an onboarding assistant. Build a 30-60-90 plan for a new hire.

Personalize the master template based on:
- Role: {ROLE}
- Department: {DEPARTMENT}
- Reporting manager: {MANAGER}
- Required certifications/training: {TRAINING_LIST}
- Key relationships to build (from org chart): {STAKEHOLDERS}

Master template: {MASTER_TEMPLATE}

Output format: 30-60-90 plan with milestones, learning objectives, and check-in cadence.

Constraints: Pull only from provided inputs. Do not invent stakeholders or training requirements.`

> **15 prompts, all production-ready, but you still need to wire them to your stack.**
> If you'd rather have us deploy the workflows, validate them against your real data, and hand your team an operational system instead of a doc, that's the Sprint.
> Book a 20-min fit call → [https://calendly.com/anthonywhitaker/discovery](https://calendly.com/anthonywhitaker/discovery)

---

### 6. The 4 Role-Based Agent Packs

Each pack is a bundle of 5-7 hooks, 3-4 integrations, and the KPIs to track. Pick the pack that matches the leader who's going to own this. Build it first, end-to-end, before you move to a second pack.

#### Pack 1: Operations Lead

For a COO, VP Ops, or GM owning operational efficiency across multiple departments.

**Hooks to deploy first:** 1.1, 1.2, 3.1, 3.3, 5.3
**Integrations needed:** CRM, service management, email, Slack
**KPIs to track:** Response time on inbound, ticket time-to-resolution, weekly status throughput
**Order of deployment:**

1. Week 1-2: Hook 1.1 (RFP triage) — fastest visible win
2. Week 3-4: Hook 3.1 (Ticket triage) — easiest to measure
3. Week 5-6: Hook 1.2 (Customer email draft) — start of agent capacity unlock
4. Week 7-8: Hooks 3.3 + 5.3 (Escalation briefs + status reports) — leadership-visible wins
#### Pack 2: Finance Lead

For a CFO, Controller, or VP Finance owning AP/AR, reporting, and month-end.

**Hooks to deploy first:** 4.1, 4.2, 4.4, 5.1, 5.2
**Integrations needed:** ERP (NetSuite or QuickBooks), email, Slack
**KPIs to track:** AP processing time, exception rate, month-end close days, board memo cycle time
**Order of deployment:**

1. Week 1-2: Hook 4.1 (Invoice exceptions) — measurable cycle time reduction
2. Week 3-4: Hook 4.4 (Collections follow-up) — AR aging improvement
3. Week 5-6: Hook 4.2 (Expense policy) — policy compliance lift
4. Week 7-8: Hooks 5.1 + 5.2 (Board memo + KPI rollup) — close-the-books speed
#### Pack 3: RevOps Lead

For a VP RevOps, CRO, or VP Sales owning pipeline hygiene, forecast accuracy, and rep productivity.

**Hooks to deploy first:** 1.3, 1.4, 2.1, 2.2, 2.4
**Integrations needed:** CRM, call recording, Slack, email
**KPIs to track:** CRM data completeness, forecast accuracy, rep selling time, deal velocity
**Order of deployment:**

1. Week 1-2: Hook 2.1 (Call → next steps) — rep time saved, immediate buy-in
2. Week 3-4: Hook 1.3 (Lead enrichment) — pipeline quality lift
3. Week 5-6: Hook 2.4 (Stale opportunity re-engagement) — pipeline reactivation
4. Week 7-8: Hooks 1.4 + 2.2 (Win/loss + deal slip alerts) — forecast accuracy lift
#### Pack 4: Service Lead

For a VP Customer Success, VP Service, or Head of Support owning resolution, escalation, and customer experience.

**Hooks to deploy first:** 3.1, 3.2, 3.3, 3.4, 7.2
**Integrations needed:** Service management, CRM, knowledge base, Slack
**KPIs to track:** First response time, time-to-resolution, escalation rate, agent capacity
**Order of deployment:**

1. Week 1-2: Hook 3.1 (Ticket triage) — measurable routing win
2. Week 3-4: Hook 3.3 (Escalation briefs) — manager time saved
3. Week 5-6: Hook 3.2 (Case resolution → KB) — knowledge base growth
4. Week 7-8: Hooks 3.4 + 7.2 (Service call notes + policy lookup) — capacity unlock
---

### 7. The 90-Day Deployment Roadmap

The Sprint model has three phases. Same shape works for a DIY deployment.

select 2-3 hooksmeasure & iteratedefend ROIWeeks 1-4Impact TriageWeeks 5-8Pilot BuildWeeks 9-12ROI & RoadmapProduction + Scale

**Weeks 1-4: Impact Triage**

- Map the top 5 processes by ROI potential in the chosen role pack
- Score them on impact (hours/dollars saved, revenue unlocked) and feasibility (data available, owner identified, integration possible)
- Pick the top 2-3 to build
- Baseline the current state metrics so you can prove the lift later
**Weeks 5-8: Pilot Build**

- Wire up the 2-3 selected hooks against real data
- Run them in shadow mode for 1-2 weeks (Claude drafts, humans review and don't act)
- Move to assisted mode for 1-2 weeks (Claude drafts, humans approve and act)
- Capture failure cases and refine prompts
**Weeks 9-12: ROI & Roadmap**

- Measure the lift against the baseline
- Build the board-ready ROI story
- Identify the next 2-3 hooks for the next quarter
- Transfer ownership to the business-side owner with a runbook
The mid-market companies that ship this successfully share two patterns: a single business-side owner per hook, and a measurement plan written before week 1 of build. Skip either one and the hook drifts.

---

### What's Next

You've got the pack. 28 hooks, 12 integrations, 15 prompts, 4 role-based agent stacks, and a 90-day roadmap. Two ways forward.

**Run it yourself.** Everything you need is above. Pick the role pack that matches your situation. Start with the first 2 hooks. Get them to production in 60 days. Then go from there.

**Have us run it for you.** The 90-Day AI ROI Sprint is what we do for mid-market companies (50-500 employees) where the board's asking about AI and the internal team doesn't have the capacity for a six-month consulting engagement. Fixed scope, 90 days, 3x ROI guarantee. You walk out with live workflows, a measurement system, and a board-ready ROI story.

It's a fit if:

- You're a CEO, COO, GM, or practice leader at a 50-500 person company
- Your board, investors, or owners are asking about AI
- You want production AI workflows, not a strategy deck
- You'd rather have someone accountable for the result than manage another consulting engagement
Book a 20-min fit call → [https://calendly.com/anthonywhitaker/discovery](https://calendly.com/anthonywhitaker/discovery)

If we're not the right fit, I'll tell you in the first 5 minutes and point you to someone who is.
