# Vantage Fit — Team Challenge Solutions Page Brief (v1)

Model workspace: `claude-fable` · Deliverable pair: this brief + `vantage-fit-team-challenge-v1.html` (1,512 lines)
Baseline: `../styles/enterprise.css` + `../styled-homepage/` · Sibling program page: `vantage-fit-steps-challenge-v1.html` · Hub: `../solutions-page/vantage-fit-solutions-v1.html`
Live page rebuilt: `https://www.vantagefit.io/team-challenges/` · URL unchanged
Filename note: the orchestrator passed `pageLabel` through as the literal string `undefined`, so this brief was written to `TEAM-CHALLENGE-BRIEF.md` to match the sibling naming. See §9.1.

---

## 1. What this page is

This is the page an HR buyer opens when they already run a step challenge and it keeps landing on the same fit third of the company. The program is a **team challenge**: employees compete in named teams (departments, sites, squads) inside a Custom, Journey or Streak challenge, and the team's rank is the **average of its members' individual scores, never the sum**. The buyer is a US enterprise HR, CHRO, benefits or wellbeing leader, with the program manager who will actually build the rosters reading over their shoulder, and a privacy reviewer waiting at the end of the process.

The page does exactly one job: **make the buyer believe that averaging changes who shows up.** An individual leaderboard rewards the fittest person in the building. A team-average leaderboard makes the least active person the highest-value recruit on every roster, because the cheapest point available to any team is the colleague who has not started yet. Everything else on the page (who is in the average, which formats carry teams, how HR builds and proves it, the customer results, the privacy boundary) exists to support or de-risk that one arithmetic claim. Primary CTA is **Book a demo**, four instances, identical label. Secondary is **See pricing**, two instances. Ten sections, roughly 1,050 words of body copy.

The live page today makes the opposite bet: it asserts inclusivity four times without ever naming the mechanism, and headlines a relabelled statistic. This rebuild publishes the mechanism and drops the relabel.

---

## 2. Research takeaways

Audited: the live page source (`content/en/pages/use-cases/team-challenges.yaml`), the help-doc corpus (`content/en/help/admin/challenges/`, `admin/reports/`, `admin/settings/`, `admin/communication/`, `employee/challenges/`, `employee/getting-started/`), the code-verified product specs (`vfit-os/specs/`), the admin dashboard designs (`vc-dashboard-design/`), and the approved-claims rules (`vfit-os/.claude/rules/data-accuracy.md`).

Path shorthand used below: `HELP` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/` · `VOS` = `/Users/anjanpathak/work/vc-os/vfit-os/`

### 2.1 The structural fact the live page never states

**There is no "Team Challenge" format.** Teams are a toggle inside three formats. Custom exposes it at Step 6 of 9 (`HELP/admin/challenges/admin-how-do-i-create-custom-challenge.md:99`), Journey at Step 5 (`admin-how-do-i-create-journey-challenge.md:90-98`), Streak at Step 5 (`admin-how-do-i-create-streak-challenge.md:69-73`). Race explicitly has no team settings and no certificates (`admin-how-do-i-create-race-challenge.md:59`), and E-Marathon's setup article has no team step at all. The live page sells "team challenges" as a product; the page we built sells teams as a mode and names the one format that cannot carry them.

### 2.2 The scoring rule, which is the single most valuable unused asset in the corpus

Team score is the arithmetic mean of member scores. It is stated in five independent places: `HELP/admin/challenges/admin-how-do-i-manage-teams.md:19-22`, `admin-how-do-i-create-custom-challenge.md:108`, `admin-how-do-i-create-journey-challenge.md:96`, `admin-how-do-i-create-streak-challenge.md:73`, and the code-verified `VOS/specs/product/02-challenges-gamification/challenges.md:99`. The docs also supply the consequences, in publishable sentences:

- "A team of 5 where everyone scores 80 beats a team of 10 where the average is 70. Adding inactive members pulls the team average down." (`admin-how-do-i-manage-teams.md:19-22`)
- "A team of 5 where everyone hits 80% scores higher than a team of 5 where 3 people hit 100% and 2 people do nothing." (`HELP/employee/challenges/how-do-teams-work.md:61`)
- "Team averaging encourages participation from every member, not just the top performers. It is the fairest model for team competition." (`admin-how-do-i-manage-teams.md:24`)

The live page says "inclusive for all" four times and never once says why. The mechanism was sitting in the help centre the whole time.

One employee-facing web article calls the team score "combined", which contradicts all five sources above. It was excluded per the foundation's contradiction ruling C2 and is not cited anywhere on the page.

### 2.3 Capabilities the live page under-sells or misses entirely

1. **Three team-build routes, not one.** The live FAQ says "admin configures teams from HR-provided specs". Reality: dashboard one at a time; **bulk upload from CSV or Google Sheets** with an exact template contract (column A team name, column B employee email, one row per person); captain-led in-app; plus an account-manager-coordinated programmatic route. `admin-how-do-i-manage-teams.md:28-75`; endpoints `bulkCreateTeamsFromGoogleSheet` / `bulkCreateTeamsFromDashboard` at `VOS/specs/05-social-community/teams.md:84-85`.
2. **Mid-flight roster surgery that is arithmetically safe.** Moving a member preserves their individual score and recomputes both team averages (`admin-how-do-i-manage-teams.md:99-106`). Late joiners score from their join date forward (`admin-how-do-i-add-remove-participants.md:61-69`; `challenges.md:49`). Removed participants keep their historical data in reporting and receive no further notifications (`admin-how-do-i-add-remove-participants.md:40-49`). Competitors freeze rosters at kickoff or say nothing.
3. **Leaderboard opt-out that still contributes to the team average.** Verbatim: "Your scores still count for your team... Opting out hides you from the individual leaderboard, but your team benefits from your effort." (`HELP/employee/challenges/can-i-opt-out-of-leaderboard.md:29`). This is the whole answer to "some of my people will hate being ranked", and it is completely absent from the live page.
4. **Nobody signs up.** Two entry paths only, auto-enrolled or admin-added, with "Action Required? None, you're already in" (`HELP/employee/challenges/how-do-i-join-a-challenge.md`). Code-verified: "There is no browse-and-join flow" (`challenges.md:42`). This inverts the category's registration-campaign framing and the live page never uses it.
5. **Max team size is a creation-time setting binding both build routes**, with a documented 4 to 6 best practice and the stated reason that larger teams dilute individual accountability (`admin-how-do-i-manage-teams.md:108-116`).
6. **The team leaderboard expands to member contribution**, sits beside Score and Steps, and the CSV export carries a **Team name** column alongside name and email, department and country, score and rank, step count and per-task scores (`HELP/admin/reports/admin-how-do-i-view-leaderboard.md:43-102`).
7. **Global fairness.** Daily targets reset at each participant's local midnight, so a 30-day challenge is a true 30 calendar days for everyone (`admin-can-i-run-challenges-across-time-zones.md`). No competitor page in the category says this.
8. **A published CAN/CANNOT data boundary** (`HELP/admin/settings/admin-data-privacy-security.md`), and audience filters that force a challenge private (`admin-how-do-i-set-target-audience.md:41`).

### 2.4 Live-page claims that could not survive

| Live claim (`content/en/pages/use-cases/team-challenges.yaml`) | Why it was dropped |
|---|---|
| H1 "Team challenges that drive **70% participation**." | Tata Motors' 70% is an **engagement rate** as the customer measured it (`VOS/.claude/rules/data-accuracy.md:50-67`). Relabelling it as participation is a P0 accuracy defect. |
| "Set up team-based step, fitness, and **weight** challenges in **under 10 minutes**." | "Under 10 minutes" is unverified in that form; the only sourced duration is "Creating a challenge takes 5-10 minutes" and it covers the wizard only (`admin-how-do-i-create-a-challenge.md:13`). Weight Burn is an ops-only format, so bundling it into a self-serve promise is a second, separate overclaim. |
| "Inclusive for all", four times, no mechanism | Replaced with the averaging arithmetic and a leaderboard panel that demonstrates it. |
| "consider team building options such as **relay races and group yoga sessions**" | NOT FOUND IN SOURCES. There is no relay format; yoga exists only as a loggable task type. |
| FAQ "How do we form teams?" → admin configures from HR specs | Understates by three routes. |
| FAQ "How do you ensure inclusivity?" → "Challenges within Vantage Fit inherently promote inclusivity" | Circular, unsourced. |
| "Realtime leaderboard" card | Product-true but duplicated verbatim across Steps, Team and Virtual Marathon. Not a team differentiator; demoted to a status chip inside the panel. |

### 2.5 Limits found in research that the page states out loud rather than hides

Captain-led team creation and employee team management are account-manager enabled and **off by default** (`admin-how-do-i-manage-teams.md:75`; `challenges.md:174-175`). Bulk upload **silently skips mismatched emails** (`admin-how-do-i-manage-teams.md:57`). There is **no scheduled report, no exec digest, no shareable dashboard link**; exports are manual CSV clicks (`admin-how-do-i-view-leaderboard.md:104-110`). Challenge reminder emails are **disabled by default** and AM-gated, so no "automatic reminders keep momentum" claim appears anywhere. Force Stop **cannot be undone** (`admin-how-do-i-manage-challenge.md:111`). Per-task and per-week breakdowns are a Custom-challenge capability, not universal. Each of these is printed on the page. Naming one limit is what buys belief in the rest.

---

## 3. Why this structure

Ten sections. The spine is: **claim the mechanism, prove the mechanism, widen the population it applies to, show where it runs, hand it to HR, then bring precedent, then clear privacy, then rollout ops, then the loop out, then the ask.**

| # | Section (`id`) | Surface | The belief it exists to create |
|---|---|---|---|
| S1 | Hero (`hero`) | Light gradient | "This vendor leads with arithmetic, not adjectives, and I can see the mechanism in the product before I scroll." |
| S2 | Fairness band (`scoring`) | White page, dark card | "Uneven teams are not a problem here, and I can check that claim myself during a trial." |
| S3 | Who is in the average (`participation`) | Canvas | "The average will actually cover my workforce, because nobody has to sign up and nobody needs a wearable." |
| S4 | Where teams run (`formats`) | White | "A team program is not automatically a step contest, and this vendor tells me which format cannot do it." |
| S5 | Control for HR (`hr`) | Canvas | "One program manager can build this at 6,000 people, and I know exactly what file I walk out with." |
| S6 | Customer results (`proof`) | `#f6f7f4` | "Real enterprises have run the team as the unit of competition and reported team-level outcomes." |
| S7 | Security and privacy (`security`) | Dark full-bleed | "Nothing here will fail privacy review, and the boundary is published rather than promised." |
| S8 | FAQ (`faq`) | White | "The rollout questions I would have raised on the call are already answered, including the awkward ones." |
| S9 | Related (`related`) | Canvas | "This is a system, not a single page, and I know which sibling page answers the thing this one did not." |
| S10 | Closer (`demo`) | Dark full-bleed | "One idea, said a third way, and a specific reason to take the meeting." |

### 3.1 The three placement decisions that carry the page

**S2 sits second, not fifth.** On every sibling page the objection band is a mid-page beat. Here the native objection *is* the differentiator, so the page proves the H1 immediately. Delaying it would have spent the buyer's attention on table stakes first.

**S3 sits third, and it is the merged enrollment plus employee-experience beat.** An averaging argument is worthless over a self-selected roster. Putting auto-enrollment immediately after the arithmetic, under the headline "An average only counts if everyone is in it", converts a table-stakes fact into the second half of the differentiator. This is the single highest-leverage structural move on the page.

**S6 sits after the mechanism, not before it.** "43 teams" is only interesting once the buyer believes averaging. Proof late, mechanism early.

### 3.2 Departures from the Steps consolidated flow

| Steps page beat | What this page does instead, and why |
|---|---|
| S2 five-format explorer, the Steps page's signature asset | Cut to **three cards plus a Race line**. Only Custom, Journey and Streak carry teams. Reproducing five formats here would repeat the sibling page and would imply teams on Race and E-Marathon, which is false. |
| S4 standalone anti-cheat / data-integrity dark band | Cut to **one clause inside `.fair-fine`**. On a team page the integrity question is "is the contest fair *between teams*", not "are the steps real". The dark band was repointed from data integrity to fairness. |
| S3 six-row employee experience | Kept as a pattern, but re-aimed. Rows now argue coverage of the average (nobody signs up, day one already on a team, no wearable, two boards, opt-out still counts, every time zone) rather than general delight. Badges, rewards wallet and wheelchair mode were dropped from the row set to keep it six rows and on-argument. |
| S6 four result cards plus a video quote | Same four-card grid, but **no video quote**. The only approved video asset is Rachel Arthur / Brazosport ISD, who is not approved for a team claim. Two text-only quotes instead. |
| No FAQ (dropped at review on the Steps page) | **FAQ restored here**, four rollout-ops questions, with FAQPage JSON-LD. The live template emits no structured data anywhere, so this is a free SEO win, and team rollout raises genuinely different operational questions (who groups the teams, what happens at churn) that do not fit inside a body section. |
| Related row of three light links | Same pattern. The `/multi-activity-challenges/` link is load-bearing rather than decorative: `vfit-os` names team-challenges and multi-activity-challenges as the worst-cannibalising pair on the site, so this page owns team formation, team averaging and inter-department competition, and hands multi-week task design to that page. |

### 3.3 Beats deliberately cut

- **A "here is what went wrong last time" diagnosis section.** Folded into two sentences of the hero lead. A whole section of diagnosis presumes the buyer's program is broken and costs 120 words on a lean page.
- **A rollout calendar or timeline rail.** No sourced duration for building teams exists. The only sourced figure is the 5 to 10 minute wizard, and it covers the wizard only.
- **A recognition and rewards section.** Badges and certificates are retention texture; certificates live in S5 tab B, badges are off the page entirely. Points and monetary rewards for challenge tasks are AM-gated to a very narrow footprint and are not presented as the participation engine. The engine here is social obligation plus averaging.
- **A third HR tab.** The design system is explicit that `.tour-tabs` is two tabs.
- **A comparison table or any named competitor.** The competitor lines in `VOS/specs/` are unverified Draft Set A assertions, and an outbound competitor link would need `rel="nofollow"`.
- **A separate four-card enrollment grid.** Merged into S3, so the page loses a grid without losing an argument.
- **Any commercial framing of team mode** ("at no additional cost", "already in your plan", tier language). No sourced statement exists.

### 3.4 Design signature

Three drawn product surfaces make the same argument at three altitudes, and all three are legible with the copy stripped out:

1. **Hero `.dash`**: the admin Team tab with a 5-member team at 80 above a 10-member team at 70, and a pill reading "Team score = average of member scores". The phone beside it shows the same standings in the employee app with a real Individual/Team segmented control.
2. **S2 `.audit-board`**: the money visual. Third place expanded to five member rows scoring 100, 100, 100, 0, 0, with an "Average of 5 members: 60" summation row. It shows superstar-carrying **losing**, which no vendor page in the category shows.
3. **S5 `.launch-mock` and `.report-mock`**: the Step 6 of 9 team-configuration panel with the CSV template docked beneath it (including one greyed row flagged "Email not matched, skipped"), and the leaderboard on the Team tab with an Export CSV button and an anchored callout listing the export's real columns plus a muted "Manual export. No scheduled digest." chip.

No trophy, podium, crown or confetti anywhere. Every drawn mock carries a visible **Illustrative data** tag and repeats that status in its `aria-label`. Five mocks, five `role="img"`, five visible tags.

---

## 4. The objection this program raises

**"The moment I split 4,000 people into teams, three things happen. Someone gets a team of eight and someone gets a team of four. One department quietly stacks its team with the cycling club. And one person on every team does 80% of the work while four people coast. Then I get the emails."**

Fairness is the native objection for this program, and it is also the differentiator, which is why it is S2 rather than a mid-page band. The page answers it with five sourced mechanics and one visual, not with reassurance.

| Sub-objection | Product answer on the page | Source |
|---|---|---|
| "One person will carry the team" | The average, not the total. Adding inactive members pulls the average down. The panel shows a team with three members at 100 and two at zero averaging 60, beneath a team of five who all did 80 averaging 80. | `admin-how-do-i-manage-teams.md:19-24`; `how-do-teams-work.md:61`; `challenges.md:99` |
| "Someone will stack their team" | Maximum team size is set at creation and applies to admin-created and employee-created teams alike. | `admin-how-do-i-manage-teams.md:108-114` |
| "My org churns; the teams will be wrong by week three" | An admin can move a member between teams. Their individual score is preserved and both team averages recompute. | `admin-how-do-i-manage-teams.md:99-106` |
| "Adding people mid-flight will look rigged" | Late joiners score from their join date forward, not from the start date. | `admin-how-do-i-add-remove-participants.md:61-69`; `challenges.md:49` |
| "The enthusiasts will run away with the board" | Non-step tasks earn points up to 100% of the daily target. Log five yoga sessions when three are required and you still earn points for three. | `admin-how-do-i-create-custom-challenge.md:94`; `ts-leaderboard-score-wrong.md` |
| "Some of my people will hate being ranked" (S3, and it is the privacy half of the same objection) | Leaderboard opt-out hides an employee from the individual leaderboard, and their activity still counts toward their team's average. | `can-i-opt-out-of-leaderboard.md:15-37` |

**Two honesty constraints, both binding and both respected in the shipped copy.**

1. The same help doc that supplies the averaging argument also advises keeping teams within one or two members of each other and calls unbalanced teams unfair. The page presents **balance as a recommendation** (`.fair-fine`) and **averaging as the mechanic** (`.fair-list`). It never claims size stopped mattering.
2. Because the mean is pulled down by inactivity, the argument sits one careless sentence away from "so drop your slowest colleague". Every rendering on the page frames the floor as the **opportunity**: "a team climbs fastest when the colleague who has not started yet gets going". Nothing on the page frames an inactive colleague as a liability to be shed. This is the sentence most likely to break in a future copy edit made by someone who has not read this brief.

**What the page refuses to claim on this objection.** No numeric anti-cheat threshold, no step-cap number, no "no ceiling" claim, no "fraud-proof", no "every step verified". Integrity gets one sourced clause about recognised sources and implausible-count filtering, and nothing more. There is also **no documented tie-break rule for a team leaderboard** anywhere in the corpus, so the page does not invent one.

---

## 5. Full copy deck (as shipped)

Every visible string on the page, in section order. `<em>` marks the coral-gradient span. One em-dash exists on the entire page, in the Niche Technology attribution.

### Page furniture

- **Meta title:** `Team Challenges for Employees: Fair Scoring | Vantage Fit`
- **Meta description:** `Team challenges scored on every member's average, not the fittest few. Tata Motors' Step Up & Elevate hit 70% engagement across 43 teams. Book a demo.`
- **Robots:** `noindex, nofollow` (mock only)
- **Nav:** Solutions (current section) · Features · Resources · Pricing · **Book a demo**. In the Solutions mega, **Team Challenge** is `is-page` / `aria-current="page"` with `href="#top"`, and Steps Challenge is restored to its live href. Mega banner: "See every program on one page: the Solutions overview".
- **Footer bottom row:** `© 2026 Vantage Circle. All rights reserved.` · `HIPAA guidelines · SOC 2 Type II` · `Wellness built for participation.` Footer brand line: "Inclusive wellness that turns participation into measurable progress." Solutions column carries `aria-current="page"` on **Team challenges**.

### S1 Hero

- Eyebrow: `Solutions · Team Challenge`
- H1: `Team fitness challenges scored on the <em>average</em>, not the total.`
- Lead: `Your last team challenge probably reached the people who were already active. A Vantage Fit team's score is the average of everyone on it, so the fastest way for a team to climb is to get its quietest colleague moving.`
- Buttons: `Book a demo` (primary) · `See pricing` (outline)
- Hero notes: `Nobody signs up to take part` · `Individual and team boards in one challenge` · `No wearable required`
- Admin mock: `Admin · Challenges` / `Step Up Together` · tabs `Score` `Steps` **`Team`** · pill `Team score = average of member scores` · columns `Rank` `Team` `Members` `Team score` · rows `1 Assembly Line A 5 members 80` / `2 Central Ops 10 members 70` / `3 Warehouse East 5 members 60` / `4 Finance Floor 2 6 members 58` · tag `Illustrative data`
- Phone mock: `Vantage Fit` · segmented `Individual` / **`Team`** · sub-segment **`Weekly`** / `Overall` · rows `Assembly Line A 5 members 80 #1` / `Central Ops 10 members 70 #2` / `Warehouse East 5 members 60 #3` · CTA `View my breakdown` · tag `Illustrative data`
- Logo band: `Trusted by 100+ organizations worldwide` · TATA MOTORS · WIPRO · TEVA · GODREJ · TEXAS INSTRUMENTS · HEIDRICK & STRUGGLES · BRAZOSPORT ISD

### S2 Fairness

- Eyebrow: `Fairness`
- H2: `Averaging is why a team of five can beat a team of ten.`
- Lead: `The first thing anyone says about a team challenge is that the teams will be uneven and one person will carry the score. Here is the arithmetic that answers it.`
- Items:
  1. **The average, not the total** — `A team's score is the average of its members' individual scores. Adding inactive members pulls the average down, so a team climbs fastest when the colleague who has not started yet gets going.`
  2. **Maximum team size is set before launch** — `It applies to admin-created and employee-created teams alike, so no team can quietly stack itself.`
  3. **Move someone and the math follows** — `An admin can move a member between teams. Their individual score is preserved and both team averages recompute.`
  4. **Late joiners get no head start** — `Anyone added mid-challenge scores from their join date forward, not from the start date.`
  5. **Enthusiasts cannot outscore the daily target** — `Non-step tasks earn points up to 100% of the daily target. Someone who logs five yoga sessions when three are required still earns points for three.`
- Fine print: `We recommend 4 to 6 members per team, kept within one or two members of each other. Steps are accepted only from recognized fitness apps and devices, and implausibly high counts in short time periods are filtered out.`
- Panel: title `Team leaderboard` · chip `Updates on sync` · columns `Rank` `Team` `Members` `Team score` · rows `1 Assembly Line A 5 members 80` / `2 Central Ops 10 members 70` / `3 Warehouse East 5 members 60` (expanded) · members `A. Rivera 100` `M. Okonkwo 100` `J. Baptiste 100` `S. Lund 0` `D. Fernandes 0` · summation `Average of 5 members  60` · caption `A team of three at 100 and two who never started averages 60. Five colleagues who all did 80 average 80.` · tag `Illustrative data`

### S3 Who is in the average

- Eyebrow: `Who is in the average`
- H2: `An average only counts if everyone is in it.`
- Rows:
  1. **Nobody signs up** — `An audience rule enrolls everyone who matches, immediately or when they next open the app. There is no browse-and-join flow to lose people at.`
  2. **Day one, already on a team** — `Employees find themselves on a team when the challenge starts. Enrollment, team assignment, and challenge start emails are on by default and carry your logo and colors.`
  3. **No wearable required** — `Steps come from the phone through Apple Health on iOS and Google Fit on Android. Fitbit, Garmin, and Samsung Watch are supported, one primary device at a time.`
  4. **Compete as yourself and as a team** — `Employees toggle the leaderboard between individual and team, and between weekly and overall. Weekly resets each Monday.`
  5. **Quiet colleagues can stay quiet** — `Leaderboard opt-out hides an employee from the individual leaderboard. Their activity still counts toward their team's average.`
  6. **One challenge, every time zone** — `Daily targets reset at local midnight for each participant, so a 30-day challenge is a true 30 calendar days for everyone.`
- Media alt: `Vantage Fit employee app showing a challenge journey, weekly tasks, and a team leaderboard`

### S4 Where teams run

- Eyebrow: `Where teams run`
- H2: `Teams are a mode, not a format.`
- Cards:
  1. **Custom Challenge** — `Weekly themes and any mix of tasks, with teams enabled when you create the challenge.` · Best for: `a multi-week team program`
  2. **Journey Challenge** — `Each member advances on a shared map while teams compete on average score. Three built-in maps included.` · Best for: `a narrative your teams follow together`
  3. **Streak Challenge** — `Consecutive days completed, with teams scored on the average of their members.` · Best for: `building a daily habit`
- Note: `Race Challenge runs as an individual format only, with no team settings and no certificates. Teams are enabled at creation on Custom, Journey, and Streak.`

### S5 Control for HR

- Eyebrow: `Control for HR`
- H2: `Build the teams, run the month, leave with the file.`
- **Tab A, `Build and launch`:**
  1. **Build teams three ways** — `From the dashboard one at a time, by bulk upload from a CSV or Google Sheet, or captain-led if your account manager enables it.`
  2. **Set the ceiling once** — `Maximum team size is set at creation and applies to every team, however it was built.`
  3. **Creating a challenge takes 5 to 10 minutes** — `From the admin dashboard. Building the roster is a separate step, and bulk upload is much faster for large challenges.`
  4. **Adjust after it is live** — `Add or remove participants, move members between teams, and add a new weekly theme mid-challenge.`
  - Note: `Mismatched emails are skipped at import. Captain-led team creation is enabled by your account manager and is off by default.`
  - Mock: `Create challenge` / `Step 6 of 9 · Team configuration` · `Enable teams` (on) · `Maximum team size 5` · helper `Best practice: 4 to 6 members` · `Who creates teams` → **Admin-created** selected, `Dashboard, individually or by CSV`; **Employee-created**, chip `Enabled by your account manager` · foot `Team score = average of all team members' individual scores.` · template `Team name | Employee email` with `Assembly Line A | a.rivera@example.com`, `Central Ops | j.baptiste@example.com`, greyed `Central Ops | s.lund@exampl.com`, flag `Email not matched, skipped` · tag `Illustrative data`
- **Tab B, `Prove it`:**
  1. **Rank teams by average score** — `The Team leaderboard sits beside Score and Steps, and expands to show each member's contribution.`
  2. **See what people skipped** — `The per-user score breakdown gives scores by task and by week, plus task completion status.`
  3. **Export the file** — `One CSV carries name and email, department and country, total score and rank, step count, per-task scores, and team name.`
  4. **Close it out with a certificate** — `Turn certificates on at creation and they generate automatically for every participant who completes, branded with your logo, seal, and signer.`
  - Note: `Results finalize after a 3-day sync buffer. Per-task and per-week breakdowns are available on Custom challenges. Exports are a manual click in the dashboard. There is no scheduled report and no emailed digest.`
  - Mock: `Step Up Together · Leaderboard` · tabs `Score` `Steps` **`Team`** · controls `Department: All`, `Search employees` · rows as S2, third expanded to the five member scores · button `Export CSV` · callout `In the export`: `Name and email` `Department and country` `Total score and rank` `Step count` `Per-task scores` `Team name` · chip `Manual export. No scheduled digest.` · tag `Illustrative data`

### S6 Customer results

- Eyebrow: `Customer results`
- H2: `Programs where the team was the unit of competition.`
- Cards:
  1. `70%` — `engagement rate across a team challenge that ran on 43 teams` — `Tata Motors · Step Up & Elevate Challenge / Automotive`
  2. `53%` — `of those 43 teams reduced their average weight` — `Tata Motors · Step Up & Elevate Challenge / Team-level outcome`
  3. `7,600+` — `average daily steps per participant, a 6% increase` — `Tata Motors · Step Up & Elevate Challenge / Per participant`
  4. `5,000+` — `participants competing across 6 in-house teams in a 30-day virtual walkathon` — `Landmark Group · Virtual Walkathon / Retail`
- Quote left: `"People wanted to continue participating so they could see their team move up in the rankings."` — `ISKL (International School of Kuala Lumpur)`
- Quote right: `"Team challenges have strengthened relationships and built a sense of community among employees."` — `— Tara Shore, Niche Technology`
- Fine print: `Results from named customer programs, labeled the way each customer measured them. Tata Motors' 70% is engagement rate as measured by the customer; the 53% is the share of the 43 teams that reduced their average weight. Outcomes vary by workforce and program design.` · Link: `Read customer stories`

### S7 Security and privacy

- Eyebrow: `Enterprise security & compliance`
- H2: `Employees see their own data. HR sees aggregate trends.`
- Lead: `A public ranking of physical activity in named teams is exactly where privacy counsel intervenes. This is the published boundary.`
- Cards:
  1. **What admins can see** — `Aggregate metrics, challenge participation status, leaderboard rankings, team scores, registration status, last active date, and device type.`
  2. **What admins cannot see** — `Weight, BMI and body measurements, health risk assessment answers, lab values, mood logs, food diary, and sleep patterns.`
  3. **Where the data lives** — `Secured regional data hosting in India, the US, the EU, and the UAE, chosen at signup, with no cross-region sharing. Vantage Fit follows HIPAA guidelines and is SOC 2 Type II.`
  4. **Private by audience** — `Any audience filter makes a challenge private and visible only to its target audience. Single sign-on is available and configured with your account manager.`
- Actions: `Book a demo` · `Explore security & compliance →`
- Plaque alt: `Vantage Fit security and compliance badges`
- Support line: `Security documentation is available during evaluation. IT may need to allow vantagecircle.com as a sender domain.`

### S8 FAQ

- Eyebrow: `Before you roll out` · H2: `Questions before rollout`
1. **How should we group the teams?** `For a company-wide challenge, build teams from departments or locations. The rivalries already exist, so nobody has to be sold on them. Captain-led teams, which your account manager switches on, suit voluntary programs where picking your own side is the point. Either way, admins see every team and can rename it, edit its membership, or move a member across.`
2. **Can this run alongside the challenges we already have?** `Yes. There is no limit on how many challenges run at once, employees can take part in several, and each challenge keeps its own leaderboard and its own completion criteria. Stagger the end dates by a week or more so each set of results lands on its own day.`
3. **What happens when someone leaves mid-challenge?** `Remove them from the participants list. They lose access to the challenge and receive no further notifications for it, their score data stays in your reporting, and their team's average recomputes across the members who remain. If someone quits on their own and wants back in, an admin can re-enroll them.`
4. **Can we change a challenge after it goes live?** `Yes. Rename it, swap the cover image, or reschedule the start and end dates, and participants are notified when dates move. You can also push a notification to everyone in the challenge, start it early, or stop it early. Stopping early is immediate and cannot be undone.`

FAQPage JSON-LD is emitted and matches these four answers character for character.

### S9 Related

- Eyebrow: `Keep exploring` · H2: `Where teams go next`
  - **Steps Challenge** — `Company-wide step goals in five formats, with team averaging on three of them.`
  - **Multi-activity Challenge** — `Design the weekly tasks your teams compete on, across 27 task types.`
  - **All Vantage Fit solutions** — `Every program on one page, from one-day events to year-round calendars.`

### S10 Closer

- H2: `Score the average. Then watch who starts walking.`
- Body: `See a team challenge built in a 30-minute demo, with your own team sizes and your own departments on the board.`
- Buttons: `Book a demo` · `See pricing`
- Checks: `30-minute walkthrough` · `No wearable required` · `No obligation`
- Note: `Turn participation into progress.`

---

## 6. Claims ledger

Status key: **A** = help doc, current shipped behaviour, verifiable by the buyer during a trial · **B** = shipped but gated or qualified, with the gate stated on the page · **P** = approved customer proof, cited from `VOS/.claude/rules/data-accuracy.md` · **I** = illustrative, visibly labelled, asserts nothing.

Path shorthand: `HELP` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/` · `VOS` = `/Users/anjanpathak/work/vc-os/vfit-os/`

| # | Claim / figure on the page | Where | Source | Status |
|---|---|---|---|---|
| 1 | A team's score is the average of its members' individual scores, not the total | H1, S1 lead, S1 pill, S2.1, S2 panel, S5 mock foot, S10 | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:19-22`; `admin-how-do-i-create-custom-challenge.md:108`; `VOS/specs/product/02-challenges-gamification/challenges.md:99` | A |
| 2 | Adding inactive members pulls the average down | S2.1 | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:19-24` | A |
| 3 | Three members at 100 and two at zero average 60; five at 80 average 80 | S2 panel caption + summation row | `HELP/employee/challenges/how-do-teams-work.md:61`; `HELP/employee/getting-started/ts-leaderboard-score-wrong.md` | A |
| 4 | Maximum team size is set at creation and applies to admin-created and employee-created teams alike | S2.2, S5 tab A.2, S5 mock | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:108-114` | A |
| 5 | 4 to 6 members recommended, teams kept within one or two of each other | S2 fine print, S5 mock helper | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:116,131` | A |
| 6 | Moving a member preserves their individual score and recomputes both averages | S2.3, S5 tab A.4, FAQ 1 | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:99-106` | A |
| 7 | Late joiners score from their join date forward | S2.4 | `HELP/admin/challenges/admin-how-do-i-add-remove-participants.md:61-69`; `VOS/specs/product/02-challenges-gamification/challenges.md:49` | A |
| 8 | Non-step tasks earn points up to 100% of the daily target; five yoga sessions when three are required still earns three | S2.5 | `HELP/admin/challenges/admin-how-do-i-create-custom-challenge.md:94`; `HELP/employee/getting-started/ts-leaderboard-score-wrong.md` | A |
| 9 | Steps accepted only from recognized fitness apps and devices; implausibly high counts in short windows filtered | S2 fine print | `HELP/admin/settings/admin-data-privacy-security.md:68-75` | A |
| 10 | Leaderboard updates on sync | S2 panel chip | `HELP/employee/challenges/how-does-the-leaderboard-work.md:63-68` | A |
| 11 | Nobody signs up; an audience rule enrolls everyone who matches, immediately or when they next open the app; no browse-and-join flow | S1 note, S3.1 | `HELP/employee/challenges/how-do-i-join-a-challenge.md`; `HELP/admin/challenges/admin-how-do-i-set-target-audience.md:49-66`; `challenges.md:42` | A |
| 12 | Employees find themselves already on a team when the challenge starts | S3.2 | `HELP/employee/challenges/how-do-teams-work.md:34` | A |
| 13 | Enrollment, team assignment and challenge start emails are on by default, branded with company logo and colours | S3.2 | `HELP/admin/communication/admin-what-emails-does-vfit-send.md:29-30,41,55-62,89-96` | A |
| 14 | No wearable required; Apple Health on iOS, Google Fit on Android; Fitbit, Garmin, Samsung Watch supported; one primary device at a time | S1 note, S3.3, S10 check | `HELP/employee/getting-started/do-i-need-a-wearable.md`; `can-i-connect-multiple-devices.md`; `VOS/specs/product/10-integrations/device-integrations.md:22` | A |
| 15 | Individual and team leaderboards in one challenge; weekly and overall; weekly resets each Monday | S1 note, S1 phone, S3.4 | `HELP/employee/challenges/how-do-teams-work.md:73-83`; `how-does-the-leaderboard-work.md:16-33` | A |
| 16 | Leaderboard opt-out hides the individual; activity still counts toward the team average | S3.5 | `HELP/employee/challenges/can-i-opt-out-of-leaderboard.md:15-37` | A |
| 17 | Daily targets reset at local midnight per participant, so 30 days is 30 calendar days for everyone | S3.6 | `HELP/admin/challenges/admin-can-i-run-challenges-across-time-zones.md` | A |
| 18 | Teams are enabled at creation on Custom, Journey and Streak | S4 cards, S4 note, S9 Steps card | `admin-how-do-i-create-custom-challenge.md:99-108`; `admin-how-do-i-create-journey-challenge.md:90-98`; `admin-how-do-i-create-streak-challenge.md:69-73` | A |
| 19 | Journey: each member advances on the map individually while teams compete on average; three built-in maps | S4 | `HELP/admin/challenges/admin-how-do-i-create-journey-challenge.md:30-38,98` | A |
| 20 | Race Challenge is individual only, with no team settings and no certificates | S4 note | `HELP/admin/challenges/admin-how-do-i-create-race-challenge.md:59` | A |
| 21 | Teams built from the dashboard, by CSV or Google Sheet bulk upload, or captain-led | S5 tab A.1, FAQ 1 | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:28-75`; `VOS/specs/05-social-community/teams.md:84-85` | A |
| 22 | Captain-led team creation is account-manager enabled and off by default | S5 tab A note, S5 mock chip, FAQ 1 | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:75`; `challenges.md:174-175` | **B** |
| 23 | Mismatched emails are skipped at import | S5 tab A note, S5 mock flag | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:57` | A |
| 24 | Creating a challenge takes 5 to 10 minutes from the admin dashboard; roster building is separate; bulk upload is faster at scale | S5 tab A.3 | `HELP/admin/challenges/admin-how-do-i-create-a-challenge.md:13`; `admin-how-do-i-manage-teams.md:44` | A |
| 25 | Team configuration is Step 6 of 9 in the Custom wizard | S5 mock header | `HELP/admin/challenges/admin-how-do-i-create-custom-challenge.md:24-135` (Step 1 to Step 9, teams at Step 6) | A |
| 26 | Add or remove participants, move members, add a new weekly theme mid-challenge | S5 tab A.4 | `HELP/admin/challenges/admin-how-do-i-manage-challenge.md:48,55-70`; `admin-how-do-i-add-remove-participants.md` | A |
| 27 | Team leaderboard ranks teams by average score, sits beside Score and Steps, expands to member contribution | S1 tabs, S5 tab B.1, S5 mock | `HELP/admin/reports/admin-how-do-i-view-leaderboard.md:28-50` | A |
| 28 | Per-user score breakdown by task and by week, plus task completion status | S5 tab B.2 | `HELP/admin/reports/admin-how-do-i-view-leaderboard.md:72-86` | A |
| 29 | Per-task and per-week breakdowns are available on Custom challenges | S5 tab B note | `HELP/admin/reports/admin-how-do-i-view-leaderboard.md:88-102` | A |
| 30 | Export CSV carries name and email, department and country, total score and rank, step count, per-task scores, team name | S5 tab B.3, S5 callout | `HELP/admin/reports/admin-how-do-i-view-leaderboard.md:88-102` | A |
| 31 | Certificates are enabled at creation and generate automatically for every participant who completes, branded with logo, seal and signer | S5 tab B.4 | `HELP/admin/challenges/admin-how-do-i-configure-certificates.md`; `HELP/employee/challenges/what-happens-when-challenge-ends.md:15-26` | A |
| 32 | Results finalize after a 3-day sync buffer | S5 tab B note | `HELP/admin/challenges/admin-how-do-i-create-race-challenge.md:66-71`; `challenges.md:124` | A |
| 33 | Exports are a manual click; no scheduled report, no emailed digest | S5 tab B note, S5 chip | `HELP/admin/reports/admin-how-do-i-view-leaderboard.md:104-110` (stated as a limit, deliberately) | A |
| 34 | What admins CAN see: aggregate metrics, participation status, rankings, team scores, registration status, last active date, device type | S7 card 1 | `HELP/admin/settings/admin-data-privacy-security.md` | A |
| 35 | What admins CANNOT see: weight, BMI and body measurements, HRA answers, lab values, mood logs, food diary, sleep patterns | S7 card 2 | `HELP/admin/settings/admin-data-privacy-security.md` | A |
| 36 | Secured regional data hosting in India, US, EU, UAE, chosen at signup, no cross-region sharing | S7 card 3 | `VOS/sources/VFit-Marketing-Content-Compacted.md:284`; `VOS/specs/product/03-health-wellness/onboarding-health-profile.md:178` | A |
| 37 | Follows HIPAA guidelines; SOC 2 Type II | S7 card 3, footer | `VOS/sources/VFit-Marketing-Content-Compacted.md:161-162` (exact approved strings only) | A |
| 38 | Any audience filter makes a challenge private, visible only to its target audience | S7 card 4 | `HELP/admin/challenges/admin-how-do-i-set-target-audience.md:41` | A |
| 39 | Single sign-on is available, configured with your account manager | S7 card 4 | `HELP/admin/settings/admin-how-do-i-enable-sso.md` | **B** |
| 40 | IT may need to allow vantagecircle.com as a sender domain | S7 support line | `HELP/admin/communication/admin-what-emails-does-vfit-send.md:117` | A |
| 41 | "Employees see their own data. HR sees aggregate trends." | S7 H2 | `VOS/.claude/rules/hr-buyer-lens.md:44` (approved verbatim translation) | A |
| 42 | No limit on concurrent challenges; employees can take part in several; each keeps its own leaderboard and completion criteria; stagger end dates by a week or more | FAQ 2 | `HELP/admin/challenges/admin-can-i-run-multiple-challenges-in-parallel.md:13,39` | A |
| 43 | Removed participants lose access, receive no further notifications, and their historical data is retained for reporting | FAQ 3 | `HELP/admin/challenges/admin-how-do-i-add-remove-participants.md:40-49` | A |
| 44 | An admin can re-enroll someone who quit | FAQ 3 | `HELP/admin/challenges/admin-how-do-i-add-remove-participants.md:71-79` | A |
| 45 | Rename, swap cover image, reschedule dates (participants notified), push a notification to all participants, Force Start, Force Stop (immediate, cannot be undone) | FAQ 4 | `HELP/admin/challenges/admin-how-do-i-manage-challenge.md:25-40,86-94,100-111` | A |
| 46 | 27 task types (used only as the multi-activity link description) | S9 | `HELP/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md:13` | A |
| 47 | Tata Motors, Step Up & Elevate Challenge: **70% engagement rate**, **43 teams**, **53% of those teams reduced average weight**, **7,600+ average daily steps, a 6% increase** | S6 cards 1 to 3, meta description | `VOS/.claude/rules/data-accuracy.md:50-67`; `vantagefit-astro/content/en/casestudy/tata-motors-step-up-elevate.md` | **P** |
| 48 | Landmark Group: **5,000+ participants across 6 in-house teams**, 30-day virtual walkathon | S6 card 4 | `VOS/.claude/rules/data-accuracy.md:154-166` | **P** |
| 49 | ISKL quote, organisation-only attribution (no person named in source) | S6 quote left | `VOS/sources/Testimonials/TESTIMONIAL-INDEX.md:93-99` | **P** |
| 50 | Niche Technology quote, "— Tara Shore, Niche Technology", no title (none exists in source) | S6 quote right | `VOS/sources/Testimonials/TESTIMONIAL-INDEX.md:185-189` | **P** |
| 51 | "Trusted by 100+ organizations worldwide" | S1 logo band | `VOS/.claude/rules/data-accuracy.md:252-261` (the only approved aggregate scale claim) | **P** |
| 52 | Logo band names: Tata Motors, Wipro, Teva, Godrej, Texas Instruments, Heidrick & Struggles, Brazosport ISD | S1 logo band | `VOS/.claude/rules/data-accuracy.md:22` approved client list | **P** |
| 53 | All team names, member names and scores in every mock: Step Up Together, Assembly Line A, Central Ops, Warehouse East, Finance Floor 2, 80 / 70 / 60 / 58, 100·100·100·0·0, max team size 5, three CSV rows, "Department: All" | S1 (x2), S2, S5 (x2) | **Invented.** Each mock carries a visible `Illustrative data` tag and repeats that status in its `aria-label` | **I** |

### 6.1 Claims cut, and why

| Cut | Reason |
|---|---|
| "70% participation" (live H1) | It is engagement rate as the customer measured it. Relabelling is a P0 defect. |
| "Set up team-based step, fitness, and weight challenges in under 10 minutes" (live hero) | Unverified in that form, and Weight Burn is ops-only, so it also overclaims self-serve. |
| "Inclusive for all" as an assertion | Replaced by the mechanism that makes it true. |
| Relay races, group yoga sessions (live page) | NOT FOUND IN SOURCES as product capabilities. |
| Employees browsing and joining a challenge | No browse-and-join flow exists. |
| Employee-formed teams as the default rollout story | AM-gated and off by default. Kept as a qualified third option only. |
| "Automatic reminders keep momentum" | Challenge reminder emails are disabled by default and AM-gated. |
| Any step-cap number, "no ceiling", numeric anti-cheat thresholds, "fraud-proof", "every step verified" | Sources conflict three ways and the code-verified spec says step normalization is currently off. |
| A default maximum team size presented as the product default | The dashboard prototype's 25 is design-repo fiction. The page shows 5 only as one admin's chosen value inside a labelled mock, with the sourced 4 to 6 as helper text. |
| Teams on Race or E-Marathon | Race is individual-only; E-Marathon teams are NOT FOUND IN SOURCES. |
| "Build your teams once and reuse them next challenge" | Team migration between campaigns is Draft Set A only, not restated in the code-verified set. |
| Any team leaderboard tie-break rule | NOT FOUND IN SOURCES. |
| Any team-level completion-rate metric | Does not exist. The team surface is average score and member count only. |
| Slack or Microsoft Teams integration | Zero spec coverage. The page says push notification and email. |
| Scheduled reports, exec digest, shareable dashboard link | Do not exist. The page states the opposite, twice. |
| ISO 27001, ISO 27701, GDPR anywhere including alt text; "HIPAA compliant"; "SOC 2 certified" | No product-KB support. The plaque alt was rewritten to `Vantage Fit security and compliance badges`. |
| Any "trusted by US enterprises" framing | No approved US-named **team** result exists. Handed to sales for the demo call. |
| Step & Stride's 59% / 1,248 / 6,246; Wipro's 3X as a team result; Landmark's 4.3M and "190,000+ average steps per team"; Serum Institute 99%; Decision Foundry 89%; ISKL 95%; Accenture; Hershey | Barred for this page by the approved-proof gate. |
| Heidrick & Struggles leaderboard quote | Held in reserve. The brand already appears in the logo band and a third quote pads S6. Approved as a substitute if ISKL or Niche is ever pulled. |
| "No credit card" in the closer checks | No sourced statement about trial or payment terms. Swapped for "No wearable required". |
| Badges, points and monetary rewards for challenge tasks | AM-gated and currently narrow. Not presented as the participation engine. |

### 6.2 Pre-ship gates, re-run against the shipped file

`Book a demo` 4 on-page instances plus the meta description, identical label · `See pricing` 2 · `Illustrative data` 5 visible tags, 5 `role="img"` mocks · em-dashes 1, the Niche Technology attribution · one `<h1>` with one `<em>` · 10 `<section>` elements, all with `id` and `aria-labelledby` · zero hits for ISO 27001, ISO 27701, GDPR, "HIPAA compliant", Slack, Microsoft Teams, 25,000, Health Connect, "any device", "70% participation", and the banned-word list · FAQPage JSON-LD parses and matches the visible answers character for character.

---

## 7. Proof decision

**The page carries a full customer-result section.** The approved-proof gate says run one for this program, and it is the only page in the Run-a-Challenge group where the **unit of competition in the source data is the team itself**.

**What is cited and why:**

- **Tata Motors, Step Up & Elevate Challenge** takes three of the four cards, because it is the only approved dataset with a team-level outcome. `70%` is labelled **engagement rate** in the card, in the fine print and in the meta description. `53% of those 43 teams reduced their average weight` is the single most relevant number on the site for this page: it is a **team-level** result, not a per-person one. `7,600+ average daily steps, a 6% increase` grounds the behaviour change per participant. Three cards from one customer is deliberate. It is the honest shape of the evidence, and splitting a coherent program across unrelated logos would have been the padding move.
- **Landmark Group** supplies scale in the exact unit this page trades in: `5,000+ participants competing across 6 in-house teams` in a 30-day virtual walkathon. Landmark's "top team logged 4.3M+ steps" is approved but only as a top-team figure, and generalising it is the classic misread, so it was omitted rather than caveated.
- **ISKL**, organisation-only attribution because no person is named in the source: "People wanted to continue participating so they could see their team move up in the rankings." This is retention evidence in the buyer's own language, attached to the team mechanic.
- **Niche Technology**, "— Tara Shore, Niche Technology" with no title because the source gives none: "Team challenges have strengthened relationships and built a sense of community among employees." The cleanest named team sentence in the approved pool.

**The geography problem, stated rather than solved.** The approved team-proof pool is India, the Gulf and Malaysia. The only US-recognisable name available for a team claim is Heidrick & Struggles, and it is a quote, not a metric. There is therefore **no "trusted by US enterprises" framing anywhere on the page**, and no implication of one. That gap goes to sales for the demo call. The page instead uses the approved global scale honestly: named enterprise programs, 43 teams, 5,000+ participants across 6 teams, and "100+ organizations worldwide" as the only approved aggregate.

**No video quote.** The only approved video asset in the repo is Rachel Arthur of Brazosport ISD, who is not approved for a team claim, so both quotes are text-only and neither carries an avatar.

---

## 8. Meta title and meta description

**Title (57 characters), shipped:**
`Team Challenges for Employees: Fair Scoring | Vantage Fit`

Colon format rather than an em-dash, ends `| Vantage Fit`, preserves the phrase the live page currently ranks on ("team challenges for employees") and adds the differentiator. Alternates considered: `Team Fitness Challenge Software for Employees | Vantage Fit` (59, chases the unowned Tier 2 term "employee fitness challenge software" but reads stuffy) and `Employee Team Fitness Challenge Software | Vantage Fit` (54, loses the ranking phrase).

**Description (150 characters), shipped:**
`Team challenges scored on every member's average, not the fittest few. Tata Motors' Step Up & Elevate hit 70% engagement across 43 teams. Book a demo.`

`&` is entity-encoded in the attribute. The stat is attributed and labelled engagement, which is what the live description fails to do while also burying the differentiator behind an unverified setup-speed claim.

**Other SEO decisions carried into the build:** URL stays `/team-challenges/` exactly, no `/solutions/` prefix, no redirect proposed. Hreflang alternates `/fr/defi-dequipe/`, `/es/desafio-de-equipo/`, `/de/team-herausforderung/` must keep resolving. Primary keyword appears in the title, the H1, the first 100 words and the description. Three internal links (`/steps-challenge/`, `/multi-activity-challenges/`, the Solutions hub) close the loop. FAQPage JSON-LD is emitted, which the live template does nowhere on the site. `noindex, nofollow` stays on the mock.

---

## 9. Assumptions and open questions

### 9.1 Page identity, the assumption everything else rests on

The orchestrator passed `pageLabel`, `slug` and `liveUrl` through as the literal string `undefined`. Both research agents and all three strategists independently resolved it to **Team Challenge** (`/team-challenges/`), on three converging signals: it is the first unbuilt row in `RUN-A-CHALLENGE-PROMPT.md:11`, it is starter kit §3.1 in the foundation index, and it is the only remaining page whose native objection matches the research that was commissioned. This brief and the HTML were built on that lock. **If the intended page was Multi-Activity, Mental Health or Virtual Marathon, nothing here transfers and the pass must be re-run.** For the same reason this file was written as `TEAM-CHALLENGE-BRIEF.md` rather than to the literal path `.../claude-fable/undefined`.

### 9.2 Things a human needs to confirm

1. **The certifications plaque image.** It is reused from the approved baseline for visual continuity, but the badges it depicts include ISO and GDPR marks that have no product-KB support. The alt text was rewritten to assert nothing (`Vantage Fit security and compliance badges`) and the copy claims only SOC 2 Type II and "follows HIPAA guidelines". **Confirm the plaque with the security team before production.**
2. **Team migration between challenges.** "Build your teams once and reuse them" is the strongest ops answer available and it was deliberately left off the page, because the migrate endpoint appears only in the Draft Set A spec and is not restated in the code-verified set. **Worth clearing with product.** If it is real and shipped, it belongs in S5 tab A.
3. **The challenge templates library.** The help doc describes it in the present tense, including presetting teams; the code-verified spec lists it as Planned. The page does not mention templates at all as a result. **One product answer would settle it.**
4. **FAQ 3, one sentence without a direct quote behind it.** "their team's average recomputes across the members who remain" is an arithmetic consequence of the averaging rule plus the move-member note, not a verbatim line about removal. Low risk, but it is the only FAQ sentence in that position.
5. **Maximum team size default.** The page prints `5` only inside a labelled mock as one admin's chosen value. The dashboard prototype's default of 25 is design-repo fiction and was not used. If product has a real shipped default, the mock should match it.
6. **Sender-domain allowlisting.** The page tells IT they may need to allow `vantagecircle.com`. Confirm this is still the correct domain for outbound challenge mail.

### 9.3 Assumptions stated

- Sibling links point at live URLs; the mega banner and the third related row point at the local hub mock file so a reviewer can navigate the set. Both use the same relative path.
- All product-UI figures in the five mocks are interface fiction, not outcome claims. Every outcome claim on the page lives in S6 with a named source.
- The `.audit-board` summation row ("Average of 5 members: 60") is an addition to the blueprint. It exists because the panel has to make the arithmetic legible without the caption, and it is arithmetic, not a product surface claim.
- Serial commas were added throughout the body copy. Seven nav mega-menu strings still omit them; that block is byte-identical across this page, the Steps page and the Solutions hub, so it should be fixed across all three in one pass rather than diverging here.
- The desktop `aria-expanded` fix and the page-scoped contrast lifts (`.logos-label`, `.logo-word`, `.trust-plaque .trust-support`, `.best-for b`, `.mock-tag`) live in this file only. The shared `enterprise.css` rules they override still fail AA on every other page and need an owner decision upstream.

---

## 10. Known gaps

Things no source in the corpus could answer, which are therefore absent from the page rather than guessed at:

1. **How long building the teams actually takes.** The only sourced duration is "Creating a challenge takes 5-10 minutes", and it covers the creation wizard. The only qualitative statement about roster building is "For large challenges with many teams, bulk upload is much faster." The page says exactly that and no more, which is why there is no rollout timeline anywhere on it.
2. **Tie-breaking on a team leaderboard.** Nothing in the corpus describes one. The only documented tie-break in the entire product is Streak's individual ranking (days completed, then total steps). The page invents nothing.
3. **Any team-level completion or participation metric.** The team surface is average score and member count. There is no team completion rate, no team participation rate, and no team-level export beyond the Team name column on the leaderboard CSV.
4. **Normalisation, handicaps, or a floor for absent members.** No minimum-active-member rule, no size normalisation, no protection for a team carrying a non-starter. An absent member is simply a zero pulled into the mean, and the page says so plainly rather than implying a protection that does not exist.
5. **What happens to unassigned members when a team is deleted.** The doc says only "depending on the challenge configuration", which is not answerable on a marketing page. Buyers will hit this.
6. **Whether an employee-created team's captain can be changed after creation, and what happens to a team whose captain leaves.** A `setCaptains` endpoint exists in the Draft spec; no help doc describes the flow.
7. **Per-team communication.** Campaign chat is not team chat, no per-team chat room is described, and push notifications go to all participants of a challenge with no per-team segment. Nothing on the page implies otherwise.
8. **US enterprise team proof.** No approved US-named customer result exists where the unit of competition was the team. This is the single biggest evidence gap on the page and the reason S6 carries no geography framing at all.
9. **Whether emails can be toggled by the admin.** Self-serve email toggles do not exist; the admin can only preview. The page therefore claims which emails are on by default and never claims control over them.
10. **Report date-filter time zone behaviour on global programs.** Report filters use the admin's time zone rather than the participant's, which is a real reconciliation annoyance on cross-region team programs. It was judged too operationally deep for the page but should be in the sales handoff.
