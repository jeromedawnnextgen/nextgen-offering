# 03 — Approval Workflow Logic

**Category:** Canvas Apps + Power Automate
**Difficulty:** Intermediate–Advanced

---

## What this prompt does

Designs multi-step approval architecture across both the Canvas App (Power Fx) and Power Automate (flow structure).
Handles dynamic approver selection, escalation, rejection paths, and notifications.
Returns both layers so you're not designing them separately and discovering they don't connect.

---

## When to use it

- You're building any kind of request/approval system (expenses, leave, purchases, onboarding)
- Approval routing depends on data (amount, department, role)
- You need escalation when approvers don't respond in time
- You need to track approval state across multiple steps

---

## The Prompt

```
You are a Power Platform architect.

Design approval logic based on this process:

[Describe approval process in plain English]

Requirements:
- Support multi-step approvals
- Dynamically determine next approver
- Include escalation logic if needed
- Output both:
   1. Power Fx logic (Canvas App)
   2. Power Automate flow structure

Return:
- Step-by-step architecture
- Power Fx formulas
- Flow design (trigger, actions, conditions)
```

---

## How to adapt it

- Describe **who approves** and **under what conditions**: "Line manager always, then Finance if amount > £500"
- Describe **where approver data lives**: "Manager is in the Dataverse Employees table as a lookup to the same table"
- Mention **what happens on rejection**: "Request is cancelled, requester notified, status updated to Rejected"
- Mention **time limits**: "Approver has 48 hours, then escalate to their manager"
- Describe **where the request is initiated**: "Canvas App form" or "SharePoint list"

---

## What to expect back

- A numbered architecture walkthrough
- Power Fx formulas for submitting and displaying approval state in the Canvas App
- Power Automate flow structure: trigger, parallel approvals or sequential, condition branches, notification actions
- Dataverse/SharePoint columns needed to track state

---

## Common mistakes

- Not storing approval state in the data source — the Canvas App needs to read the current status back
- Using a single-approver flow and adding conditions inside it (messy) vs. using child flows per approval stage (clean)
- Not handling the case where an approver is blank/unassigned

---

## Learn more

Covered in **Week 5 (Power Automate Foundations)**, **Week 6 (Advanced Power Automate)**, and **Week 7 (Dataverse)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
