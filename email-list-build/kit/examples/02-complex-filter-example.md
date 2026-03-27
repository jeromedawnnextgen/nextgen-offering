# Example: Complex Filter / Business Logic

## Scenario
Colour-coding a status badge in a gallery based on project status and due date proximity.

## Full prompt used

```
You are an expert in Power Fx.

Convert this business logic into a clean, optimized Power Fx formula.

Business Logic:
If the project status is "Complete" show grey. If it's "Cancelled" show light red. If it's "Active" AND the due date is more than 7 days away, show green. If it's "Active" AND the due date is within 7 days, show amber. If it's "Active" AND the due date has passed, show red. Handle blank status and blank due date gracefully.

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

## Expected output (summary)

Claude returns a `With()` block that captures `DateDiff(Today(), ThisItem.DueDate, Days)` once, then a `Switch` on status with nested `If` for the Active branch, wrapped in `IsBlank` checks for both fields.

## Pro tip

Use this same pattern for icon names, font weights, border colours — any property that changes based on record state.
