# Top 10 Sample Prompts — Ready to Paste

**Power Platform Developer: Claude Co-Work Skills Kit**
By Jerome Dawn — NextGen PowerApps

> These are pre-filled versions of the kit prompts using realistic scenarios.
> Copy any of them directly into Claude and adapt as needed.

---

## 1. Build a Project Tracker Collection (Canvas App)

```
You are a senior Power Apps developer.

I need help building a collection in a Canvas App.

Context:
- Data source: Dataverse
- Table name: cr123_Projects
- Columns: cr123_ProjectName, cr123_Status, cr123_DueDate, cr123_AssignedTo, cr123_BudgetUsed, cr123_BudgetTotal
- Goal: A collection that shows all active projects with a calculated % budget used, filtered to the current user's assignments

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

## 2. Status-Based Colour Logic (Power Fx)

```
You are an expert in Power Fx.

Convert this business logic into a clean, optimized Power Fx formula.

Business Logic:
If the project status is "On Track" return green, if "At Risk" return amber, if "Overdue" return red, if "Complete" return grey. Default to white for anything else.

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

## 3. Three-Level Purchase Approval Flow

```
You are a Power Platform architect.

Design approval logic based on this process:

Purchase requests under £500 go to line manager only.
Requests between £500–£5000 go to line manager, then finance.
Requests over £5000 go to line manager, finance, then CFO.
If any approver rejects, the request is cancelled and the requester is notified.
Approvers have 48 hours to respond before escalation to their manager.

Requirements:
- Support multi-step approvals
- Dynamically determine next approver
- Include escalation logic if needed
- Output both:
   1. Power Fx logic (Canvas App)
   2. Power Automate flow structure

Return:
- Step-by-step architecture
- Power Fx formulas
- Flow design (trigger, actions, conditions)
```

---

## 4. Format a Date with Null Safety

```
You are a Power Automate expert.

Convert this requirement into a Power Automate expression:

Requirement:
Take a datetime value from a SharePoint column called "DueDate" and format it as "DD/MM/YYYY". If the column is empty or null, return the string "No due date set".

Constraints:
- Use correct expression syntax
- Handle null values safely
- Optimize for readability

Return:
- Expression only
- Short explanation
```

---

## 5. Invoice Payload for Parse JSON

```
You are an expert in JSON for Power Platform integrations.

Generate a JSON structure for:

Scenario:
An invoice received from an external API. It contains invoice number, supplier name, invoice date, line items (description, quantity, unit price), subtotal, VAT amount, and total amount.

Requirements:
- Include realistic sample values
- Ensure proper formatting
- Compatible with Power Automate Parse JSON

Return:
- JSON
- Suggested schema (optional)
```

---

## 6. Teams Approval Card for Expense Claims

```
You are an expert in Microsoft Adaptive Cards.

Build an adaptive card for this scenario:

Scenario: Expense claim approval notification sent via Power Automate to a manager in Microsoft Teams

Fields:
- Employee Name
- Expense Date
- Category (Travel / Meals / Equipment)
- Amount
- Description
- Receipt Attached (Yes/No)

Requirements:
- Use Adaptive Card schema version 1.4+
- Include actions (Approve / Reject if needed)
- Clean layout (Containers, FactSet, etc.)

Return:
- Full JSON (ready for Teams)
```

---

## 7. Weekly Project Status Email

```
You are a UI developer specializing in HTML for Power Automate emails.

Generate HTML for:

Scenario:
A weekly project status report email sent automatically every Monday morning. It shows project name, status badge (colour-coded), owner, and percentage complete for up to 10 projects. Footer includes a link to the Power App.

Requirements:
- Clean styling (inline CSS)
- Mobile-friendly
- Table-based layout where needed

Return:
- HTML only
```

---

## 8. Multi-Screen Form Variables

```
You are a Power Apps expert.

Help me design variables for this app:

Scenario:
A multi-screen new starter onboarding app. Screen 1 collects personal details. Screen 2 collects role and manager. Screen 3 collects IT requirements. Screen 4 is a summary/review before submission. User can go back and edit any screen. On submit, a Power Automate flow is triggered with all collected data.

Requirements:
- Use Set, UpdateContext, and collections appropriately
- Explain when to use each
- Keep naming consistent (var*, loc*, col*)

Return:
- Variable definitions
- Example usage
```

---

## 9. Debug: Gallery Not Showing All Records

```
You are a senior Power Platform developer.

I am getting this issue:
My gallery is only showing 500 records even though I have over 2000 rows in my SharePoint list. The gallery is set to show all items. I have no filter applied.

Context:
I am using a Gallery connected directly to a SharePoint list called "ProjectTasks". The Items property is just set to ProjectTasks with no filter. I need to show all records and allow the user to search by project name.

Requirements:
- Identify root cause
- Provide corrected code
- Explain why it failed

Return:
- Fixed version
- Explanation
```

---

## 10. Natural Language → Full App (Leave Request System)

```
You are a Power Platform expert.

Turn this business process into working app logic:

Process:
Employees submit annual leave requests via a Canvas App. They select dates, see their remaining allowance, and add a note. The request goes to their line manager for approval via Teams. If approved, the leave is logged in a central Dataverse table and the employee's allowance is updated. If rejected, the employee receives a notification with a reason. HR can view all requests across the company in a separate model-driven app.

Output:
1. Data model (tables + fields)
2. Canvas app logic (Power Fx)
3. Power Automate flows
4. Approval logic
5. Edge cases

Make it production-ready.
```

---

*© 2026 NextGen PowerApps — jerome@nextgenpowerapps.com*
*Full course: nextgenpowerapps.com*
