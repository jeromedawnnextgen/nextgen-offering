# 04 — Power Automate Expression Generator

**Category:** Power Automate
**Difficulty:** Beginner–Intermediate

---

## What this prompt does

Converts plain-English requirements into correct Power Automate workflow expressions.
Handles `formatDateTime`, `substring`, `coalesce`, `if`, `concat`, `triggerOutputs`, `items()` and more.
Returns the expression with null safety built in and a short explanation you can actually understand.

---

## When to use it

- You need to format a date/time value
- You're extracting part of a string
- You need a null-safe fallback value
- You're building a dynamic subject line, file name, or body
- You're working with arrays and need `first()`, `last()`, or `join()`

---

## The Prompt

```
You are a Power Automate expert.

Convert this requirement into a Power Automate expression:

Requirement:
[Describe logic]

Constraints:
- Use correct expression syntax
- Handle null values safely
- Optimize for readability

Return:
- Expression only
- Short explanation
```

---

## How to adapt it

- Be specific about the **input**: "A datetime from a SharePoint column called 'DueDate' in ISO format"
- Be specific about the **output**: "Formatted as DD/MM/YYYY"
- Mention the **null case**: "If the column is empty, return 'No date set'"
- Reference the **exact dynamic content name** if you know it: `triggerBody()?['DueDate']`

---

## What to expect back

- The expression ready to paste into the Expression editor in Power Automate
- A one or two line explanation of what each function does
- The null-safe wrapper (usually `coalesce()` or `if(empty(...), ...)`)

---

## Common mistakes

- Pasting the expression into the wrong field — expressions go in the `fx` Expression tab, not the Dynamic Content tab
- Not wrapping in `@{...}` when used inside a string (e.g. email body) vs. a pure expression field
- Forgetting that Power Automate dates are ISO 8601 UTC — you often need to convert timezone before formatting

---

## Learn more

Covered in **Week 5 (Power Automate Foundations)** and **Week 6 (Advanced Power Automate)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
