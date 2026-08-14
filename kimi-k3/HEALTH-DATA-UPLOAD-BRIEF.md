# Health Data Upload — brief

URL: `/features/health-data-upload/` · Mock: `vantage-fit-health-data-upload-v1.html`

## Research takeaways

- Facts lock: `FEATURES-ENTERPRISE-BRIEFS.md` §14. This page owns lab upload, AI extraction, biomarkers, risk bands, org-level prevalence, count-only targeting, and the whitelist / annual tier flag.
- Availability leads the first screen: annual / premium, whitelist; for annual partners running health check-up programs; enabled per company by the account manager; currently limited to selected organisations. Most buyers will not get this module, and the page says so.
- Upload facts: PDF, JPG, or PNG (images converted to PDF) on iOS, Android, or web; PDF max 30 MB; employee self-upload once enabled.
- AI extraction, 5 stages: PDF extract → test-name match → insight → summary visualization → recommendations. No manual typing. No vendor named. Q2 2025 launch with AI analysis used as a light recency line.
- Coverage: ~14 health areas across ~104 biomarkers (kept as "about 104", VERIFY per lock). Areas listed: diabetes / metabolic, heart, liver, kidney, thyroid, blood health / anaemia, Vitamin D / B12, inflammation.
- Risk bands: low (in range), medium (within 20% of the nearest bound), high (beyond 20%, or critical / alert / abnormal on the source report). Vitamin D has its own bands: deficient / insufficient / sufficient / toxic.
- Privacy: employee Lab Reports history with permanent self-delete; hidden entirely in Lite Mode; suggestions are general wellness guidance, not medical advice, disclaimer stays.
- HR: org-level prevalence only ("% of workforce flagged at risk" per health area). No department / team / location slices. Risk-cohort targeting is count only with the privacy disclaimer. Risk-targeted challenges hedged to "for Workforce-Health-enabled companies" (rollout status contradictory in specs). Bulk SFTP intake exists for one company and is not marketed as available.
- BAA: one line, scoped to this pipeline, cross-linked to Security & Compliance.

## Why this structure

Narrow-ICP page. The hero carries an availability panel (not buried fine print), then the employee story (upload → 5-stage extraction → risk bands), then the privacy contract, then the HR aggregate view with the biomarker dashboard shot captioned as org-level sample data. The honest limits (no department slices, SFTP is a one-company arrangement, not medical advice) are stated as product rules, which is the page's credibility play.

Sections: hero (mobile lab-summary shot + availability panel) → upload and 5-stage extraction → coverage and risk bands → privacy (self-delete, Lite Mode, not medical advice) → HR org-level view (biomarker dashboard + photo) → intake and limits → FAQ (3) → siblings → CTA.

## Copy deck (condensed)

- H1: "Turn a lab report into a private, personal plan."
- H2s: "Upload a PDF. Skip the typing." / "About 104 biomarkers, banded by risk." / "Private to the employee, by design." / "HR gets prevalence, never a person."
- Availability panel: "Annual partner module. Enabled per company by your account manager. Currently limited to selected organisations running health check-up programs."
- CTAs: "Book a walkthrough" (primary), "Check availability" (secondary, anchors to availability).

## Sources

- `FEATURES-ENTERPRISE-BRIEFS.md` §14, shared physics, live contradictions.
- `FEATURES-ENTERPRISE-PROMPT.md` (images: AI lab-report summary mobile + workforce biomarker dashboard desktop, captioned org-level / sample).

## Meta

- Title: `Workforce health risk analytics from lab reports | Vantage Fit`
- Description: `Employees upload lab reports as PDF or image; AI extraction bands about 104 biomarkers by risk. HR sees org-level prevalence only. Annual, whitelist module.`

## Critic result

- Annual / whitelist / limited availability in the first screen. No vendor named. No 100% accuracy claim. Not-medical-advice disclaimer present. ~104 kept approximate. No department / team / location slices. Bulk SFTP described as a one-company arrangement, not generally available. Risk-targeted challenges hedged to Workforce-Health-enabled companies. Sample dashboard captioned as org-level sample, no individual values or name lists. No Org Wellness Score. Two CDN product shots + one photograph. Copy ≈ 640 words. Pass.
