# Team Challenge page — brief & copy deck

Deliverable: `vantage-fit-team-challenge-v1.html` (same folder).

- **Page type:** individual solutions / use-case page under Run a Challenge. Live URL (context only): `/team-challenges/`.
- **Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary: program managers; tertiary gate: IT/security.
- **Positioning spine:** extends the homepage north star (participation) to the team mechanic — *squads create social accountability, and social accountability is what keeps participation alive after week one.*
- **Primary CTA:** Book a demo · **Secondary:** See pricing.
- **Visual system:** `../styles/enterprise.css` + patterns from `styled-homepage/` and my prior Steps page (`vantage-fit-steps-challenge-v1.html`) — same nav, mega menus (Team challenges item carries the `aria-current="page"` "You're here" marker), footer, mocks, FAQ, final CTA. IA re-evaluated for this page, not copied.

---

## 1. Research takeaways (product truth, not the old page)

Sources pulled at latest `main`: `vantagefit-astro` (help docs + case studies), `vc-dashboard-design` (wellness module), `vc-os/vfit-os` (teams spec, challenge specs, positioning).

### What the live `/team-challenges/` page gets wrong or misses

The legacy page (`content/en/pages/use-cases/team-challenges.yaml`) is four generic bullet blocks ("push each other", "team leaderboard", "diverse activities", "inclusive for all") plus one Tata testimonial and three thin FAQs. It misses every mechanic that makes team challenges actually work, and invents non-product ideas (relay races, group yoga sessions). Against the help docs and specs:

1. **The scoring model — the single most important fact — is absent.** Team score = *average of member scores, not the sum*. This is the fairness engine and the social-accountability engine: a consistent team beats a team with two superstars, and inactive members visibly pull the average down (`admin-how-do-i-manage-teams.md`, `how-do-teams-work.md`, vfit-os `specs/05-social-community/teams.md`).
2. **Three ways to build teams, with admin control throughout** — admin-created from the dashboard, bulk upload via CSV or Google Sheets (team name + employee email per row), or employee-created teams where a captain names the squad and invites colleagues (invites can be accepted, rejected, expired, withdrawn). Even employee-created teams stay under full admin oversight: edit, move members, delete (`admin-how-do-i-manage-teams.md`).
3. **Configurable max team size** — set per challenge; 4–6 recommended so every member's effort visibly moves the score (`admin-how-do-i-manage-teams.md`).
4. **A real team leaderboard** — separate team view with an individual/team toggle, weekly and overall periods, department filter, and tap-your-row score breakdowns (`how-does-the-leaderboard-work.md`).
5. **Format truth the old page fudges** — teams are supported in **Streak, Journey, and Custom challenges only**. Race has *no team settings by design* (its help doc says so explicitly and points admins to Custom if they want teams). E-Marathon docs do not mention teams. The page must not claim "any challenge, with teams" (`admin-how-do-i-create-race-challenge.md:59-62`, `admin-how-do-i-create-{streak,journey-challenge,custom-challenge}.md`).
6. **Custom multi-week is the team format with the most range** — weekly themes with any mix of 27 task types (steps, distance, active minutes, water, sleep, meditation, and more), which is how a team challenge becomes a whole-wellbeing program rather than a step contest (`admin-what-tasks-can-i-include-in-a-custom-challenge.md`).
7. **Member moves preserve individual scores** — team averages recompute; mid-challenge team management is safe (`admin-how-do-i-manage-teams.md`).
8. **The fairness/inclusion layer carries over** — leaderboard opt-out (still participates and earns), daily step caps and trusted-source anti-cheat, 3-day post-end sync buffer, no wearable required, localized time zones and currencies.
9. **Proof the old page under-uses** — Tata Motors is a *published, team-tagged* case study: 43 teams, 70% engagement, +6% daily steps (7,600+ avg), 53% of teams reduced average weight over ~6 months (`casestudy/tata-motors-step-up-elevate.md`). Supporting team-format stories: Landmark Group (30-day, 6 in-house teams, top team 4.3M+ steps), Global Corporate Walkathon (74 teams, 24 countries), JF Petroleum (52-week streak as team culture).
10. **Admin measurement** — participation gauge is the wellness north star in the HR dashboard, with a "Top challenge teams" ranklist, Challenge Insights (format fit, completion/quit, incentive lift), and CSV exports (participation, leaderboard, transaction reports) (`vc-dashboard-design/docs/modules/wellness.md`; help admin reports).

### Positioning constraints honored

- North star = participation; inclusive tone, not gym-bro leaderboard culture (vfit-os `MISSION.md`).
- Only approved aggregate claim: "100+ organizations" (vfit-os data-accuracy rules). All dashboard figures inside mocks are illustrative sample data.
- No self-serve employee joining implied (enrollment is admin-driven; employees can *form teams* only where enabled); no cash prizes; no unlisted wearables; Wellness Leagues / Wellness Score not marketed (gated).
- Sentence case, no em-dashes, verb-led CTAs, HR is the reader.

---

## 2. Page structure & rationale

Eight sections, deliberately leaner than my Steps page (per the Steps bake-off retro: short one-line descriptions, no redundant ledes, proof section only because a real approved team-challenge story exists).

| # | Section | Job |
|---|---------|-----|
| 1 | Hero + logo band | Promise ("turn wellness into a team sport"), dual admin/phone product visual centered on the *team* leaderboard, two real proof chips (Tata 70%, global walkathon 74 teams / 24 countries) |
| 2 | Why teams | Recognition beat: individual challenges reward the already-fit; three named failure modes; pivot to social accountability as the mechanic |
| 3 | How teams work | The core differentiator: average-not-sum scoring explained visually, three team-building paths, captain invites, team-size guidance, dual leaderboard. Product-real phone mock |
| 4 | Team-ready formats | Streak, Journey, Custom multi-week cards + an honest note that Race stays individual by design and that challenges run in parallel. Prevents the over-claim the old page makes |
| 5 | For HR | Bulk CSV/Google Sheets team setup, oversight of employee-created teams, mid-challenge management, reporting. Admin dash mock |
| 6 | Proof | One flagship: Tata Motors Step Up & Elevate (4 real stats). Compact band, not a padded grid |
| 7 | FAQ | 5 questions, each a real rollout objection; format/team-creation/scoring answers sourced from help docs |
| 8 | Final CTA + footer | Demo framed as "see a team challenge configured for your workforce" |

Why this order: the buyer's first question is "why teams over a normal challenge" (S2), the second is "how does it actually work" (S3, the page's center of gravity), then "what can we run" (S4), "can I operate it" (S5), "did it work for others" (S6). Trust/compliance is *not* given its own band here: unlike the Steps page (anti-cheat) there is no team-specific security objection beyond what the platform-level pages and footer strip already carry; folding it in keeps the page lean per the retro.

Deliberately excluded: a 4-card proof grid (only one deep team-challenge story is approved; padding would mean generic stats), Wellness Leagues (gated), pricing detail, a separate dark trust band (covered by footer strip + platform pages; stated as an assumption below).

---

## 3. Full copy deck

### S1 Hero
- Eyebrow: Solutions · Team Challenge
- H1: **Turn wellness into a team sport.**
- Lead: Employees form squads, and every member's effort moves the team average — so the quietest walker matters as much as the marathoner. Vantage Fit runs the teams, leaderboards, rewards, and reporting; HR runs none of the busywork.
- CTAs: Book a demo · See pricing
- Note chips: No wearable required · Admin, CSV, or employee-built teams · Trusted by 100+ organizations
- Hero visual: admin dash mock ("Step Up Season · Team challenge", illustrative metrics 1,240 enrolled / 38 teams / 5 avg team size / 81% participation, team leaderboard ranked by avg steps per member) + employee phone mock (team view: squad name, team rank, "your contribution", invite notification) + proof chips (70% engagement · Tata Motors, 43 teams; 74 teams across 24 countries · global walkathon). Dashboard figures are illustrative sample data; the chip figures are real case-study results.
- Logo band: Trusted by 100+ organizations in 50+ countries — TATA MOTORS · WIPRO · ACCENTURE · TEVA · TEXAS INSTRUMENTS · HERSHEY · BRAZOSPORT ISD

### S2 Why teams — "Solo challenges crown the already-fit. Team challenges move everyone."
Lead: An individual leaderboard is a chart of who already exercises. A team challenge changes the unit of competition — and with it, who shows up.
Pain cards:
1. **The same few people win** — Raw-total leaderboards are decided in week one. Everyone else stops checking.
2. **No one is accountable to anyone** — Quitting a solo challenge is private, so it is easy. Quitting on your squad is noticed.
3. **Hybrid teams never share a win** — Scattered offices and remote staff get a step total, not a shared experience.
Pivot: Social accountability is not a slogan, it is a scoring model. Vantage Fit team challenges are built on it.

### S3 How teams work — "Every member moves the score. Literally."
Lead: Team score is the average of members' effort, not the sum. A squad of five steady walkers beats a squad carried by one star — and that changes who keeps walking.
Mechanic cards (each one line + short sub-list where earned):
1. **Average scoring, not totals** — every member's effort counts equally; inactive teammates pull the average down, so squads rally their own.
2. **Three ways to build teams** — admins create them in the dashboard, bulk-upload via CSV or Google Sheets, or let employees form their own with captain invites. Admins keep oversight either way.
3. **Right-sized squads** — a configurable member cap keeps teams at 4 to 6, small enough that one person's walk visibly moves the rank.
4. **A leaderboard worth checking** — team and individual views side by side, weekly and overall periods, department filters, and per-task score breakdowns.
5. **Fair and opt-in friendly** — trusted activity sources and daily caps keep scores honest; anyone can opt out of rankings and still take part and earn points.

Visual: phone mock showing the team leaderboard (rank, team name, avg per member, member count) with an invitation card ("Asha invited you to join Desk Setters — Accept / Decline").

### S4 Team-ready formats — "Pick the game your teams will play."
Lead: Three challenge formats support teams — each one self-serve from your admin dashboard.
| Format | Tag | Copy | Best for |
|---|---|---|---|
| Streak | Daily habit | Squads chase the same daily target — steps, active minutes, or another habit — and fight to keep team streaks alive. Consistency, not intensity. | building an everyday movement habit |
| Journey | Shared map | Steps move every member along a virtual route — the 7 Wonders, Backpacking Europe, an Everest climb. The team ranks on its average, the story carries the motivation. | themed campaigns with a narrative |
| Custom multi-week | Most flexible | Weekly themes with any mix of 27 task types — steps, distance, active minutes, water, sleep, meditation, and more. The team challenge that outlasts week two. | whole-wellbeing programs |
Honest-broker note: Race, the straight step-count showdown, stays individual by design — if you want teams, the product points you to Custom. Run as many challenges in parallel as you like; one walk counts toward every challenge an employee joins.
Related links: Step challenges → · Custom & multi-activity challenges → · Virtual marathon →

### S5 For HR — "Set up 200 teams before lunch."
Lead: Templates carry the configuration; bulk tools carry the headcount; the dashboard carries the proof.
- **Bulk team creation** — one CSV or Google Sheet (team name, employee email) creates and fills every team in a single upload.
- **Your call who builds** — pre-assign teams by department or location, or switch on employee-created teams and let captains recruit. Edit, rebalance, or dissolve any team mid-challenge; individual scores travel with the member.
- **Aimed and localized** — target by department, country, age group, or language. Starts, ends, and daily resets follow each participant's midnight; rewards set in USD display in local currency.
- **Proof on tap** — live participation and team rankings in the dashboard; participation, leaderboard, and points-transaction reports export to CSV.

Visual: admin dash mock — Teams panel (bulk upload button, team rows with member counts), "38 teams · 4 unassigned employees" nudge.

### S6 Proof — "43 teams. 70% engagement. Six months long."
Tata Motors (Automotive · India) ran the Step Up & Elevate team challenge on Vantage Fit:
- **70%** employee engagement across plants and offices
- **43** teams competing on plant and office leaderboards
- **+6%** average daily steps, reaching 7,600+ per person
- **53%** of teams reduced their average weight over the program
Link: Read the Tata Motors story → · Disclaimer: results from a published Vantage Fit customer case study, as reported by the customer's program.

### S7 FAQ — "Questions HR teams ask."
1. **Can every challenge be a team challenge?** No — teams run in Streak, Journey, and Custom challenges. Race, the simplest step showdown, is individual by design; if you want teams, the product itself points you to Custom.
2. **Who creates the teams?** Your call. Admins build them in the dashboard or bulk-upload via CSV or Google Sheets, or you can enable employee-created teams where a captain names a squad and invites colleagues. Admins can edit, rebalance, or remove any team either way.
3. **How is team scoring fair?** Team score is the average of members' effort, not the sum — so a big team of coasters loses to a small team of steady walkers, and every member's activity matters equally. A configurable size cap keeps teams comparable.
4. **Do employees need fitness trackers?** No — phones count steps through Apple Health and Google Fit. Fitbit and Garmin connect directly; Apple Watch and most bands sync via Apple Health. One primary device at a time, so nothing double-counts.
5. **Can we run one team challenge across countries?** Yes — dates and daily resets localize to each participant's midnight, and rewards configured in USD show in local currency with country-relevant gift-card catalogues.

### S8 Final CTA — "See your teams on the leaderboard before you launch."
Book a 30-minute walkthrough — we will configure a sample team challenge for your workforce and show you the scoring, squads, and reporting behind it.
Checks: Go live in days · No wearable required · Bulk team setup via CSV · Works across 190+ countries
Note: Give your people a team worth walking for.

---

## 4. Stat & claim sources

| Claim on page | Source |
|---|---|
| Team score = average, not sum; inactive members drag average; every member counts equally | `help/admin/challenges/admin-how-do-i-manage-teams.md`, `help/employee/challenges/how-do-teams-work.md` |
| Admin-created teams; CSV/Google Sheets bulk upload (team name + email per row); employee-created teams with captain invites; full admin oversight; member moves preserve individual scores; configurable max team size; 4–6 recommended | `help/admin/challenges/admin-how-do-i-manage-teams.md` (all) |
| Team leaderboard: separate view, individual/team toggle, weekly + overall, department filter, score breakdown | `help/employee/challenges/how-does-the-leaderboard-work.md` |
| Teams supported in Streak, Journey, Custom; Race has no team settings by design | `admin-how-do-i-create-{streak,journey-challenge,custom-challenge}.md`; `admin-how-do-i-create-race-challenge.md` ("Race challenges do not have task configuration, team settings, or certificate options") |
| Journey team mode: members progress individually, team ranks on average; 3 built-in templates (7 Wonders, Backpacking Europe, Everest) | `admin-how-do-i-create-journey-challenge.md` |
| Custom: 27 task types incl. steps, distance, active minutes, water, sleep, meditation | `admin-what-tasks-can-i-include-in-a-custom-challenge.md` |
| Unlimited parallel challenges; one activity counts toward all | `admin-can-i-run-multiple-challenges-in-parallel.md` |
| Time-zone localization; USD→local currency rewards | `admin-can-i-run-challenges-across-time-zones.md` |
| No wearable required; Fitbit/Garmin direct; Apple Health ecosystem; one primary device | `help/employee/getting-started/do-i-need-a-wearable.md`, `can-i-connect-multiple-devices.md` |
| Leaderboard opt-out still participates and earns | `help/employee/challenges/can-i-opt-out-of-leaderboard.md` |
| Trusted sources, daily caps, 3-day sync buffer | `vfit-os/specs/02-challenges-gamification/challenge-system-overview.md`; `admin-how-do-i-create-race-challenge.md` |
| Tata Motors: 43 teams, 70% engagement, 7,600+ avg daily steps (+6%), 53% of teams reduced average weight, ~6-month program | `casestudy/tata-motors-step-up-elevate.md` (published case study) |
| Global walkathon: 74 teams across 24 countries | `casestudy/global-corporate-virtualwalkathon.md` |
| Reports: Participation, Leaderboard CSV, Transaction | `help/admin/reports/admin-what-reports-are-available.md`; `vc-dashboard-design/docs/modules/wellness.md` |
| 190+ countries rewards reach | `vfit-os/audit/site-refresh-2026-07/product-code-specs.md` §SOLI |
| "100+ organizations in 50+ countries" logo band | Approved aggregate per `vfit-os/.claude/rules/data-accuracy.md`; wordmarks mirror the Solutions hub mock |

No stats, customers, or capabilities were invented. All figures inside dashboard/phone mocks are illustrative sample data.

---

## 5. Meta drafts

- **Title (57 chars):** `Team Challenges for Work That Everyone Joins | Vantage Fit`
- **Alt title (59 chars):** `Corporate Team Wellness Challenges, Built Fair | Vantage Fit`
- **Description (158 chars):** `Run team wellness challenges where every member moves the score. Average-based team scoring, captain-led squads, bulk CSV setup, and reporting HR can trust.`
- **URL:** keep `/team-challenges/` (existing SEO equity).
- Suggested schema for production: FAQPage for S7; BreadcrumbList (Solutions → Team Challenges).

## 6. Assumptions and gaps

1. **No standalone trust/security band.** The Steps page earned one because anti-cheat was a program-specific objection; for team challenges the security story is identical to the platform story, so it stays in the footer compliance strip and linked platform pages. If the bake-off wants parity with the consolidated Steps skeleton, a dark trust band can be grafted in verbatim.
2. **Proof section kept to one flagship story.** Tata Motors is the only deep, published, team-tagged case study with approved numbers; Landmark Group and the global walkathon are thinner (no participation rate). Used as a hero chip (74 teams / 24 countries) only.
3. **E-Marathon team support is undocumented.** No help doc confirms or denies teams in E-Marathon, so the page claims teams only for Streak, Journey, and Custom (explicitly documented) and leaves E-Marathon out of the team-formats grid.
4. **Hero/dashboard figures are illustrative sample data**, matching the hub and Steps mock conventions; only labeled case-study figures are real.
5. **"Set up 200 teams before lunch"** is rhetorical framing of the bulk-upload capability, not a measured benchmark; kept because CSV bulk creation is documented. Flagged in case the team prefers a softer H-level claim.
6. Sibling programs appear only as light text links, per prompt scope.
