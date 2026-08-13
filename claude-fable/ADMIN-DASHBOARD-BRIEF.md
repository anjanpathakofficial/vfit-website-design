# Admin Dashboard & Analytics — page brief

**Slug:** `/features/admin-dashboard-analytics/`
**Mock:** `claude-fable/vantage-fit-admin-dashboard-analytics-v1.html`
**Angle:** the participation number, without the spreadsheet.
**Page type:** feature page. It proves a capability. It does not sell a program outcome.

---

## 1. Research takeaways

Read in this order: `FEATURES-HR-BRIEFS.md` page 8 (facts lock), then help docs, then the two OS spec generations, then the dashboard prototype repo.

**The Overview is four cards, not a story.** `vc-os/vfit-os/specs/product/09-admin-platform/admin-dashboard.md` is the newer of the two spec generations and names them exactly: Enrolled Users, Active Users, Incentivization (rewards spend in the signed-in admin's currency, SOLI-converted), Participation Rate. Each carries a delta vs the previous period and a sparkline. One filter bar drives every section: date presets 7d / 30d / quarter / year / custom, plus country, department, age group, gender.

**Leadership Insights and Recommended Actions are different machines.** Leadership Insights is a real internal ML call, fed aggregated signal buckets with no PII, rendered as two columns, Key Insights and Focus Areas. Recommended Actions are rule-based navigational links, max five, priority-ordered. The help doc collapses both under one "AI-Powered Insights" heading. The facts lock separates them, and the separation is the most defensible thing on this page, so it became a section rather than a footnote.

**The absorbed reports are real and boring, which is the selling point.** `content/en/help/admin/reports/admin-what-reports-are-available.md` confirms Employee, Transaction, Redemption, Challenge Leaderboard and League Report, each with an Export CSV button, and confirms that filters apply before export. It also confirms the leaderboard's team view ranks on average, not sum. Certificates generate per campaign as PDF.

**The gate has a specific look.** The spec describes the non-annual state precisely: grayscale plus a diagonal stripe overlay, "You currently do not have access to this component," and a Contact Account Manager CTA that opens a pre-filled email compose window and does not auto-send. That is drawn on the page rather than described, because a screenshot of a gate is more honest than a sentence about tiers.

**What I deliberately left on the floor.** No customer-result band. Brazosport 86% belongs to the two-week Fit Wars campaign of May 2024, and Wipro 3X is cumulative across three 2025 challenges that the case study attributes to the program, not the console. Neither has a causal link to the dashboard, so putting either near a KPI card would have implied one. The page uses the approved aggregate signal, 100+ organizations, and nothing else.

---

## 2. Why this structure

No required spine, so the order follows what a skeptical HR buyer checks, in the order they check it.

| # | Section | Job |
|---|---|---|
| 1 | Hero + drawn KPI row | Name the four cards in the first fold. A screenshot of four cards at 430px is unreadable, so these are drawn at hero scale and tagged illustrative. |
| 2 | Six kinds of logging. One rate. | The participation through-line. Everything an employee logs lands in the same rate, so the Overview measures one thing. Carries the employee-app product shot. |
| 3 | Cut it the way you get asked about it. | Filters, then the large real product screenshot. |
| 4 | One panel is AI. The other is a rulebook. | The AI-honesty split, drawn as two panels. |
| 5 | Admins see the department. Never the person. | Privacy answered with the product rule, plus At a Glance as proof that the org-level metrics really are org-level. Carries the photograph. |
| 6 | The rows behind the number, as CSV. | Absorbed reports, certificates, and the tier gate drawn as it appears in product. |
| 7 | FAQ, 3 | Only rollout objections the body did not already answer. |
| 8 | Closer | Book a walkthrough. |

Must-cover items were folded, not enumerated. Filters are a chip row, not a section. Certificates are one line in the export list. SOLI appears twice, once as a footnote inside the KPI mock and once as an FAQ answer, because "which currency" is a genuine multi-country buyer question rather than a feature.

**Density:** 746 words of marketing copy outside nav, footer and in-mock labels. Budget 450 to 750.

---

## 3. Copy deck

**Meta title:** Corporate Wellness Dashboard for HR Teams | Vantage Fit
**Meta description:** One corporate wellness dashboard for enrolled users, active users, rewards spend and participation rate. Filter by department, then export the rows as CSV.

**H1:** One corporate wellness dashboard. *One participation rate.*
**Lead:** Enrolled users, active users, rewards spend and participation rate sit on the Overview, each with a delta against the previous period and a sparkline. Filter to one country or one department, then export the rows underneath.
**CTAs:** Book a walkthrough / See the dashboard
**Hero notes:** Aggregate reporting only · CSV export on every report · 100+ organizations

**S2 — Where the number comes from**
Six kinds of logging. One rate.
Steps, a GPS run, a logged meal, a glass of water, a mindfulness session, a lab report. Every one counts toward the same participation rate and the same challenges, so the Overview measures one thing instead of stitching six.
Chips: Steps · Runs and workouts · Meals · Water · Mindfulness · Sleep · Lab reports
Note: Most employee logging happens in the mobile app. Lab report upload is the web exception.

**S3 — Filters**
Cut it the way you get asked about it.
One filter bar drives every section of the Overview. Pick a window, then narrow to the population you are about to be asked about.
Chips: 7 days · 30 days · Quarter · Year · Custom range · Country · Department · Age group · Gender
Caption: Insights Hub, activity view. Participation broken out by department, gender, age and location, under the same country and date filters.

**S4 — What is AI here, and what is not**
One panel is AI. The other is a rulebook.
Leadership Insights is written by an internal ML service from aggregated buckets, with no personal data sent to it. Recommended Actions are rule-based shortcuts, capped at five and ordered by priority.
Leadership Insights foot: Read only, on aggregated buckets. It observes. It does not predict, and it does not change your configuration.
Recommended Actions foot: Links into the dashboard, not automations. Nothing here sends itself.

**S5 — Privacy**
Admins see the department. Never the person.
There is no screen in this dashboard where an admin opens one employee's health. Aggregation is the product rule here, not a setting somebody can switch off.
· No weight, BMI or biometric values against a name
· No health assessment answers or risk names
· No individual health profile, in any report or export
HIPAA-guideline aligned on this point.
At a glance · This month: Avg steps, Active minutes, Mindful minutes, Avg sleep. Organization averages, each with a sparkline and a trend direction.

**S6 — Exports**
The rows behind the number, as CSV.
Filters apply before export, so the file matches the screen you were looking at. No ticket, no data team.

| Row | Line | Tag |
|---|---|---|
| Employee report | Active, inactive and dormant status per employee. Search, or filter by department and country. | CSV |
| Transaction report | Points earned and redeemed, converted through SOLI, filtered by date and category. | CSV |
| Redemption report | What was redeemed, when, and in which reward category. | CSV |
| Challenge leaderboard | Score, steps and team views per challenge. Teams rank on the average of member scores. | CSV |
| League report | Tier standings and rolling average steps, over a configurable window of 7 or 30 days. | Annual plan |
| Campaign certificates | Generated per campaign as a PDF, with your logo, seal and signer, ready to send. | PDF |

Gate note: That is what an admin without those surfaces sees: the card grayed out behind a diagonal stripe, with a link that opens a pre-filled email to their account manager. Wellness Leagues needs an annual contract. Health Insights is narrower than a plain annual plan, so confirm eligibility before it reaches a proposal. `[Verify with product]`

**S7 — FAQ**
1. Do I need IT to pull a report? / No. Every report exports as CSV from the dashboard itself, and the filters you set on screen are applied before the file downloads.
2. Our teams sit in six countries. Which currency does rewards spend show in? / The Incentivization card converts total rewards spend into the currency of the admin who is signed in, using the Standard of Living Index.
3. What is included without an annual contract? / The four KPI cards, every Overview filter, Recommended Actions, the Employee, Transaction and Redemption reports, and campaign certificates. Wellness Leagues and Health Insights stay locked until an account manager enables them.

**Closer:** Bring the number to your next leadership review. / We will walk the Overview, the filters and the exports against your own headcount and rollout. / Book a walkthrough · Compare the tiers

---

## 4. Sources

| Claim on page | Source |
|---|---|
| Four KPI cards, names, delta and sparkline | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` §Overview; facts lock p8 |
| Incentivization is SOLI-converted to the signed-in admin's currency | same spec; `vfit-os/specs/product/08-rewards-marketplace/soli-currency.md` |
| Filter set (7d/30d/quarter/year/custom + country, department, age group, gender) | same spec; `help/admin/workforce-health/admin-dashboard-overview.md` |
| Leadership Insights: internal ML API, aggregated buckets, no PII, Key Insights + Focus Areas, read-only | same spec §Leadership Insights; facts lock p8 |
| Recommended Actions: rule-based, max 5, priority-ordered, links | same spec; facts lock p8 |
| At a Glance metrics (this month) | same spec §Three cards row |
| Report names, locations, CSV export, filters applied before export | `help/admin/reports/admin-what-reports-are-available.md` |
| Team leaderboard ranks on average | same help doc; facts lock p9 do-not-claim |
| Certificates: per-campaign PDF | `vfit-os/specs/09-admin-platform/reports-analytics.md`; facts lock p8 |
| Gate: grayscale + diagonal stripe + Contact Account Manager, pre-filled email, no auto-send | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` §Feature Gating |
| League rolling average phrased as a configurable 7 or 30 day window | facts lock, live contradiction 1 |
| Aggregate only, no individual health profile, HIPAA-guideline aligned on this point | facts lock p8 and platform guardrails |
| 100+ organizations | facts lock, proof hygiene |

Illustrative figures in the drawn mocks (2,480 / 1,712 / $9,240 / 69%, the At a Glance values, the insight and action strings) carry an `Illustrative data` tag on every mock that shows a number. The KPI values match the sibling mocks in `claude-fable/` so the folder stays internally consistent.

---

## 5. Conflicts found, not silently resolved

1. **Help doc KPI names are stale.** `admin-dashboard-overview.md` lists Active Users, Enrollment Rate, Completion Rate, Org Wellness Score. The facts lock and the newer OS spec both say Enrolled Users, Active Users, Incentivization, Participation Rate. Shipped the facts lock. The help doc should be re-cut.
2. **Help doc labels Recommended Actions as part of "AI-Powered Insights."** The facts lock and the spec both say rule-based. Shipped rule-based, and made the distinction a section.
3. **Delta chips.** The facts lock and OS spec say each KPI card carries a delta vs the previous period. `vc-dashboard-design/docs/modules/wellness.md` records that production disabled invented delta chips backend-side. The facts lock wins per the prompt, so deltas are shown. Worth confirming with product before this goes live.
4. **Org Wellness Score is still everywhere upstream.** It is described in the help docs (`admin-what-is-org-wellness-score.md`, the Wellness Score Report row in the report table), in both OS spec generations, and in the dashboard repo's v1/v2 notes. Treated as retired throughout. It is not on the page, not in the export list, and not shown as a locked teaser. The two locked cards are Wellness Leagues and Health Insights only.
5. **Health Insights gating.** The OS spec says "annual clients"; the facts lock flags it as whitelist-gated in code, narrower than any annual plan. The page says it is narrower than a plain annual plan and carries a visible `[Verify with product]` tag rather than a clean claim.
6. **`vc-dashboard-design` is a redesign prototype, not production.** Its Overview (workforce ladder, participation gauge, archived AI panel) is a proposed future state. Used it only for vocabulary and for the honesty notes, never as a source for what ships today.

Assumptions stated: the "figures are as of yesterday" behaviour recorded in `vc-dashboard-design` is a genuinely good trust detail for this buyer, but it is not in the facts lock, so it is not on the page. Worth verifying and adding.

---

## 6. Design system compliance

- Links `../styles/enterprise.css`. Page-local CSS adds section shells and the new mocks only. No token, font stack, colour or logo is redeclared.
- Noto Sans loaded exactly as `styled-homepage/index.html` loads it.
- Nav, footer, `.shell`, `.btn`, `.eyebrow`, `.hero`, `.dash` chrome, `.metric-*`, `.final` and the footer grid are reused from the system.
- Nav Features → For HR teams rebuilt to the locked IA, with this page marked `aria-current="page"`. Reports & exports and Health data upload are gone from that column. Health data upload sits under Enterprise. No SOC 2 / GDPR / ISO in the Enterprise column. Audience targeting is described as country, department, age, gender and health-risk code, never activity level.
- Footer strip no longer carries the homepage's HIPAA · SOC 2 · GDPR · ISO line.
- **One system fix:** the inherited `.mega` is centred on its own trigger (`translateX(-40%)`), which pushed the 920px Features panel past the right edge of a 1440px window and clipped its banner. Page-local rule anchors the panels to the nav shell on desktop and moves the 12px hover bridge from `.nav-item::after` to `.nav-trigger::after`. Worth pulling back into `enterprise.css` for the siblings.

## 7. Images

| Asset | Where | Type |
|---|---|---|
| `../styled-homepage/logo.png` | Nav | logo |
| CDN `vfit-analytics-dashboard-desktop.png` | S3, full width | product screenshot |
| CDN `vfit-challenge-mobile.png` | S2 | product screenshot |
| `../styled-homepage/card-measure-generic.jpg` | S5 | photograph |
| `../styled-homepage/logo-white.png` | Footer | logo |

Two real product screenshots and one photograph, above the minimum. Every `<img>` carries descriptive alt. The dashboard shot is the Insights Hub activity view, so the caption and alt say that rather than implying it is the Overview. Drawn mocks use `role="img"` with a full `aria-label` and `aria-hidden` decorative interiors.

## 8. Critic result

Ran the prompt's critic list. Pass.

Fixed during the run:
- "actually" (banned filler) in the gate note. Rewritten.
- `vfit-challenge-mobile.png` is a 820x541 two-screen composite, not a tall phone. The wrong height attribute and a 260px cap left a dead column in S2. Reframed as a captioned card at column width.
- Features mega panel clipped at the right edge of the window. Fixed as described above.
- Mobile KPI grid stacked to four full-width cards and stretched the sparklines. Held at 2x2 down to 390px.
- FAQ ran as a narrow column against empty space. Now head left, questions right.

Checked and clean: no invented customer, metric, capability or certification; Recommended Actions labelled rule-based; Leadership Insights labelled read-only and never predictive; no individual health profile anywhere; no "activity level"; no Health Connect; no Android task-sync source claim; no SOC 2 / ISO / GDPR / HIPAA-compliant claim; no language count; no third Journey template; no Org Wellness Score, composite score, individual score or Score Report in any state including locked; team score described as an average; no implication that monetary rewards are on for every customer; the one VERIFY item ships tagged; no em-dashes, exclamation marks, "Learn more" or banned filler; the page reads as a capability page; tier gates are drawn, not buried; 746 marketing words; no horizontal overflow at 390px.
