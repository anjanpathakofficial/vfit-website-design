# Security & Compliance — brief

URL: `/features/security-compliance/` · Mock: `vantage-fit-security-compliance-v1.html`

## Research takeaways

- Facts lock: `FEATURES-ENTERPRISE-BRIEFS.md` §13 plus shared physics. This page owns multi-tenant isolation, residency, auth-layer facts, what HR cannot see, Leadership Insights no-PII, account deletion, and BAA scope.
- Precise auth numbers from the lock: lockout after 5 failed password attempts; reset links single-use, expire in 1 hour; 8 chars minimum on reset vs 6 chars for in-app change (two separate flows); OTP valid 10 minutes (configurable per country); TrustKit SSL pinning on mobile; captcha on non-mobile web and admin.
- Residency phrasing: four regional instances (India, US, EU, UAE), in-region endpoints, no post-setup region change without migration. Never "a dedicated data center in your region."
- HR boundary: aggregate org / department metrics only; no individual health profiles, HRA, labs; health-risk targeting is count only with the privacy disclaimer ("The list of users is not displayed to protect individual privacy").
- Leadership Insights: AI-generated, no PII, aggregated buckets, internal ML API, read-only.
- HIPAA: "BAA provisions for HIPAA compliance," scoped to the lab-report pipeline only; phrased as "HIPAA-guideline aligned." Never platform-wide.
- Not claimed anywhere: SOC2, ISO 27001, GDPR compliance, encryption specifics (AES-256, TLS versions, at-rest), audit logs, biometric app lock, Org Wellness Score.

## Why this structure

Due-diligence tone, not a fitness hero. The first screen is a numbered facts panel (auth + residency facts a reviewer can paste into a questionnaire) instead of a product hero shot, per the prompt's Security exception. Then: isolation and residency, what HR can and cannot see (with the analytics screenshot as proof of aggregate-only reporting), account deletion, and the HIPAA scope note. Photograph: `card-measure-generic.jpg` (review / due-diligence imagery).

Sections: hero (facts panel + photo) → regions and isolation → what HR sees (analytics shot) → account lifecycle + HIPAA scope → FAQ (3) → siblings → CTA with "Request a security packet" secondary (no invented contents).

## Copy deck (condensed)

- H1: "The participation number is safe to report. The person behind it stays private."
- H2s: "Four regions. No quiet move later." / "HR sees the crowd, never the person." / "Offboarding that forgets the person, not the record."
- HIPAA line: "For companies on the lab-report pipeline, BAA provisions for HIPAA compliance apply to that pipeline. The platform is HIPAA-guideline aligned; the BAA is scoped to lab data, not the whole product."
- CTAs: "Book a walkthrough" (primary), "Request a security packet" (secondary).

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` §13, shared physics, guardrails.
- `FEATURES-ENTERPRISE-PROMPT.md` (locked IA, images, density, no trust-badge row).
- Analytics screenshot per prompt: `vfit-analytics-dashboard-desktop.png` (aggregate admin view; no Wellness Score shots used).

## Meta

- Title: `Employee wellness platform data privacy and security | Vantage Fit`
- Description: `Four regional instances, company-scoped isolation, SAML 2.0, and aggregate-only HR reporting. How Vantage Fit handles corporate wellness platform security.`

## Critic result

- No SOC2 / ISO / GDPR claims or badges. No encryption specifics invented. No "HIPAA-compliant platform." No dedicated-data-center overclaim (four regional instances). No audit logs or biometric lock. No Org Wellness Score. No individual health data on screen. SAML mentioned as an auth fact only; device catalog not reprinted. Facts panel + analytics shot + one photograph. Copy ≈ 620 words. Pass.
