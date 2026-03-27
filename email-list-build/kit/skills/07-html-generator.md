# 07 — HTML Generator (Emails / PDFs)

**Category:** Power Automate
**Difficulty:** Beginner

---

## What this prompt does

Generates clean, mobile-friendly HTML with inline CSS for use inside Power Automate email actions.
Table-based layout where needed, readable on all email clients including Outlook.
No external stylesheets — everything inline so it works in the Send Email action.

---

## When to use it

- You're sending formatted notification emails from a flow
- You need an invoice, expense summary, or report in email body
- You want professional-looking emails instead of plain text
- You're generating HTML to attach as a PDF (via a third-party connector)

---

## The Prompt

```
You are a UI developer specializing in HTML for Power Automate emails.

Generate HTML for:

Scenario:
[Invoice / Approval summary / Report]

Requirements:
- Clean styling (inline CSS)
- Mobile-friendly
- Table-based layout where needed

Return:
- HTML only
```

---

## How to adapt it

- Describe the **document type**: invoice, weekly summary, approval confirmation, onboarding welcome
- List the **fields** that need to appear and their order
- Mention any **branding**: "Use a blue (#0078D4) header, company logo placeholder at the top"
- Mention **dynamic content placeholders**: "Employee name, request date, and amount will come from Power Automate dynamic content"

---

## What to expect back

- Complete HTML with `<table>` layout and inline `style=""` on every element
- Placeholder values like `[EmployeeName]` or `{{Amount}}` you replace with Power Automate dynamic content
- Mobile-responsive structure using `max-width` and percentage widths

---

## Inserting dynamic content

After you get the HTML, paste it into the Body of a "Send an email" action.
Switch the body field to **Code View** (the `</>` icon) and paste the HTML.
Then replace each placeholder with the corresponding dynamic content token from Power Automate.

---

## Common mistakes

- Using external CSS classes — they get stripped by email clients. Everything must be `style="..."` inline
- Using flexbox or CSS Grid in email HTML — not supported in Outlook. Use `<table>` layout
- Forgetting to escape special characters like `&` → `&amp;` in HTML content

---

## Learn more

Covered in **Week 5 (Power Automate Foundations)** and **Week 8 (SharePoint & Teams Integration)**
of the 12-Week Power Platform Mastery Program.
→ nextgenpowerapps.com
