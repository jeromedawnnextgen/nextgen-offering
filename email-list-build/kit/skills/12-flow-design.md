# 12 — Flow Design (End-to-End)

**Category:** Power Automate
**Difficulty:** Intermediate–Advanced

---

## What this prompt does

Designs a complete Power Automate flow from trigger to logging — including error handling, conditions, and key expressions.
Returns a step-by-step architecture you can follow to build it, not just a description of what it should do.

---

## When to use it

- You're starting a new flow and want to plan it before building
- You have a complex multi-branch flow and want to validate the logic
- You want to add proper error handling to an existing flow
- You need to design a flow that integrates multiple systems

---

## The Prompt

```
You are a Power Automate architect.

Design a flow for this process:

[Describe process]

Requirements:
- Include trigger
- Actions
- Conditions
- Error handling
- Logging strategy

Return:
- Step-by-step flow
- Key expressions
```

---

## How to adapt it

- **Trigger** — describe what starts the flow: "When a new item is created in SharePoint", "When a button is clicked in Power Apps", "Every day at 8am"
- **Process** — describe the full happy path first, then exceptions
- **Integrations** — mention every system involved: SharePoint, Dataverse, Teams, Outlook, external APIs
- **Error handling** — mention how you want failures handled: "Send an email to the admin if anything fails"

---

## What to expect back

A numbered step-by-step flow design:
1. Trigger definition
2. Initial data retrieval actions
3. Condition branches with true/false paths
4. Core actions per branch
5. Error handling (scope + catch block pattern)
6. Logging strategy (Dataverse log table, SharePoint list, or Application Insights)
7. Key expressions for the most complex parts

---

## The error handling pattern to always use

```
Scope: Try
  [all your main actions here]
Scope: Catch (Configure Run After → Has failed, Has timed out)
  Send email / log to Dataverse with:
  - Flow name
  - Error message: @{body('Scope_Try')?['error']?['message']}
  - Timestamp
  - Input data that caused the failure
```

Ask Claude to include this in every flow design it produces.

---

## Common mistakes

- Not including error handling until something breaks in production
- Using a single flat flow for everything instead of child flows for reusable logic
- Not logging enough context — when a flow fails at 2am you need to know what data it was processing
- Using "Run after" on individual actions instead of a Try/Catch scope pattern

---

## Learn more

Covered in **Week 5 (Power Automate Foundations)**, **Week 6 (Advanced Power Automate)**, and **Week 11 (ALM & Deployment)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
