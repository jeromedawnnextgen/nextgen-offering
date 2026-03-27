# Example: Natural Language → Full App Logic

## Scenario
A leave management system for a 500-person company replacing a manual email process.

## Full prompt used

```
You are a Power Platform expert.

Turn this business process into working app logic:

Process:
Employees at a 500-person manufacturing company currently request annual leave by emailing their manager. The manager emails HR to check allowances, then replies to approve or reject. HR updates an Excel spreadsheet. There is no visibility into team leave overlap.

We need a Canvas App where employees submit leave requests (date range, type: annual/sick/other, notes). Managers get a Teams notification with approve/reject. HR has a model-driven app to manage allowances and view all requests. The system must prevent requests that would leave fewer than 2 people in a team on any given day. Managers have 24 hours to respond before it escalates to the department head. All data in Dataverse.

Output:
1. Data model (tables + fields)
2. Canvas app logic (Power Fx)
3. Power Automate flows
4. Approval logic
5. Edge cases

Make it production-ready.
```

## Expected output (summary)

**Data model:** 4 tables — Employees (with TeamId lookup), LeaveRequests (employee, dates, type, status, approver), LeaveAllowances (employee, year, type, totalDays, usedDays), Teams (name, minimumCoverage)

**Canvas App:** 3 screens — Request submission form, My Requests gallery with status, Team Calendar view showing overlaps

**Flows:** 3 flows — Submit request (validates coverage, triggers approval), Approval response handler (updates status, notifies employee), Daily escalation check (scheduled, flags overdue approvals)

**Approval logic:** Manager gets Teams Adaptive Card. 24h timeout triggers escalation to department head lookup. Rejection requires a reason which is sent to the employee.

**Edge cases:** Overlapping date requests from same employee, requests spanning public holidays, sick leave bypassing approval, employees with no manager assigned

## Pro tip
Use this output as the agenda for your first scoping call with the client — walk through each section and confirm or correct with them. The gaps they identify become your change request scope.
