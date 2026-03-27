# 09 — Screen Documentation from Code

**Category:** Architecture
**Difficulty:** Advanced
**Value:** 🔥 Premium offer — clients pay for this as a standalone deliverable

---

## What this prompt does

Takes raw Power Fx code pasted from any Canvas App screen and returns structured documentation.
Covers purpose, data sources, collections, business logic, user actions, dependencies, and risks.
Turns undocumented inherited apps into something a new developer can actually understand.

---

## When to use it

- You've inherited an app with no documentation
- You're onboarding a new developer to an existing solution
- You're doing a health check or audit for a client
- You want to document your own app before handing it over
- You're preparing a technical spec for a change request

---

## The Prompt

```
You are a Power Platform solution architect.

I will paste Power Fx code from a screen.

Your job:
- Analyze the code
- Document what the screen does

Output format:
1. Screen Purpose
2. Data Sources Used
3. Key Collections
4. Business Logic
5. User Actions
6. Dependencies (Flows, APIs)
7. Risks / Improvements

Code:
[Paste code]
```

---

## How to get the code to paste

In Power Apps Studio:
1. Select the screen in the left panel
2. Go to **File → Save as → This computer** to export, OR
3. Select all controls on the screen, copy, paste into a text editor
4. For individual control formulas: click the control, use the formula bar, copy the formula

For a full screen export, use the **Power Apps CLI** (`pac canvas unpack`) to extract all formulas to text files.

---

## What to expect back

A structured document with 7 sections:
1. **Screen Purpose** — one paragraph explaining what the screen does
2. **Data Sources** — every connected table, list, or collection referenced
3. **Key Collections** — what each collection contains and when it's populated
4. **Business Logic** — conditional rules, calculations, routing logic
5. **User Actions** — what the user can do and what happens when they do it
6. **Dependencies** — Power Automate flows called, external APIs, environment variables
7. **Risks / Improvements** — delegation issues, performance concerns, hardcoded values

---

## Consulting use case

This prompt generates a **technical audit document** you can deliver to clients as part of a health check engagement.
Charge for this as a standalone service: "Power Platform App Audit — £500–£1500 depending on app complexity."

---

## Common mistakes

- Pasting only one control's formula — paste as much code as possible for a complete picture
- Not mentioning the app context: "This is screen 3 of 5 in an expense management app" helps Claude produce better output

---

## Learn more

Covered in **Week 4 (Advanced Canvas Patterns)** and **Week 12 (Consulting Mindset)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
