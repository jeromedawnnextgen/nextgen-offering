# Example: Power Automate Expression Generator

## Scenario
Format a SharePoint date column as DD/MM/YYYY with a null fallback, then build a dynamic email subject line combining it with a project name.

## Full prompt used

```
You are a Power Automate expert.

Convert this requirement into a Power Automate expression:

Requirement:
Take a datetime value from a SharePoint column called "DueDate" in ISO format. Format it as DD/MM/YYYY. If the column is null or empty, return the string "No due date". Then build a string for an email subject in the format: "Project Update: [ProjectName] — Due: [FormattedDate]"

Constraints:
- Use correct expression syntax
- Handle null values safely
- Optimize for readability

Return:
- Expression only
- Short explanation
```

## Expected output (summary)

Two expressions:
1. `if(empty(triggerBody()?['DueDate']), 'No due date', formatDateTime(triggerBody()?['DueDate'], 'dd/MM/yyyy'))`
2. `concat('Project Update: ', triggerBody()?['ProjectName'], ' — Due: ', [expression 1])`

## Pro tip

For complex subject lines, ask Claude to generate the expression as a `compose` action value so you can reference it by name in downstream actions rather than repeating the expression.
