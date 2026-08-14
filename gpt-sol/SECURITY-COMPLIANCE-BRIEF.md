# Security & Compliance

## Page job

Give an IT or security reviewer a fast, factual review surface for tenant isolation, residency, authentication behavior, employee privacy, AI boundaries, deletion, and the narrowly scoped lab-pipeline agreement. The page should help HR explain why aggregate participation is usable without exposing individual health.

## Research takeaways

- Each company is an isolated tenant and company ID is carried through the platform. Health-risk and lab queries are company-scoped.
- Vantage Fit operates four regional instances: India, US, EU, and UAE. A region is selected at onboarding. Changing it later requires migration.
- Authentication facts are precise and flow-specific: five failed password attempts trigger lockout; reset links are single-use for one hour; reset passwords require eight characters while in-app changes require six; OTP lasts ten minutes; mobile uses TrustKit SSL pinning; non-mobile web and admin use captcha.
- HR can see participation and aggregate organization or department metrics. HR cannot see an employee’s health profile, HRA answers or risk category, mood, food diary, or lab and biomarker values.
- Health-risk audiences return a count with the privacy message, “The list of users is not displayed to protect individual privacy.” They do not return a name list.
- Leadership Insights uses aggregated signal buckets and sends no PII to the internal ML API. It is read-only.
- Account deletion hashes name and email, clears tokens, and retains historical activity or transaction records for reporting. Availability is company-configurable.
- BAA provisions for HIPAA compliance apply only to the lab-report pipeline. The accurate page-level language is “HIPAA-guideline aligned,” not a platform-wide compliance claim.

## Structure and visual rationale

The hero behaves like a short review memo: a four-line fact ledger sits beside restrained due-diligence photography. The residency section shows four peer instances rather than implying dedicated infrastructure. The authentication section uses an HTML control table with exact values. The privacy section pairs the required analytics screenshot with a large “HR sees / HR never sees” boundary. AI, deletion, and lab-pipeline scope follow as three contained review notes.

The page uses Noto Sans and the existing ink, canvas, coral, and mint tokens from `enterprise.css`. The signature is the full-width privacy aperture: a crowd-shaped aggregate panel on the HR side and a closed employee-health panel on the other. It encodes the product boundary without certification badges.

## Copy deck

- **H1:** Data your security team can sign off.
- **Lead:** Review where company data lives, how access is challenged, and the line HR cannot cross into individual health.
- **Key heads:** Four regional instances. One onboarding decision. / Exact controls, not broad assurances. / HR sees the crowd, not the person.
- **Primary CTA:** Talk to security
- **Secondary CTA:** Review the facts

## Availability language

- Region: standard at onboarding.
- SAML 2.0: configured by the Vantage Fit integration team on all tiers.
- Health Insights: whitelist only.
- BAA provisions: lab-report pipeline only.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md`, Security & Compliance facts lock
- `vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md`
- `vantagefit-astro/content/en/help/employee/getting-started/` privacy, password, OTP, lockout, and deletion articles
- `vfit-os/specs/product/00-platform/auth-login-signup.md`
- `vfit-os/specs/product/03-health-wellness/workforce-health.md`
- `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`
- `vfit-os/specs/10-integrations/vantage-circle-ecosystem.md`

## Search metadata

- **Title:** Employee wellness platform data privacy | Vantage Fit
- **Description:** Review Vantage Fit regional instances, company isolation, authentication controls, aggregate-only HR health views, and lab-pipeline BAA scope.

## Critic result

Pass. No certification badges, encryption specifications, audit logs, or blanket compliance claim are used. The page says four regional instances, preserves the two password-length flows, limits health-risk output to count only, keeps Leadership Insights free of PII, and scopes BAA provisions to the lab-report pipeline.
