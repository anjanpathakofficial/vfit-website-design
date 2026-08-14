# Integrations & SSO

## Page job

Prove two separate enterprise capabilities on one URL: employees can bring a supported phone or wearable into the same participation surface, while IT can place the right employees on that surface through existing identity and workforce systems. The audience shifts at the module break from HR and benefits to IT and implementation teams.

## Research takeaways

- A wearable is optional. Apple Health is the iPhone step source and Google Fit is the Android default. Health Connect can import other Android health data, but it is not described as the Android step source.
- The app uses one primary step source. Fitbit and Garmin take priority over Apple Health or Google Fit. Trusted-source filtering is live; a daily step cap is not.
- Fitbit is OAuth-based and updates on app open or on demand. It can bring in up to 30 days of history, but it is not real-time.
- Garmin is the only real-time connection. It uses a webhook, supports daily and activity summaries plus GPS routes, accepts payloads up to 50 MB, and requires reconnection when its token expires after 60 days.
- SSO is SAML 2.0 and integration-led. HRIS readiness and lead time must be confirmed. Region is chosen from India, US, EU, or UAE at onboarding and later change requires migration.
- Vantage Circle and Vantage Fit share user, company, and authentication context. Employees can enter Vantage Fit from R&R without creating another account when their employer enables it.

## Structure and visual rationale

The hero frames the page as two systems feeding one participation surface. A compact handoff rail visually names the sequence without blending the two buying stories. Module A uses the required connected-devices product shot, a workplace movement photograph, and a precise source matrix. A full-width dark transfer band creates a hard persona and topic break. Module B then presents SSO, provisioning, region, and language as an implementation console rather than another device catalog. The closing navigation links both enterprise siblings and the Features hub.

The page uses the shared `enterprise.css` palette and Noto Sans. No token or brand is replaced. The signature device is the hard-break transfer band labeled “Employee signal boundary” and “IT identity boundary,” which makes the two-module architecture unmistakable.

## Copy deck

- **H1:** What employees wear. What IT already runs.
- **Lead:** Bring phone and wearable activity into the same participation number, then use your identity and workforce systems to put the right employees on it.
- **Module A:** Device activity, without a device mandate.
- **Module B:** Identity and workforce access, set up with your IT team.
- **Primary CTA:** Book a walkthrough
- **Secondary CTA:** Review implementation paths

## Availability language

- Wearable connection: standard and employee self-serve.
- SAML, HRIS, and SFTP: configured with the Vantage Fit integration team and dependent on lead time.
- Employee-ID login and SMS OTP: whitelist only.
- Region: selected at onboarding.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md`, Integrations & SSO facts lock
- `vantagefit-astro/content/en/help/employee/getting-started/` device connection and source articles
- `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-enable-sso.md`
- `vfit-os/specs/10-integrations/fitbit-integration.md`
- `vfit-os/specs/10-integrations/garmin-integration.md`
- `vfit-os/specs/10-integrations/vantage-circle-ecosystem.md`
- `vfit-os/specs/product/10-integrations/device-integrations.md`
- `vfit-os/specs/product/00-platform/auth-login-signup.md`

## Search metadata

- **Title:** Employee wellness platform integrations and SSO | Vantage Fit
- **Description:** Connect Apple Health, Google Fit, Fitbit, Garmin, and supported devices, then plan SAML 2.0 SSO and HRIS provisioning with Vantage Fit.

## Critic result

Pass. The two H2 modules are separated structurally and visually. The page does not call Fitbit real-time, name Health Connect as the Android step source, claim self-serve SSO, add BambooHR, or claim active step normalization. Every availability boundary is explicit, and the required product shot and workplace photograph are assigned.
