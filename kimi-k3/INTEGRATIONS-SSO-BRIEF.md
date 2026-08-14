# Integrations & SSO — brief

URL: `/features/integrations-sso/` · Mock: `vantage-fit-integrations-sso-v1.html`

## Research takeaways

- Facts lock: `FEATURES-ENTERPRISE-BRIEFS.md` §12 and "Shared enterprise physics". Device facts inherited from Group A (`grok/vantage-fit-fitness-exercise-v1.html` rules): no wearable required, one primary device, Fitbit not real-time, Garmin the only real-time webhook push, Garmin tokens expire at 60 days, Samsung as Android device option, 70+ apps via Apple Health.
- Android steps = Google Fit (or selected Android device source), never Health Connect. Health Connect not mentioned on the page to keep it simple.
- SSO = SAML 2.0 only, IdP metadata exchange with the Vantage Fit integration team. Not a self-serve toggle. Named IdPs: Okta, Azure AD, OneLogin, Ping Identity.
- HRIS list from the lock, no BambooHR: Workday, DarwinBox, ADP, Zoho People, SAP, Infor ION, Synergita, Adrenalin, Workline, Knit. Most are client-specific, so the page says "confirm readiness with the integration team."
- Region (India, US, EU, UAE) chosen at onboarding, no later change without migration. 13+ languages. VC ecosystem single account (R&R employee reaches VFit without a second account).

## Why this structure

One page, two hard-separated H2 modules with an anchor sub-nav and a labeled divider band, so it never reads as blended "integrations soup." Wearables first (HR persona, visual, device product shot), IT module second (SSO / auth / provisioning, darker and more spec-like). Each module carries its own small FAQ (2 + 1, separate FAQPage schema blocks). A short through-line strip closes: devices and identity exist so logs become one participation number.

Sections: hero (device sync shot) → module 1 wearables (device cards + photograph) → hard divider → module 2 SSO/HRIS (SAML panel, other auth, HRIS list, tier flags) → through-line → sibling links → CTA.

## Copy deck (condensed)

- H1: "Works with what employees wear. And with what IT runs."
- Module 1 H2: "Module 1 · Wearables and device sync" / "The watch they already own is the tracker."
- Module 2 H2: "Module 2 · SSO, HRIS, and provisioning" / "One login, one roster, one region."
- Through-line: "Every synced step and every SSO login lands on the same participation score."
- CTAs: "Book a walkthrough" (primary), "Talk to the integration team" (secondary).

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` §12, shared physics, guardrails.
- `FEATURES-ENTERPRISE-PROMPT.md` (locked IA, images, density).
- Device facts cross-checked against `grok/vantage-fit-fitness-exercise-v1.html` (Group A inheritance).

## Meta

- Title: `Employee wellness platform integrations and SSO | Vantage Fit`
- Description: `Apple Health, Google Fit, Fitbit, Garmin, and 70+ apps sync into Vantage Fit. SAML 2.0 SSO, HRIS provisioning, and four data regions for corporate wellness.`

## Critic result

- No SOC2 / ISO / GDPR / HIPAA claims. No Org Wellness Score. No Health Connect as step source. Fitbit not called real-time. Garmin softened to "real-time webhook push, not periodic polling" (no competitor number). No BambooHR. SSO not self-serve. No Withings / Polar / Oura / Whoop. No step-cap / normalization claim. 13+ languages, 65 not mentioned. Two modules with a hard break and separate FAQs. One CDN product shot + one photograph. Copy ≈ 600 words. Pass.
