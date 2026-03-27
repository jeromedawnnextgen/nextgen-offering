# Example: Approval Workflow Logic

## Scenario
A purchase request system where approval routing depends on amount and department.

## Full prompt used

```
You are a Power Platform architect.

Design approval logic based on this process:

Requests under £500: line manager only.
Requests £500–£5000: line manager then finance manager.
Requests over £5000: line manager, finance manager, then CFO.
Rejection at any stage cancels the request and notifies the requester.
If no response within 48 hours, escalate to the approver's manager.
Approver info is stored in a Dataverse table called cr123_Employees with a self-referencing ManagerId lookup.

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

## Expected output (summary)

- A Dataverse status column on the request table to track current approval stage
- Power Fx to set initial status on submit and display current stage in the app
- Three sequential child flows (one per approval tier) triggered conditionally based on amount
- Each child flow uses the Start and wait for an approval action with a 48h timeout branch
- Escalation implemented via a parallel branch that fires after timeout

## Pro tip

Ask Claude to design the Dataverse schema for tracking the audit trail of each approval decision separately — you'll want this for reporting.
