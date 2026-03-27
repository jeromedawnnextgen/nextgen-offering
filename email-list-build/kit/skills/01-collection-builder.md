# 01 — Collection Builder

**Category:** Canvas Apps
**Difficulty:** Beginner–Intermediate

---

## What this prompt does

Generates a complete, delegation-aware `ClearCollect` formula for a Canvas App collection.
Handles `AddColumns` for calculated fields, correct Power Fx syntax, and performance notes.
Output is ready to paste directly into your App.OnStart or a button's OnSelect.

---

## When to use it

- You need to load data into a collection on app start
- You want to add calculated columns (e.g. % complete, days overdue, full name)
- You're combining data from multiple columns into a single usable structure
- You want to pre-filter or pre-sort data before binding to a gallery

---

## The Prompt

```
You are a senior Power Apps developer.

I need help building a collection in a Canvas App.

Context:
- Data source: [SharePoint / Dataverse / SQL]
- Table name: [table name]
- Columns: [list columns]
- Goal: [what the collection should represent]

Requirements:
- Use ClearCollect
- AddColumns if needed
- Include calculated fields
- Optimize for performance (avoid delegation issues if possible)
- Use proper Power Fx syntax with semicolons

Return:
- Full working formula (ready to paste)
- Brief explanation of each column
```

---

## How to adapt it

- **Data source** — be specific: `Dataverse`, `SharePoint list named "ProjectTasks"`, or `SQL table "dbo.Employees"`
- **Columns** — list the actual internal column names, not display names. In Dataverse these look like `cr123_ColumnName`
- **Goal** — describe the purpose in plain English: "show all open requests assigned to the current user, sorted by due date"
- **Calculated fields** — mention them explicitly: "add a column called DaysOverdue that subtracts DueDate from Today()"

---

## What to expect back

A complete `ClearCollect` formula with:
- All columns listed
- Any `AddColumns` wrappers for calculated fields
- Inline comments explaining each part
- A note if delegation is a concern and how to handle it

---

## Common mistakes

- Pasting the formula without checking the column names match your actual data source
- Using display names instead of internal names for Dataverse columns
- Ignoring the delegation warning — if your list has more than 500–2000 rows, this matters
- Not calling `ClearCollect` in the right place — App.OnStart vs a button depends on how often data needs to refresh

---

## Learn more

Covered in depth in **Week 2 (Canvas App Architecture)** and **Week 3 (Forms, Galleries & UX)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
