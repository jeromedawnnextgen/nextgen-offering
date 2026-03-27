# NextGen PowerApps — Offering Website

Deployed on Azure Static Web Apps via GitHub Actions.

**Base URL:** `https://ambitious-beach-0ef305710.4.azurestaticapps.net`

---

## Pages

| URL | File | Purpose |
|-----|------|---------|
| https://ambitious-beach-0ef305710.4.azurestaticapps.net | `index.html` | Course sales page — hero, curriculum, pricing, enroll |
| https://ambitious-beach-0ef305710.4.azurestaticapps.net/email-list-build/ | `email-list-build/index.html` | Opt-in landing page — collects name + email for the lead magnet |
| https://ambitious-beach-0ef305710.4.azurestaticapps.net/email-list-build/thank-you.html | `email-list-build/thank-you.html` | Post-submit confirmation page — shown after email is captured |
| https://ambitious-beach-0ef305710.4.azurestaticapps.net/email-list-build/lead-magnet.html | `email-list-build/lead-magnet.html` | The full Power Platform AI Starter Kit — 12 prompts + bonus, copy buttons, download as ZIP |

---

## Email Funnel Flow

```
Visitor lands on /email-list-build/
        ↓
Enters name + email → submits form
        ↓
JS POSTs to Logic Apps HTTP webhook (eastus)
        ↓
Logic App fires → sends email via Office 365 Outlook
Email contains link to /email-list-build/lead-magnet.html
        ↓
Browser redirects to /email-list-build/thank-you.html
Thank-you page shows direct link to lead magnet
```

---

## Integrations

| Service | What it does | Where to manage |
|---------|-------------|-----------------|
| Azure Static Web Apps | Hosts all pages | portal.azure.com → nextGenSetupProject1 → nextgenpowerapps-offering |
| GitHub Actions | Auto-deploys on push to `main` | github.com/jeromedawnnextgen/nextgen-offering/actions |
| Logic Apps | Receives form webhook, sends lead magnet email | portal.azure.com → nextGenSetupProject1 |
| Office 365 Outlook | Email delivery via Logic App | Configured in Logic App connector |
| Stripe | Course checkout | buy.stripe.com/dRm7sMbOIfG02MdgAKdMI00 |

---

## Deployment

Push to `main` → GitHub Actions deploys automatically. No build step.

```bash
git add .
git commit -m "your message"
git push origin main
```

---

## Placeholders Still Outstanding

- `jerome@nextgenpowerapps.com` — confirm this is the right reply-to address
- Social proof avatars on opt-in page — replace initials with real photos
- Jerome photo on opt-in page — replace `JD` circle with `<img>`
- Testimonials on course page — replace placeholder quotes with real ones
- Privacy Policy / Terms pages — linked in footer, pages don't exist yet
