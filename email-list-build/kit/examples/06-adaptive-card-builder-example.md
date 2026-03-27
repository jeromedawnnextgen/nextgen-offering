# Example: Adaptive Card Builder

## Scenario
A Teams notification card for a new expense claim awaiting manager approval.

## Full prompt used

```
You are an expert in Microsoft Adaptive Cards.

Build an adaptive card for this scenario:

Scenario: Expense claim approval request sent to a line manager in Microsoft Teams via Power Automate

Fields:
- Employee Name
- Submission Date
- Expense Category (Travel / Meals / Equipment / Other)
- Total Amount (formatted as currency)
- Business Justification
- Receipt Attached (Yes / No)
- Link to view full claim in Power Apps

Requirements:
- Use Adaptive Card schema version 1.4+
- Include Approve and Reject action buttons
- Clean layout (Containers, FactSet for key-value fields)
- Blue header bar with title "Expense Approval Required"

Return:
- Full JSON (ready for Teams)
```

## Expected output (summary)

Full Adaptive Card JSON with:
- A `Container` with blue background for the header
- A `FactSet` for the structured fields (employee, date, category, amount, receipt)
- A `TextBlock` for the business justification
- An `ActionSet` with `Action.Submit` for Approve and Reject, each with a `data` payload so the flow can read the response

## Pro tip

Test the JSON at adaptivecards.io/designer before putting it in the flow. The designer shows exactly how it renders in Teams and highlights schema errors instantly.
