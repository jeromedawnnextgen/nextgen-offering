# 05 — JSON Generator

**Category:** Integrations
**Difficulty:** Beginner

---

## What this prompt does

Generates realistic JSON payloads for API calls and HTTP actions, complete with sample values.
Also generates the Parse JSON schema — the thing you'd normally get by clicking "Generate from sample"
but with correct types and nullable fields handled properly.

---

## When to use it

- You're calling an external API from a Power Automate HTTP action
- You need to build a request body for a POST/PATCH call
- You're setting up a Parse JSON action and want the schema without trial and error
- You're building a custom connector and need example payloads

---

## The Prompt

```
You are an expert in JSON for Power Platform integrations.

Generate a JSON structure for:

Scenario:
[Describe API or payload]

Requirements:
- Include realistic sample values
- Ensure proper formatting
- Compatible with Power Automate Parse JSON

Return:
- JSON
- Suggested schema (optional)
```

---

## How to adapt it

- Describe the **entity**: "An invoice from an accounts payable system"
- List the **fields**: "Invoice number, supplier, date, line items array, total"
- Mention **array fields** explicitly: "Line items is an array where each item has description, quantity, and unit price"
- If calling a specific API, name it: "This is a payload for the Xero Invoices API"

---

## What to expect back

- A properly formatted JSON object with realistic sample data
- Field names in the casing convention you need (camelCase by default)
- Array examples with multiple items so the schema is correct
- The Power Automate-compatible schema (paste directly into Parse JSON)

---

## Common mistakes

- Not specifying array fields — Claude will generate a flat object and the schema won't handle your line items
- Using the generated JSON directly in production — it has sample values, not real ones
- Forgetting that Parse JSON schema needs `"type": "array"` with an `"items"` definition for arrays

---

## Learn more

Covered in **Week 6 (Advanced Power Automate)** and **Week 9 (Azure Integrations)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
