# Features hub brief — `/features/` (Group E, Kimi)

**Shipped:** `vantage-fit-features-hub-v1.html` (this folder). One page, no child rebuilt.

## Research takeaways

- The hub is a directory, not an essay. The 14 child pages already carry the depth; the hub's job is the through-line plus honest gating.
- Org Wellness Score is retired. The unifying idea on the page is **one participation surface**: every log (steps, GPS run, meal, water, mindfulness, lab upload) counts toward the same challenges and the same participation number.
- Availability is four states: Self-serve / Annual / Select-partner / Not in Lite Mode. Leagues = annual; Training Plans and Health Data Upload = select-partner (HDU is annual whitelist); Lite Mode collapses logging to steps.
- Web parity: full experience on iOS / Android; web is steps + limited manual logging + admin dashboard, with lab-report upload as the single web exception.
- Only approved hub stat: **100+ organizations**. No single-program figures, no customer stats borrowed from child pages.
- Only two AI features exist platform-wide (Leadership Insights, lab-report extraction). The hub is not branded AI.

## Why this structure

1. **Hero** — eyebrow carries the primary keyword, H1 states the through-line, lead lists the log types. Photo (runner) + mobile product shot + chips, matching Admin Dashboard density.
2. **One participation surface strip** — the through-line shown as a small flow (log types → one number), not a paragraph per feature.
3. **Availability legend** — the four badges defined once, before the grid, so card badges read instantly.
4. **The grid** — 3 groups (For employees 7 / For HR teams 4 / Enterprise 3), 14 cards, one spec-true line each, badges per the lock. This is the page.
5. **Platform strip** — cross-platform reality stated once (iOS / Android full, web limited, lab upload the exception).
6. **FAQ (3, optional max)** — web vs app, Lite Mode, who sees lab data. Carries `FAQPage` schema.
7. **Final CTA** — Book a walkthrough / Compare the tiers, 100+ organizations in the checks.

## Copy deck

**Meta title:** Employee wellness platform features | Vantage Fit
**Meta description:** All 14 Vantage Fit features in one grid: employee logging, HR tools, and enterprise plumbing. Everything logged counts toward one participation surface. Trusted by 100+ organizations.

**H1:** Every feature. One participation surface.
**Lead:** Steps, a GPS run, a logged meal, a glass of water, a mindful minute, a lab report. Everything an employee logs counts toward the same challenges and the same participation number. This is the whole employee wellness platform, grouped by who uses what.

### The 14 card lines (badges)

**For employees**
1. Activity tracking — 65 activity types. No wearable required. Honest step math. *(Self-serve)*
2. Fitness & exercise — GPS runs, a squat tracker, Fitbit and Garmin. One primary device. *(Self-serve, Not in Lite Mode)*
3. Nutrition & hydration — Meal targets from a basic profile. One tap logs 250 ml. *(Self-serve, Not in Lite Mode)*
4. Health metrics — Sleep, heart rate, weight, optional HRA. Next to the step count. *(Self-serve, Not in Lite Mode)*
5. Mental wellbeing — Guided sessions. Minutes count as participation, not mood. *(Self-serve, Not in Lite Mode)*
6. Wellness leagues — Always-on Gold, Silver, and Bronze. Ops-configured. *(Annual, Not in Lite Mode)*
7. Personalized programs — Two live training plans plus a content library. *(Select-partner, Not in Lite Mode)*

**For HR teams**
8. Admin dashboard & analytics — Four KPI cards. The number you take upstairs is participation rate. *(Self-serve)*
9. Program builder & templates — Five formats. 27 task types. A challenge live before lunch. *(Self-serve)*
10. Audience targeting — Aim a challenge without seeing who is in the cohort. *(Self-serve)*
11. Communications & nudges — 29 email templates, 34+ push types. Account manager owns the master switch. *(Self-serve)*

**Enterprise**
12. Integrations & SSO — Wearables employees connect. SAML and HRIS that IT sets up. *(Self-serve)*
13. Security & compliance — Four data regions. Aggregate-only reporting for HR. *(no badge; underpins every plan)*
14. Health data upload — Lab PDF in, AI extraction out. Annual whitelist. HR sees prevalence, not people. *(Select-partner, Not in Lite Mode)*

## Sources

- `FEATURES-HUB-PROMPT.md`, `FEATURES-HUB-BRIEFS.md` (facts lock; card lines tightened, not inflated)
- `grok/vantage-fit-admin-dashboard-analytics-v1.html` (density and chrome peer)
- `kimi-k3/vantage-fit-admin-dashboard-analytics-v1.html` (nav / footer / script reused; Features mega-menu rebuilt to the locked IA)
- `styles/enterprise.css`, `styled-homepage/` (tokens, type, photo assets)
- Product shot: `vfit-overview-mobile.png` from the approved CDN list. No Wellness Score shots.

## Assumptions and flags

- Card hrefs are relative sibling mocks (per prompt); locked public slugs appear only in schema / copy.
- Linked `vantage-fit-mental-wellbeing-v1.html` for Mental wellbeing (the locked features child). A similarly named `vantage-fit-mental-health-wellbeing-v1.html` in this folder is a solutions-side mock and was not linked.
- Security & compliance wears no tier badge: it is not a gated add-on. Health Data Upload shows Select-partner + Not in Lite Mode, with "annual whitelist" stated in its line.
- Nav mega-menu now lists the locked 14-child IA; "All features" is marked current.

## Critic result (self-check)

- 14 cards, 3 groups, no 15th; no Surveys / eNPS / SOLI / Reports card. Pass.
- All 14 hrefs are sibling mocks that exist in this folder. Pass (verified on disk).
- No Org Wellness Score anywhere. Pass.
- No "AI-powered platform"; AI appears only as lab-report extraction on the HDU card. Pass.
- No SOC2 / ISO / GDPR / HIPAA-compliant-platform claims or badges. Pass.
- Legend present; Leagues and HDU visibly gated; Lite Mode flags on seven cards. Pass.
- 100+ organizations only; no Tata / Wipro / IBS / Brazosport stat. Pass.
- No activity-level targeting, 13+ languages (never 14), no Health Connect, mood stays private. Pass.
- `SoftwareApplication` JSON-LD on this page only, plus `WebPage`, `BreadcrumbList`, `FAQPage`. No invented ratings. Pass.
- `../styles/enterprise.css` linked; logo.png wordmark; photograph present; sentence case, no em-dashes, no exclamation marks, verb-led CTAs. Pass.
- Marketing copy 476 words outside nav, footer, and card lines (scripted count). Pass.
