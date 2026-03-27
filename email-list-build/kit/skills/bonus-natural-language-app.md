# Bonus — Natural Language → Full App Logic

**Category:** Architecture
**Difficulty:** Advanced

---

## What this prompt does

Takes a plain-English description of a business process and returns the complete solution architecture:
data model, Canvas App logic, Power Automate flows, approval logic, and edge cases.
Use this at the start of every new engagement to collapse scoping time from days to minutes.

---

## When to use it

- You're starting a new client project and need to design the solution fast
- You've been given a business requirement and need to translate it to a technical plan
- You want to validate your own architecture against an independent view
- You're preparing a scoping document or proposal

---

## The Prompt

```
You are a Power Platform expert.

Turn this business process into working app logic:

Process:
[Plain English description]

Output:
1. Data model (tables + fields)
2. Canvas app logic (Power Fx)
3. Power Automate flows
4. Approval logic
5. Edge cases

Make it production-ready.
```

---

## How to adapt it

This is the one prompt where **more context = dramatically better output**.

Include:
- **Who the users are**: "200 warehouse staff on mobile, 5 managers on desktop, 2 HR admins"
- **Where data currently lives**: "Currently tracked in Excel on SharePoint"
- **Integration requirements**: "Must notify via Teams, update an SAP system via HTTP"
- **Compliance/security**: "GDPR applies — no personal data outside EU. Role-based access required"
- **Scale**: "~500 submissions per month, peaks at month end"
- **Non-functional requirements**: "Must work offline on mobile"

The more you put in, the closer to production-ready the output will be.

---

## What to expect back

1. **Data model** — Dataverse table names, column names, data types, relationships, security roles
2. **Canvas App logic** — screen list, key formulas, navigation flow, variable strategy
3. **Power Automate flows** — trigger, actions, conditions, error handling for each flow
4. **Approval logic** — who approves, under what conditions, escalation paths
5. **Edge cases** — offline scenarios, duplicate submissions, permission gaps, data validation

---

## How to use the output

Treat this as a **technical design document draft**, not a finished spec.
Walk through it and:
- Validate the data model against real business requirements
- Check that the approval logic matches actual org hierarchy
- Add environment-specific details (tenant IDs, list names, etc.)
- Identify what the client hasn't told you yet (this always reveals gaps)

Then use the individual skill prompts (01–12) to generate the actual code for each component.

---

## Consulting use case

This prompt + the Screen Documentation prompt (09) form the core of a **Power Platform Discovery & Design** engagement.

Typical structure:
1. Client describes their process (30-min call)
2. You run this prompt during/after the call
3. You return a structured technical proposal within 24 hours
4. Charge £500–£2000 for the design phase depending on complexity

---

## Common mistakes

- Being too vague: "Build me a project tracker" produces generic output. "Build a project tracker for a construction firm tracking 50 active sites with weekly progress updates submitted by site managers and reviewed by a central PMO team" produces architecture
- Not iterating — run this prompt, review the output, then run it again with corrections and additions
- Treating the output as final — always validate with the actual stakeholders

---

## Learn more

Covered in **Week 12 (AI-Powered Capstone + Consulting Mindset)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
