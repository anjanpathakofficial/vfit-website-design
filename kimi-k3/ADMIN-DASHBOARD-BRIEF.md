# Admin Dashboard & Analytics — page brief

**Page:** `/features/admin-dashboard-analytics/` · **Mock:** `vantage-fit-admin-dashboard-analytics-v1.html` · **Angle:** the participation number, without the spreadsheet.

## Research takeaways

Facts lock (`FEATURES-HR-BRIEFS.md` page 8) checked against all three sibling repos. What the research added (used for authentic UI labels, not new claims):

- Exact KPI card labels are title case in product: `Enrolled Users` / `Active Users` / `Incentivization` / `Participation Rate`, delta default `vs Prev Quarter`, one sparkline each. Incentivization is SOLI-converted to the admin's currency. Source: `vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md` §1d, `vc-os/vfit-os/specs/product/09-admin-platform/admin-dashboard.md`.
- Production freshness caption "figures are as of yesterday" (reads snap to endDate minus one day). Used in the filter row.
- Leadership Insights carries an `AI-generated` badge with `Key Insights` / `Focus Areas` columns; the ML call sends signal buckets only, no PII. Matches the lock.
- Recommended Actions subheader is "System suggested next steps"; exact example labels include "View Inactive Employees (92 users inactive for 30+ days)", "Nudge Inactive Users", "View Wellness Leagues".
- Locked-state string for annual-gated surfaces is "Contact Account Manager". Reflected in the League Report card and FAQ.
- Report names per help doc `content/en/help/admin/reports/admin-what-reports-are-available.md`: Employee Report, Transaction Report, Redemption Report, Challenge Leaderboard (always available); League Report (annual-gated). All CSV, filters applied before export.
- At a Glance production units: `/day`, `min/day`, `hr / mins`. Adopted for the sample cards.
- Certificates: automated per-campaign PDF, confirmed (`POST /v1/campaign/sendCertificate`, S3-stored PDFs).

### Org Wellness Score: retired

The prompt (this revision) retires Org Wellness Score: do not show it, gate it, or explain it. The facts lock page 8 and the help / OS sources still describe it (weights 20/30/30/20, annual-gated, Wellness Score Report); per the prompt those are stale. The page therefore has **no score surface of any kind**: no Org Wellness Score, no composite score, no individual wellness scores, no Score Report, and no locked-teaser card. The research also supports this: `vc-dashboard-design` records a 2026-08-04 internal decision retiring the composite Wellness Score from the Overview prototype, and ground truth flags its "Industry Benchmark" as a hardcoded constant. Flagged here because the facts lock file itself has not been updated yet.

### Other conflicts flagged (facts lock / prompt preferred)

1. Recommended Actions: lock and product spec say max 5; production code ranks up to 10. Page says "never more than five".
2. Date presets: lock / help / spec say 7d/30d/quarter/year/custom; production backend has a 13-preset canon. Page uses the documented five.
3. At a Glance: lock / spec show 4 cards; production shows up to 5 (adds Active Calories). Page shows 4.

### Deliberate omissions

- Health Insights: whitelist-narrower than "any annual plan" (lock flag). Not pitched anywhere on the page.
- Wipro 3X: VERIFY-flagged against dashboard attribution. Left off; Brazosport carries the proof strip alone.

## Why this structure

Feature page, not a Solutions page: the reader should recognize the product in the first screen and finish in under a minute. Order follows how an admin meets the product:

1. **Hero** — the real dashboard product shot (CDN) with two floating chips; H1 is the angle; CTAs Book a walkthrough / See the dashboard.
2. **Four numbers. One participation rate.** — the 4 KPI cards as a compact UI fragment plus the filter row (must-cover: KPIs, deltas, sparklines, presets, dimensions, SOLI note).
3. **Leadership Insights + Recommended Actions** — paired cards, each tagged honestly (`AI-generated · aggregated buckets only · read-only` vs `Rule-based · links, not automations`).
4. **At a Glance** — the four habit metrics with sparkline and trend, plus the aggregate-only reminder.
5. **Reports & exports** — the absorbed reports, one line each, the annual gate flagged on the League Report card; certificates as the sixth card.
6. **Privacy band** — the buying objection answered with the product rule (aggregate only, no PII to the ML API, HIPAA-guideline aligned), with the measure photograph.
7. **Proof strip** — Brazosport only, labeled to Fit Wars (May 2024).
8. **FAQ (3)** — individual data, annual gates, AI behavior. The real rollout objections.
9. **Sibling links + final CTA** — the other three HR pages and Compare the tiers.

Nav chrome is copied from `styled-homepage` with the Features → For HR column rebuilt to the locked IA (this page marked current via `aria-current`) and the Enterprise column scrubbed of SOC 2 / GDPR / ISO claims. The footer certification strip was replaced with allowed claims (aggregate-only, 13+ languages, EU data residency).

## Copy deck (final, as shipped)

- **Title:** Admin Dashboard & Analytics, a Corporate Wellness Dashboard | Vantage Fit
- **Meta description:** Vantage Fit's corporate wellness dashboard turns every employee log into one participation rate, with KPI trends, AI leadership insights, CSV reports, and aggregate-only privacy.
- **H1:** The participation number, without the spreadsheet.
- **Lead:** Every step, workout, logged meal, and mindful minute your employees record lands in one corporate wellness dashboard, as a single participation rate you can take to leadership.
- Section heads: Four numbers. One participation rate. · Reads the dashboard, so you do not have to. · The habits behind the number. · Board-ready exports, no assembly required. · Aggregate only. Never a person. · What a measured campaign looks like. · Rollout questions HR asks first · The rest of the HR toolkit · See your participation number.
- Primary keyword `corporate wellness dashboard` in title, meta, and hero lead; secondary `employee wellness analytics dashboard` intentionally left to adjacent phrasing ("participation analytics" appears in nav) to avoid stuffing.
- Marketing copy: ~640 words outside nav, footer, and product-mock labels (budget 450–750).

## Sources for stats / quotes

- **100+ organizations** — approved aggregate trust signal (facts lock, proof hygiene).
- **86% employee engagement** — Brazosport ISD "Fit Wars", May 6–19, 2024, labeled Employee Engagement in `vantagefit-astro/content/en/casestudy/brazosport-case-study.md`. Shown only inside the labeled proof strip.
- **Quote** — Rachel Arthur, Director of Benefits & Wellness, BISD, from the same case study: "It's a great way to log activities. Employees are also rewarded with points, recognition and prizes."
- All numbers inside KPI and At a Glance mocks are sample data; the Overview carries the caption "Figures are as of yesterday. Product UI shown with sample data." and the hero shot is captioned "shown with sample data."

## Critic result: pass

Checked against the full list in `FEATURES-HR-PROMPT.md` (current revision): no invented capabilities or certifications (SOC 2 / ISO / GDPR / HIPAA-compliant nowhere); Recommended Actions labeled rule-based, Leadership Insights read-only and non-predictive; no individual health data shown; no "activity level" targeting; no Health Connect; 13+ languages only; **no Org Wellness Score, composite score, individual score, or Score Report anywhere, including as a locked teaser**; no em-dashes, exclamation marks, "Learn more", or banned filler; the remaining annual gate (Leagues / League Report) shown on the report card and in the FAQ; `../styles/enterprise.css` linked; images: 1 large product screenshot (CDN dashboard) + 1 photograph (`card-measure-generic.jpg`) + logos/avatar, all with real alt; ~640 marketing words; nav IA updated and current page marked. Not a Solutions page: no outcome promises, every section proves the capability in the product's own labels.
