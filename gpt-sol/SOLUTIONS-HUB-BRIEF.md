# Vantage Fit Solutions hub

## Page job

Act as a concise chooser for `/solutions/`. The page should help a buyer move to the right solution in one scan, not restate every capability or compete with the platform page.

**Audience:** HR, benefits and wellbeing leaders who know the outcome they want but may not know Vantage Fit's product vocabulary.

**Primary action:** Choose a solution page

**Secondary conversion:** Book a demo

## IA decision

The signed-off menu has two columns plus a featured platform page:

1. **Wellness challenges:** what HR wants to run.
2. **Workforce health and rewards:** how HR turns a baseline into action, ordered as data in → data out → action.
3. **Wellness platform:** what Vantage Fit is as a shared employee and HR system.

The hub preserves those exact groups. It does not introduce industries, personas, or new top-level solution labels.

## Product and messaging takeaways

- Challenge types are separate choices because they solve different program-design needs. The flagship Wellness challenges page is the right first click for buyers who want to browse.
- Health Risk Assessment, Workforce health insights and Wellness rewards program are a connected sequence. The hub explains the relationship without making the three pages feel dependent on one another.
- The platform page earns a prominent entry because “employee wellness platform” is a category-level need, not another program card.
- The platform's north star is participation. Hub copy therefore uses concrete buyer verbs such as run, understand and reinforce instead of broad promises about culture or outcomes.
- The current health analytics model keeps participation, challenge, activity and aggregate health-risk measures separate. The hub uses “signals” and avoids promising a single wellness score.

## Page architecture

1. **Compact hero**
   - H1: “Choose the wellness job you need to solve”
   - One sentence of orientation and direct anchor links.
2. **Featured platform rail**
   - A wide, high-contrast definition card for buyers comparing platform categories.
3. **Two-column chooser**
   - Left: Wellness challenges, with the flagship library highlighted first and four format-specific routes beneath it.
   - Right: Workforce health and rewards as a connected three-step pathway: establish a baseline, understand signals, reinforce action.
4. **Decision prompt**
   - A small “Not sure where to start?” panel with two honest starting recommendations.
5. **Short conversion close**
   - Book a demo / See pricing.

There is intentionally no FAQ, proof band, generic feature grid, or long platform explanation. Those belong on destination pages.

## Visual direction

The hub uses the shared enterprise type, tokens, nav, buttons and footer. Its distinct architecture is a **route map** rather than a normal landing-page stack. A dark platform rail forms the top of the map. Below it, the two signed-off solution columns use different navigation grammar:

- Challenge routes look like a browsable program shelf.
- Health and rewards routes form a connected vertical signal path with explicit Data in, Data out and Action labels.

This difference is structural, not decorative. It teaches buyers how the IA works. Hover and focus raise the selected route slightly and move its arrow. Reduced-motion preferences remove those transitions.

## Full copy deck

### Metadata

**Meta title:** Employee wellness solutions | Vantage Fit

**Meta description:** Find the right Vantage Fit solution for your workforce, from wellness challenges to health assessment, workforce insights, rewards, and the complete wellness platform.

### Hero

**Eyebrow:** Vantage Fit solutions

**H1:** Choose the wellness job you need to solve

**Body:** Start with a program to run, a workforce signal to understand, or the complete employee wellness platform.

**Jump links:** Run a challenge / Measure and motivate / Explore the platform

### Platform rail

**Label:** The complete system

**Heading:** Looking for an employee wellness platform?

**Body:** See how Vantage Fit connects the employee experience, HR program controls, participation signals and rewards in one operating model.

**CTA:** Explore the wellness platform

### Column 1: Wellness challenges

**Label:** What you want to run

**Heading:** Wellness challenges

**Intro:** Choose a ready-to-run program or start with a format that fits your workforce.

- **Wellness challenges** · Library
  - Browse the full challenge library and choose a useful starting point.
  - CTA: Browse the library
- **Step challenges**
  - Create a simple shared movement goal with individual or team competition.
  - CTA: Explore step challenges
- **Multi-activity challenges**
  - Let different activities contribute to one inclusive program.
  - CTA: Explore multi-activity challenges
- **Remote and hybrid team challenges**
  - Connect teams across locations through shared wellness goals.
  - CTA: Explore remote team challenges
- **Virtual marathon**
  - Turn accumulated steps into a distance event with clear progress.
  - CTA: Explore virtual marathon

### Column 2: Workforce health and rewards

**Label:** Measure and motivate

**Heading:** Workforce health and rewards

**Intro:** Establish a baseline, understand the response, then reinforce useful action.

1. **Health Risk Assessment** · Data in
   - Run a voluntary assessment that gives employees personal results and HR an aggregate workforce baseline.
   - CTA: Explore Health Risk Assessment
2. **Workforce health insights** · Data out
   - Read participation, challenge, activity and aggregate health-risk signals in one decision view.
   - CTA: Explore workforce insights
3. **Wellness rewards program** · Action
   - Connect points and gift card redemption to completed tasks and recognized effort.
   - CTA: Explore wellness rewards

### Decision prompt

**Heading:** Not sure where to start?

**Option 1:** Need a fast participation moment? Browse Wellness challenges and pick a program employees can understand quickly.

**Option 2:** Building a broader operating model? Start with the Wellness platform to see how employee participation and HR decisions connect.

### Final CTA

**Heading:** Bring us the outcome you are working toward

**Body:** We will help you map the right mix of programs, signals and rewards for your workforce.

**Primary CTA:** Book a demo

**Secondary CTA:** See pricing

## Exact routes

| Destination | Intended route | Mock sibling |
|---|---|---|
| Solutions hub | `/solutions/` | `vantage-fit-solutions-hub-v1.html` |
| Wellness platform | `/solutions/wellness-platform/` | `vantage-fit-wellness-platform-v1.html` |
| Wellness challenges | `/solutions/wellness-challenges/` | `vantage-fit-wellness-challenges-v1.html` |
| Step challenges | `/solutions/step-challenges/` | `vantage-fit-steps-challenge-v1.html` |
| Multi-activity challenges | `/solutions/multi-activity-challenges/` | `vantage-fit-multi-activity-challenge-v1.html` |
| Remote and hybrid team challenges | `/solutions/remote-team-wellness/` | `vantage-fit-team-challenge-v1.html` |
| Virtual marathon | `/solutions/virtual-marathon/` | `vantage-fit-virtual-marathon-v1.html` |
| Health Risk Assessment | `/solutions/health-risk-assessment/` | `vantage-fit-health-risk-assessment-v1.html` |
| Workforce health insights | `/solutions/workforce-health-insights/` | `vantage-fit-workforce-health-insights-v1.html` |
| Wellness rewards program | `/solutions/wellness-rewards-program/` | `vantage-fit-wellness-rewards-v1.html` |

The HTML mock uses local sibling filenames for solution routes so the prototype remains navigable from disk. The intended production paths are recorded above.

## Sources

- `menu/vantage-fit-solutions-menu-preview.html`
- `REMAINING-SOLUTIONS-PROMPT.md`
- `../../../vc-os/vfit-os/MISSION.md`
- `../../../vc-os/vfit-os/FEATURE-INDEX.md`
- `../../../vc-os/vfit-os/specs/02-challenges-gamification/challenge-system-overview.md`
- `../../../vc-os/vfit-os/specs/03-health-wellness/health-risk-assessment.md`
- `../../../vc-os/vfit-os/specs/08-rewards-marketplace/points-rewards.md`
- `../../../vc-os/vfit-os/specs/09-admin-platform/reports-analytics.md`
- `../../../vc-dashboard-design/docs/modules/wellness.md`
- `../../../vantagefit-astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md`
- `../../../vantagefit-astro/content/en/help/admin/reports/admin-what-reports-are-available.md`

No external statistics or customer claims are used.
