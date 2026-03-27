# Example: Debugging + Error Fixer

## Scenario
Gallery showing only 500 records from a SharePoint list of 3000+ items.

## Full prompt used

```
You are a senior Power Platform developer.

I am getting this issue:
My gallery is only showing 500 records even though I have over 3000 rows in my SharePoint list. I have no filter applied. The Items property is just set to the list name directly.

Context:
Gallery connected to a SharePoint list called "AssetRegister". Items property is: AssetRegister
I need to show all records and let users search by AssetName and filter by Category.

Requirements:
- Identify root cause
- Provide corrected code
- Explain why it failed

Return:
- Fixed version
- Explanation
```

## Expected output (summary)

Claude identifies the delegation limit (SharePoint default is 500, configurable to 2000 in settings).
Returns two options:
1. Increase delegation limit to 2000 in App Settings and use a delegable `Filter` with `StartsWith` for search
2. Use `ClearCollect` in `App.OnStart` with paging via `ForAll` and `Collect` to load all records into a collection (for truly large lists)

Also explains why `Search()` is not delegable on SharePoint and what to use instead.

## Pro tip
After Claude fixes the immediate issue, ask it: "What other delegation issues might exist in this app?" — it will audit the pattern and flag other at-risk formulas.
