# Workforce health insights page brief

## Page job

Help a US enterprise wellbeing leader understand how Vantage Fit turns program data into decisions. The page consolidates participation, challenge performance, activity trends, and related health-risk signals without implying that unlike measures should be collapsed into one magic score.

Intended URL: `/solutions/workforce-health-insights/`

Primary audience: CHRO, Benefits, Wellbeing, and program leaders

Primary CTA: **Book a demo**

Secondary CTA: **See pricing**

## Product truth used

- The current admin direction uses a four-rung workforce intelligence model: Adoption / Participation, Program / Challenge, Behavior / Activity, and Outcome / Health risk. Each measure remains independent and links to its own analysis surface. The former composite Wellness Score is retired.
- Participation analysis includes trends, department comparisons, steps, activity source, and team context.
- Challenge Performance is the evidence layer for program format, completion, exits, and incentive response. Challenge management stays on a separate operational surface.
- Activity Trends compares recent behavior with a personal longer-term baseline across Move, Mind, and Rest. Rest is treated as a healthy band, not a more-is-better metric.
- Health-risk analysis is scoped to a defined HRA cycle. It uses the assessed population as its denominator and does not model unassessed employees into the health result.
- HRA and lab insights are aggregate. Admins do not see individual lab reports or biomarker values. Private health-risk targeting returns a cohort count without exposing identities.
- Employee, challenge, leaderboard, transaction, and redemption reporting exists in the admin dashboard, with CSV export for supported reports. Health-risk privacy boundaries must not be weakened by the reporting story.

## Narrative and architecture

The hero is a connected decision path rather than a dashboard collage. It establishes the page thesis: HR can follow participation through program performance and behavior change to aggregate health risk, while keeping each measure honest.

1. **Hero: See where participation becomes progress.** A product-real intelligence rail shows the four independent lenses and makes the aggregate boundary visible in the same frame.
2. **Four questions, one program story.** Four concise cards explain what each lens answers and the appropriate action it supports.
3. **Read the pattern, not a pile of reports.** A high-fidelity admin view demonstrates scope controls, trends, challenge context, and assessed coverage. All example figures are clearly labeled illustrative.
4. **Move from signal to program decision.** A lean decision map connects concrete patterns to valid actions such as re-engagement, challenge redesign, and broader HRA participation.
5. **Privacy is part of the analysis.** A dark boundary section states what HR can see, what employees keep private, and how health cohorts are protected.
6. **Data in, data out, action.** A compact three-link chain connects HRA, insights, and rewards without repeating either sibling page.
7. **Objection handling and CTA.** Three FAQs cover data sources, individual health data, and reporting.

This is deliberately different from a challenge page. It has no format browser, leaderboard theater, or catalog. Its signature is the four-lens intelligence rail, which acts as a truthful visual model for the product.

## Full copy deck

### Hero

Eyebrow: Workforce health insights

Headline: **See where participation becomes progress.**

Body: Bring participation, challenge performance, activity trends, and aggregate health-risk signals into one connected view. Give HR the context to improve the program without turning employee health into a performance score.

Support line: Four independent lenses. One clearer program story.

Primary CTA: Book a demo

Secondary CTA: See pricing

Product rail labels:

- Adoption / Participation: Who is showing up?
- Program / Challenge: What is working?
- Behavior / Activity: What is changing?
- Outcome / Health risk: Where does the group need support?

Boundary note: Measures stay independent. Health-risk views use assessed, aggregate populations.

### Four questions section

Headline: **Start with the question HR needs answered.**

- **Are people participating?** Track program reach and participation patterns across the workforce.
- **Which challenges hold attention?** Compare challenge performance so the next program reflects what employees actually finish.
- **Is behavior shifting?** Read recent Move, Mind, and Rest patterns against longer-term personal baselines.
- **Where might support be needed?** Review HRA-cycle and lab-report prevalence in aggregate, with assessed coverage kept visible.

### Product view section

Eyebrow: One analysis workspace

Headline: **Keep context attached to every signal.**

Body: Scope the relevant lens, compare its trend, and see the program context behind it. Health-risk results always state the assessment cycle and coverage so missing responses are not mistaken for healthy outcomes.

Illustrative UI labels: Participation; Challenge performance; Activity trends; Health risk assessment; Latest HRA cycle; Assessed coverage; Department; Country; As of yesterday.

### Decision map

Headline: **Turn the pattern into the next program decision.**

- Participation is uneven → Focus communications where reach is low.
- A format loses people early → Adjust challenge design before the next launch.
- Recent activity shifts from baseline → Reinforce the behavior with a relevant program.
- HRA coverage is incomplete → Improve assessment participation before drawing conclusions.
- An aggregate risk area needs attention → Offer a private, relevant intervention without exposing identities.

### Privacy section

Eyebrow: Aggregate by design

Headline: **See the workforce pattern. Keep personal health personal.**

Body: Employees keep access to their own reports and biomarker details. HR sees organization-level prevalence and assessed coverage, not individual lab results.

Proof points:

- Health-risk views use the assessed population as the denominator.
- Individual lab reports and biomarker values are not exposed to admins.
- Private health-risk audiences return a count, not a list of names.
- Health insights are for program design, not employee performance decisions.

### Connected chain

Headline: **A clear path from input to action.**

- Data in: Health Risk Assessment establishes a voluntary baseline.
- Data out: Workforce health insights connect program and aggregate health signals.
- Action: Wellness rewards reinforce the behaviors your program asks for.

### FAQ

**What data can the insights bring together?** Participation, challenge performance, activity trends, HRA-cycle results, and related aggregate lab-risk signals where those features are enabled.

**Can HR see an employee's lab report?** No. Employees keep private access to their own reports and biomarker values. Admin health-risk views are aggregate.

**Can teams export data?** Supported admin reports can be filtered and exported as CSV. Health-risk outputs retain their aggregate privacy boundary.

### Final CTA

Headline: **Give every wellness decision its context.**

Body: See how Vantage Fit connects participation, program performance, activity, and aggregate health risk for your workforce.

Buttons: Book a demo · See pricing

## Visual direction

- Shared system: `styles/enterprise.css`, Noto Sans, Vantage Fit coral, mint, ink, canvas, radii, shadows, navigation, buttons, and footer.
- Page-specific palette: signal coral `#F15162`, participation mint `#41D8B4`, assessment amber `#F6B93B`, ink `#29294C`, cloud `#F1F1F6`, paper `#FFFFFF`.
- Signature: a wide four-lens intelligence rail in the hero. It visually moves from participation to aggregate health risk but explicitly prevents the measures from becoming a composite score.
- Aesthetic risk: the primary hero artifact is a horizontal causal model instead of a standard floating analytics screenshot. It fits the subject because the product's value is the connection between signals.
- Responsive behavior: the rail becomes a vertical path on small screens; all grids collapse to one column; navigation condenses; touch targets remain at least 44px.
- Accessibility: semantic headings and landmarks, visible focus states, text labels in addition to color, reduced-motion support, and no chart meaning encoded by color alone.

## Sources

No external statistics or customer outcome claims are used. Interface figures in the mock are labeled illustrative.

- `../../../vc-dashboard-design/docs/modules/wellness.md`, current Workforce Intelligence contract and the four independent analysis lenses.
- `../../../vc-dashboard-design/docs/superpowers/specs/2026-08-09-wellness-admin-dashboard-IMPLEMENTATION.md`, current participation, challenge, activity, HRA, and privacy direction.
- `../../../vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md`, production ground truth and known honesty constraints.
- `../../../vc-os/vfit-os/specs/product/03-health-wellness/workforce-health.md`, aggregate lab-report intelligence and privacy rules.
- `../../../vc-os/vfit-os/specs/09-admin-platform/reports-analytics.md`, report and export capabilities.
- `../../../vantagefit-astro/content/en/help/admin/reports/admin-what-reports-are-available.md`, current admin report catalog.
- `../../../vantagefit-astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md`, workforce health workflow and aggregate lab-data boundary.

## Metadata draft

Meta title: **Workforce Health Insights for HR | Vantage Fit**

Meta description: **Connect participation, challenge performance, activity trends, and aggregate health-risk signals in one workforce wellness analysis experience.**

## Solutions IA fit

This page owns **Data out** in the Workforce health & rewards column. It receives baseline context from Health Risk Assessment and points forward to Wellness rewards program as an action layer. Those relationships appear once, near the end, so the page still stands on its own as the measurement story.
