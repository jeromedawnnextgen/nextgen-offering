# Example: Collection Builder

## Scenario
Loading all open IT support tickets assigned to the current user into a collection on app start, with a calculated "DaysOpen" column.

## Full prompt used

```
You are a senior Power Apps developer.

I need help building a collection in a Canvas App.

Context:
- Data source: Dataverse
- Table name: cr123_SupportTickets
- Columns: cr123_TicketId, cr123_Title, cr123_Status, cr123_Priority, cr123_CreatedOn, cr123_AssignedTo (lookup to SystemUser)
- Goal: Collection of all Open or In Progress tickets assigned to the current user, with a DaysOpen calculated column

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

## Expected output (summary)

Claude returns a `ClearCollect` wrapping a `Filter` on the Dataverse table with `AssignedTo` matching `User().Email`, status in `["Open","In Progress"]`, and an `AddColumns` wrapping it to calculate `DaysOpen` as `DateDiff(cr123_CreatedOn, Today(), Days)`.

## Pro tip

Ask Claude to also generate the `App.OnStart` initialization so you know exactly where to place it.
