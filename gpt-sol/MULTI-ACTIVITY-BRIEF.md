# Multi-activity challenge page brief

## Page decision

**Subject:** Vantage Fit Custom, also called Multi-Week Multi-Activity, challenges.

**Audience:** US enterprise HR, Benefits, Wellbeing, and CHRO buyers. Program managers are the secondary reader. IT and privacy reviewers should be able to understand the data boundary without hunting for it.

**Single job:** Show that one challenge can give a varied workforce several credible ways to participate, while HR still runs one coherent, measurable program.

**Primary CTA:** Book a demo  
**Secondary CTA:** See pricing

The page leads with participation, not an activity catalog. The product is useful because HR can compose weekly themes and tasks into one program, employees can contribute through different habits, and the results still resolve into one challenge experience.

## Research takeaways

Paths in this section are exact paths from the design-repository root in this worktree.

### What the product supports

- Custom is the product's most flexible challenge format. It is a multi-week program with independent weekly names, imagery, colors, and multiple tasks per week. Admins can set daily or weekly targets and per-task points. Source: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-custom-challenge.md`.
- The current help catalog documents **27 task types** across movement, workouts and strength, mind and body, nutrition and hydration, health tracking and vitals, content, and specialized habits. Some tasks auto-track, some are logged, and some complete through an in-app event. Availability depends on company configuration, and Lite Mode supports steps only. Source: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md`.
- A challenge can include auto-tracked activity, manual logs, custom activities, adherence check-ins, content, and upload tasks. Employees see overall percentage, today's progress, target counters, and a week selector. Source: `../../../vantagefit-astro/content/en/help/employee/challenges/how-do-i-complete-challenge-tasks.md`.
- HR can create company-specific loggable activities such as Walking Meeting or Office Yoga. Adherence activities support yes/no daily habits and can persist outside a challenge. Sources: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-custom-activities.md` and `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-adherence-activities.md`.
- Pre-built templates provide a configurable starting point with format, tasks, targets, scoring, and themes already set. HR can still change dates, audience, tasks, targets, points, teams, certificates, and rewards. Source: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-use-templates.md`.
- Audience rules can filter by country, city, department, gender, age range, language, or health risk code. Matching employees can be enrolled immediately or when they become active. Filtered challenges become private. Source: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md`.
- Teams are optional in a Custom challenge. Admin-created and employee-created teams are supported subject to configuration, and team score is the average of member scores. Sources: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-custom-challenge.md` and `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-manage-teams.md`.
- While a challenge is active, HR can manage upcoming themes and tasks, participants, teams, notifications, dates, and challenge controls. Score, steps, and team leaderboard views are available, along with CSV export. Source: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-manage-challenge.md`.
- A single program can run across time zones with localized daily boundaries. Source: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-can-i-run-challenges-across-time-zones.md`.
- Employees can hide from individual leaderboard rankings and keep participating and earning points. HR sees participation and challenge ranking data, but not an individual's weight, HRA answers, lab results, mood log, or food diary. Sources: `../../../vantagefit-astro/content/en/help/employee/challenges/can-i-opt-out-of-leaderboard.md` and `../../../vantagefit-astro/content/en/help/employee/getting-started/what-is-data-privacy.md`.

### Admin and OS corroboration

- The dashboard redesign models Custom as the distinct multi-activity family, with pre-built templates as editable seeds and a true weeks-by-activities builder. It also models audience resolution, per-task configuration, reward denomination, and the create/manage lifecycle. Sources: `../../../vc-dashboard-design/docs/superpowers/specs/2026-07-19-create-challenge-wizard-redesign-PROMPT.md`, `../../../vc-dashboard-design/crud-schema-spike/challenge.schema.ts`, and `../../../vc-dashboard-design/vc-data.js`.
- The OS spec maps Custom to `vfit_campaign`, with multiple tasks per week, per-week visual identity, daily or weekly target mode, and company-dependent task availability. Source: `../../../vc-os/vfit-os/specs/02-challenges-gamification/challenge-custom.md`.
- The challenge system and admin specs corroborate enrollment, live management, leaderboards, notifications, exports, and completion processing. Sources: `../../../vc-os/vfit-os/specs/02-challenges-gamification/challenge-system-overview.md`, `../../../vc-os/vfit-os/specs/02-challenges-gamification/leaderboards.md`, `../../../vc-os/vfit-os/specs/09-admin-platform/admin-dashboard.md`, and `../../../vc-os/vfit-os/specs/09-admin-platform/reports-analytics.md`.

### Approved proof

JF Petroleum's case study directly names multi-activity challenges covering nutrition logging, hydration, sleep, squats, weight tracking, and mindfulness. It reports that multi-activity participation grew from **38% at launch to 65% at peak** during its 52-week program. The page uses only that tightly related result and does not imply that every customer will achieve it. Source: `../../../vantagefit-astro/content/en/casestudy/jf-petroleum-vantage-fit-case-study.md`.

### What the legacy page under-sells

The old page treats the solution mainly as a list of activity choices, a unified tracker, a leaderboard, and pre-planned tasks. It misses or underweights:

- the weeks-by-tasks program model;
- templates as editable starting points;
- daily versus weekly targets and balanced scoring;
- auto-tracked, logged, and event-based task behavior;
- custom activities and adherence habits;
- precise audience rules and auto-enrollment;
- in-flight management, notifications, and reporting;
- employee leaderboard choice and the boundary around personal health data.

Historical source reviewed for gaps only: `../../../vantagefit-astro/content/en/pages/use-cases/multi-activity-challenges.yaml`.

## Positioning and claim boundaries

The page uses **27 task types** because that count is explicit in the current help documentation. It also says that available tasks depend on company configuration. It does not claim that every tenant has every task.

The page describes variety as a way to create more relevant entry points. This is a product and program-design inference, not a quantified performance promise. The only customer result is the approved JF Petroleum figure.

All employee and admin UI numbers in the mock are labeled **Illustrative**. No customer, participation rate, completion rate, or time-to-launch figure is fabricated.

## Narrative and information architecture

1. **Hero:** “One challenge. More ways to take part.” Show the employee's current week beside the admin's four-week program canvas. This proves the core idea before explaining it.
2. **Participation logic:** Three concise reasons the format broadens the invitation: choice, weekly freshness, and one shared outcome.
3. **Weekly program canvas:** Explain how weekly themes, multiple tasks, daily or weekly targets, and points become a coherent program rather than a feature pile.
4. **Activity breadth:** Make the documented 27-task range scannable by participation mode and wellness dimension. Include the configuration caveat.
5. **HR control:** Show template-or-scratch setup, audience selection, in-flight nudges, and exportable results in one admin surface.
6. **Privacy note:** Keep the distinction crisp: challenge participation is visible; private health records are not. Mention leaderboard opt-out.
7. **Program proof:** Use one compact JF Petroleum result because it is specifically related to multi-activity participation.
8. **FAQ:** Handle configuration, tracking, teams, privacy, and global rollout objections.
9. **Closer:** Reconnect choice for employees with proof for HR.

## Design plan developed before build

### Tokens

- **Vantage ink:** `#29294C`
- **Participation coral:** `#F15162`
- **Progress mint:** `#41D8B4`
- **Habit amber:** `#F6B93B`
- **Cloud canvas:** `#F8F8F9`
- **Paper:** `#FFFFFF`

The palette is inherited from `../styles/enterprise.css`. Coral marks decisions and CTAs, mint marks completed progress, and amber identifies habits that need an employee check-in. These meanings are maintained in the product mocks.

### Type

- **Display:** Poppins, used only for large headings and the proof number. Its round geometry suits the weekly blocks and matches the consolidated Steps reference.
- **Body and UI:** Noto Sans, matching the enterprise homepage and shared CSS.
- **Utility:** Noto Sans in compact uppercase labels with restrained tracking for weeks, modes, and status.

### Layout options considered

Option A was a conventional left-copy, right-phone hero followed by activity cards. It was rejected because it could describe any fitness app and makes the defining multi-week structure secondary.

Option B, selected, uses a wide product canvas as the hero thesis:

```text
+-----------------------+--------------------------------------+
| One challenge.        | ADMIN PROGRAM CANVAS                 |
| More ways to take     | Week 1 | Week 2 | Week 3 | Week 4  |
| part.                 | Move   | Nourish| Reset  | Thrive  |
| [CTAs]                |    EMPLOYEE CURRENT-WEEK CARD        |
+-----------------------+--------------------------------------+
```

The deeper product section expands the same object instead of introducing a second visual metaphor:

```text
+------------------------------+-------------------------------+
| Why weekly themes work       | PROGRAM THREAD                |
| Daily and weekly targets     | W1 -> W2 -> W3 -> W4         |
| One score across task types  | task rows inside each week    |
+------------------------------+-------------------------------+
```

### Signature

The page's signature is the **program thread**, a connected four-week canvas where each week has a distinct theme and task mix, but one coral line carries progress through the whole program. It encodes the actual product structure and makes “multi-activity” feel like a designed program rather than a bag of features.

### Plan critique and revision

The first plan leaned on a grid of colorful activity category cards. That read as a generic wellness marketplace and spent visual emphasis on taxonomy instead of the product's real differentiator. I revised it so the week canvas carries the visual weight, while the task catalog becomes a compact, filterable utility panel. I also removed a proposed abstract gradient illustration and an extra KPI strip. The only large number is approved customer proof. This keeps boldness in one place and stays aligned with the lean Steps-page direction.

## Full copy deck

### Navigation

- Brand: Vantage Fit
- Links: Why multi-activity · How it works · For HR · Questions
- CTA: Book a demo

### Hero

**Eyebrow:** Multi-activity challenge

**H1:** One challenge. More ways to take part.

**Body:** Build a multi-week program around movement, hydration, mindfulness, nutrition, sleep, and learning. Employees follow one clear weekly plan. HR sees one measurable challenge.

**CTAs:** Book a demo · See pricing

**Proof points:** 27 task types · Daily or weekly targets · Templates or build from scratch

**Product mock:**

- Program canvas
- 4-week wellbeing reset
- Week 1 Move · Week 2 Nourish · Week 3 Reset · Week 4 Thrive
- Employee card: This week · Nourish · 3 of 4 tasks on track
- Walk 35,000 steps · 28,440 complete
- Drink water on 5 days · 4 days complete
- Read: Building a balanced plate · Complete
- Log one healthy meal · Pending
- Illustrative employee view

### Participation logic

**Eyebrow:** Built for broader participation

**H2:** A single metric is not everyone's way in.

- **Offer credible choice:** Mix auto-tracked movement with simple logs, content, and habit check-ins.
- **Renew the invitation weekly:** Change the theme and task mix before the program starts to feel repetitive.
- **Keep one shared outcome:** Different activities earn points inside one challenge, so participation stays measurable.

### Program canvas

**Eyebrow:** The multi-week builder

**H2:** Plan a story, not a pile of tasks.

**Body:** Give each week a theme, visual identity, and mix of activities. Set daily or weekly targets, weight task points, and show employees exactly what matters now.

**Week tabs:** Move · Nourish · Reset · Thrive

**Selected week copy:**

- Week 2 · Nourish
- A practical week for hydration, nutrition awareness, and everyday movement.
- Water log · Daily target · 5 days
- Meal log · Weekly target · 3 logs
- Steps · Weekly target · 35,000
- Content reading · One time · Balanced plate
- Employee-created teams optional
- Completion certificates optional

### Activity breadth

**Eyebrow:** 27 documented task types

**H2:** Combine the habits your program is actually trying to build.

**Body:** Use auto-tracked activity for low-friction progress, quick logs for awareness, and in-app content or check-ins for learning and consistency.

**Filters:** All · Auto-tracked · Quick log · In-app event

**Sample task labels:** Steps · Distance · Active minutes · Yoga · Strength · Meditation · Mindfulness · Water · Meals · Sleep · Mood · Heart rate · Weight · Health assessment · Content · Video workout · Book reading · Custom activity · Adherence

**Caveat:** Task availability depends on company configuration. Lite Mode supports step-based challenges only.

**Privacy note:** Personal stays personal. HR can see challenge participation and rankings. Individual weight, HRA answers, lab results, mood logs, and food diaries remain private. Employees can also hide from individual leaderboards and keep participating.

### HR control

**Eyebrow:** Control for HR

**H2:** Start with a template. Make it yours. Run it from one place.

- **Choose a starting point:** Use a pre-built multi-activity template or build each week from scratch.
- **Set the right audience:** Invite everyone or use audience rules, then auto-enroll eligible employees.
- **Manage the live program:** Update upcoming themes, send participant notifications, and manage teams or dates.
- **Close with usable results:** Review score, steps, and team views, then export leaderboard data to CSV.

**Admin mock:**

- 4-week wellbeing reset · Ongoing
- Program health · Illustrative
- Enrolled 1,240
- Active this week 72%
- On track 684
- Week 2 participation by task
- Steps 78%
- Water 69%
- Content 61%
- Meal log 54%
- Next action: Nudge 146 participants with a pending task
- Send notification · Export CSV

### Proof

**Label:** Customer program result

**Stat:** 38% → 65%

**Copy:** Multi-activity participation grew from launch to peak during JF Petroleum's 52-week wellness program.

**Context:** JF Petroleum used multi-activity challenges across nutrition, hydration, sleep, squats, weight tracking, and mindfulness. Results are specific to this customer program.

### FAQ

**H2:** Questions before you build the first week

**Can we start from a template and still change it?**  
Yes. Pre-built templates seed the themes, tasks, targets, and scoring. Your team can change the dates, audience, activities, goals, points, teams, certificates, and rewards before publishing.

**How do employees complete different task types?**  
Steps, distance, calories, and active minutes can sync automatically from supported sources. Other tasks use a quick log, a daily check-in, or a specific in-app action such as reading content. The task card tells the employee what to do.

**Can we run it as a team challenge?**  
Yes. Custom challenges can support teams. HR can create teams and bulk assign members, or employee-created teams can be enabled for the company. Team standings use average member scores.

**What does HR see when tasks include personal health habits?**  
HR can see participation, challenge scores, and leaderboard position. Individual weight, HRA answers, lab results, mood logs, and food diaries are not visible to admins. Employees can opt out of individual leaderboards without leaving the challenge.

**Will daily tasks work across global time zones?**  
Yes. Daily boundaries, start times, and end times follow each participant's local time zone within a global challenge.

### Final CTA

**H2:** Build one challenge more of your workforce can join.

**Body:** See how weekly themes, varied activities, and one HR workflow come together in Vantage Fit.

**CTAs:** Book a demo · See pricing

**Demo callouts:** Bring your wellness goals · Review task availability · Map the first four weeks · Plan reporting

## SEO drafts

**Meta title:** Multi-Activity Employee Wellness Challenges | Vantage Fit

**Meta description:** Build multi-week employee wellness challenges with varied activities, weekly themes, flexible targets, audience controls, and measurable results in Vantage Fit.

**Suggested H1:** One challenge. More ways to take part.

**Canonical context:** `https://www.vantagefit.io/multi-activity-challenges/`

