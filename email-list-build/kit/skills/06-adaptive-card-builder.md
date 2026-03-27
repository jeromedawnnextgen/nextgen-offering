# 06 — Adaptive Card Builder

**Category:** Power Automate / Teams Integration
**Difficulty:** Intermediate
**Value:** 🔥 High — clients pay for this specifically

---

## What this prompt does

Generates complete Adaptive Card JSON ready to paste into a Power Automate "Post adaptive card" Teams action.
Handles containers, FactSets, column layouts, action buttons (Approve/Reject), and schema version compatibility.
Saves 30–60 minutes of trial and error in the Adaptive Card Designer.

---

## When to use it

- You're sending approval notifications to Teams
- You want structured data cards (not just plain text notifications)
- You're building bot responses in Copilot Studio
- You need interactive cards with action buttons

---

## The Prompt

```
You are an expert in Microsoft Adaptive Cards.

Build an adaptive card for this scenario:

Scenario:
[Approval / Notification / Data display]

Fields:
[List fields]

Requirements:
- Use Adaptive Card schema version 1.4+
- Include actions (Approve / Reject if needed)
- Clean layout (Containers, FactSet, etc.)

Return:
- Full JSON (ready for Teams)
```

---

## How to adapt it

- **Scenario** — be specific: "Expense claim approval", "New hire notification to HR", "Daily project status update"
- **Fields** — list every field that should appear on the card, and in what order
- **Actions** — state what buttons you need and what they do: "Approve button submits 'Approved' back to the flow, Reject opens a text input for reason"
- **Branding** — mention if you want a colour header or logo: "Include a blue header bar with the company name"

---

## What to expect back

- Full Adaptive Card JSON — schema 1.4+
- Correct structure: `body` array with containers, `FactSet` for key-value data, `ActionSet` for buttons
- Dynamic content placeholders using `${FieldName}` syntax if using templating, or string values you can replace with Power Automate dynamic content

---

## Testing your card

Paste the JSON into the Adaptive Card Designer before deploying:
**https://adaptivecards.io/designer/**

This shows exactly how it will render in Teams.

---

## Common mistakes

- Using schema version 1.5+ features in environments that only support 1.4 (check your Teams version)
- Not handling the response from action buttons back in the flow — the card submit returns a `body` object you need to parse
- Using `TextBlock` for everything instead of `FactSet` for key-value pairs (looks unprofessional)

---

## Learn more

Covered in **Week 8 (SharePoint & Teams Integration)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
