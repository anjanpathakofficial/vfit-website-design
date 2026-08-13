# Admin Dashboard & Analytics

**URL:** `/features/admin-dashboard-analytics/`  
**Mock:** `vantage-fit-admin-dashboard-analytics-v1.html`  
**Angle:** The participation number, without the spreadsheet.

## Page job

Prove the HR Overview is a real console: four KPI cards, one participation rate, filters, AI Leadership Insights, rule-based Recommended Actions, At a Glance, CSV reports, certificates. Not a Solutions outcome page. Not a help article.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See the dashboard (hero), Compare the tiers (close).

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Overview KPIs (lock + OS ADMIN-001 + Q1-26 product update):** Enrolled Users, Active Users, Incentivization (SOLI-converted), Participation Rate. Each with delta + sparkline. Help Overview still lists Enrollment Rate, Completion Rate, Org Wellness Score. Stale. Not used.
- **Filters (lock + help + OS):** 7d / 30d / quarter / year / custom + country, department, age group, gender. Live production has a longer preset list. Page shows the lock set.
- **Leadership Insights (lock + OS):** AI via internal ML API. Aggregated signal buckets only. No PII. Two columns: Key Insights + Focus Areas. Read-only. Not predictive. Not auto-configuring.
- **Recommended Actions (lock + OS):** Rule-based, max 5, links not automations, not AI. Production ground-truth notes max 10. Page follows lock (max 5). Example strings from OS: View Inactive Employees (92…), Nudge Inactive Users. Nudge is named as a link, not a one-click send (`[VERIFY]` on comms page).
- **At a Glance this month (lock + OS):** Avg Steps, Active Minutes, Mindful Minutes, Avg Sleep. Production may also show Active Calories. Page uses the four lock metrics.
- **Privacy (lock + help privacy article + OS FAQ):** Admins see aggregates. Never an individual health profile (weight, BMI, HRA). HIPAA-guideline aligned on this point. Not “HIPAA-compliant platform.”
- **Reports (lock):** Employee, Leaderboard, Transaction, Redemption CSVs. League annual-gated. **No Score Report.** Help and OS still document Wellness Score Report. Flagged, omitted.
- **Certificates:** Lock + OS: automated per-campaign PDF. Employee help says image file. Shipped PDF per lock.
- **Gates (lock):** Leagues = annual, Contact Account Manager. Health Insights = whitelist, narrower than any annual plan. Not self-serve toggles. Wellness Score is **retired**, not gated. OS and help still describe Org Wellness Score as live. Left off the page.
- **Proof:** 100+ organizations (approved). Brazosport 86% is Fit Wars (May 2024), not a dashboard KPI. Wipro 3X is three 2025 challenges and VERIFY before tying to the dashboard. Both omitted.
- **Participation formula:** Homepage defines a 30-day qualifying-action rate. Not in the lock or OS. Not claimed.

### Conflicts left unresolved (not silently fixed)

1. Org Wellness Score: help, OS ADMIN-001, Q1-26 update still live. Lock: retired.
2. Help Overview KPI names vs lock/OS/product-update names.
3. Certificate PDF (lock/OS) vs image file (employee help).
4. Recommended Actions max 5 (lock/OS) vs max 10 (dashboard live sweep).
5. Health Insights: lock says whitelist-narrower; OS Insights Hub is annual; Workforce Health / labs are whitelist. Page uses lock wording.

## Why this structure

No required spine. Folded must-cover into UI, not one section per bullet.

| Section | Job |
|---|---|
| Hero + photo + participation card | First screen: this is the number. Photograph + HTML fragment, not an HTML-only fake console. |
| Four KPI cards + CDN screenshot | Prove Overview. Filters as chips. Product shot does the work. |
| Insights / Actions / At a Glance | AI vs rule-based, without an essay. |
| Reports + locked cards | Absorbed CSVs, certificates, annual/whitelist gates. Score Report called out as gone. |
| Privacy | Product rule, not a trust-badge row. |
| 3 FAQs + sibling links | Rollout objections already not answered. Lateral HR pages. |
| Close | Book a walkthrough / Compare the tiers. |

Skipped a customer-result band so the page stays a capability page.

**Visual:** `../styles/enterprise.css`, Noto Sans, coral / ink / mint, homepage nav/footer chrome, `logo.png` / `logo-white.png`. Features → For HR updated to the locked IA. No SOC 2 / GDPR / ISO in Enterprise or footer.

## Copy deck

**Title:** Corporate wellness dashboard and analytics | Vantage Fit  
**Meta:** See participation rate, enrolled and active users, and rewards spend on one employee wellness analytics dashboard. Aggregate only. Book a walkthrough.

**Eyebrow:** Features · For HR teams  
**H1:** The participation number, without the spreadsheet.  
**Lead:** Vantage Fit’s corporate wellness dashboard turns every employee log into four KPI cards. The one you take upstairs is participation rate.  
**Hero notes:** 100+ organizations · Aggregate health only · Date, country, department, age, gender  
**CTAs:** Book a walkthrough · See the dashboard

**H2:** Four numbers. One participation rate.  
**Lead:** Overview opens on Enrolled Users, Active Users, Incentivization, and Participation Rate. Each card has a delta and a sparkline. Filters apply to the whole view.  
**Cards (one line):** Everyone on the program, across countries. / Who used the app in the selected period. / Rewards spend, SOLI-converted to your currency. / The number you take upstairs.  
**Caption:** KPI figures above are illustrative. Incentivization is a spend view, not a claim that monetary rewards are on for every plan.

**H2:** Insights read the buckets. Actions stay links.  
Leadership Insights: AI, aggregated buckets, read-only, not predictive, not auto-configuring.  
Recommended Actions: rule-based, max 5, links, not AI. Nudge is not described as a one-click send.  
At a Glance this month: Avg Steps, Active Minutes, Mindful Minutes, Avg Sleep.

**H2:** Export the CSV. Skip the score report.  
Employee / Leaderboard / Transaction / Redemption / League (annual-gated) / Certificates (automated per-campaign PDF).  
Locked: Wellness Leagues (annual). Health Insights (whitelist). Contact Account Manager.

**H2:** Admins see the crowd, not the person.  
Aggregates yes. Weight, BMI, HRA, mood, labs no. HIPAA-guideline aligned.

**FAQ**  
1. Can I see who is inactive without seeing their health?  
2. What is locked, and what is gone?  
3. Do I still export a Score Report?

**Close H2:** See the number you would take upstairs.

KPI numbers, insight bullets, and At a Glance figures are labeled **illustrative**.

## Sources

- `FEATURES-HR-BRIEFS.md` platform rules + page 8
- `vc-os/vfit-os/specs/product/09-admin-platform/admin-dashboard.md`
- `vc-os/vfit-os/specs/product/08-rewards-marketplace/soli-currency.md`
- `vantagefit-astro/content/en/help/admin/workforce-health/admin-dashboard-overview.md` (filters; KPI names stale)
- `vantagefit-astro/content/en/help/admin/reports/admin-what-reports-are-available.md`
- `vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md`
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-configure-certificates.md`
- `vantagefit-astro/src/data/product-update-lists.json` (Admin Dashboard Revamp)
- `vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md` (recognizable Overview; Score still live there)
- Case studies read, not used: Brazosport Fit Wars May 2024 86%; Wipro 3X across three 2025 challenges

## Assumptions

- Participation Rate needs no invented formula on the page.
- “Nudge Inactive Users” is a Recommended Action label only.
- Health Insights gate copy follows the lock (whitelist), not OS “any annual.”
- Homepage mega-menu chrome updated only in the Features columns required by the prompt.

## Critic

Run after the mock. Failures found in draft and fixed:

- Dropped a customer-result band (would read as Solutions).
- Removed any Org Wellness Score card, gate, or “Review Org Wellness Score” action.
- Labeled Recommended Actions rule-based. Did not call them AI.
- Labeled Leadership Insights read-only / not predictive.
- Did not claim HIPAA-compliant, SOC2, ISO, or GDPR.
- Did not use activity level as a targeting dimension.
- Did not imply monetary rewards are on for every customer.
- Footer cert row removed (homepage chrome is not a source of truth).
- Features → For HR set to the locked four pages.

**Pass.** Marketing copy in `<main>` is ~670 words including product-mock labels (under the 800 fail line; in the 450–750 band). `../styles/enterprise.css` is linked. Images: CDN Overview shot + three photographs + logos. No em-dashes or exclamation marks in copy. Org Wellness Score appears only as retired. Visual check at 1440 and 390: same site as `styled-homepage`.
