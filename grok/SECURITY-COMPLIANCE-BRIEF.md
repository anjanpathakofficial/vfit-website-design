# Security & Compliance

**URL:** `/features/security-compliance/`  
**Mock:** `vantage-fit-security-compliance-v1.html`  
**Angle:** Data your security team can sign off.

## Page job

Prove residency, isolation, auth-layer facts, and what HR cannot see, so an IT reviewer can stay in the room with HR. Due-diligence page. Not a certification landing page. Not a lab-pipeline reprint. Not a device catalog.

**Reader:** IT / security, with HR sitting next to them.  
**Primary CTA:** Book a walkthrough. **Secondary:** Talk to security (hero), Request a security packet (close). Packet contents not invented.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Isolation (lock + AUTH-001):** Company-scoped multi-tenant isolation (`companyId` throughout). Lab / health-risk queries company-scoped.
- **Residency (lock + AUTH-001 + help privacy):** India, US, EU, UAE. In-region endpoints. Chosen at onboarding. No later change without migration. **Not** “a dedicated data center in your region.” Four regional instances.
- **Auth facts (lock + AUTH-001):** SAML 2.0 (pointer only; Integrations owns IdPs). Lockout after **5** failed password attempts. Reset links single-use, expire in **1 hour**. Reset min **8** chars. In-app change min **6** chars. OTP **10 min** (configurable per country). TrustKit SSL pinning on mobile. Captcha on non-mobile web / admin.
- **HR view (lock + help privacy):** Aggregates only. Cannot see individual health profiles, HRA, lab / biomarker data, or mood. Health-risk target = **count only** + disclaimer: *The list of users is not displayed to protect individual privacy.*
- **Leadership Insights (lock + OS admin-dashboard):** AI, **no PII**, aggregated buckets, internal ML API, read-only. Recommended Actions stay rule-based and live on Admin Dashboard, not here.
- **Account deletion (lock + AUTH-001):** Name / email hashed, tokens cleared, historical activity / transaction records kept for reporting. Company-configurable. Some clients disable it.
- **HIPAA (lock):** “BAA provisions for HIPAA compliance,” lab-report pipeline only. Write “HIPAA-guideline aligned.” Never “HIPAA-compliant platform.”
- **Do not claim:** SOC2, ISO 27001, GDPR compliance, encryption specifics (AES-256, TLS, at-rest), audit logs, biometric lock, dedicated DC, Org Wellness Score.
- **Proof:** 100+ organizations only. No invented packet contents.

### Conflicts left unresolved (not silently fixed)

1. AUTH-001 FAQ says reset links last 24 hours. Spec body and lock: 1 hour. Page uses 1 hour.
2. Help privacy mentions encryption of some fields and “encrypted connections.” Lock: do not invent encryption specifics. Page omits encryption language.
3. Help Workforce Health still describes Org Wellness Score and employee-level drill-down. Lock: retired, and HR never sees a person. Absent here.
4. Live marketing Security pages claim SOC 2 / GDPR / ISO. Out of scope. Not copied.

## Why this structure

Quieter hero than Integrations. Signature is an HTML auth facts panel, not a badge row. Photograph is a review meeting. Analytics CDN shot is supporting (participation view), never a Wellness Score shot.

| Section | Job |
|---|---|
| Hero + review photo + residency chips | First screen: four instances, no badge wall. |
| Four regions | No later move. Not a dedicated DC. |
| Auth facts panel | Exact lockout / reset / OTP / TrustKit / captcha numbers. |
| Analytics shot + crowd vs person | What HR sees. Count-only disclaimer. |
| Insights + deletion + BAA | AI without PII. Deletion rule. Lab-pipeline BAA only. |
| 3 FAQs + siblings | HIPAA scope, region move, packet without inventing certs. |
| Close | Book a walkthrough / Request a security packet. |

**Visual:** Same chrome as Admin Dashboard and Integrations. Darker hero wash. No trust-badge row. Features mega-menu current: Security & compliance.

## Copy deck

**Title:** Employee wellness platform data privacy | Vantage Fit  
**Meta:** Four regional instances, company-scoped isolation, and aggregate-only health views. Review auth lockout, OTP, and BAA scope. Book a walkthrough.

**Eyebrow:** Features · Enterprise  
**H1:** Data your security team can sign off.  
**Lead:** Four regional instances. Company-scoped isolation. HR sees a crowd, never a name list. That is how the participation number stays usable upstairs.  
**Hero notes:** India, US, EU, UAE · Aggregate only · 100+ organizations  
**CTAs:** Book a walkthrough · Talk to security

**H2:** Four regions. No later move.  
India, US, EU, UAE. Chosen at onboarding. In-region endpoints. Migration required to change.

**H2:** The numbers a reviewer will ask for.  
5 lockouts. 1-hour reset. 8 vs 6 chars. 10-min OTP. TrustKit. Captcha. SAML 2.0.

**H2:** Count only. Never a name list.  
Disclaimer quoted. Labs and HRA stay with the employee.

**H2:** Insights without names. A BAA on the lab pipe.  
Leadership Insights: AI, no PII, read-only. Deletion hashes identity. BAA for the lab-report pipeline. HIPAA-guideline aligned.

**FAQ**  
1. Can HR open an individual’s labs or HRA?  
2. Is Vantage Fit a HIPAA-compliant platform?  
3. Can we change region after go-live?

**Close H2:** Review the facts. Then book the room.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` shared physics + page 13
- `vc-os/vfit-os/specs/product/00-platform/auth-login-signup.md`
- `vc-os/vfit-os/specs/product/09-admin-platform/admin-dashboard.md` (Leadership Insights no-PII)
- `vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md` (admin can/cannot; Org Wellness Score language unused)
- `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-enable-sso.md` (SAML as an auth fact only)

## Assumptions

- “Request a security packet” is a CTA only. No invented attachments.
- SAML is named as an auth fact. IdP catalog stays on Integrations.
- Lab privacy depth stays on Health Data Upload. This page owns BAA scope and aggregate-only.
- Generated review photo is brand photography, not a product UI.

## Critic

Run after the mock. Failures found in draft and fixed:

- No SOC2 / ISO / GDPR / HIPAA-compliant-platform badges or claims.
- No AES-256 / TLS / at-rest invention.
- No dedicated-data-center overclaim.
- Org Wellness Score absent.
- Device catalog not reprinted.
- Audit logs and biometric lock not claimed.
- `../styles/enterprise.css` linked. Photograph + analytics shot + HTML facts panel present.

**Pass.** Marketing copy in `<main>` is 592 words. No badge row. HIPAA-compliant platform appears only as a denial. Visual check at 1440 and 390.
