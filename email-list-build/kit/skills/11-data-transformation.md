# 11 — Data Transformation

**Category:** Canvas Apps
**Difficulty:** Intermediate

---

## What this prompt does

Converts, reshapes, and type-casts data between structures using Power Fx.
`ClearCollect`, `AddColumns`, `GroupBy`, `Ungroup`, `ForAll` with correct `Value()`, `DateValue()`, `Text()` casting.
Handles the messy reality of data arriving in one shape and needing to be in another.

---

## When to use it

- Data from SharePoint comes as text but you need numbers for calculations
- You need to group records by category for a summary view
- You're combining two collections into one
- You need to flatten a nested structure
- Dates are arriving as strings and breaking your date comparisons

---

## The Prompt

```
You are a Power Fx data transformation expert.

Convert this:

Input:
[Describe structure OR paste sample]

Into:
[Desired output structure]

Requirements:
- Use ClearCollect, AddColumns, GroupBy, etc.
- Ensure correct typing (Value, DateValue, etc.)

Return:
- Full formula
```

---

## How to adapt it

- **Input** — describe or paste a sample row: `{ Title: "Project A", Budget: "15000", DueDate: "2026-03-15", Status: "Active" }`
- **Output** — describe what you want: "Same structure but Budget as a number, DueDate as a Date, add a column IsOverdue that is true if DueDate < Today()"
- Mention the **data source**: the transformation needs to happen in memory (collection) vs. at query time (filter formula) affects the approach

---

## What to expect back

- A complete `ClearCollect` or `ForAll` formula
- Type conversion functions applied to each field that needs them
- `AddColumns` for any derived/calculated fields
- Notes on where to put this formula (App.OnStart, button OnSelect, etc.)

---

## Common mistakes

- Trying to `Value()` a field that's already a number — causes an error in some contexts
- Using `GroupBy` without `Ungroup` when you need to go back to a flat structure
- Forgetting that `DateValue()` requires a specific format — locale matters
- Running heavy transformations in a Gallery's Items property — do it once in a collection instead

---

## Learn more

Covered in **Week 2 (Canvas App Architecture)** and **Week 3 (Forms, Galleries & UX)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
