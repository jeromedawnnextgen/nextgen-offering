# Example: HTML Generator

## Scenario
A weekly project status digest email sent every Monday to department heads.

## Full prompt used

```
You are a UI developer specializing in HTML for Power Automate emails.

Generate HTML for:

Scenario:
A weekly project status digest sent to department heads every Monday morning. Shows a summary table of all active projects: project name, owner, status (colour-coded badge), percentage complete, and due date. Header includes company name and report date. Footer has a link to the Power Apps project tracker.

Requirements:
- Clean styling (inline CSS)
- Mobile-friendly
- Table-based layout where needed

Return:
- HTML only
```

## Expected output (summary)

Complete HTML document with:
- A blue header bar with "Weekly Project Status — [ReportDate]"
- A `<table>` with alternating row colours for each project
- Inline-styled status badges (green/amber/red) as `<span>` elements with background colours
- A footer with "View all projects →" link placeholder
- All values as `[ProjectName]`, `[Owner]`, `[Status]`, `[PercentComplete]`, `[DueDate]` placeholders

## Inserting dynamic content
In the Power Automate "Send an email" action, switch the body to Code View and paste the HTML. Then replace each `[Placeholder]` with the corresponding dynamic content — typically from an Apply to each loop if generating a row per project.

## Pro tip
For the status badge colours, tell Claude the exact hex values you want so it matches your brand.
