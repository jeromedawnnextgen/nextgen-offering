# Example: Variables + State Management

## Scenario
A 4-screen asset request app where users fill in details across screens and submit on the final screen.

## Full prompt used

```
You are a Power Apps expert.

Help me design variables for this app:

Scenario:
A 4-screen asset request app. Screen 1: requester selects asset type and quantity. Screen 2: requester adds business justification and cost centre. Screen 3: shows a summary for review. Screen 4: confirmation after submission. Users can go back and edit. On submit, a Power Automate flow is triggered. Show a loading spinner during submission. Track whether the form is in New or Edit mode (edit loads an existing draft).

Requirements:
- Use Set, UpdateContext, and collections appropriately
- Explain when to use each
- Keep naming consistent (var*, loc*, col*)

Return:
- Variable definitions
- Example usage
```

## Expected output (summary)

- `varFormMode` (Text, global) — "New" or "Edit", set on app start or when loading a draft
- `varSelectedDraft` (Record, global) — the loaded draft record if in edit mode
- `varIsSubmitting` (Boolean, global) — drives the loading spinner visibility
- `locAssetType`, `locQuantity` (local on Screen 1) — captured on Next button, promoted to global before navigation
- `colRequestLines` (Collection) — if multiple asset lines are supported

## Pro tip
Ask Claude to also generate the `App.OnStart` formula that initialises all global variables to their default values — this prevents blank/error states on first load.
