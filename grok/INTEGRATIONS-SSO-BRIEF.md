# Integrations & SSO

**URL:** `/features/integrations-sso/`  
**Mock:** `vantage-fit-integrations-sso-v1.html`  
**Angle:** Works with what employees wear and what IT runs.

## Page job

Prove two capabilities on one URL: wearables / device sync for HR, and SAML / HRIS / provisioning for IT. Hard-separated H2 modules. Not a blended integrations soup. Not a second Fitness catalog. Not a Security reprint.

**Reader:** Split brain. HR on wearables. IT on SSO / HRIS.  
**Primary CTA:** Book a walkthrough. **Secondary:** See wearables (hero), Review SSO (hero + IT band).

## Research takeaways

Preferred the facts lock when sources disagreed.

- **No wearable required (lock + help + DEVICE-001):** Steps via Apple Health (iOS) and Google Fit (Android default). Phone sensors suffice.
- **Health Connect:** Legitimate for Android import of workouts, sleep, weight, heart rate, calories, distance. **Not** the Android step source. Omitted from this page so Fitness keeps the import story.
- **Apple Health / Apple Watch:** Steps, workouts, weight, calories, sleep, heart rate, distance. Watch automatic via paired iPhone.
- **Fitbit (lock + OS Fitbit):** OAuth. Steps / workouts / HR zones / sleep stages. Historical up to 30 days. **Not** real-time. Syncs on app open + on-demand.
- **Garmin (lock + OS Garmin):** OAuth 1.0a, 3-step, **real-time webhook** push, daily + activity summaries + GPS, 50 MB payloads, historical backfill. Tokens **expire after 60 days**. Softened competitor-polling claim to "real-time webhook push, not periodic polling."
- **Samsung Watch:** Android device option. **70+** via Apple Health (Amazfit / Zepp, Mi Band, Huawei, Nike Run Club, Strava).
- **One primary device.** Fitbit / Garmin override Apple Health / Google Fit as the step source.
- **Trusted step-source filtering is real.** Daily cap / normalization exists in code and is **disabled globally**. Not claimed as active.
- **SSO (lock + AUTH-001 + help SSO):** SAML 2.0. Okta, Azure AD, OneLogin, Ping Identity, etc. Integration-team metadata exchange. **Not self-serve.** IdP login / branding; VFit sign-in screen keeps VFit branding. Full white-label is a separate build.
- **Other auth:** Password. OTP email; 4-digit mobile / 6-digit web; 10-min; SMS whitelist. Google Sign-In = GSuite enterprise only. Employee-ID login = whitelist.
- **HRIS (lock + AUTH-001):** Workday, DarwinBox, ADP, Zoho People, SAP, Infor ION, Synergita, Adrenalin, Workline, Knit. Most client-specific. **Confirm readiness.** No BambooHR.
- **Provisioning:** HR Admin CSV, SFTP, HRIS. Self-registration by work-email domain on by default. Blocked-domain examples are a one-line fact.
- **Region:** India, US, EU, UAE at onboarding. **13+** languages, never 14 (help language table lists 14 rows including fr-CA; lock wins).
- **VC ecosystem:** Shared user / company / auth. FitnessConfig 15+ flags. R&R employee reaches VFit without a second account.
- **Proof:** 100+ organizations. No integration-specific client stat.

### Conflicts left unresolved (not silently fixed)

1. Help language article lists 14 rows (fr + fr-CA). Lock: 13+. Page says 13+.
2. AUTH-001 FAQ says password-reset links last 24 hours. Spec body and lock: 1 hour. Not on this page (Security owns the number).
3. DEVICE-001 still describes step normalization as if configurable. Lock: disabled globally. Page does not claim the cap is on.
4. Help Workforce Health / OS still mention Org Wellness Score. Retired. Absent here.

## Why this structure

Two modules. Wearables first (HR is the more common Features reader), then a dark IT band as a hard break, then SSO / HRIS. Jump chips in the hero so IT can skip.

| Section | Job |
|---|---|
| Hero + desk photo + jump chips | First screen: two jobs, not one blended story. Photograph + watch. |
| Wearables H2 + device cards | Phone first. Fitbit not real-time. Garmin webhook + 60 days. |
| Product shot + one-primary-device | Assigned CDN devices shot. Override rule. |
| Wearables FAQ (2) | Watch required? Fitbit real-time? |
| Dark IT band | Visual module break. Not a styled divider pretending to be a section. |
| SSO H2 + IdP / auth facts | SAML, named IdPs, not a toggle. Other auth as labels. |
| Roster + region | HRIS list with confirm-readiness. Four regions. 13+. VC single account. |
| SSO FAQ (1) | Self-serve? |
| Siblings + close | Security, Health Data Upload, Features hub. |

Skipped a customer-result band. Did not reprint Fitness GPS / 65 types.

**Visual:** `../styles/enterprise.css`, Noto Sans, coral / ink / mint, homepage nav/footer chrome. Features mega-menu locked IA. Current item: Integrations & SSO. Generated desk photograph in the model folder plus the assigned connected-devices shot.

## Copy deck

**Title:** Employee wellness platform integrations | Vantage Fit  
**Meta:** Connect Apple Health, Google Fit, Fitbit, and Garmin, plus SAML 2.0 SSO and HRIS roster sync. Two modules. Book a walkthrough.

**Eyebrow:** Features · Enterprise  
**H1:** What they wear. What IT already runs.  
**Lead:** Employee wellness platform integrations have two jobs. Devices put a Garmin run or a phone-only step day on the same participation number. SSO and HRIS put people on that surface without a second account.  
**Hero notes:** No wearable required · SAML 2.0 · 100+ organizations  
**CTAs:** Book a walkthrough · See wearables

**H2 (wearables):** Phone first. Watch optional.  
Apple Health / Google Fit / Fitbit (not real-time) / Garmin (webhook, 60-day tokens) / Samsung / 70+ via Apple Health.  
One primary device. Trusted source filtering. Cap not claimed.

**H2 (SSO):** SAML 2.0. Not a dashboard toggle.  
Named IdPs. Integration team. Confirm HRIS readiness. India, US, EU, or UAE. 13+ languages. Shared Vantage Circle account.

**FAQ**  
Wearables: Do employees need a wearable? / Is Fitbit real-time?  
SSO: Can we turn SSO on from the admin dashboard?

**Close H2:** Two modules. One participation number.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` shared physics + page 12
- `vc-os/vfit-os/specs/product/10-integrations/device-integrations.md`
- `vc-os/vfit-os/specs/product/00-platform/auth-login-signup.md`
- `vc-os/vfit-os/specs/10-integrations/garmin-integration.md` (60-day tokens, webhook, 50 MB)
- `vc-os/vfit-os/specs/10-integrations/fitbit-integration.md` (no webhook)
- `vc-os/vfit-os/specs/10-integrations/vantage-circle-ecosystem.md`
- `vantagefit-astro/content/en/help/employee/getting-started/do-i-need-a-wearable.md`
- `vantagefit-astro/content/en/help/employee/getting-started/how-does-step-syncing-work.md`
- `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-enable-sso.md`
- `vantagefit-astro/content/en/help/employee/getting-started/how-do-i-change-app-language.md` (13+ lock; 14-row table unused)

## Assumptions

- Wearables first, IT second. Jump chips let IT skip.
- Azure AD named as the lock names it. Help's "Entra ID" not used as the primary label.
- Health Connect omitted here (Fitness owns Android import). Android steps stay Google Fit.
- Help SSO "about 2 weeks" is not a committed SLA. Page says lead-time dependent.
- Generated desk photo is brand photography, not a product UI.

## Critic

Run after the mock. Failures found in draft and fixed:

- Two H2 modules with a dark IT band, not one blended narrative.
- Fitbit not called real-time. Garmin 60-day tokens stated.
- No Health Connect as Android step source.
- No BambooHR. SSO not self-serve.
- 13+, not 14. No 47+ activity types.
- Step cap not claimed active.
- Withings / Polar / Oura / Whoop absent.
- Org Wellness Score absent.
- No SOC2 / ISO / GDPR / HIPAA badges.
- `../styles/enterprise.css` linked. Product shot + photograph present.

**Pass.** Marketing copy in `<main>` is 715 words (450–750 band). Two H2 modules with a dark IT band. Fitbit not real-time. Garmin 60-day tokens. Visual check at 1440 and 390.
