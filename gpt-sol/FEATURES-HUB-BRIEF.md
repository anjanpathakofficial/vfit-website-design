# Vantage Fit Features hub brief

## Page job

Give a time-poor US HR buyer a complete, honest view of Vantage Fit before they choose a feature page. The page is a directory, not another feature essay. Its core idea is that employee inputs across movement, food, water, mindfulness, health metrics, and enabled lab uploads meet on one participation surface.

## Research takeaways

- The locked IA contains exactly 14 children in three groups: seven employee, four HR, and three enterprise pages.
- Availability is part of the product story. Core Full-Mode capabilities can be self-serve, Wellness Leagues are annual and ops-configured, Training Plans and Health Data Upload are select-partner, and Lite Mode collapses to steps.
- The complete experience is on iOS and Android. Web supports steps, limited manual logging, and the admin dashboard. Lab-report upload is the explicit web exception.
- The only approved hub proof is 100+ organizations.
- Org Wellness Score is retired. The shared outcome is participation, not a composite score.

## Structure and visual direction

1. A compact photo-led hero states the participation thesis and starts the capability story in the first screen.
2. A three-stop participation rail explains the path from employee log to challenge to aggregate HR view.
3. The four-state availability legend sits directly above the grid.
4. The page body is the 7 / 4 / 3 linked-card matrix, with gating visible on the relevant cards.
5. A short close repeats the two buyer actions without adding an FAQ or another marketing section.

The page uses the existing Noto Sans, canvas, ink, coral, mint, 22px radius, navigation, footer, and buttons from `enterprise.css`. Its one distinctive device is the participation rail: small input labels converge on one coral path that continues into all three grid groups. This encodes the product truth without creating a new visual language.

## Copy deck

### Hero

**Eyebrow:** Employee wellness platform features

**H1:** Every capability. One participation surface.

**Lead:** Employees can log a walk, workout, meal, glass of water, mindfulness session, health metric, or enabled lab report. The same challenges and one participation number connect the experience for HR.

**Primary CTA:** Book a walkthrough  
**Secondary CTA:** Compare the tiers  
**Proof:** Used by 100+ organizations

### Participation rail

- **Employees log:** Phone steps, GPS workouts, daily habits, guided minutes, and health inputs begin in one mobile experience.
- **Challenges count:** Eligible logs meet the same task and challenge rules, so participation does not split into program silos.
- **HR reviews:** Aggregate reporting shows whether the program is being used without opening an employee's private health record.

### Availability legend

- **Self-serve:** On for Full-Mode clients without an extra contract toggle.
- **Annual:** Enabled with the account manager for annual clients.
- **Select-partner:** Ops-enabled or whitelisted, not a day-one switch.
- **Not in Lite Mode:** Hidden or reduced to steps when Lite Mode is on.

### For employees

1. **Activity tracking:** 65 activity types. No wearable required. Honest step math.
2. **Fitness & exercise:** GPS, squat tracker, Fitbit and Garmin. One primary device.
3. **Nutrition & hydration:** Meal targets from a basic profile. One tap = 250 ml. Full-Mode only.
4. **Health metrics:** Sleep, heart rate, weight, optional HRA. Next to the step count.
5. **Mental wellbeing:** Guided sessions. Minutes count as participation, not mood.
6. **Wellness leagues:** Always-on Gold / Silver / Bronze. Annual / ops-configured.
7. **Personalized programs:** Two live training plans plus a content library. Select-partner for plans.

### For HR teams

1. **Admin dashboard & analytics:** Four KPI cards. The number you take upstairs is participation rate.
2. **Program builder & templates:** Five formats. 27 task types. A challenge live before lunch.
3. **Audience targeting:** Aim a challenge without seeing who is in the cohort.
4. **Communications & nudges:** 29 email templates. 34+ push types. Account-manager owns the master switch.

### Enterprise

1. **Integrations & SSO:** Wearables employees connect. SAML and HRIS that IT sets up.
2. **Security & compliance:** Four regions. Aggregate-only for HR. No fake certification row.
3. **Health data upload:** Lab PDF in. AI extraction. Annual / whitelist. HR sees prevalence, not people.

## Search and schema

- **Meta title:** Employee wellness platform features | Vantage Fit
- **Meta description:** Explore 14 Vantage Fit employee wellness platform features across employee, HR, and enterprise needs, with clear self-serve, annual, partner, and Lite Mode availability.
- **JSON-LD:** `WebPage`, `BreadcrumbList`, and `SoftwareApplication` only. No FAQ schema.

## Sources

- `FEATURES-HUB-PROMPT.md`
- `FEATURES-HUB-BRIEFS.md`
- `styles/enterprise.css`
- `styled-homepage/index.html`
- `grok/vantage-fit-admin-dashboard-analytics-v1.html`
- The 14 sibling feature mocks in `gpt-sol/`

## Critic result

Pass. The mock contains exactly 14 linked cards and three groups. Every link resolves to an existing sibling mock. It includes the required four-state legend, visible Annual / Select-partner / Lite gating, a real photograph, 100+ organizations, responsive behavior, and the page-only `SoftwareApplication` schema. It excludes Org Wellness Score, certification badges, an AI-platform claim, activity-level targeting, Surveys / eNPS, SOLI, and single-program results.
