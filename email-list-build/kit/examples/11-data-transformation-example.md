# Example: Data Transformation

## Scenario
SharePoint list returns budget figures as text strings — need them as numbers with a percentage calculated column.

## Full prompt used

```
You are a Power Fx data transformation expert.

Convert this:

Input:
SharePoint list "Budgets" with columns: ProjectName (text), BudgetAllocated (text, e.g. "50000"), BudgetSpent (text, e.g. "32500"), QuarterEnd (text, e.g. "2026-03-31")

Into:
A collection where BudgetAllocated and BudgetSpent are numbers, QuarterEnd is a Date, and there is a new column PercentSpent (number, 0–100) and a column IsOverBudget (boolean).

Requirements:
- Use ClearCollect, AddColumns, GroupBy, etc.
- Ensure correct typing (Value, DateValue, etc.)

Return:
- Full formula
```

## Expected output (summary)

A `ClearCollect` with `AddColumns` wrapping the SharePoint data source, using:
- `Value(BudgetAllocated)` and `Value(BudgetSpent)` for numeric conversion
- `DateValue(QuarterEnd)` for date conversion
- `Round(Value(BudgetSpent) / Value(BudgetAllocated) * 100, 1)` for PercentSpent
- `Value(BudgetSpent) > Value(BudgetAllocated)` for IsOverBudget

## Pro tip
Ask Claude to also handle the edge case where `BudgetAllocated` is "0" or blank to avoid division by zero in the percentage calculation.
