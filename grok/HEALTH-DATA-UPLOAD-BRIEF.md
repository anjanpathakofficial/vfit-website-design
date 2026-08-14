# Health Data Upload

**URL:** `/features/health-data-upload/`  
**Mock:** `vantage-fit-health-data-upload-v1.html`  
**Angle:** Turn a lab report into a private, personal plan. Lead with availability.

## Page job

Prove the lab-report module is real, private, and **not generally available**. First screen must say annual / whitelist / selected organisations. Not a Security reprint. Not a generic corporate-wellness keyword page.

**Reader:** HR / benefits at annual health-check enterprises.  
**Primary CTA:** Book a walkthrough. **Secondary:** See a private report (hero jump).

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Availability (lock + WORKFORCE-HEALTH-001):** Annual / premium, whitelist. Enabled per company by the account manager. Currently limited to selected organisations. Hidden in **Lite Mode**.
- **Upload (lock + OS lab-reports + help):** PDF, JPG, or PNG (images → PDF). iOS, Android, or **web**. PDF max **30 MB**. JPEG / PNG only for images. No manual typing.
- **AI pipeline (lock + OS):** 5 stages: PDF extract → test-name match → insight → summary viz → recommendations. **Do not name the vendor.** Suggestions are general wellness guidance, **not medical advice.** Recommended Actions (admin) are rule-based and not this page.
- **Coverage (lock):** **~14 health areas across ~104 biomarkers** (VERIFY). Areas: diabetes / metabolic, heart, liver, kidney, thyroid, blood health / anaemia, Vitamin D / B12, inflammation.
- **Risk (lock + OS):** Low = in range. Medium = ≤20% from nearest bound. High = >20%, or critical / alert / abnormal on the source. Vitamin D has its own bands (deficient / insufficient / sufficient / toxic).
- **Employee:** Lab Reports history. Permanent self-delete.
- **HR:** **Org-level prevalence only.** Not sliced by department / team / location. No screen or export exposes an individual’s report.
- **Targeted challenge:** Count only + privacy disclaimer. Client-rollout status contradictory. Phrase as **for Workforce-Health-enabled companies**. Not generally shipped.
- **Bulk SFTP:** One company (355). **Do not market as generally available.**
- **Proof:** No named-client stat. Optional Q2 2025 AI analysis launch. 100+ organizations as generic trust only.
- **Dashboard shot:** Caption **org-level / sample** if numbers are visible. Never a named client. Never Org Wellness Score shots.

### Conflicts left unresolved (not silently fixed)

1. Help upload article says 100+ biomarkers. Lock: ~104 VERIFY. Page uses ~104, marked VERIFY in the figcap.
2. Help Workforce Health still describes Org Wellness Score and employee-level drill-down. Lock: retired, and HR never sees a person. Absent here.
3. Risk-targeted challenges: capability live in one spec; roadmap says Backlog / used internally. Page hedges.
4. OS lab-reports marketing brief names ChatGPT and sample prevalence (Diabetes 65%, etc.). Vendor name omitted. Sample figures, if shown, labeled sample.

## Why this structure

Availability is the hero, not a footnote. Product shots do the extraction and org-prevalence work. Photograph is a sealed envelope, no readable values.

| Section | Job |
|---|---|
| Hero + availability flag + photo | First screen: annual / whitelist / selected orgs. |
| Upload facts | PDF / JPG / PNG, web, 30 MB. Lite Mode hidden. |
| 5-stage pipeline + mobile shot | AI, no vendor, not medical advice. |
| Coverage + risk bands | ~104 / ~14. Vitamin D bands. VERIFY. |
| Employee vs HR + desktop shot | Private history vs org prevalence. Sample caption. |
| What is not generally available | Bulk SFTP = one company. Risk-targeted challenges hedged. |
| 3 FAQs + siblings | HR visibility, bulk, Lite Mode. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** Same chrome. Features mega-menu current: Health data upload. Assigned lab-summary mobile shot + biomarker desktop shot. Generated envelope photograph.

## Copy deck

**Title:** Workforce health risk analytics | Vantage Fit  
**Meta:** Upload a lab PDF for a private biomarker plan. Annual, whitelist, selected organisations. Org prevalence only. Book a walkthrough.

**Eyebrow:** Features · Enterprise  
**Availability (first screen):** Annual. Whitelist. Selected organisations.  
**H1:** A lab report. A private plan.  
**Lead:** Available for annual partners running health check-up programs. Enabled per company by the account manager. Currently limited to selected organisations.  
**Hero notes:** PDF, JPG, PNG · 30 MB · Hidden in Lite Mode  
**CTAs:** Book a walkthrough · See a private report

**H2:** Upload on the phone or on the web.  
PDF / JPG / PNG. Web works. 30 MB. No typing.

**H2:** Five stages. No vendor name.  
Extract, match, insight, summary, recommendations. Not medical advice.

**H2:** About 104 biomarkers. Fourteen areas.  
Risk bands including Vitamin D. VERIFY on the count.

**H2:** You see the report. HR sees a percentage.  
Org prevalence only. Count-only targeting for Workforce-Health-enabled companies.

**H2:** What this page will not sell.  
Bulk SFTP is one company. Not a general offering.

**FAQ**  
1. Can HR see an employee’s lab values?  
2. Can we bulk-load reports over SFTP?  
3. Does Lite Mode include this?

**Close H2:** Ask whether your org is on the list.

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` shared physics + page 14
- `vc-os/vfit-os/specs/product/03-health-wellness/workforce-health.md`
- `vc-os/vfit-os/specs/03-health-wellness/lab-reports-biomarkers.md` (pipeline, 30 MB, company 355; vendor name unused)
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-upload-lab-reports.md`
- `vantagefit-astro/content/en/help/employee/getting-started/what-is-lite-mode.md` (gate only)

## Assumptions

- Q2 2025 AI analysis line used once, as optional recency.
- Dashboard numbers on the CDN shot are labeled sample / org-level.
- Generated envelope photo shows no PHI.
- Security already owns BAA wording. This page restates the employee privacy promise, not the BAA essay.

## Critic

Run after the mock. Failures found in draft and fixed:

- Availability is in the first screen, not a footer note.
- No OpenAI / ChatGPT.
- Bulk SFTP not marketed as generally available.
- Risk-targeted challenges hedged.
- No department slices. No individual lab values. No named-client prevalence.
- Not medical advice. Not HIPAA-compliant platform.
- Org Wellness Score absent.
- Lite Mode hidden.
- `../styles/enterprise.css` linked. Two product shots + photograph present.

**Pass.** Marketing copy in `<main>` is 566 words. Annual / whitelist flag is in the first screen. Bulk SFTP not sold as general. Visual check at 1440 and 390.
