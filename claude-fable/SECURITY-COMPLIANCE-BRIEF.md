# Security & Compliance — build brief

**Page:** `/features/security-compliance/`
**Mock:** `vantage-fit-security-compliance-v1.html`
**Group:** D · Enterprise (page 2 of 3)
**Angle:** Data your security team can sign off.

---

## Research takeaways

1. **The honest version is the differentiator.** Live marketing carries SOC 2, ISO and GDPR badges. The facts lock rules all three out, and there is no usable spec behind them. A page that names what it will not claim reads more credible to a reviewer than a badge row, so that became a section rather than a footnote.
2. **Residency is precise and one-way.** Four separate regional instances, India, US, EU and UAE, chosen at onboarding, in-region endpoints, no cross-region sharing, no move without migration (`admin-data-privacy-security.md`, `auth-login-signup.md`). "Dedicated data center in your region" is the overclaim to avoid.
3. **The auth layer is the only place with hard numbers**, so it carries the page: lockout at 5 failed attempts, reset links single-use and valid one hour, 8 characters on reset versus 6 on in-app change (two separate flows), OTP valid 10 minutes and configurable per country, SSL pinning through TrustKit on mobile, captcha on non-mobile web and admin.
4. **What HR cannot see is the trust argument**, not a privacy paragraph. Help doc is explicit that admins cannot open individual health data, HRA detail, lab values, mood or food diary. Health-risk targeting returns a count with the disclaimer that the list of users is not displayed.
5. **AI is narrow.** Leadership Insights only: aggregated buckets through an internal ML API, read-only, no PII. Recommended Actions are rule-based. Lab extraction is the other AI surface and belongs to page 3.
6. **Encryption has no spec to quote.** The help article describes encryption in general terms; the lock forbids inventing specifics. The page therefore states that encryption detail is not published here and belongs in the review, rather than guessing at ciphers.

## Why this structure

- **The hero is a document, not a product mock.** A "security review sheet" panel of seven label and value rows sits where a screenshot would sit on the other two pages. That is the large HTML facts panel the run asks for, and it makes the first screen answer a reviewer's opening questions before they scroll.
- **The hero gradient is cooled off** so the page does not open like a fitness hero. Same tokens, quieter mix.
- The order runs the way a review runs: where the data lives, who can see it, how people get in, what leaves the dashboard, what is not claimed, then questions.
- **The dark band is the "does not claim" section.** On Admin Dashboard the dark band is the closer. Here it carries the four refusals, which is the most memorable thing on the page.
- Device catalogue is not reprinted. SAML appears as an auth fact only, with the detail linked to Integrations.

## Copy deck (key lines)

- **H1:** Data your security team can sign off.
- **Lead:** Written for a due-diligence review rather than a badge row.
- **S2 H2:** Four regions. No later move.
- **S3 H2:** Count only. Never a name list.
- **S4 H2:** Access, in numbers.
- **S6 H2:** Claims this page does not make.
- **BAA line:** HIPAA-guideline aligned, which is not the same as a HIPAA-compliant platform, and we will not write it as if it were.
- **Primary CTA:** Book a walkthrough. **Secondary:** Talk to security.

## Images

| Asset | Role |
|---|---|
| Hero `.sc-sheet` | Large HTML facts panel, stands in for a screenshot |
| CDN `vfit-analytics-dashboard-desktop.png` | What an admin actually opens: aggregates, sample figures |
| `../styled-homepage/card-measure-generic.jpg` | Photograph, review and hand-off |
| `../styled-homepage/logo.png` / `logo-white.png` | Nav and footer wordmark |

No badge imagery of any kind. Wellness Score screenshots are not used.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` (facts lock)
- `vantagefit-astro`: `admin/settings/admin-data-privacy-security.md`, `admin-how-do-i-enable-sso.md`
- `vfit-os`: `specs/product/00-platform/auth-login-signup.md`, `specs/09-admin-platform/admin-dashboard.md`
- Design system: `styles/enterprise.css`, `grok/vantage-fit-admin-dashboard-analytics-v1.html`

## Assumption stated

The help article mentions departmental patterns in Workforce Health. The facts lock restricts lab-risk reporting to org-level prevalence, so this page says aggregate org and department metrics for **participation** and org-level only for **health risk**. Lock wins over help.

## Meta

- **Title:** Employee wellness platform data privacy and security | Vantage Fit
- **Description:** Four regional instances, company-scoped isolation, aggregate-only admin reporting and the auth rules in numbers. No certification badges. Book a walkthrough.

## Critic result

| Check | Result |
|---|---|
| `../styles/enterprise.css` linked, no new brand | Pass |
| Large HTML facts panel plus product shot plus photograph | Pass |
| Marketing copy outside chrome | ~700 words |
| SOC2 / ISO 27001 / GDPR-compliant / HIPAA-compliant claimed or badged | No. Named only inside the "does not claim" section |
| Encryption specifics invented | No. Explicitly deferred to the review |
| Audit logs or biometric lock claimed live | No. Listed as not shipped |
| "Dedicated data center in your region" | Not used. Four regional instances |
| Org Wellness Score | Absent |
| Department or team drill-down on individual health data | Absent |
| Individual lab values or a health-risk name list on screen | Absent. Count only, with the privacy disclaimer quoted |
| Device catalogue reprinted from Integrations | No. SAML named as an auth fact, detail linked |
| Em-dashes, exclamation marks, "Learn more" | None |
