# 08 — Variables + State Management

**Category:** Canvas Apps
**Difficulty:** Intermediate

---

## What this prompt does

Designs your complete variable strategy before you start building.
Decides between `Set` (global), `UpdateContext` (local), and collections for each piece of state.
Returns named variable definitions with consistent `var*`, `loc*`, `col*` naming and example usage.

---

## When to use it

- You're starting a new multi-screen app and want a clean variable plan
- Your app has grown messy with variables scattered everywhere
- You're not sure whether to use Set or UpdateContext for a given value
- You need to pass data between screens without using a collection

---

## The Prompt

```
You are a Power Apps expert.

Help me design variables for this app:

Scenario:
[Describe app behavior]

Requirements:
- Use Set, UpdateContext, and collections appropriately
- Explain when to use each
- Keep naming consistent (var*, loc*, col*)

Return:
- Variable definitions
- Example usage
```

---

## How to adapt it

- Describe **all screens** and what data moves between them
- Describe **user actions**: "User selects a record in gallery, edits it on the next screen, submits back"
- Mention **loading states**: "Show a spinner while data loads"
- Mention **form modes**: "The same form is used for New and Edit — the mode is passed from the gallery screen"

---

## What to expect back

- A table or list of every variable needed with: name, type (boolean/text/record/table), scope (global/local), and purpose
- Example `Set()` and `UpdateContext()` calls showing where each variable is set and read
- Collection definitions with `ClearCollect` where appropriate
- Notes on which variables to initialise in `App.OnStart`

---

## Naming convention used

| Prefix | Scope | Example |
|--------|-------|---------|
| `var` | Global (Set) | `varCurrentUser`, `varIsLoading` |
| `loc` | Local (UpdateContext) | `locFormMode`, `locSelectedRecord` |
| `col` | Collection | `colProjects`, `colFilteredTasks` |

---

## Common mistakes

- Using `Set` for everything — global variables persist across screens, which can cause stale data bugs
- Using `UpdateContext` to pass data to the next screen — it doesn't work, use `Set` or a collection
- Not initialising variables in `App.OnStart` — leads to `blank` values causing errors on first load

---

## Learn more

Covered in **Week 2 (Canvas App Architecture)** and **Week 4 (Advanced Canvas Patterns)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
