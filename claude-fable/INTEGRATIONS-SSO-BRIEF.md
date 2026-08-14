# Integrations & SSO — build brief

**Page:** `/features/integrations-sso/`
**Mock:** `vantage-fit-integrations-sso-v1.html`
**Group:** D · Enterprise (page 1 of 3)
**Angle:** Works with what employees wear and what IT runs.

---

## Research takeaways

1. **Two buyers, one URL.** Wearables is an HR and employee question. SSO, HRIS and provisioning is an IT question. The locked IA keeps them on one slug, so the page has to keep them apart visually rather than blend them into an "integrations ecosystem" story.
2. **No wearable required is the real headline of the first module.** Apple Health on iOS, Google Fit on Android. A tracker adds detail, it is not an entry ticket. (`do-i-need-a-wearable.md`, briefs.)
3. **Garmin is the only real-time connection** — OAuth 1.0a, three-step flow, webhook push, GPS routes, historical backfill, and access tokens that expire at 60 days (`specs/10-integrations/garmin-integration.md`). Fitbit is OAuth token storage that syncs on app open and on demand (`fitbit-integration.md`). The uncited "vs 15–30 min competitor polling" line is not used.
4. **SSO is not a toggle.** Help doc is explicit: configured by the Vantage Fit integration team, not from the admin dashboard, with IdP metadata exchange in both directions and a pilot group before go-live (`admin-how-do-i-enable-sso.md`). Help names Microsoft Entra ID (formerly Azure AD), Okta, OneLogin, Ping Identity.
5. **HRIS roster is code-verified and client-specific.** Workday, DarwinBox, ADP, Zoho People, SAP, Infor ION, Synergita, Adrenalin, Workline, Knit — with "confirm readiness with the integration team" attached (`auth-login-signup.md`). BambooHR is not on the list and was not added.
6. **Region is a one-way door.** India, US, EU, UAE at onboarding, no move without migration. Stated here as an onboarding fact only; Security owns residency in depth.

## Why this structure

The page is two modules with a hard break, not a blend:

- **Module 01 — Wearables and device sync.** Photograph plus the connected-devices product shot, a device table, the one-primary-device rule, and its own two-question FAQ.
- **A dark hand-off band** between them: "Devices settle what gets logged. Identity settles who can log at all." This is the visual wall the prompt asks for, and it carries the participation through-line across the seam.
- **Module 02 — Identity and provisioning.** No photograph and no consumer imagery. A four-step HTML setup flow, a sign-in method list, an HRIS chip roster, and its own two-question FAQ. The change in texture (schematic instead of photographic) is what tells a scanner the reader has changed.

FAQ schema is split per module, so wearables and SSO never share one blob. Device facts inherit Group A and do not contradict `grok/vantage-fit-fitness-exercise-v1.html`.

## Copy deck (key lines)

- **H1:** Works with what employees wear, and what IT runs.
- **Lead:** Two integration questions arrive from two different rooms, and neither answers the other. This page keeps them apart.
- **Module 01 H2:** Wearables, and the phone in every pocket.
- **Hand-off:** Devices settle what gets logged. Identity settles who can log at all.
- **Module 02 H2:** SAML 2.0, set up by people, not a toggle.
- **Rule callout:** One primary device at a time. Connect Fitbit or Garmin and it becomes the step source, so no day is counted twice.
- **Closer:** Bring your IdP list and your device mix.
- **Primary CTA:** Book a walkthrough.

## Images

| Asset | Role |
|---|---|
| `../styled-homepage/card-participate.jpg` | Hero photograph, movement |
| CDN `vantage-fit-connected-devices-sync-mobile.png` | Module 01 product shot, connected devices screen |
| `../styled-homepage/logo.png` / `logo-white.png` | Nav and footer wordmark |

Module 02 deliberately carries no photograph. Its visuals are the setup flow and the roster, which is the point.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` (facts lock, prevails over live marketing)
- `vantagefit-astro`: `admin/settings/admin-how-do-i-enable-sso.md`, `employee/getting-started/` device articles
- `vfit-os`: `specs/product/00-platform/auth-login-signup.md`, `specs/10-integrations/garmin-integration.md`, `fitbit-integration.md`, `vantage-circle-ecosystem.md`
- Design system: `styles/enterprise.css`, `styled-homepage/`, `grok/vantage-fit-admin-dashboard-analytics-v1.html` (density peer), `grok/vantage-fit-fitness-exercise-v1.html` (device facts inherited)

## Meta

- **Title:** Employee wellness platform integrations and SSO | Vantage Fit
- **Description:** Steps from Apple Health, Google Fit, Fitbit, Garmin or Samsung, plus SAML 2.0 single sign-on and CSV, SFTP or HRIS provisioning. Book a walkthrough.

## Critic result

| Check | Result |
|---|---|
| `../styles/enterprise.css` linked, no new brand | Pass |
| Real images, every `<img>` has alt | Pass — 1 photograph, 1 product shot |
| Marketing copy outside chrome | ~660 words |
| Health Connect named as Android step source | Not present. Google Fit named as the Android step source |
| Fitbit called real-time | No. Explicitly "not in real time" |
| Step normalization / daily cap claimed active | Not claimed. Trusted-source filtering only |
| 47+ activity types, 14 languages | Not present. 13+ languages |
| BambooHR | Absent |
| SSO as self-serve toggle | Explicitly denied, twice |
| Wearable required | Explicitly denied |
| Withings / Polar / Oura / Whoop | Absent |
| SOC2 / ISO / GDPR / HIPAA badges | None anywhere, including the mega menu and footer |
| Org Wellness Score | Absent |
| Two hard-separated modules | Yes — dark hand-off band, separate FAQs, separate FAQ schema entries |
| Em-dashes, exclamation marks, "Learn more" | None |
