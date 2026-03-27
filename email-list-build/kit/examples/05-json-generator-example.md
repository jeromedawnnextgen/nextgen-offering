# Example: JSON Generator

## Scenario
Calling an external finance API to post a new supplier invoice with line items.

## Full prompt used

```
You are an expert in JSON for Power Platform integrations.

Generate a JSON structure for:

Scenario:
A POST request body to submit a supplier invoice to an external finance system. The invoice has a header (invoice number, supplier ID, invoice date, currency, payment terms) and line items array (line number, GL code, description, quantity, unit price, VAT rate).

Requirements:
- Include realistic sample values
- Ensure proper formatting
- Compatible with Power Automate Parse JSON

Return:
- JSON
- Suggested schema (optional)
```

## Expected output (summary)

A JSON object with a header object and a `lineItems` array with 2–3 sample items. Claude also returns the Power Automate Parse JSON schema with correct types (`string`, `number`, `integer`, `array`) and an `items` definition for the line items array.

## Pro tip

After getting the schema, test it in Power Automate by using the "Use sample payload to generate schema" button and paste the sample JSON — compare it to what Claude generated and reconcile any differences.
