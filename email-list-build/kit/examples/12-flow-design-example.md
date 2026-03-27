# Example: Flow Design (End-to-End)

## Scenario
Automated onboarding flow triggered when a new employee record is created in Dataverse.

## Full prompt used

```
You are a Power Automate architect.

Design a flow for this process:

When a new employee record is created in Dataverse (table: cr123_Employees), automatically:
1. Create an Azure AD account via Graph API
2. Assign a Microsoft 365 licence
3. Create a SharePoint site for their department if it doesn't already exist
4. Send a welcome email to the employee
5. Send a notification to IT and HR via Teams
6. Log the completion status back to the Dataverse employee record

Requirements:
- Include trigger
- Actions
- Conditions
- Error handling
- Logging strategy

Return:
- Step-by-step flow
- Key expressions
```

## Expected output (summary)

A numbered 12-step flow design:
1. Trigger: When a row is added (Dataverse) on cr123_Employees
2. Get manager details via a related record lookup
3. HTTP POST to Graph API to create AAD user
4. Condition: check HTTP response code = 201
5. HTTP POST to assign M365 licence
6. Get SharePoint sites, check if department site exists
7. Condition: create site if not exists via SharePoint REST API
8. Send welcome email (HTML template)
9. Post Teams notification to IT channel
10. Post Teams notification to HR channel
11. Update Dataverse employee record with OnboardingStatus = "Complete"
12. Try/Catch scope around steps 3–11 with error logging to cr123_FlowLogs table

## Pro tip
Ask Claude to also generate the Dataverse schema for the `cr123_FlowLogs` table it references — you'll need it for the logging step to work.
