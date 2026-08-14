# Features hub, `/features/`, build brief

**Mock:** `vantage-fit-features-hub-v1.html`
**Group:** E (hub). Last page in the locked 15-page IA. No child page was rebuilt.

---

## Research takeaways

1. **The through-line had to be shown, not asserted.** With Org Wellness Score retired, the only honest unifying idea is that six different log types write to one place. A sentence claiming that is wallpaper. So the hero carries a convergence object: six chips (steps, run, meal, water, mindfulness, lab report) fanning into one output row, "One participation rate." It carries no number, because a headline percentage on a hub would be an invented stat.
2. **The gating is the differentiator.** Any vendor can print fourteen tiles. Almost none will say on the index page that leagues are annual, that training plans are select-partner, and that health data upload is annual *and* whitelisted *and* absent in Lite. That is why the legend sits above the grid rather than in a footnote, and why the legend uses the exact same badge components the cards use.
3. **Two cards are load-bearing, twelve report into them.** Activity tracking is what every employee log is measured against; admin dashboard is where HR reads the result. Giving those two a full-width spine card produced the grid rhythm without a single extra paragraph, and gave a place for "where a log lands" and "the four KPI cards" to sit as labels rather than prose.
4. **Seven does not divide by three.** The spine-card decision solved a layout problem and a hierarchy problem at once: 1 full-width + 6 in a clean 3×2 for employees, 1 full-width + 3 for HR, 3 for enterprise. No orphan tiles, no filler fifteenth card.

## Why this structure

Hero → legend → grid → cross-platform → FAQ → close.

The legend is deliberately **before** the grid. A buyer who reads the badges after scanning fourteen tiles has already built the wrong mental model. Reading them first makes every badge on every card legible on first pass.

Everything else is scaffolding. There is no per-card paragraph, no platform essay, no eleven-section spine. **564 marketing words** outside nav, footer and the fourteen card lines (budget 450–750); 901 including every word inside the cards.

## The 14 card lines (locked slugs, spec-true)

Cards link to sibling mocks in this folder. Public URLs below are for copy and schema only.

### For employees (7)

| Card | Public URL | Line | Badges |
|---|---|---|---|
| Activity tracking | `/features/activity-tracking/` | 65 activity types. No wearable required. Honest step math, and the source of the number everything else is measured against. | Self-serve |
| Fitness & exercise | `/features/fitness-exercise/` | GPS runs, a squat tracker, Fitbit and Garmin. One primary device at a time. | Self-serve · Not in Lite Mode |
| Nutrition & hydration | `/features/nutrition-hydration/` | Meal targets from a basic profile. One tap logs 250 ml of water. | Self-serve · Not in Lite Mode |
| Health metrics | `/features/health-metrics/` | Sleep, heart rate, weight and an optional HRA, sitting next to the step count. | Self-serve · Not in Lite Mode |
| Mental wellbeing | `/features/mental-wellbeing/` | Guided sessions. The minutes count as participation. Mood stays private. | Self-serve · Not in Lite Mode |
| Wellness leagues | `/features/wellness-leagues/` | Always-on gold, silver and bronze tiers on a rolling average that never resets. | **Annual** · Not in Lite Mode |
| Personalized programs | `/features/personalized-programs/` | Nine training plans exist, two you can start today, plus an on-demand content library. | **Select-partner** · Not in Lite Mode |

### For HR teams (4)

| Card | Public URL | Line | Badges |
|---|---|---|---|
| Admin dashboard & analytics | `/features/admin-dashboard-analytics/` | Four KPI cards, filters and every CSV export. The number you take upstairs is participation rate. | Self-serve |
| Program builder & templates | `/features/program-builder/` | Five self-serve formats. 27 task types. A challenge live before lunch. | Self-serve |
| Audience targeting | `/features/audience-targeting/` | Aim a challenge without seeing who is in the cohort. Health-risk targeting needs Workforce Health. | Self-serve · **Select-partner** |
| Communications & nudges | `/features/communications-nudges/` | 29 email templates. 34+ push types. Your account manager owns the master switch. | Self-serve |

### Enterprise (3)

| Card | Public URL | Line | Badges |
|---|---|---|---|
| Integrations & SSO | `/features/integrations-sso/` | Wearables employees connect themselves. SAML and HRIS that IT sets up once. | Self-serve |
| Security & compliance | `/features/security-compliance/` | Four regional instances, set at onboarding. Aggregate only for HR, and no certification row. | Self-serve |
| Health data upload | `/features/health-data-upload/` | Lab PDF in, AI extraction, a private plan out. HR sees prevalence counts, never a person. | **Annual · Select-partner · Not in Lite Mode** |

## Copy deck (everything outside the cards)

**H1** Fourteen features. *One participation surface.*

**Lead** The employee wellness platform features below are not fourteen separate products. A step, a GPS run, a logged meal, a mindfulness session and, where it is enabled, a lab report all land in the same challenges and the same participation rate.

**CTAs** Book a walkthrough · Scan the grid · Compare the tiers
**Hero note** 100+ organizations · Full logging on iOS and Android · Every card says what it costs to switch on

**Legend, H2** Not every card is on for every client.
- Self-serve. On for Full-Mode clients with no extra contract toggle.
- Annual. Configured by your account manager on an annual plan.
- Select-partner. Ops-enabled or whitelisted. Not available on day one.
- Not in Lite Mode. Hidden, or reduced to steps, while Lite Mode is on.
- *Lite Mode collapses the logging surface to steps. In the program builder you get the Race format and the step count task, and nothing else.*

**Grid, H2** The whole platform, in three groups.
Group lines: "Seven ways to log, all writing to the same challenges and the same rate." / "Four surfaces for the person who has to report the number." / "Three answers for the people who sign off before rollout."

**Cross-platform, H2** Full on the phone. Limited on the web.
iOS, Android: every log type in the grid, plus challenges, leagues and rewards. Web, employee: steps and limited manual logging; uploading a lab report is the exception that belongs here. Web, HR: the whole admin console.

**FAQ (3)** Does everything work in a browser? · What changes in Lite Mode? · Who gets to read an uploaded lab report?

**Closer, H2** Bring the whole grid to one call.

## Meta

- **Title:** `Employee wellness platform features | Vantage Fit`
- **Description:** All 14 Vantage Fit features in one grid. Steps, workouts, meals, mindfulness and lab uploads feed the same challenges and the same participation rate. See what is self-serve, annual or select-partner.
- **Primary keyword:** `employee wellness platform features`, used in the title and the first clause of the lead. Not repeated in H1 or H2s.
- **Schema:** `SoftwareApplication` (this page only) + `WebPage` + `BreadcrumbList` + `FAQPage`, in one `@graph`. `featureList` carries the 14. No `offers`, no `aggregateRating`, no reviews. None of those exist to cite.

## Design system

- Links `../styles/enterprise.css`. Noto Sans loaded the same way `styled-homepage/index.html` loads it.
- Reuses `.shell` `.nav` `.mega` `.eyebrow` `.lead` `.btn` `.hero-note` `.final` `.final-checks` and the footer grid unchanged. No token, font stack or brand colour is redeclared. Page-local CSS is prefixed `.fh-` / `.fcard` / `.conv-` / `.badge`.
- Wordmark is `../styled-homepage/logo.png` and `logo-white.png`. No invented mark.
- Features mega-menu rebuilt to the locked IA (7 / 4 / 3), all fourteen links pointing at sibling mocks, Features marked current and the hub banner marked `aria-current="page"`. No SOC 2 / GDPR / ISO anywhere in nav, body or footer.

**Images (5, all with real alt):** `card-participate.jpg` as the hero photograph, `card-measure-generic.jpg` as the HR group thumbnail, the `vfit-overview-mobile.png` product shot in the cross-platform band, plus the two wordmarks. No Wellness Score screenshot. No certification seals.

## Deviations from the facts lock, flagged

1. **Personalized programs.** The lock's line is "Two live training plans plus a content library." The shipped child page leads with "Nine plans exist. Two are startable today." I used the child's fuller framing because it is the honesty test on that card, and naming the catalog size makes "two" a disclosure rather than a shortfall. Substance is identical, and the Select-partner badge still carries the gate.
2. **Security & compliance has no badge in the lock's availability table.** I gave it Self-serve, because it genuinely is on for every Full-Mode client, and leaving one card in fourteen unbadged would read as an oversight rather than a statement. The line carries the real nuance: regions are "set at onboarding," which is not a toggle.
3. **Activity tracking carries no "Not in Lite Mode" badge.** Lite Mode reduces the logging surface *to* steps, and steps are this card's core, so the card survives Lite. The six cards that do not are badged.

## Sources

`FEATURES-HUB-BRIEFS.md` (facts lock, prevails over live marketing), the 14 shipped child mocks and briefs in this folder (checked for descriptor accuracy: 65 activity types, 250 ml, 27 task types, five formats, 29 email templates, 34+ push types, four KPI cards, four regions, nine plans / two live), `styles/enterprise.css`, `styled-homepage/`, and `grok/vantage-fit-admin-dashboard-analytics-v1.html` as the density peer.

## Critic result

| Check | Result |
|---|---|
| Exactly 14 cards, 3 groups, no 15th, no Surveys / eNPS / SOLI / Reports card | Pass |
| All 14 hrefs open a real sibling mock | Pass. Verified all 14 files exist on disk |
| Every relative href and img src resolves | Pass. No dead links, no missing assets |
| Org Wellness Score shown, gated or used as the through-line | Pass. Zero occurrences |
| "AI-powered platform," or Recommended Actions labeled AI | Pass. The only AI mention is "AI extraction" on the health data upload card |
| SOC 2 / ISO / GDPR / HIPAA-compliant platform | Pass. Zero. The only HIPAA text is "BAA provisions for HIPAA compliance" on the lab pipeline, in the FAQ |
| Legend present, gated cards badged | Pass. Legend above the grid; leagues Annual, programs Select-partner, health data upload Annual + Select-partner + Not in Lite |
| 100+ organizations present, no single-program stat | Pass. Two uses, no Tata / Wipro / IBS / Brazosport / 3X |
| Activity level as targeting · 14 languages · Health Connect | Pass. None present |
| `SoftwareApplication` schema present, no invented reviews or ratings | Pass. JSON parses; graph is SoftwareApplication + WebPage + BreadcrumbList + FAQPage |
| Em-dashes, exclamation marks, "Learn more," banned filler | Pass. Zero in prose |
| Word count outside chrome and card labels | Pass. 564 (fails at ~800) |
| `../styles/enterprise.css` linked, no new brand or primary colour | Pass |
| Photograph present | Pass. Hero runner photo, plus an HR photo and a product screenshot |
| Rebuilt a child page | No |
| HTML well-formed | Pass. No unclosed or mismatched tags |
| Responsive | Pass. No horizontal overflow at 390 / 768 / 1024 / 1440; grid 3 → 2 → 1, spine cards stack |
