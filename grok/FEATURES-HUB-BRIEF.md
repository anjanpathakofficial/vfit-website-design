# Features hub

**URL:** `/features/`  
**Mock:** `vantage-fit-features-hub-v1.html`  
**Angle:** Every capability, one platform. Everything logged counts toward the same participation surface.

## Page job

Index of 14 locked capabilities so a time-poor HR buyer can scan the platform, see the participation through-line, and see which cards are self-serve, annual, select-partner, or absent in Lite Mode. Not a Solutions hub. Not a 15th feature essay. Not a child rebuild.

**Reader:** US enterprise HR / CHRO / Benefits. IT glances at Enterprise.  
**Primary CTA:** Book a walkthrough. **Secondary:** Compare the tiers.

## Research takeaways

Preferred `FEATURES-HUB-BRIEFS.md` when children, live marketing, or help disagreed.

- **Through-line:** Steps, GPS, meal, water, mindfulness, and (where enabled) lab upload feed the **same challenges and the same participation number**. Org Wellness Score is retired. Not shown, gated, or explained.
- **IA:** 14 cards, 3 groups. No Surveys / eNPS, SOLI, Reports, or merged “Activity & health tracking.”
- **Availability:** Self-serve / Annual / Select-partner / Not in Lite Mode. Leagues = annual. Training Plans and Health Data Upload = select-partner (lab also annual / whitelist). Lite Mode = steps; builder keeps Race + `step_count`. Health-risk targeting needs Workforce Health (select-partner), not a standard dimension. Health Insights, if mentioned at all, is whitelist-narrower than “any annual plan.” Hub does not pitch Health Insights.
- **Surfaces:** iOS / Android full. Web = steps + limited manual logging + admin dashboard. Lab-report upload is the web exception, on Health Data Upload only.
- **AI:** Only lab-report extraction is named on this page (on that card). Leadership Insights stays on Admin Dashboard. Recommended Actions stay rule-based and off this page. Not an “AI-powered platform.”
- **Proof:** 100+ organizations only. No Tata, Wipro, IBS, Brazosport, 3X, or mindfulness-minute stats.
- **Do not claim:** SOC2, ISO 27001, GDPR, HIPAA-compliant platform. Activity-level targeting. 14 languages. Health Connect as the Android step source.

### Child line vs this lock

Prefer this lock. Flagged, not rewritten on children:

1. Several child mega lines still say “the same score.” Hub uses participation number / surface.
2. Personalized Programs mega still says “plans and journeys.” Lock is two live training plans plus a content library. Select-partner for plans.
3. Health Data Upload mega on some children says “annual track.” Lock is annual / whitelist / select-partner.
4. Lock table title “Mental wellbeing” vs locked IA “Mental wellbeing & mindfulness.” Hub uses the IA title, lock href, lock one-liner.
5. Security lock one-liner includes “No fake certification row” (a writer guardrail). Tightened on the card to “Four regions. Aggregate-only for HR.”

### Conflicts left unresolved (not silently fixed)

1. Org Wellness Score still in help, OS, and live marketing. Lock: retired. Absent here.
2. Live Features menu still merges Activity & health tracking, parks Reports and Health data under HR, and shows SOC 2 / GDPR / ISO. Lock IA used.
3. Health Insights: OS “any annual” vs lock whitelist. Not a hub card. Not pitched as standard annual.

## Why this structure

The grid is the page. Compact hero so the legend and first cards start in the first or second screen.

| Section | Job |
|---|---|
| Hero + participate photo + log rail | Through-line in one glance. Photograph + designed rail, not a 200-word opener. |
| Legend + jump links | Four badges, defined once. Scan path into the three groups. |
| 3-group grid, 14 cards | Locked slugs, spec-true one-liners, badges on gates and Lite. Relative links to sibling mocks. |
| Phone / web + product shot | Parity once. Lab upload named as the web exception. |
| 3 FAQs | Web vs app, Lite Mode, who sees labs. |
| Close | Book a walkthrough / Compare the tiers. 100+ organizations. |

No customer-result band. No cert row. No 15th card.

**Visual:** `../styles/enterprise.css`, Noto Sans, coral / ink / mint, homepage nav/footer, `logo.png` / `logo-white.png`. Features mega-menu is the locked IA with relative child hrefs. Features + hub banner marked current. Density peer: `vantage-fit-admin-dashboard-analytics-v1.html`.

## Copy deck

**Title:** Employee wellness platform features | Vantage Fit  
**Meta:** Corporate wellness platform all features on one participation surface. 14 capabilities for employees, HR, and IT. See what is self-serve, annual, or select-partner.

**Eyebrow:** Features · 14 capabilities  
**H1:** Fourteen features. One participation surface.  
**Lead:** A corporate wellness platform with all features on one grid. Steps, a GPS run, a logged meal, a glass of water, a mindfulness session, and a lab-report upload (where enabled) feed the same challenges and the same participation number. iOS and Android are the full employee experience. Web is steps, limited manual logging, and the admin dashboard.  
**Hero notes:** 100+ organizations · iOS and Android full · Web limited  
**CTAs:** Book a walkthrough · Compare the tiers

**Rail (illustrative, not a customer result):** Steps · GPS · Meal · Water · Mindfulness · Lab (if enabled) → Participation

**H2:** What is on, and what is gated.  
Self-serve / Annual / Select-partner / Not in Lite Mode. Leagues are annual. Training plans and lab upload are select-partner. Lite Mode is steps. Race plus step_count in the builder.

**Cards (lock lines; Security tightened)**

| Group | Card | Href (schema) | Mock | Line | Badges |
|---|---|---|---|---|---|
| Employees | Activity tracking | `/features/activity-tracking/` | `vantage-fit-activity-tracking-v1.html` | 65 activity types. No wearable required. Honest step math. | Self-serve |
| Employees | Fitness & exercise | `/features/fitness-exercise/` | `vantage-fit-fitness-exercise-v1.html` | GPS, squat tracker, Fitbit and Garmin. One primary device. | Self-serve · Not in Lite Mode |
| Employees | Nutrition & hydration | `/features/nutrition-hydration/` | `vantage-fit-nutrition-hydration-v1.html` | Meal targets from a basic profile. One tap = 250 ml. Full-Mode only. | Self-serve · Not in Lite Mode |
| Employees | Health metrics | `/features/health-metrics/` | `vantage-fit-health-metrics-v1.html` | Sleep, heart rate, weight, optional HRA. Next to the step count. | Self-serve · Not in Lite Mode |
| Employees | Mental wellbeing & mindfulness | `/features/mental-wellbeing/` | `vantage-fit-mental-wellbeing-v1.html` | Guided sessions. Minutes count as participation, not mood. | Self-serve · Not in Lite Mode |
| Employees | Wellness leagues | `/features/wellness-leagues/` | `vantage-fit-wellness-leagues-v1.html` | Always-on Gold / Silver / Bronze. Annual / ops-configured. | Annual · Not in Lite Mode |
| Employees | Personalized programs | `/features/personalized-programs/` | `vantage-fit-personalized-programs-v1.html` | Two live training plans plus a content library. Select-partner for plans. | Select-partner · Not in Lite Mode |
| HR | Admin dashboard & analytics | `/features/admin-dashboard-analytics/` | `vantage-fit-admin-dashboard-analytics-v1.html` | Four KPI cards. The number you take upstairs is participation rate. | Self-serve |
| HR | Program builder & templates | `/features/program-builder/` | `vantage-fit-program-builder-v1.html` | Five formats. 27 task types. A challenge live before lunch. | Self-serve |
| HR | Audience targeting | `/features/audience-targeting/` | `vantage-fit-audience-targeting-v1.html` | Aim a challenge without seeing who is in the cohort. | Self-serve |
| HR | Communications & nudges | `/features/communications-nudges/` | `vantage-fit-communications-nudges-v1.html` | 29 email templates. 34+ push types. Account-manager owns the master switch. | Self-serve |
| Enterprise | Integrations & SSO | `/features/integrations-sso/` | `vantage-fit-integrations-sso-v1.html` | Wearables employees connect. SAML and HRIS that IT sets up. | Self-serve |
| Enterprise | Security & compliance | `/features/security-compliance/` | `vantage-fit-security-compliance-v1.html` | Four regions. Aggregate-only for HR. | (no plan toggle) |
| Enterprise | Health data upload | `/features/health-data-upload/` | `vantage-fit-health-data-upload-v1.html` | Lab PDF in. AI extraction. Annual / whitelist. HR sees prevalence, not people. | Select-partner · Not in Lite Mode |

HR group note: Health-risk targeting needs Workforce Health. Select-partner, not a standard dimension.

**H2:** Full on the phone. Limited on the web.

**FAQ**  
1. Is the web app the same as the phone?  
2. What is Lite Mode?  
3. Who sees a lab report?

**Close H2:** Walk the grid with the gates still on.

## Sources

- `FEATURES-HUB-BRIEFS.md` (facts lock)
- `FEATURES-HUB-PROMPT.md`
- 14 child briefs in `grok/` (tone + what each card already shipped)
- `grok/vantage-fit-admin-dashboard-analytics-v1.html` (chrome + density)
- `styled-homepage/index.html`, `styles/enterprise.css`

Did not need a fresh OS audit. Did not borrow child proof stats.

## Assumptions

- Security is always on for the tenant, so it wears no availability badge. The other 13 wear legend language.
- Program builder stays Self-serve (not “Not in Lite Mode”) because Lite still has Race + `step_count`. FAQ states the reduction.
- Audience targeting stays Self-serve. Health-risk gate lives in the HR group note, not as a card-wide select-partner badge.
- Health Insights stays off the hub.
- Schema `url` values use the intended public slugs. Mock `href`s are the sibling HTML files.
- “One tap = 250 ml” is the lock mechanic on Nutrition, not the banned filler “one tap away.”

## Schema

This page only: `SoftwareApplication` + `WebPage` + `BreadcrumbList` + `FAQPage`. No ratings, reviews, or invented offers.

## Critic

Run after the mock. Failures found in draft and fixed:

- First H1 stuffed the keyword and wrapped to five lines. Replaced with two short lines: Fourteen features. / One participation surface. Keywords stay in title and lead.
- Gradient `em` on the H1 was treated as an unbreakable box. Switched the accent to coral `color` and `display: block` so 390px wraps. `inner === scroll` at 390.
- Dropped “Honest gating” from the close checks (writer voice). Now “Lite Mode is steps.”
- Security one-liner tightened (dropped “No fake certification row”).
- No Org Wellness Score, no cert badges, no AI-powered platform, no Surveys / eNPS / SOLI, no single-program stats.

**Pass.** Marketing copy in `<main>` is ~525 words outside nav, footer, and the 14 card lines (in the 450–750 band). `../styles/enterprise.css` linked. Images: `card-participate.jpg` + CDN employee-home product shot + logos. 14 cards, 3 groups, relative sibling hrefs all 200. SoftwareApplication + WebPage + BreadcrumbList + FAQPage. No em-dashes or exclamation marks in copy. Visual check at 1440 and 390: same site as Admin Dashboard and Activity tracking.
