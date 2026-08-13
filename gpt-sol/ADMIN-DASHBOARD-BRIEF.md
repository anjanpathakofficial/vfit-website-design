# Admin Dashboard & Analytics brief

## Page decision

**Job:** Prove that Vantage Fit gives HR one operational participation view, with enough detail to inspect the signal and enough export control to take it into a leadership review.

**Structure:** A short product-first page: real dashboard in the hero, compact Overview proof, aggregate insights beside workplace photography, reports and tier access, then one CTA. The signature is the participation-rate pin attached to the real product screenshot. It makes the locked through-line visible without turning the page into an essay or a challenge-program story.

## Research takeaways

- The locked source of truth is `FEATURES-HR-BRIEFS.md`, platform rules plus page 8. It defines Participation Rate as the north-star metric and retires Org Wellness Score completely.
- `vc-os/vfit-os/specs/09-admin-platform/admin-dashboard.md` and `reports-analytics.md` support filtered reporting, CSV leaderboards, campaign PDF certificates, and the 100+ organizations proof point.
- Vantage Fit help docs support Employee, Transaction, Redemption, Leaderboard, and League report behavior, plus automatic per-campaign certificates. They also contain stale Org Wellness Score and individual-level health language. The page follows the facts lock and newer dashboard documentation, so none of that stale material ships.
- `vc-dashboard-design/docs/modules/wellness.md` confirms the newer direction: participation is the spine, the composite score is retired, and health analytics remain aggregate.
- The hero uses the required Vantage Fit admin screenshot. The workplace photograph is `styled-homepage/card-measure-generic.jpg`. The four KPI values and deltas in the compact UI fragment are labeled illustrative and are not presented as customer results.

## Copy deck

### Hero

**Eyebrow:** Admin dashboard and analytics

**H1:** Participation. No spreadsheet.

**Lead:** See what employees logged, where participation moved, and what deserves attention in one corporate wellness dashboard.

**Primary CTA:** Book a walkthrough

**Secondary CTA:** See the dashboard

**Proof notes:** Aggregate HR view · 100+ organizations · CSV and PDF outputs

### Overview

**Headline:** Four numbers. One participation rate.

**Copy:** Track reach, active use, rewards spend converted from SOLI to your admin currency, and participation. Steps, workouts, nutrition, hydration, mindfulness, and other employee logs feed the same participation surface. Use preset or custom dates, then filter by country, department, age group, or gender.

**UI labels:** Enrolled users · Active users · Incentivization · Participation rate · 7d · 30d · Quarter · Year · Custom · Country · Department · Age group · Gender

**At a glance:** Avg steps · Active minutes · Mindful minutes · Avg sleep

### Insights and actions

**Headline:** Know what changed. Know where to look next.

**Copy:** The employee wellness analytics dashboard separates interpretation from action, so every recommendation stays honest about what the product does. The result is a reviewable signal, not an automatic verdict.

**Leadership Insights:** AI summarizes aggregated buckets into Key Insights and Focus Areas. No PII is sent, and the observations do not predict outcomes or change program settings.

**Recommended Actions:** Up to five priority-ordered shortcuts point admins to relevant work, such as viewing inactive employees or opening a nudge. They are links, not automations.

**Privacy rule:** HR sees aggregate participation, never an individual health profile.

### Reports and access

**Headline:** Export the detail when the meeting needs it.

**Copy:** Move from the overview to filtered CSV files, challenge results, reward records, or a per-campaign certificate PDF. Keep the selected detail for finance, recognition, and program follow-up.

**Outputs:** Employee report · Leaderboard · Transaction report · Redemption report · Annual-gated League report · Campaign certificate PDF

**Tier copy:** Standard includes Overview, filters, Recommended Actions, core reports, and certificates. Wellness Leagues is annual and account-managed. Health Insights requires the narrower whitelist approval and is not pitched as a plain annual entitlement.

### Final CTA

**Headline:** Take the participation number upstairs.

**Copy:** Walk through the overview, filters, aggregate insights, and reports with your own HR questions in mind, instead of starting with a spreadsheet.

**CTA:** Book a walkthrough

## Metadata

**Title:** Corporate wellness dashboard and analytics | Vantage Fit

**Description:** See participation, trends, aggregate insights, and exportable reports in the Vantage Fit corporate wellness dashboard.

Primary keyword appears in the title and opener. The secondary phrase, employee wellness analytics dashboard, appears once in the insights section.

## Proof and sources

- **100+ organizations:** `FEATURES-HR-BRIEFS.md`, page 8; `vc-os/vfit-os/specs/09-admin-platform/admin-dashboard.md`
- **Report types and CSV behavior:** `FEATURES-HR-BRIEFS.md`, page 8; `vantagefit-astro/content/en/help/admin/reports/admin-what-reports-are-available.md`; `admin-how-do-i-view-employee-reports.md`
- **Certificate generation:** `FEATURES-HR-BRIEFS.md`, page 8; `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-configure-certificates.md`; `vc-os/vfit-os/specs/09-admin-platform/reports-analytics.md`
- **Leadership Insights, Recommended Actions, tier gates, privacy rule:** `FEATURES-HR-BRIEFS.md`, page 8
- No customer quote or program-result statistic is used.

## Critic result

**Pass.** The page links the shared stylesheet, uses Noto Sans, Vantage Fit logos, the required real product screenshot, and a real photograph. It stays feature-led, marks sample KPI figures illustrative, labels AI and rule-based surfaces correctly, keeps HR aggregate-only, exposes tier gates, and omits the retired score and Score Report. The first render was tightened by reducing the H1 to two lines, preserving the product shot's real aspect ratio on mobile, and loading the workplace photograph eagerly so it is present in full-page renders.
