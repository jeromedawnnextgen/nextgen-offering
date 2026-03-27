# 02 — Complex Filter / Business Logic

**Category:** Canvas Apps
**Difficulty:** Intermediate

---

## What this prompt does

Converts plain-English business logic into clean, null-safe Power Fx.
Handles `If`, `Switch`, `With()`, blank checks, and nested conditions.
Stops you guessing syntax and introduces readability patterns senior developers use.

---

## When to use it

- You have conditional display logic (colours, labels, icons based on status)
- You're writing multi-condition filter formulas for a gallery
- You have nested If statements getting unreadable
- You need to handle blanks and nulls safely

---

## The Prompt

```
You are an expert in Power Fx.

Convert this business logic into a clean, optimized Power Fx formula.

Business Logic:
[Describe in plain English]

Requirements:
- Use If / Switch appropriately
- Handle nulls and blanks
- Use With() where helpful
- Optimize readability
- Avoid redundant LookUps

Return:
- Final formula
- Explanation of logic mapping
```

---

## How to adapt it

- Write your business logic as if explaining it to a non-technical colleague
- Mention the column names involved: "If the Status column equals..."
- State what value/result you want back: "...return the color green / return true / return the string 'Overdue'"
- If there are edge cases (null, blank, unknown status), mention them explicitly

---

## What to expect back

- The final formula, ready to paste
- A mapping that shows how each condition in your plain English maps to the Power Fx
- Notes on why `Switch` was used instead of `If` (or vice versa)

---

## Common mistakes

- Forgetting to handle `IsBlank()` — a null status field will fall through all your conditions
- Using `=` instead of `=` (they're the same in Power Fx, but coming from other languages this trips people up)
- Not using `With()` when the same sub-expression appears multiple times — causes performance issues

---

## Learn more

Covered in **Week 3 (Forms, Galleries & UX)** and **Week 4 (Advanced Canvas Patterns)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
