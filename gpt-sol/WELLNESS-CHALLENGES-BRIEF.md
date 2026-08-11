# Wellness challenges page brief

## Page job

Help an HR or wellbeing leader choose a useful starting program, then make the next step feel simple. This is the flagship entry to the challenge library, not a page for one challenge format.

**Intended URL:** `/solutions/wellness-challenges/`

## Audience and buying question

- Primary: US enterprise HR, benefits, and wellbeing leaders
- Secondary: program managers who will configure and run challenges
- Core question: “Which kind of challenge fits our workforce and goal?”

## Product truth used

- Vantage Fit supports five self-serve formats: Custom, Race, Journey, Streak, and E-Marathon.
- Custom challenges can combine weekly themes and task types. Race is a step competition. Journey uses visual milestones. Streak focuses on daily consistency. E-Marathon converts steps into distance.
- Specialized, account-managed formats include Level, Marathon Event, Weight Burn, and Training Plans.
- Challenge programs can be individual, team-based, or both, depending on configuration.
- Admins can configure dates, tasks, teams, target audiences, and rewards. They can also start with pre-built templates.
- The live challenge library currently spans physical fitness, mental wellness, nutrition, sleep and recovery, and team and social goals.
- Multiple challenges can run at the same time, with separate progress, points, and rankings.
- Target audiences can be scoped by organization attributes such as country, city, and department. The product also supports company-enabled health risk targeting.
- Global challenges localize daily resets to each participant’s time zone.

No customer results, completion rates, or setup-time claims are used on the page.

## Narrative and structure

1. **Chooser hero:** Lead with the buyer’s decision, not a broad category claim. A compact “program shelf” visually establishes breadth.
2. **Goal-first jump rail:** Let buyers begin with the outcome they recognize: move more, build habits, support recovery, strengthen connection, or run an event.
3. **Interactive program library:** Category filters reveal a curated, source-backed set of program cards. Each card names its goal, participation mode, and challenge format.
4. **Format guide:** Explain the five self-serve mechanics in one scannable row so buyers can distinguish a program theme from the product format underneath it.
5. **One admin workflow:** Show the real sequence from selecting a format to launching and reviewing participation.
6. **Enterprise control band:** Address global time zones, audience targeting, parallel programs, and rewards without turning the page into a feature dump.
7. **Short FAQ and CTA:** Resolve practical buying questions and invite a tailored recommendation.

This structure makes the page a real library and chooser. It avoids reusing the narrative of a single-format challenge page.

## Visual direction

The page uses the shared Vantage Fit enterprise system: Noto Sans, coral action color, deep navy, mint status accents, soft gray canvas, pill CTAs, and disciplined rounded cards.

The signature element is a filterable “program shelf” with a persistent results count. It turns the product’s breadth into a useful decision surface. The aesthetic risk is the compact editorial catalog treatment inside an otherwise restrained SaaS page. It is specific to a library page and does not carry into HRA.

## Full copy deck

### Hero

**Eyebrow:** Wellness challenges

**Headline:** Find the challenge your workforce will want to join

**Body:** Start with the outcome you want, then choose a format that fits. Run focused programs for movement, healthy habits, recovery, connection, and company-wide events.

**Primary CTA:** Book a demo

**Secondary CTA:** Browse the library

**Utility line:** Individual and team options · Self-serve and supported formats · Programs for distributed workforces

### Goal-first rail

**Heading:** Start with the behavior you want to support

- Move more: Steps, cardio, cycling, and strength
- Build a daily habit: Consistency through repeatable actions
- Support recovery: Sleep, breathwork, and boundaries
- Bring teams together: Shared goals and friendly competition
- Create an event: Virtual distance and live GPS formats

### Library

**Eyebrow:** Program library

**Heading:** Browse a starting point

**Body:** Filter by wellbeing goal. Each program can be configured for the audience, dates, tasks, and rewards that fit your organization.

**Filters:** All programs · Physical fitness · Mental wellness · Nutrition · Sleep and recovery · Team and social

Program card copy follows the source library names and concise, buyer-facing descriptions. Cards identify their underlying format and whether they support individual, team, or both participation modes.

### Format guide

**Eyebrow:** Choose the mechanic

**Heading:** One goal can work in different ways

- Custom: Combine weekly themes, tasks, content, and activities.
- Race: Build energy around a straightforward step leaderboard.
- Journey: Turn progress into a visual route with milestones.
- Streak: Reinforce a daily target through consistency.
- E-Marathon: Convert steps into progress toward a chosen distance.

**Supporting line:** Specialized formats such as Level, Marathon Event, Weight Burn, and Training Plans are set up with your Vantage Fit account team.

### Workflow

**Eyebrow:** From idea to active program

**Heading:** Give every challenge a clear path to participation

1. Pick a format or template: Match the mechanic to your goal and audience.
2. Configure the experience: Set dates, tasks, teams, eligibility, and optional rewards.
3. Launch and follow along: Employees join in the app while HR manages the active program.
4. Learn and plan the next one: Review participation and use what worked to shape the next challenge.

### Enterprise controls

**Heading:** Built for a program, not just a leaderboard

- Target the right audience: Scope eligibility by location, department, and other supported criteria.
- Run across time zones: Daily goals reset in each participant’s local time.
- Layer your calendar: Run separate challenges in parallel, each with its own progress and ranking.
- Connect effort to rewards: Configure points and rewards where they support the program.

### FAQ

**Can we run more than one challenge at a time?** Yes. Each active challenge keeps its own progress, points, completion criteria, and rankings.

**Do all challenges need to be step based?** No. Custom challenges can combine activities, manual logs, content, uploads, quizzes, and adherence tasks. Other formats focus on steps, distance, or daily consistency.

**Can we launch challenges for specific groups?** Yes. Admins can use supported audience filters to control eligibility and visibility.

**How do global challenges handle different time zones?** Daily targets reset at midnight in each participant’s local time, so each person receives a local calendar day.

### CTA

**Heading:** Choose a challenge with a reason behind it

**Body:** Tell us the behavior, audience, and timeline you have in mind. We’ll help you map it to the right program and format.

**Primary CTA:** Book a demo

**Secondary CTA:** See pricing

## Metadata draft

**Meta title:** Employee Wellness Challenges for Every Workforce | Vantage Fit

**Meta description:** Browse employee wellness challenge ideas for movement, habits, recovery, team connection, and virtual events. Choose the right Vantage Fit format for your workforce.

## Solutions IA fit

This page is the flagship first entry in mega-menu column ①, **Wellness challenges**. It links buyers into focused challenge solutions while remaining the broad goal-and-program chooser. It should be reachable from `/solutions/` and should link back to that hub in breadcrumbs and footer navigation.

## Sources

- `../../../vantagefit-astro/src/data/wellness-challenges.ts`
- `../../../vantagefit-astro/src/data/wellness-challenge-thumbnails.js`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-what-challenge-formats.md`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-a-challenge.md`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-custom-challenge.md`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-use-templates.md`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-can-i-run-multiple-challenges-in-parallel.md`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md`
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-can-i-run-challenges-across-time-zones.md`
- `../../../vc-os/vfit-os/specs/02-challenges-gamification/challenge-system-overview.md`
- `../menu/vantage-fit-solutions-menu-preview.html`
- `../styles/enterprise.css`
- `../consolidated/vantage-fit-multi-activity-challenge-consolidated.html`

