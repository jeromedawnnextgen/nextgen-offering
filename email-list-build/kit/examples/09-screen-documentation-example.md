# Example: Screen Documentation from Code

## Scenario
Documenting an inherited Canvas App screen with no existing documentation before making changes.

## Full prompt used

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
[Pasted formula bar content from the screen's controls — OnVisible, gallery Items, button OnSelect formulas, etc.]
```

## Expected output (summary)

A structured document covering all 7 sections. For a typical gallery + edit screen Claude will identify:
- The data source and filter logic from the gallery Items formula
- Any collections populated in OnVisible
- Business logic embedded in button formulas
- Calls to Power Automate via `PowerAutomateFlowName.Run()`
- Delegation risks if `Filter` uses non-delegable functions
- Hardcoded values that should be environment variables

## Pro tip
This output is a deliverable. Format it as a Word doc or Confluence page and include it in your client handover pack. Clients rarely have documentation — this differentiates your delivery.
