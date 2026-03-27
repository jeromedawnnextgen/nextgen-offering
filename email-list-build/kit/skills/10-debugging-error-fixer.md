# 10 — Debugging + Error Fixer

**Category:** Architecture
**Difficulty:** All levels

---

## What this prompt does

Takes an error message or unexpected behavior description and returns root cause analysis, corrected code, and an explanation.
Works for Power Fx errors, Power Automate run failures, delegation warnings, and unexpected empty results.

---

## When to use it

- You see a red error banner in Power Apps and don't know why
- A Power Automate flow is failing and the error message is unhelpful
- Your gallery is showing empty even though data exists
- A formula that worked on one screen breaks on another
- You're getting "delegation warning" yellow triangles

---

## The Prompt

```
You are a senior Power Platform developer.

I am getting this issue:

[Paste error or behavior]

Context:
[What you're trying to do]

Requirements:
- Identify root cause
- Provide corrected code
- Explain why it failed

Return:
- Fixed version
- Explanation
```

---

## How to adapt it

- **Paste the exact error** — copy the full error text, not a paraphrase. "The formula contains unknown functions" is more useful than "it shows an error"
- **Describe the context fully**: what screen, what control, what action triggered it
- **Include your current formula** — Claude can't fix what it can't see
- For flow errors: paste the error from the failed action's output panel

---

## What to expect back

- Root cause in plain English
- Corrected formula or flow expression ready to paste
- Explanation of why the original failed — so you don't make the same mistake again
- Occasionally: alternative approaches if the pattern itself is flawed

---

## Getting better error context

**Power Apps:**
- Look in the App Checker (the shield icon) for a full list of formula errors
- Hover over red underlines in the formula bar for inline error details

**Power Automate:**
- Click the failed action in the run history — expand "Show raw outputs" for the full error object
- The `innerError` field often has the real error hidden inside the top-level message

---

## Common mistakes

- Describing the behavior without pasting the actual formula — Claude will guess and may guess wrong
- Pasting only the error without the context of what you're trying to do
- Not mentioning the data source type — delegation errors behave differently on SharePoint vs Dataverse

---

## Learn more

Covered across the entire 12-Week Power Platform Mastery Program — debugging is woven into every module.
→ nextgenpowerapps.com
