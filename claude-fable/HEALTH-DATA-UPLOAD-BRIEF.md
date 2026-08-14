# Health Data Upload — build brief

**Page:** `/features/health-data-upload/`
**Mock:** `vantage-fit-health-data-upload-v1.html`
**Group:** D · Enterprise (page 3 of 3)
**Angle:** Turn a lab report into a private, personal plan. Lead with availability.

---

## Research takeaways

1. **Availability is the story, not a footnote.** This is the most gated capability of the three: annual and premium partners running health check-up programs, enabled per company by the account manager, currently limited to selected organisations. A buyer who reads the whole page and only then learns they cannot have it has been wasted.
2. **Formats differ between help and spec.** The help article says PDF. The spec and the facts lock allow PDF, JPEG and PNG, with images converted to PDF, 30 MB maximum, and web as a valid upload surface. Lock wins.
3. **Five stages, no vendor name.** Extract, match test names against the biomarker database, generate insight, summarise, recommend (`specs/03-health-wellness/lab-reports-biomarkers.md`). The extraction vendor is named in the spec and is deliberately not named on the page.
4. **Coverage is a VERIFY number.** Help says 100+ biomarkers, the lock says about 104 across about 14 areas and marks it VERIFY. The page uses "about" and carries the marker rather than rounding a soft number into a hard one.
5. **Risk-targeted challenges are contradictory in our own documentation.** One spec says usable, its roadmap says backlog and internally used. The page hedges in public and shows the VERIFY marker rather than quietly picking a side.
6. **Bulk SFTP is one company.** It reads as an enterprise capability in the spec's positioning section, but the implementation is admin-only for VFit admin plus company 355. Marketing it as generally available would be the single easiest way to fail this page.
7. **HR gets org-level prevalence only.** The help article mentions departmental patterns; the lock restricts lab-risk reporting to organisation level. The page states the restriction explicitly, which is stronger than staying silent.

## Why this structure

- **The gate sits in the hero copy column, above the buttons.** Not a badge, not a footnote, not a tier table at the bottom. Three lines: who it is for, who switches it on, how many have it. A time-poor buyer learns their answer in the first screen.
- The rest of the page runs employee first, then HR, because that is the privacy argument: the employee sees values, HR sees prevalence, and nothing crosses.
- **Two product shots do opposite jobs.** The mobile Health Summary shows what an employee sees, captioned as employee-only and sample. The workforce dashboard shows what HR sees, captioned as org-level and sample. Putting them on the same page, labelled, is the proof.
- The VERIFY marker appears on the page itself, not only in this brief, for biomarker count and for risk-targeted challenge rollout.
- Lab pipeline detail lives here. Security carries the BAA and aggregate-only line and links across.

## Copy deck (key lines)

- **H1:** Turn a lab report into a private, personal plan.
- **Gate label:** Limited availability.
- **S2 H2:** Upload the PDF. Type nothing.
- **S3 H2:** About 104 biomarkers, about 14 health areas.
- **S4 H2:** HR sees prevalence. Nobody sees a person.
- **S5 H2:** How reports get in.
- **Closer:** Find out whether your plan includes it.
- **Primary CTA:** Book a walkthrough.

## Images

| Asset | Role |
|---|---|
| CDN `vantage-fit-ai-lab-report-summary-mobile.png` | The employee view. Captioned employee-only and sample |
| CDN `vantage-fit-workforce-biomarker-dashboard-desktop.png` | The HR view. Captioned org-level and sample, never a named client |
| `../styled-homepage/card-invite.jpg` | Photograph, an annual check-up program |
| `../styled-homepage/logo.png` / `logo-white.png` | Nav and footer wordmark |

The mobile shot does contain biomarker values. It is a sample employee self-view, which is the feature, and the caption says so. No HR-facing screen on this page shows an individual, and no health-risk name list appears anywhere.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` (facts lock)
- `vantagefit-astro`: `employee/health-tracking/how-do-i-upload-lab-reports.md`, `admin/workforce-health/admin-what-is-workforce-health.md`
- `vfit-os`: `specs/03-health-wellness/lab-reports-biomarkers.md`
- Design system: `styles/enterprise.css`, `grok/vantage-fit-admin-dashboard-analytics-v1.html`

## Meta

- **Title:** Workforce health risk analytics from lab reports | Vantage Fit
- **Description:** Employees upload a lab report as PDF, JPG or PNG. AI extraction covers about 104 biomarkers. HR sees org-level prevalence only. Annual and whitelist.

## Critic result

| Check | Result |
|---|---|
| `../styles/enterprise.css` linked, no new brand | Pass |
| Annual, whitelist and limited availability in the first screen | Yes. Gate box above the hero buttons |
| Two product screenshots plus one photograph | Pass |
| Marketing copy outside chrome | ~700 words |
| Vendor named | No. Five stages described, no vendor |
| Biomarker count stated as hard fact | No. "About 104", VERIFY marker on the page |
| Department, team or location slices of lab-risk data | Explicitly denied in the copy |
| Bulk SFTP marketed as generally available | No. Stated as one company, with a do-not-plan-on-it line |
| Risk-targeted challenges asserted as shipped | No. Hedged with the VERIFY marker and the contradiction named |
| Sample prevalence presented as a client result | No. Screenshot captioned org-level and sample |
| Individual lab values on an HR screen | None. The only values shown are in the employee's own view, labelled sample |
| Medical-advice or diagnostic framing | No. General wellness guidance, disclaimer repeated |
| 100% extraction accuracy | Not claimed |
| HIPAA-compliant platform | Not claimed. BAA scope only, linked to Security |
| Lite Mode | Stated as hiding the feature |
| Em-dashes, exclamation marks, "Learn more" | None |
