# Vantage Fit: Wellness challenges (library, flagship). Page brief

- **Page:** 1 of 6 in the Solutions set
- **Archetype:** Library / flagship (Section ① row 1)
- **URL:** `/solutions/wellness-challenges/`
- **Mock to build:** `claude-fable/vantage-fit-wellness-challenges-v1.html`
- **Stylesheet:** `<link rel="stylesheet" href="../styles/enterprise.css">` and nothing else. Everything else is a page-local `<style>` block.
- **Chrome:** paste nav, footer, closer and scripts from `scratchpad/research/chrome.html`. Nav self-location: `is-current` on the Solutions trigger, `is-page` + `aria-current="page"` on the `Wellness challenges` mega link and on the footer Solutions row 2.
- **Written:** 2026-08-11

---

## 1. Research takeaways that decided this page

Sourced facts only. `HELP` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/`. `SITE` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/src/`. `VOS` = `/Users/anjanpathak/work/gitcode/vc-os/vfit-os/specs/`.

### 1.1 There is a real catalogue, and it has exactly 21 entries

`SITE/data/wellness-challenges.ts` is the single source of truth for the marketing challenge library. I read it directly rather than trusting the dossier summary, and confirmed: **21 objects, each with a `name`, `tagline`, `category`, `format`, `type`, `description` and `href` to a live detail page.** Six category keys are declared in the type union; `holistic` has zero members, so the live library renders five categories. The live page prints "20+" only because `WellnessChallengesPage.astro:158-160` rounds a 22-slot card count down to the nearest ten.

**Decision:** the page renders all 21 as real, filterable cards and says "21" out loud. A page that claims to be a library and shows six cards is a teaser, not a library. Risk noted in §9.

### 1.2 The catalogue's own `type` field contradicts the product in two rows

`SITE/data/wellness-challenges.ts` types **Charity walk** as `Race` while describing it as GPS-tracked cumulative kilometres, and types **Team step challenge** as `Race` while it is a team competition. Race in the shipped product is steps-only, has **no target, no team settings and no certificate options** (`HELP/admin/challenges/admin-how-do-i-create-race-challenge.md:13, :59`). Both rows are therefore unprintable as `Race`.

**Decision:** the library cards carry **no VFit format chip at all.** Format taxonomy gets its own section (S5) where it is explained once, correctly, for all five self-serve formats. This kills the contradiction instead of papering over it, and it stops the library grid from becoming a second formats explorer.

### 1.3 Duration is a dead filter axis

Pulled from every detail-page spec bar (`SITE/components/marketing/*ChallengePage.astro`, summarised in `scratchpad/research/challenges.md` §2.1): **17 of 21 challenges run 30 days**, one runs "4 weeks (28-30 days)", three run 21 days. A duration filter would return "all of them" or "three of them".

**Decision:** the suggested "filter by category and duration" becomes **filter by category and by how it runs (solo / teams)**. The `format` field (`individual` / `team` / `both`) is real data in the same file, it splits the catalogue usefully, and "do we need to build teams?" is an actual HR rollout decision. Duration still appears on every card as a printed field, just not as a control. This is the one place I departed from the suggested architecture, and this is why.

### 1.4 The defining objection has a two-part product answer, and both parts are sourced

- **"Do we have to design a program ourselves?"** No. Templates ship with a pre-selected format, pre-set tasks and targets, balanced scoring, and suggested weekly themes; the admin sets dates, audience, branding, teams and certificates (`HELP/admin/challenges/admin-how-do-i-use-templates.md:17-54`). And *"Creating a challenge takes 5-10 minutes from the Admin Dashboard."* (`HELP/admin/challenges/admin-how-do-i-create-a-challenge.md:13`).
- **"Will employees actually join?"** They do not join. *"Employees do not self-join challenges. There is no browse-and-join flow."* (`VOS/product/02-challenges-gamification/challenges.md:42`). The admin sets a target audience by Country, City, Department, Gender, Age Range, Language or Health Risk Code, sees **a live preview of matching employees**, and picks **Enroll Immediately** or **Enroll When Active** (`HELP/admin/challenges/admin-how-do-i-set-target-audience.md:17-68`). The employee help article's own answer to "how do I join" is *"Action Required? None. You're already in."* (`HELP/employee/challenges/how-do-i-join-a-challenge.md:17-38`).

**Decision:** both halves are put in the **hero visual**, not deferred to a mid-page section. The hero pairs a library-browse frame with a create-challenge audience card. That is the whole page argument in one composition.

### 1.5 There is a second library asset nobody else is using

`SITE/data/wellness-challenge-builder-calendar.js:5-186` holds a 12-month themed programme calendar: theme, challenge name, and four weekly focuses per month. `scratchpad/research/challenges.md` §8 explicitly lists it as something **only the library page can own**.

**Decision:** it becomes S4, "A themed program for every month". It converts the buying objection from "what do we run in May?" to "here is the year". The **badge names in that file are campaign naming ideas, not product badges** (`challenges.md` §2.2), so every badge name is stripped from the copy deck.

### 1.6 Sources that conflicted, and which one this page follows

| Conflict | Sources | Followed |
|---|---|---|
| Bed time crafts is `format: "team"` in the data file, `Format: Individual` on its detail page | `SITE/data/wellness-challenges.ts:53` vs `SITE/components/marketing/BedtimeCraftsChallengePage.astro` | **Individual (Solo).** The detail page is the more specific source. Flagged in §9. |
| Digital detox is `category: "mental"` in the data file, rendered under Sleep & recovery on the live page | `SITE/data/wellness-challenges.ts:66` vs `WellnessChallengesPage.astro:76-82` | **Mental wellness.** The data file is the declared single source of truth and the component grouping is a rendering choice. Also keeps category counts honest (5/5/4/3/4). Flagged in §9. |
| Weight Burn mechanic: weight loss (help docs) vs a display wrapper over a Calorie Burn race (code-verified spec) | `HELP/admin/challenges/admin-what-challenge-formats.md:85` vs `VOS/product/02-challenges-gamification/challenges.md:73` | **Neither is described.** Weight Burn is named as an account-manager format with no mechanic sentence. Precedence rule cannot resolve it safely and the code-verified version carries a legal guardrail. |
| Step cap: 25,000 (help), disabled (code-verified), 10,000/hr + 50,000/day (Draft) | three sources, three answers | **No number, and no "no ceiling" superlative either.** The fairness section talks about the 100%-of-daily-target cap on non-step tasks, which is unambiguous, and says nothing about step ceilings. |
| Manual activity types: 47+ vs 65 | `VOS/product/10-integrations/device-integrations.md:143` vs `VOS/product/01-core-tracking/activity-tracking.md:244` | **"65+ activity types"**, the help-doc phrasing that outranks both (`challenges.md` addendum B2). Used once, in FAQ 4. |
| Task type count: 27 (help + code-verified) vs "20+" (Draft spec) | `HELP/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md:13` | **27.** Used once, on the Custom Challenge format card. |
| Challenge type count: 9 (code-verified) vs "7 distinct challenge types" (Draft) | `VOS/product/02-challenges-gamification/challenges.md:230` vs `VOS/02-challenges-gamification/challenge-system-overview.md:8` | **9: five self-serve, four account-manager configured.** |
| Templates: SHIPPED help article vs "Planned" in the code-verified roadmap | `HELP/admin/challenges/admin-how-do-i-use-templates.md` vs `VOS/product/…/challenges.md:219` | **Treated as SHIPPED**, with **no template count published** (no source enumerates them). |
| URL prefix: `/solutions/…` (signed-off menu) vs root-level, no prefix (`vfit-os/.claude/rules/seo-conventions.md:69,83`) | | **The signed-off menu.** It is the newer decision. Flagged in §9 as an unresolved IA question, not silently picked. |

### 1.7 Facts that shaped individual sections

- **Scoring fairness, quotable:** *"For other task types, you can earn up to 100% per day, meaning everyone has an equal opportunity regardless of how much they exceed the target."* (`HELP/employee/challenges/how-does-the-leaderboard-work.md:47`)
- **Team score is an average**, never a sum (`HELP/admin/challenges/admin-how-do-i-manage-teams.md:19`).
- **Leaderboard opt-out** hides an employee from individual rankings but they still participate, still earn points, and **their score still counts toward the team average** (`HELP/employee/challenges/can-i-opt-out-of-leaderboard.md:24-37`).
- **Wheelchair Mode** adds Wheelchair as a workout type and its GPS workouts count toward **distance and active-minutes** tasks. It does **not** convert pushes to steps (`HELP/employee/getting-started/what-is-wheelchair-mode.md:45-64`).
- **Badges are recognition-only and award no points.** 7 categories, over 25 levels, automatic, within minutes (`HELP/admin/challenges/admin-how-do-badges-work.md:12, :130-138`).
- **Certificates are optional per challenge** and Race challenges have no certificate option (`HELP/admin/challenges/admin-how-do-i-configure-certificates.md:17-20`; `admin-how-do-i-create-race-challenge.md:59`). Always phrased "if enabled".
- **No limit on concurrent challenges.** *"You can run as many challenges at the same time as you want."* Each has its own leaderboard, point pool and completion criteria, and one walk contributes to every challenge whose tasks it matches (`HELP/admin/challenges/admin-can-i-run-multiple-challenges-in-parallel.md:13-22`; `admin-what-challenge-formats.md:106`).
- **Custom is the recommended default:** *"Custom is the go-to format for most clients. If you are unsure which format to pick, start here."* (`HELP/admin/challenges/admin-what-challenge-formats.md:28`)
- **Late joiners** score from the join date forward, no retroactive credit, no penalty (`HELP/admin/challenges/admin-how-do-i-add-remove-participants.md:61-69`).
- **Custom Journey map** is a design project: an account-manager setup call, annual clients with sufficient order value, **2 to 3 week lead time** (`HELP/admin/challenges/admin-how-do-i-create-journey-challenge.md:48-58`).

### 1.8 What the sibling pages already own (so this page stays shallow)

Per `scratchpad/research/challenges.md` §8: the steps page owns the five-format **tab** explorer and the data-integrity band; the multi-activity page owns the 27-task explorer and the Move / Nourish / Reset / Thrive theme strip; the team page owns team formation and the average-score argument in depth; the virtual marathon page owns E-Marathon, time zones and the run book.

**Decision:** S5 here is a **compact five-card grid, not a tab explorer**, and it adds the one thing no sibling has: the honest 5-versus-4 split between what HR builds alone and what the account manager sets up. Everything deeper is a cross-link.

---

## 2. Strategy

### 2.1 The buyer

HR Director or wellness program owner at a 500 to 25,000 employee company, told to "run a wellness program this year", who has a budget, a launch date and no program design. Secondary reader: the CHRO who will ask "did anyone actually use it?"

### 2.2 The one thing this page must land

**You do not have to invent a program, and your employees do not have to find one.** Pick from 21 ready-to-run designs, set who is in it, and everyone who matches is enrolled.

### 2.3 Why this section order

The page is a **catalogue**, so it is structured the way a good catalogue is structured: enter by intent, browse the shelf, then learn the mechanics.

| # | Section | Job | Why here |
|---|---|---|---|
| S1 | Hero | Breadth plus readiness | Both halves of the objection in one visual |
| S2 | Start from the outcome you want | Intent router | A buyer who knows the outcome but not the format leaves in 8 seconds without this. Also the page's primary routing spine into the four sibling pages. |
| S3 | The library | The shelf | The signature. Everything before it is a way in; everything after is a way to trust it. |
| S4 | A themed program for every month | The calendar | Converts "what do we run?" into "here is the year". Nothing else in the set owns this. |
| S5 | Formats | The mechanics | Deliberately after the browse, because a buyer picks a program before they care what a Streak is. |
| S6 | How any challenge runs | The rollout | Compressed to four beats, because siblings own the depth. |
| S7 | Fair, inclusive, and private | The objection under the objection | "Only the fit people will play" is the reason wellness programs die. Answered with product rules, not reassurance. |
| S8 | Proof | Did it work | Four programs of four lengths, each labelled with what it measured. |
| S9 | FAQ | Rollout blockers | Five, all real. |
| S10 | Related | Route out | The four sibling challenge pages. |
| S11 | Closer | Convert | |

### 2.4 What I deliberately left out, and why

| Left out | Why |
|---|---|
| **The standard `.trust-screen` band** | This page's objection is participation, not privacy. A generic security band here is filler that pushes the proof section below the fold. The two privacy facts a challenge rollout actually needs (leaderboard opt-out, aggregate-only HR visibility) are inside S7 where they answer something, and the compliance line plus the link to `/features/security-and-compliance/` rides in `.fair-fine`. The other five pages keep the band. This is the deliberate architectural difference the bake-off asked for, not an omission. |
| **A tab-based formats explorer** | The steps page owns it. Rebuilding it here would give two pages the same spine. |
| **The 27-task explorer** | The multi-activity page owns it. Referenced as a number on one card, linked, not rebuilt. |
| **A phone mock in the hero** | Every sibling has one. The signature here is a catalogue, so the hero is a library frame plus an audience card. |
| **Challenge thumbnails from `wellness-challenge-thumbnails.js`** | The design system bans photography outside customer avatars and the two approved product PNGs (`design-system.md` §10.4). 21 photoreal Cloudinary rasters would also cost roughly 21 network requests on a page whose value is scanning speed. Cards are typographic. |
| **A VFit format chip on library cards** | Two of 21 rows contradict the product's Race definition (§1.2). |
| **A duration filter** | Degenerate axis (§1.3). |
| **Wellness Score, Leagues, Lite Mode** | All account-manager gated or tenant-tier facts. They would need caveats longer than the claim. The virtual marathon page took the same decision on Lite Mode. |
| **Trees Challenge, manual/QR join, admin-created training plans, admin self-serve for the ops formats** | All Backlog in `VOS/product/…/challenges.md:214-218`. Not present tense, so not on the page. |
| **The 2026 calendar's badge names** | Campaign naming ideas, not product badges. |
| **Step-cap and anti-cheat detail** | Three contradicting sources, and the steps page owns the integrity band. |
| **An `.illume` scroll-lit statement section** | Heavy, homepage-only, and this page's emotional beat is the shelf itself. |

---

## 3. Section-by-section copy deck

Everything below is final copy. The builder writes no new strings. Sentence case throughout, terminal periods on H2s, no em-dashes anywhere.

### Page furniture

- `<title>`: `Employee Wellness Challenges | Vantage Fit`
- `<meta name="description">`: see §6
- `<meta name="robots" content="noindex, nofollow">` (required, it is a preview mock)
- Nav: Solutions trigger gets `is-current`; the `Wellness challenges` mega link gets `is-page` and `aria-current="page"`
- Footer: `Wellness challenges` in the Solutions column gets `aria-current="page"` and `style="color:#fff;font-weight:700"`
- Skip link as the first child of `<body>`
- Section ids in order: `#hero` `#outcomes` `#library` `#calendar` `#formats` `#rollout` `#fairness` `#proof` `#faq` `#related` `#demo`

---

### S1 Hero. `#hero`, class `hero challenges-hero`

**Eyebrow:** `Challenge library`

**H1** (one `<em>`, gets the coral gradient fill):
> 21 employee wellness challenges, ready to run. <em>Enrollment is automatic.</em>

**Lead:**
> Browse by what you want to change, pick a program, and set the audience. Employees are enrolled by rule, so there is nothing for them to go and join.

**Buttons (`.btn-row`):**
- `.btn .btn-primary` → `https://www.vantagefit.io/request-demo/` → **Book a demo**
- `.btn .btn-outline` → `#library` → **Browse the library**

**`.hero-note`** (lime dot via `span::before`):
> Creating a challenge takes 5 to 10 minutes from the admin dashboard.

**Logo band** (last child of `<header class="hero">`, verbatim from `chrome.html`):
- `.logos-label`: **Trusted by 100+ organizations worldwide**
- `.logo-word` × 7: `TATA MOTORS` · `WIPRO` · `TEVA` · `GODREJ` · `TEXAS INSTRUMENTS` · `HEIDRICK & STRUGGLES` · `BRAZOSPORT ISD`

---

### S2 Start from the outcome you want. `#outcomes`, `.hub-section .outcomes-screen`, ground `var(--canvas)`

**Eyebrow:** `Start here`
**H2:** `Start from the outcome you want.`
**Lead:** `Five goals HR teams actually get handed, and the programs that produce them.`

Five `.format-card`s in the `.format-grid` five-item layout (`repeat(6,1fr)`, cards span 2, cards 4 and 5 span 3). Each carries a `.format-glyph`, an `h3`, a one-line `p`, a `.best-for` footer whose `<b>` label reads **Start with**, and a `.text-link` route.

| # | H3 | `p` | `.best-for` (label: Start with) | `.text-link` |
|---|---|---|---|---|
| 1 | Get everyone moving | One number everyone understands, and a phone is enough to count it. | Step it up challenge, Team step challenge | See step challenges → `/solutions/step-challenges/` |
| 2 | Cover more than steps | Weekly themes that pull in sleep, food, mind and movement. | Mental health awareness, Sleep challenge | See multi-activity challenges → `/solutions/multi-activity-challenges/` |
| 3 | Bring remote and hybrid teams together | Teams rank on the average of member scores, so nobody carries the group. | Team yoga, Lunch walk | See remote and hybrid challenges → `/solutions/remote-team-wellness/` |
| 4 | Build a habit that survives a bad week | One small target a day, so a missed day costs that day and not the program. | Breathing exercise, Sugar free | Browse habit challenges → `#library` |
| 5 | Run one company-wide moment | A distance event the whole company can finish, counted in kilometres. | Charity walk | See virtual marathon → `/solutions/virtual-marathon/` |

> **Correction, review pass.** Cards 4 and 5 originally read "ranked by days completed rather than totals" and "counted from everyday steps". Both were unprintable. The first attaches the **Streak Challenge** ranking rule to Breathing exercise and Sugar free, and Streak is **steps-only** (`challenges.md` §1.2 row 4), so neither program can rank that way. This is the same data-file defect §1.2 caught for `Race`, one row further down: **9 of the 21 rows are typed `Streak` on non-step mechanics.** The second attributes step-derived distance to **Charity walk**, which is GPS-tracked cumulative kilometres (`challenges.md` row 21) and is printed as "Distance from GPS workouts and wearables" on its own library card three sections below. Both replacements are format-neutral and true of every program named.

**Glyph briefs** (74×44 inline SVG, greys `rgba(41,41,76,.14/.16/.24/.34)` plus one `#41d8b4` and one `#F15162` accent, per `design-system.md` §3.B):
1. A rising row of footprint marks, last one coral.
2. Four stacked task bars of different lengths, one mint, one coral.
3. Two clusters of three dots joined by a dashed line, cluster averages drawn as a single mint bar.
4. Seven day-squares in a row, six filled mint, one hollow, then the row continues.
5. A start pin, a dotted arc, a finish flag in coral.

---

### S3 The library. `#library`, `.hub-section .library-screen`, ground `#fff`

**Eyebrow:** `The library`
**H2:** `21 challenges, grouped by what they change.`
**Lead:** `Filter by focus, and by whether it runs solo or in teams. Every program here is built from one of the five challenge formats in the dashboard.`

**Filter row A, `.lib-filters` with `role="group" aria-label="Filter by focus"`.** Six `.lib-pill` buttons, `aria-pressed` toggled, `All` pressed on load. Counts printed in a `<span class="lib-count">`:

`All 21` · `Physical fitness 5` · `Mental wellness 5` · `Nutrition & hydration 4` · `Sleep & recovery 3` · `Team & social 4`

**Filter row B, `.lib-filters` with `role="group" aria-label="Filter by how it runs"`.** Label text `Runs as` then three `.lib-pill` buttons:

`Any` · `Solo` · `Teams`

("Solo" matches `individual` and `both`. "Teams" matches `team` and `both`.)

**Live region:** `<p class="lib-status" role="status" aria-live="polite">Showing 21 of 21 challenges</p>`, updated by the filter script.

**Grid:** `.lib-grid`, `repeat(3,1fr)` at desktop, `repeat(2,1fr)` at 1100px, 1 column at 640px, gap 14px. Each card:

```html
<article class="lib-card reveal" data-cat="physical" data-runs="both">
  <span class="lib-tag">Physical fitness</span>
  <h3>Step it up challenge</h3>
  <span class="lib-line">One Step Ahead</span>
  <p>Log daily steps and race up the team leaderboard.</p>
  <div class="lib-meta"><span>30 days</span><span>Solo or teams</span><span>Steps, auto-synced</span></div>
</article>
```

`.lib-line` is the tagline, reproduced verbatim from the data file in its original Title Case. It is the only Title Case string on the card.

**The 21 cards, in this order:**

| # | H3 (name) | `.lib-line` (tagline, verbatim) | `.lib-tag` | `data-cat` | `data-runs` | `p` | Meta 1 | Meta 2 | Meta 3 |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Step it up challenge | One Step Ahead | Physical fitness | physical | both | Log daily steps and race up the team leaderboard. | 30 days | Solo or teams | Steps, auto-synced |
| 2 | Cardio challenge | Every Workout Earns Points | Physical fitness | physical | both | Any workout counts, ranked on calories burned. | 30 days | Solo or teams | Workout calories |
| 3 | Weight loss challenge | Sustainable Progress, Real Results | Physical fitness | physical | both | Movement, food logging and mindful habits in one program. | 30 days | Solo or teams | Weight, food and activity logs |
| 4 | Cycle to work | Commute Smarter, Live Better | Physical fitness | physical | individual | A streak for every day someone commutes by bike. | 30 days | Solo | Cycling, app or wearable |
| 5 | Push-up challenge | Stronger Every Day | Physical fitness | physical | both | Daily push-up sets, no equipment and no gym. | 30 days | Solo or teams | Manual activity log |
| 6 | Breathing exercise | Ten Minutes to Reset | Mental wellness | mental | both | Ten minutes of breathwork a day, logged as a streak. | 30 days | Solo or teams | Mindfulness session log |
| 7 | Daily affirmations | Rewire How You Think | Mental wellness | mental | individual | One positive affirmation a day, checked off in the app. | 30 days | Solo | Daily task check-in |
| 8 | Work life balance | Sustainable Beats Heroic | Mental wellness | mental | both | Breaks, offline hours and mindful transitions, logged daily. | 30 days | Solo or teams | Daily task check-in |
| 9 | Mental health awareness | Check In, Not Out | Mental wellness | mental | both | Mood check-ins and mindfulness sessions across four weeks. | 30 days | Solo or teams | Mood log and mindfulness |
| 10 | Digital detox challenge | Unplug to Recharge | Mental wellness | mental | both | A daily screen-time limit, with offline hours logged. | 4 weeks | Solo or teams | Daily task check-in |
| 11 | Mindful eating challenge | The Mindful Plate | Nutrition & hydration | nutrition | both | Slow down and log every meal for four weeks. | 30 days | Solo or teams | Meal log |
| 12 | No caffeine | Break the Dependency | Nutrition & hydration | nutrition | individual | Thirty clean days off caffeine, tracked one day at a time. | 30 days | Solo | Food log and daily check-in |
| 13 | Plant based diet | Eat Clean, Feel the Difference | Nutrition & hydration | nutrition | both | Thirty days of plant-based meals, logged in the food diary. | 30 days | Solo or teams | Meal log |
| 14 | Sugar free | Cut the Sugar, Feel the Shift | Nutrition & hydration | nutrition | individual | Thirty sugar-free days, one check-in at a time. | 30 days | Solo | Food log and daily check-in |
| 15 | Time to wind down | Signal Your Body It's Time | Sleep & recovery | sleep | individual | A 30-minute evening wind-down routine, every night. | 30 days | Solo | Mindfulness session log |
| 16 | Bed time crafts | Create Your Way to Sleep | Sleep & recovery | sleep | individual | Swap pre-bed screens for journaling, sketching or reading. | 21 days | Solo | Daily task check-in |
| 17 | Sleep challenge | 7 Hours, Every Night | Sleep & recovery | sleep | both | Seven hours a night, logged daily and tracked as a streak. | 30 days | Solo or teams | Sleep log |
| 18 | Team step challenge | May the Best Team Win | Team & social | team | team | Departments head to head on steps, scored on the team average. | 30 days | Teams | Steps, auto-synced |
| 19 | Team yoga | Stretch Together, Stress Less | Team & social | team | both | A shared weekly yoga session your department shows up for. | 21 days | Solo or teams | Yoga log and active minutes |
| 20 | Lunch walk | Best Conversations Happen Walking | Team & social | team | both | A midday team walk away from the desk, every working day. | 21 days | Solo or teams | Steps, auto-synced |
| 21 | Charity walk | Walk for a Cause | Team & social | team | team | Team kilometres counted toward a shared cause. | 30 days | Teams | Distance from GPS workouts and wearables |

**Trailing note** (`.format-note`, `.8rem`, muted):
> Durations are the recommended program length. Your admin sets the real start and end dates when the challenge is published.

**Section `.text-link`:**
> See how a multi-activity program is built → `/solutions/multi-activity-challenges/`

**Filter script spec** (page-local, ~25 lines): two state variables (`cat`, `runs`, both defaulting to `all`), a click handler on `.lib-pill` that sets `aria-pressed` within its own group, a pass over `.lib-card` toggling `hidden`, and a rewrite of `.lib-status` to `Showing N of 21 challenges`. When a filter returns zero cards, `.lib-status` reads `No challenges match that combination. Clear a filter to see more.` Pills are `<button type="button">`, keyboard-operable for free, with `:focus-visible { outline: 3px solid var(--coral-dark); outline-offset: 2px; }`.

---

### S4 A themed program for every month. `#calendar`, `.hub-section .calendar-screen`, ground `var(--canvas)`

**Eyebrow:** `Plan the year`
**H2:** `A themed program for every month.`
**Lead:** `Run it as it stands or take the months that suit your calendar. Each one carries a theme, a challenge name and four weekly focuses.`

`.year-grid`, `repeat(4,1fr)` at desktop, `repeat(2,1fr)` at 1100px, 1 column at 640px, gap 12px. Each `.year-card` is `padding:18px 20px; border:1px solid var(--line); border-radius:16px; background:var(--paper)` with `.year-month` (`.62rem`, 800, uppercase, `letter-spacing .12em`, `--coral-dark`), `.year-theme` (`.72rem`, muted), `.year-name` (`.95rem`, 750, `--ink`), `.year-weeks` (`.7rem`, muted, `line-height 1.5`).

| `.year-month` | `.year-theme` | `.year-name` | `.year-weeks` |
|---|---|---|---|
| Jan | Dry January | New Year, Better You Challenge | Hydrate and Elevate · Move to Improve · Stress Less · Healthy Replacements |
| Feb | Heart Month | Heart Health Month Challenge | Start Strong · Cardio Boost · Stress-Free Heart · Rest and Recover |
| Mar | National Nutrition Month | Mindful March | Mindful Beginnings · Building Consistency · Stress Relief · Mindful Celebration |
| Apr | Stress Awareness Month | Spring Into Fitness | Fresh Start · Move with Nature · Stress Less · Fitness Boost |
| May | Mental Health Awareness Month | Mind in Motion | Check In Daily · Move for Your Mind · Connect and Share · Sustain the Practice |
| Jun | Men's Health Month | Strong June | Foundations · Cardio and Core · Yoga Day Build-Up · Preventive Care Week |
| Jul | Plastic Free July | Plastic-Free Steps | Hydration without Plastic · Outdoor Focus · Active Commuting · Team Cleanup |
| Aug | National Wellness Month | Wellness Habit Stack | Water and Steps · Add Movement · Add Mindfulness · Stack and Sustain |
| Sep | Self-Care Awareness Month | Whole-Self September | Physical · Mental · Social Self-Care · Integration Week |
| Oct | Breast Cancer Awareness Month | Pink Steps | Aware and Active · Cardio for Cause · Team Walkathon · Sustain and Celebrate |
| Nov | World Vegan Month | Plant-Powered November | One Plant Meal Daily · Plant + Move · Conscious Consumption · Plant-Based Streak |
| Dec | Universal Human Rights Month | Finish Strong | Inclusive Start · Reflect and Recharge · Holiday-Proof Your Wellness · Close the Year |

**Trailing note** (`.format-note`):
> A planning calendar, not a product setting. Four themed weeks is exactly how a Custom Challenge is configured, one week at a time.

---

### S5 Formats. `#formats`, `.hub-section .formats-screen`, ground `#fff`

**Eyebrow:** `Formats`
**H2:** `Five formats you build yourself. Four your account manager sets up.`
**Lead:** `Every program in the library is one of these. Pick the format and the scoring rule comes with it.`

Five `.format-card`s, `.format-grid` five-item layout. `.best-for` `<b>` label reads **Ranked by**.

| # | H3 | `p` | Ranked by |
|---|---|---|---|
| 1 | Custom Challenge | Weekly themes, each with its own mix of tasks drawn from 27 task types. The Help Center calls it the go-to format if you are unsure. | Total points across all tasks and weeks |
| 2 | Race Challenge | A pure step leaderboard with no target. No tasks, no teams, no certificate. | Total steps |
| 3 | Journey Challenge | Steps unlock milestones along a route map. Three built-in templates ship with it. | Points earned at milestones |
| 4 | Streak Challenge | One daily step target. A miss resets the streak, it does not end the challenge. | Days completed, with total steps as the tiebreaker |
| 5 | E-Marathon | Steps convert to distance at a ratio you set, 1,000 steps to 1 km by default. | Total distance covered |

**Glyph briefs:**
1. Four stacked task rows grouped into two week blocks, one row mint.
2. Two runner-lane bars racing right, the longer one coral.
3. A dotted route with three milestone pins, the third mint.
4. Seven day squares, six mint-filled, one hollow, streak line continuing past it.
5. A step-count bar transforming into a distance ruler with a coral tick.

**Ops-configured strip** (`.ops-strip`, sits under the grid: a `var(--canvas)` inset with `1px solid var(--line)`, `border-radius:16px`, `padding:20px 22px`):
- Label (`.ops-label`, `.62rem`, 800, uppercase, `letter-spacing .12em`, muted): **Set up with your Vantage Fit account manager**
- Four `.ops-item`s, each `<b>` name plus one muted line:
  - **Level Challenge**: escalating step targets, one level per week.
  - **Marathon Event**: a real GPS-tracked running event with distance tiers.
  - **Weight Burn**: available on request.
  - **Training plans**: employees start their own from a Vantage Fit library.

**Trailing note** (`.format-note`):
> Nine formats in total: five you create from the dashboard, four your account manager configures.

**Section `.text-link`:**
> See the step formats in depth → `/solutions/step-challenges/`

---

### S6 How any challenge runs. `#rollout`, `.hub-section .rollout-screen`, ground `var(--canvas)`

**Eyebrow:** `Rollout`
**H2:** `How any challenge in this library runs.`
**Lead:** `Same four beats, whichever program you pick.`

`.steps` 4-up numbered cards (`.step` with `.step-no` and `.step-tag`):

| No | H3 | `p` | `.step-tag` |
|---|---|---|---|
| 1 | Set who is in it | Filter by country, city, department, age range, language and more, with a live count of who matches before you publish. | 01 |
| 2 | Employees are enrolled, not recruited | Everyone who matches is added when the challenge starts, or when they next open the app, so new hires are picked up too. | 02 |
| 3 | Activity tracks itself | Steps sync from Apple Health and Google Fit, or from a connected Fitbit or Garmin. Everything else is a tap in the app. | 03 |
| 4 | Recognition lands on its own | Badges fire on thresholds within minutes, certificates generate at the end if you enabled them, and Vantage Points land in the wallet. | 04 |

**Trailing note** (`.format-note`):
> Creating a challenge takes 5 to 10 minutes from the admin dashboard, and you can run as many at the same time as you want.

**Section `.text-link`:**
> See how points and gift cards work → `/solutions/wellness-rewards-program/`

---

### S7 Fair, inclusive, and private. `#fairness`, `.hub-section .fairness-screen`, ground `#fff`, with a dark `.fairband` inset

**Section head** (outside the band):
- **Eyebrow:** `Fair by design`
- **H2:** `The rules protect the people most likely to opt out.`
- **Lead:** `Scoring, teams and privacy settings are built so a first-time participant is not out of it on day one.`

**Inside `.fairband`** (left column):
- `.eyebrow` (renders `--lime` on dark): `Built into the scoring`
- Compressed `h3` (`.fairband h3`, max-width 460px): `Nobody has to be an athlete to place well.` **Review-pass correction: this was specified as an `h2`, which put a second section-level heading inside a section already titled by `#fairness-heading`. It is an `h3`. The CSS selector moved with it; the two elements render identically because `enterprise.css` gives `h1, h2, h3` the same weight and the page-local rule sets the size.**
- `.lead`: `Four rules that apply to every challenge in the library, whatever format it runs on.`

**`.fair-list`, four `.fair-item`s** (`<b>` title, `<p>` body, 17px mint-stroke SVG in the `i` tile):

| `<b>` | `<p>` | Icon brief |
|---|---|---|
| Everyone can max out the day | Non-step tasks score as a percentage of the daily target and cap at 100% a day, so going far over the target does not buy a bigger lead. | A gauge topping out at a filled arc |
| Team score is an average | Team leaderboards rank on the average of member scores, not the total, so a bigger team is not a better team. | Three dots resolving into one bar |
| Opting out of the leaderboard does not opt you out | Employees can hide from individual rankings in Settings, keep taking part, keep earning points, and their score still counts toward the team average. | An eye with a slash, next to a still-checked box |
| Wheelchair mode is a setting, not a separate program | Turning it on adds Wheelchair as a workout type. Route, distance and pace track exactly as they do for a run, and count toward distance and active-minutes tasks. | A wheelchair glyph on a route line |

**`.fair-fine`** (top hairline, `.72rem`, `rgba(255,255,255,.62)`):
> HR sees participation and rankings. Weight, assessment answers, lab reports, food logs and mood logs stay with the employee. Vantage Fit operates under HIPAA guidelines and is SOC 2 Type II audited.

**`.text-link .text-link-light`:**
> Explore security and compliance → `https://www.vantagefit.io/features/security-and-compliance/`

**Right column of `.fairband`: the score-breakdown mock.** See §4.3.

---

### S8 Proof. `#proof`, `.hub-section .proof-hub`, ground `#f6f7f4`

**Eyebrow:** `Customer programs`
**H2:** `Four programs, four workforces, four measured results.`

> **Correction, review pass.** The H2 read "four lengths". The four programs run 28 days, six months, two weeks and two weeks, so only three lengths are distinct and the headline counted wrong. "Workforces" is a plain descriptor of four separate named customers and adds no metric claim.
**Lead:** `Each number is labelled with what it actually counted, and links to the customer story it came from.`

`.results-grid`, four `.result-card`s. The `.segment` line links to the case study.

| `.stat` | `<p>` | `.segment` (line 1 / line 2) | `.segment` link |
|---|---|---|---|
| 88% | engagement rate over 28 days, with 500+ of 660 invited employees active | IBS Software · March to Fitness / Mar 1-28, 2024 | `https://www.vantagefit.io/casestudy/ibs-software-case-study/` |
| 59% | engagement rate across plant locations over six months | Tata Motors · Step & Stride Challenge / 6-month program | `https://www.vantagefit.io/casestudy/tata-motors-case-study/` |
| 86% | engagement rate over a two-week challenge with 132 active participants | Brazosport ISD · Fit Wars / May 6-19, 2024 | `https://www.vantagefit.io/casestudy/brazosport-case-study/` |
| 97% | participation rate in a two-week walkathon of 72+ participants | POSOCO · Walking Miles, Losing Inches / Dec 6-19, 2021 | `https://www.vantagefit.io/casestudy/posoco-walkathon-challenge/` |

**`.proof-fine`:**
- `small`: `Results from named customer programs. Engagement and participation are different measures, and each card names the one its program reported. Outcomes vary by workforce and program design.`
- `.text-link`: `See the reporting behind these numbers →` `/solutions/workforce-health-insights/`

**`.quote-duo`, two `.quote-band.text-only` cards:**

1. `<blockquote>`: `"We love the Vantage Fit app! The wide variety of wellness options kept our team interested week by week."`
   `.quote-who`: `ISKL`
2. `<blockquote>`: `"It is engaging and has features that keep everyone motivated. From tracking activity levels to earning rewards, the app has made wellness accessible and fun for all our employees."`
   `.quote-who`: `Tara Shore, Niche Technology`

> Builder note: both quotes are verbatim from the approved register. Do not repunctuate, do not trim, do not add a title to ISKL. The single exclamation mark in quote 1 is the page's only one; do not add another anywhere.

---

### S9 FAQ. `#faq`, `.hub-section .faq-screen`, ground `#fff`

**Eyebrow:** `Before you launch`
**H2:** `Questions HR asks before the first challenge.`

Five native `<details class="faq-item">`. First one `open`.

**1. What is an employee wellness challenge?**
> An employee wellness challenge is a time-bound program in which a company sets one or more healthy targets, tracks progress automatically from phones and wearables, and ranks or recognizes the people taking part. In Vantage Fit, HR picks a format, sets a target audience, and every matching employee is enrolled without signing up. Progress appears on individual and team leaderboards, and taking part can earn points, badges and a certificate.

**2. Do employees have to sign up?**
> No. There is no browse-and-join flow. HR sets a target audience using filters such as department, location, age range or language, and everyone who matches is enrolled. You can enroll everyone immediately, or choose Enroll When Active so new hires and late installers are picked up as they open the app. Late joiners score from their join date forward, with no retroactive credit and no penalty.

**3. Do we have to design the program ourselves?**
> No. Start from a template in the dashboard, which arrives with a format, tasks, targets, balanced scoring and suggested weekly themes, then set your own dates, audience and branding. Level, Marathon Event, Weight Burn and training plans are set up with your Vantage Fit account manager instead. A custom Journey map with your own artwork is a design project with a 2 to 3 week lead time, for annual clients.

**4. Does everyone need a wearable?**
> No. Steps come from the phone through Apple Health and Google Fit. Employees who own a Fitbit or Garmin can connect one primary device instead, and the app uses that device's data exclusively so nothing is double counted. Everything that is not a step, including water, sleep, meals, yoga and mood, is logged in the app, across 65+ activity types.

**5. Can we run more than one challenge at once?**
> Yes, with no limit. Each challenge has its own leaderboard, point pool and completion criteria, and a single walk contributes to every challenge whose tasks it matches. A common pattern is an always-on streak underneath a shorter seasonal race.

---

### S10 Related. `#related`, `.related-screen`, ground `var(--canvas)`

**Eyebrow:** `Keep exploring`
**H2:** `Go deeper on one format`

**Four** `.related-row` cards (see §4.5 for the grid override). Description lines are verbatim from the signed-off mega-menu.

| H3 | `p` | href |
|---|---|---|
| Step challenges | Company-wide step goals that get everyone moving. | `https://www.vantagefit.io/solutions/step-challenges/` |
| Multi-activity challenges | Any activity, solo or in teams, over themed weeks. | `https://www.vantagefit.io/solutions/multi-activity-challenges/` |
| Remote and hybrid team challenges | Wellness that works away from the office. | `https://www.vantagefit.io/solutions/remote-team-wellness/` |
| Virtual marathon | Distance events powered by steps. | `https://www.vantagefit.io/solutions/virtual-marathon/` |

Icon briefs: footprints · four stacked task bars · two linked person glyphs · a route with a finish flag. Each `h3` keeps the 14px coral arrow SVG.

---

### S11 Closer. `#demo`, `.final`

**H2:** `See the library on your own headcount.`
**`p`:** `In a 30-minute demo we will pick a starting program for your workforce, walk the employee app, and show the participation reporting your leadership will see.`
**Buttons:** `.btn .btn-primary` → `https://www.vantagefit.io/request-demo/` **Book a demo** · `.btn .btn-outline` → `https://www.vantagefit.io/pricing/` **See pricing**
**`.final-checks`** (three spans): `Set up in 5 to 10 minutes` · `No wearable required` · `No obligation`
**`.final-note`:** `Start with one program. Add the next one when it lands.`

---

## 4. Product-real UI spec

Five drawn surfaces. All hand-built HTML/CSS/SVG, no images. Every one carries `role="img"`, a full `aria-label` ending **"Figures shown are illustrative."**, `aria-hidden="true"` on all decorative children, a visible `<span class="mock-tag">Illustrative data</span>`, and `font-variant-numeric: tabular-nums` on digits.

### 4.1 Hero, primary surface: the library browse frame (`.dash`)

Reuses `.dash` / `.dash-top` / `.dash-dot` / `.dash-url` / `.dash-body` / `.dash-title` from `enterprise.css`. Positioned `top:6px; left:0; width:min(100%,430px)`, rotated `1.1deg`, shadow `0 30px 74px rgba(41,41,76,.18)`.

- `.dash-title` `<small>`: `Vantage Fit · Challenge library`
- `.dash-title` `<strong>`: `Pick a program to run`
- `<span class="mock-tag">Illustrative data</span>` in the title row
- **`.hl-pills`** (page-local): five 9px-radius chips, `.7rem`, first one filled `--ink` white-on-dark, the rest `var(--soft)` on muted: `All` · `Physical` · `Mental` · `Nutrition` · `Sleep`
- **`.hl-grid`** (page-local): `repeat(2,1fr)`, gap 8px, six `.hl-tile`s. Each tile is `padding:10px 11px; border:1px solid var(--line); border-radius:11px;` with a `<b>` (`.74rem`, 700) and a `<span>` (`.62rem`, muted):

| `<b>` | `<span>` |
|---|---|
| Step it up challenge | 30 days · Solo or teams |
| Mental health awareness | 30 days · Solo or teams |
| Sleep challenge | 30 days · Solo or teams |
| Team step challenge | 30 days · Teams |
| Mindful eating challenge | 30 days · Solo or teams |
| Lunch walk | 21 days · Solo or teams |

`aria-label`: *"Challenge library browser showing filter chips for focus areas and six ready-to-run challenge cards including Step it up challenge and Team step challenge. Figures shown are illustrative."*

### 4.2 Hero, secondary surface: the audience card (`.aud-card`)

A `.launch-mock`-shaped white card, `width:238px`, `border-radius:16px`, `box-shadow:0 22px 54px rgba(41,41,76,.16)`, positioned `right:-10px; bottom:6px; z-index:2`, rotated `-2.4deg`. It replaces the `.phone` that every sibling page uses.

- `.lm-head`: `<b>Create challenge</b>` / `<span>Step 5 of 7 · Target audience</span>`
- `.lm-row` ×3: `Country` → `All` · `Department` → `All` · `Age range` → `All`
- `.lm-row` with a `.lm-chip`: `Audience` → `1,284 employees match`
- Two `.lm-opt` radio cards: **Enroll immediately** (`is-selected`, mint ring dot) and **Enroll when active**
- `.lm-note`: `Matching employees are enrolled when the challenge starts. Nothing for them to accept.`
- `.mock-tag`

`aria-label`: *"Create-challenge wizard on the target audience step, with all filters set to All, 1,284 employees matching, and Enroll immediately selected. Figures shown are illustrative."*

> The only fabricated number on this surface is `1,284`, which matches the figure used across the shipped v1 pages. It is inside a `.mock-tag` surface, so it is disclosed.

Responsive: below 860px the `.dash` unrotates to full width and `.aud-card` sits below it at `width:100%; max-width:320px; margin:14px auto 0; transform:none`.

### 4.3 The score-breakdown panel (`.audit-board` variant), inside `.fairband`

Same white 380px shell as `.audit-board` (`box-shadow:0 26px 60px rgba(0,0,0,.32)`), different contents. This is the employee's own view, reached in-product by tapping your own leaderboard row, so it is labelled as such and shows a mood row (mood data is private to the employee and never shown to admins, so it may only appear in an employee-view mock).

- `.audit-head`: `<b>Mental health awareness</b>` and `<span class="audit-live"><i></i> My score breakdown · Week 3</span>`
- `.audit-cols` header row: `Task` · `Logged` · `Scored` · `Points`
- Four rows, grid `1fr 78px 62px 46px`:

| Task | Logged | Scored | Points |
|---|---|---|---|
| Mood log | 7 of 7 days | 100% | 70 |
| Mindfulness | 12 min of 10 | 100% | 60 |
| Content reading | 2 of 3 articles | 67% | 40 |
| Water log | 9 of 8 glasses | 100% | 50 |

Rows 2 and 4 carry a small `.cap-flag` chip reading **Capped** beside the `Scored` cell, styled like `.audit-flag` but mint rather than coral (`rgba(65,216,180,.14)` background, `#128f72` text, `1px solid rgba(65,216,180,.35)`). It marks over-completion that earned nothing extra, which is the point of the panel.

- `.audit-caption`: `Every task scores as a percentage of its daily target, capped at 100%. Going far over the target does not buy a bigger lead.`
- `.mock-tag`

`aria-label`: *"An employee's own score breakdown for week 3 of a Mental health awareness challenge, showing four tasks where over-completion is capped at 100 percent of the daily target. Figures shown are illustrative."*

### 4.4 Library cards and calendar cards

Not mocks. They are page content built from real catalogue data, so they carry **no** `.mock-tag` and no `role="img"`. Nothing on them is fabricated: names, taglines, categories, durations and run modes are all sourced (§7). The card `<p>` lines are editorial rewrites of the sourced descriptions, which is copy, not data.

### 4.5 Grid overrides the builder must add page-locally

```css
/* S10: four sibling routes, not the standard three. This page is the parent of all four. */
.challenges-related .related-grid { grid-template-columns: repeat(4, 1fr); }
@media (max-width: 1100px) { .challenges-related .related-grid { grid-template-columns: repeat(2, 1fr); } }
@media (max-width: 640px)  { .challenges-related .related-grid { grid-template-columns: 1fr; } }
```

Also carry, verbatim from `design-system.md` §3.B: the `.btn-primary` contrast fix, the `.eyebrow`/`.logos-label`/`.logo-word` contrast lifts, the `@media (forced-colors: active)` fallback for gradient-clipped text, the `.mock-tag` disclosure colour, `.skip-link`, the `.faq-item` block from addendum F3, and `.format-card` / `.format-glyph` / `.best-for` / `.format-grid` / `.fairband` / `.fair-list` / `.audit-board` / `.launch-mock` / `.result-card` / `.quote-band` / `.related-row`, none of which are in `enterprise.css`.

### 4.6 Band alternation check

`hero gradient` → `--canvas` (S2) → `#fff` (S3) → `--canvas` (S4) → `#fff` (S5) → `--canvas` (S6) → `#fff` (S7, dark `.fairband` inset) → `#f6f7f4` (S8) → `#fff` (S9) → `--canvas` (S10) → dark (S11). No two identical grounds adjacent. Two dark moments only (the `.fairband` inset and `.final`), separated by three bands. `#f6f7f4` is used once, on the proof band, as the system requires.

---

## 5. Claims table

Every factual assertion on the page. Anything without a source is not on the page.

### 5.1 Product claims

| # | Claim as it appears | Source | Status |
|---|---|---|---|
| 1 | 21 ready-to-run challenges, five focus areas | `SITE/data/wellness-challenges.ts:35-68` (read directly, 21 objects, 5 populated categories) | SHIPPED (marketing asset) |
| 2 | Every challenge name, tagline, category and run mode on a library card | same file, verbatim fields | SHIPPED (marketing asset) |
| 3 | Every printed duration and tracking method on a library card | `SITE/components/marketing/<Name>ChallengePage.astro` spec bars, tabulated in `challenges.md` §2.1 | SHIPPED (marketing asset) |
| 4 | The 12-month calendar: months, themes, challenge names, weekly focuses | `SITE/data/wellness-challenge-builder-calendar.js:5-186` | MARKETING-ASSET, labelled on the page as a planning calendar |
| 5 | "Creating a challenge takes 5 to 10 minutes from the admin dashboard" | `HELP/admin/challenges/admin-how-do-i-create-a-challenge.md:13` | SHIPPED |
| 6 | Five self-serve formats: Custom, Race, Journey, Streak, E-Marathon | `HELP/admin/challenges/admin-what-challenge-formats.md:15-88`; `VOS/product/02-challenges-gamification/challenges.md:57-74, :200` | SHIPPED |
| 7 | Four account-manager formats: Level, Marathon Event, Weight Burn, Training plans | same, plus `VOS/product/07-training-programs/training-plans.md:22, :80-82` | SHIPPED, ops-configured |
| 8 | "Nine formats in total: five you create from the dashboard, four your account manager configures" | `VOS/product/…/challenges.md:230` | SHIPPED |
| 9 | Custom Challenge draws on 27 task types | `HELP/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md:13`; `VOS/product/…/challenges.md:242` | SHIPPED |
| 10 | "the go-to format if you are unsure" | `HELP/admin/challenges/admin-what-challenge-formats.md:28` | SHIPPED |
| 11 | Race has no tasks, no teams, no certificate | `HELP/admin/challenges/admin-how-do-i-create-race-challenge.md:59` | SHIPPED |
| 12 | Journey ships with three built-in templates | `HELP/admin/challenges/admin-how-do-i-create-journey-challenge.md:32-38` | SHIPPED |
| 13 | Streak resets on a miss; ranked by days completed with total steps as tiebreaker | `HELP/admin/challenges/admin-how-do-i-create-streak-challenge.md:22-29, :69-74` | SHIPPED |
| 14 | E-Marathon converts steps to distance, default 1,000 steps to 1 km, adjustable | `HELP/admin/challenges/admin-how-do-i-create-e-marathon.md:22-29, :49-55` | SHIPPED |
| 15 | Race ranks by total steps; Journey by milestone points; Custom by total points; E-Marathon by total distance | `HELP` format setup articles, listed in `challenges.md` §5.3 | SHIPPED |
| 16 | Audience filters: country, city, department, gender, age range, language, health risk code, with a live preview of matching employees | `HELP/admin/challenges/admin-how-do-i-set-target-audience.md:17-47` | SHIPPED |
| 17 | Enroll Immediately / Enroll When Active, and the latter catches new hires and mid-challenge installers | `HELP/admin/challenges/admin-how-do-i-set-target-audience.md:49-68` | SHIPPED |
| 18 | Employees do not sign up; there is no browse-and-join flow | `VOS/product/…/challenges.md:42`; `HELP/employee/challenges/how-do-i-join-a-challenge.md:17-38` | SHIPPED |
| 19 | Late joiners score from the join date forward, no retroactive credit, no penalty | `HELP/admin/challenges/admin-how-do-i-add-remove-participants.md:61-69` | SHIPPED |
| 20 | Steps sync from Apple Health and Google Fit, or a connected Fitbit or Garmin | `VOS/product/01-core-tracking/activity-tracking.md:164-166`; `VOS/product/10-integrations/device-integrations.md:81-86` | SHIPPED. Apple Health and Google Fit always named together. |
| 21 | One primary device at a time, used exclusively so nothing is double counted | `VOS/product/10-integrations/device-integrations.md:81`; `HELP/employee/getting-started/can-i-connect-multiple-devices.md:12-49` | SHIPPED |
| 22 | 65+ activity types | `HELP/employee/health-tracking/what-activities-can-i-track.md:3, :13` (`challenges.md` addendum B2) | SHIPPED |
| 23 | Badges fire automatically on thresholds, within minutes | `HELP/admin/challenges/admin-how-do-badges-work.md:12, :67-78` | SHIPPED |
| 24 | Certificates generate at the end "if you enabled them" | `HELP/admin/challenges/admin-how-do-i-configure-certificates.md:17-20` | SHIPPED, always conditional |
| 25 | Vantage Points land in the wallet | `VOS/product/…/challenges.md:113-120`; `HELP/admin/challenges/admin-how-wellness-rewards-work.md:30-36` | SHIPPED. "Vantage Points" is canonical; "Fit points" is banned. |
| 26 | Non-step tasks cap at 100% of the daily target | `HELP/employee/challenges/how-does-the-leaderboard-work.md:39-47` | SHIPPED |
| 27 | Team score is the average of member scores | `HELP/admin/challenges/admin-how-do-i-manage-teams.md:19`; `HELP/employee/challenges/how-does-the-leaderboard-work.md:17-25` | SHIPPED. Never a sum. |
| 28 | Leaderboard opt-out: hidden from individual rankings, still participates, still earns, still counts toward the team average | `HELP/employee/challenges/can-i-opt-out-of-leaderboard.md:24-37` | SHIPPED |
| 29 | Wheelchair Mode adds Wheelchair as a workout type; route, distance and pace track; counts toward distance and active-minutes tasks | `HELP/employee/getting-started/what-is-wheelchair-mode.md:14-20, :45-64` | SHIPPED. No claim that pushes convert to steps. |
| 30 | HR sees participation and rankings; weight, assessment answers, lab reports, food logs and mood logs stay with the employee | `HELP/admin/settings/admin-data-privacy-security.md:43-56` | SHIPPED |
| 31 | Operates under HIPAA guidelines; SOC 2 Type II audited | `vfit-os/.claude/rules/data-accuracy.md`; `audit/site-refresh-2026-07/prior-audits.md` | APPROVED-CLAIM. Never "HIPAA compliant". No ISO or GDPR anywhere on the page. |
| 32 | Templates arrive with a format, tasks, targets, balanced scoring and suggested weekly themes; admin sets dates, audience, branding | `HELP/admin/challenges/admin-how-do-i-use-templates.md:17-54` | SHIPPED. **No template count published.** |
| 33 | Custom Journey map: account-manager design project, 2 to 3 week lead time, annual clients | `HELP/admin/challenges/admin-how-do-i-create-journey-challenge.md:48-58` | SHIPPED |
| 34 | No limit on concurrent challenges; each has its own leaderboard, point pool and completion criteria; one walk counts toward every matching challenge | `HELP/admin/challenges/admin-can-i-run-multiple-challenges-in-parallel.md:13-22`; `admin-what-challenge-formats.md:106` | SHIPPED |
| 35 | Four themed weeks is how a Custom Challenge is configured | `HELP/admin/challenges/admin-how-do-i-create-custom-challenge.md:59, :80-85` | SHIPPED |
| 36 | Training plans are started by the employee from a Vantage Fit library | `VOS/product/07-training-programs/training-plans.md:41-49, :104-113` | SHIPPED, ops-enabled |

### 5.2 Customer and scale claims

| # | Claim | Source | Status |
|---|---|---|---|
| 37 | "Trusted by 100+ organizations worldwide" | `data-accuracy.md:252-261` | APPROVED-CLAIM. The only aggregate scale figure permitted. |
| 38 | Logo row: Tata Motors, Wipro, Teva, Godrej, Texas Instruments, Heidrick & Struggles, Brazosport ISD | `data-accuracy.md:22` | All on the approved-names list |
| 39 | IBS Software: 88% engagement rate, 28 days, 500+ of 660 invited active, March to Fitness, Mar 1-28 2024 | `data-accuracy.md:72-85`; `content/en/casestudy/ibs-software-case-study.md` | APPROVED-CLAIM. 28 days, never 30. |
| 40 | Tata Motors: 59% engagement rate over six months, Step & Stride Challenge | `data-accuracy.md:34-48` | APPROVED-CLAIM. Never mixed with the 70% Step Up & Elevate program. |
| 41 | Brazosport ISD: 86% engagement rate, 132 active participants, Fit Wars, May 6-19 2024 | `data-accuracy.md:135-150` | APPROVED-CLAIM. "Engagement", per the register, even though the case-study body says participation. |
| 42 | POSOCO: 97% participation rate, 72+ participants, Dec 6-19 2021 | `data-accuracy.md:183-191` | APPROVED-CLAIM. Spelling POSOCO, never POSCO. |
| 43 | ISKL quote | `data-accuracy.md:193-240` Tier A | APPROVED-CLAIM. Company attribution only, no name, no title. |
| 44 | Niche Technology quote, Tara Shore | `data-accuracy.md:193-240` Tier A | APPROVED-CLAIM. Name exactly as registered. |

### 5.3 Claims considered and cut

| Cut | Why |
|---|---|
| "20+ task types", "7 challenge types", "47+ activity types" | Stale Draft-spec figures. Correct values used instead. |
| Any step-cap number, and "no ceiling on steps" | Three sources, three answers. The fairness section talks only about the 100% daily cap on non-step tasks. |
| Weight Burn's mechanic | Help docs and the code-verified spec describe two different things. Named only, with "Available on request". |
| A template count | No source enumerates them. |
| Wellness Score, Wellness Leagues | Account-manager gated, off in Lite Mode. Would need more caveat than claim. |
| Lite Mode format restrictions | Tenant-tier fact, not a format fact. The virtual marathon page made the same call. |
| Trees Challenge, manual/QR join, admin self-serve for Level/Marathon/Weight Burn | All Backlog. |
| "50+ countries", "190+ countries", any "X% to Y% engagement" range | Banned or not a customer footprint. |
| The Cloudinary certification raster and any ISO 27001 / ISO 27701 / GDPR mark | Banned. The page carries no trust plaque at all; the compliance line lives in `.fair-fine`. |
| Beroe 96%, JF Petroleum 81%, Allston 94%, Cotiviti 89%, Embrace 94% | Unregistered or contradicted metrics. |
| A completion rate for anything | No completion rate is approved anywhere. |
| Any Slack or Microsoft Teams mention | Zero spec coverage. |
| "Start free trial" | No trial exists. |
| An HRA cross-link in the rollout strip | The HRA is a Section ② page and a task type, not a challenge rollout step. Forcing it in would blur the two menu columns. |

### 5.4 Voice gate self-check

- **Em-dashes:** zero in the copy deck. Verified by reading every string above. The two verbatim customer quotes contain none either.
- **Banned words:** none of robust, seamless, comprehensive, user-friendly, holistic, empower, leverage, game-changer, best-in-class, all-in-one, intuitive, optimize, utilize, simply, just, revolutionize, cutting-edge appear. "Holistic" is avoided even though the data file declares an unused `holistic` category key, which is one more reason that category is not rendered.
- **Surveillance framing:** no "monitor", no "health monitoring", no "identify bottlenecks".
- **Exclamation marks:** exactly one, inside the verbatim ISKL quote.
- **Capitalization:** sentence case everywhere except product nouns (Vantage Fit, Vantage Points, Custom Challenge, Race Challenge, Journey Challenge, Streak Challenge, E-Marathon, Level Challenge, Marathon Event, Weight Burn, Apple Health, Google Fit, Fitbit, Garmin, Enroll When Active, Wheelchair Mode) and the verbatim Title Case taglines and calendar strings.
- **CTAs:** verb-led. "Book a demo", "Browse the library", "See pricing", "See step challenges", "Browse habit challenges", "Explore security and compliance".
- **Stats:** every one names the customer, the program and the window, with no causal clause appended.

---

## 6. Meta title and meta description

**Meta title** (42 characters):
```
Employee Wellness Challenges | Vantage Fit
```

Alternate, if a human decides the new page must visibly differ from the live `/wellness-challenges/` library in SERP (55 characters):
```
Employee Wellness Challenges for HR Teams | Vantage Fit
```

**Meta description** (155 characters, within the 140-155 rule):
```
Browse ready-to-run employee wellness challenges for steps, mind, food, sleep and teams. Employees are enrolled automatically, not by sign-up. Book a demo.
```

Notes for the builder:
- No em-dash in either, despite the `seo-conventions.md` template using one.
- Primary keyword "employee wellness challenges" (590/mo per the signed-off menu preview) leads the title and opens the description.
- Do not ship JSON-LD on this mock unless the copy is frozen. If it does ship, the FAQPage block must reproduce FAQ items 1 to 5 word for word, and it must carry no stat that is not in §5.2. `schema-data.js` is known to drift from visible copy on every page audited (`prior-audits.md` P14).

---

## 7. Menu fit

| Field | Value |
|---|---|
| Column | ① Wellness challenges, "what you want to run" |
| Row | 1 of 5, first item |
| Menu label (verbatim) | `Wellness challenges` |
| Badge | `Library` in the nav, `Library · flagship` on the sign-off gallery card |
| Description line (verbatim) | `The full library of ready-to-run challenges` |
| URL | `/solutions/wellness-challenges/` |
| Footer | Solutions column, row 2, under `Wellness platform` |

**Its job in the IA.** Column ① rows 2 to 5 are conceptually children of row 1. This page is the parent, and it is the only page in the set whose primary conversion event can legitimately be an internal click rather than a demo request. It routes to all four siblings twice: once in the S2 outcome chooser (where the buyer arrives with an intent) and once in the S10 related row (where they arrive having browsed). It must never become a sixth format page.

**Data in → data out → action** is Section ②'s chain and does not apply here. This page touches that chain at exactly two points, both one-way and both deliberate: S6 step 4 links forward to **Wellness rewards program** (action), and S8 links forward to **Workforce health insights** (data out) as "the reporting behind these numbers". It does not link to the **Health Risk Assessment**, because the HRA is a screening instrument, not a challenge, and a link from a browse-and-pick page would blur the two columns.

**On the mega-menu markup:** use the signed-off two-column Solutions panel verbatim from `ia-claims-proof.md` §1.6, and pick one treatment for the column headers (em-dash, as in the signed-off source, or the colon used in `chrome.html`) and hold it across all six pages. `chrome.html` uses the colon; keep the colon.

---

## 8. Cross-links

| From | Anchor text | To | Why |
|---|---|---|---|
| S2 card 1 | See step challenges → | `/solutions/step-challenges/` | Buyer intent "get everyone moving" |
| S2 card 2 | See multi-activity challenges → | `/solutions/multi-activity-challenges/` | Buyer intent "cover more than steps" |
| S2 card 3 | See remote and hybrid challenges → | `/solutions/remote-team-wellness/` | Buyer intent "distributed workforce" |
| S2 card 4 | Browse habit challenges → | `#library` | In-page route into the filtered grid |
| S2 card 5 | See virtual marathon → | `/solutions/virtual-marathon/` | Buyer intent "one company-wide event" |
| S3 | See how a multi-activity program is built → | `/solutions/multi-activity-challenges/` | That page owns the 27-task explorer |
| S5 | See the step formats in depth → | `/solutions/step-challenges/` | That page owns the format tab explorer and the integrity band |
| S6 | See how points and gift cards work → | `/solutions/wellness-rewards-program/` | Section ② "action" |
| S7 | Explore security and compliance → | `https://www.vantagefit.io/features/security-and-compliance/` | Verified slug in `marketing-urls.js` FEATURE_SLUGS |
| S8, each `.segment` | Customer and program name | the four case-study URLs in §3 S8 | Required: hyperlink stats to their source case study |
| S8 | See the reporting behind these numbers → | `/solutions/workforce-health-insights/` | Section ② "data out" |
| S10 | Four sibling cards | the four Section ① URLs | The routing spine |
| Footer | All nine Solutions rows | as shipped in `chrome.html` | |

**Inbound links this page should receive:** the Solutions hub (as the Section ① lead card), the Wellness platform page (from its challenges section), and all four sibling challenge pages (each should link back up to "the full library"). Note that `seo-conventions.md` recommends 2 to 3 internal links per page; this page carries far more by design, because routing is its function. Flag it for the SEO reviewer rather than trimming the routes.

---

## 9. Assumptions and gaps

### 9.1 Open IA questions a human must resolve (do not block the build)

1. **Slug collision.** The shipped multi-activity consolidated page already claims `/solutions/wellness-challenge` (singular) with the title "Employee Wellness Challenge Platform & Ideas | Vantage Fit", described in its own decision doc as "likely a pillar-level page". This page targets `/solutions/wellness-challenges/` (plural). Two near-identical slugs both aiming at "employee/corporate wellness challenge" will cannibalise. Either this page takes the pillar slug and multi-activity moves to `/solutions/multi-activity-challenges/`, or this page takes a clearly distinct slug. Escalated, not decided here.
2. **Relationship to the live library.** `https://www.vantagefit.io/wellness-challenges/` already exists, renders the same 21 challenges from the same data file, and has 21 child detail pages. This page must either replace it, or sit above it as a Solutions-level entry that links down into the 21 detail pages. This brief assumes **it sits above it**, which is why the library cards here are summaries rather than links to nowhere. If the decision goes the other way, each `.lib-card` becomes an `<a>` to its `href` from the data file and the grid gains hover lift.
3. **URL prefix.** `vfit-os/.claude/rules/seo-conventions.md:69,83` says solution pages are root-level with no `/solutions/` prefix and instructs "do not propose URL changes". The signed-off menu and the shipping brief both use the prefix. This page follows the menu. Unresolved above this brief.

### 9.2 Data-file defects to fix upstream

4. **Bed time crafts** is `format: "team"` in `wellness-challenges.ts:53` but `Format: Individual` on its detail page. This page prints **Solo**. Fix the data file.
5. **Digital detox challenge** is `category: "mental"` in the data file but rendered under Sleep & recovery on the live page. This page prints **Mental wellness**. Pick one upstream.
6. **Charity walk** and **Team step challenge** are typed `Race` in the data file, which contradicts the product's Race definition. This page prints no format chip, so nothing is wrong on the page, but the data file should be corrected before anything else consumes that field.
7. The `holistic` category key exists in the type union with zero members. Either populate it or remove it.

### 9.3 Assumptions stated

8. **"21" is printed as a literal in the H1, the S3 H2, the filter pill and the status line.** If a challenge is added or removed from `wellness-challenges.ts`, four strings drift. On the real page this should be derived from `challenges.length`, exactly as the live library derives its `displayTotal`. In a static mock it is hard-coded, and the builder should leave an HTML comment saying so.
9. **The 2026 calendar is presented as a planning artifact**, not a product feature. Its badge names ("Dry January Champion", "Pink Warrior" and the rest) are stripped, because product badges are a fixed set of 7 categories.
10. **The library card `<p>` lines are editorial rewrites** of the sourced `description` field, shortened to one line and stripped of em-dashes. The names, taglines, categories, durations, run modes and tracking methods are verbatim or directly derived. Nothing was invented.
11. **`1,284 employees match`** in the hero audience card is illustrative, disclosed by `.mock-tag` and by the `aria-label`. It is the same figure the shipped v1 pages use, kept for consistency.
12. **The score-breakdown mock shows a mood row.** That is correct for an employee-view surface and would be wrong on an admin surface, because mood data is never shown to admins or on leaderboards. If the builder relabels the mock as an admin view, the mood row must be removed.
13. **Dropping the `.trust-screen` band is a deliberate architectural choice for this page only** (§2.4). If a reviewer wants it back, it goes between S8 and S9, the fairness `.fair-fine` compliance sentence moves into it, and the band alternation still holds (`#f6f7f4` → dark → `#fff`).
14. **The related grid runs four columns, not the standard three** (§4.5). Justified because routing to all four Section ① siblings is this page's stated job in the IA.

### 9.4 Gaps I could not close

15. **No sourced participation figure exists for the library as a whole.** Every approved engagement or participation number belongs to a single named program. The page therefore shows four labelled program results and never aggregates them. There is no "average engagement across the library", and one must not be constructed.
16. **No source enumerates the in-product template catalogue.** The page says templates exist and describes what they carry, and never says how many or names one.
17. **No source gives a completion rate for any Vantage Fit program.** The word "completion" appears on the page only in "days completed" (a Streak ranking metric) and "Challenge Completion" (a badge category), never as a rate.
