# Vantage Fit — Virtual Marathon Solutions Page Brief (v1)

Model workspace: `claude-fable` · Deliverable pair: this brief + `vantage-fit-virtual-marathon-v1.html` (1,786 lines)
Baseline: `../styles/enterprise.css` + `../styled-homepage/` · Sibling program pages: `vantage-fit-steps-challenge-v1.html`, `vantage-fit-team-challenge-v1.html` · Hub: `../solutions-page/vantage-fit-solutions-v1.html`
Live page rebuilt: `https://www.vantagefit.io/virtual-marathon/` · URL unchanged
Format lock: the page is built on **E-Marathon**, the self-serve format. `Marathon Event`, the GPS-tracked race, is named once and correctly labelled as account-manager arranged.

This brief documents the file as shipped, including the eleven places where the build diverged from the approved blueprint after review and repair. Every divergence is marked **[shipped, not blueprint]**.

---

## 1. What this page is

This is the page an HR leader opens when they have a date on the calendar that leadership already cares about (wellness week, World Heart Day, a program relaunch, an office anniversary) and a step program that has settled into the same fit third of the company. The program is a **virtual marathon**, and in the product it is an **E-Marathon**: employees' ordinary steps are converted to distance at a company-wide ratio, default 1,000 steps = 1 km, and the leaderboard ranks by total distance covered. No GPS. No route. No registration. The buyer is a US enterprise HR, CHRO, benefits or wellbeing leader; the program manager who will actually build and promote it is reading over their shoulder, and an IT or privacy reviewer waits at the end.

The page does one job: **make the buyer believe the two thirds of their workforce who ignore step challenges can finish this event by walking, and that finishing costs those people nothing to sign up for and nothing to keep up with.** Every section supports one of three clauses in that sentence. Distance from steps rather than GPS (S2, S9). Nobody signs up, because there is no sign-up flow in the product (S1, S3, S4, S9). Nothing breaks, because the format is cumulative with no daily target and no streak (S2, S4). Primary CTA is **Book a demo**, four on-page instances with an identical label. The secondary in the hero is the gated **virtual marathon guide**, which already exists in the repo and which nothing on the site currently links to; the closer's secondary is **See pricing**. Eleven blocks, roughly 1,150 words of body copy.

The live page makes the opposite bet. It is written to "runners of all levels", headlines three fixed race tiers that do not exist in the self-serve format, and awards badges that can only be earned by GPS-tracked runs. This rebuild inverts the page's own name: the marathon is the hook precisely because you finish it by walking.

---

## 2. Research takeaways

Audited: the live page source (`content/en/pages/use-cases/virtual-marathon.yaml`), the help-doc corpus (`admin/challenges/`, `admin/reports/`, `admin/communication/`, `employee/challenges/`, `employee/getting-started/`), the code-verified product specs (`vfit-os/specs/product/**`), the Draft spec set (`vfit-os/specs/0X-**`), the admin dashboard designs (`vc-dashboard-design/`), and the approved-claims rules (`vfit-os/.claude/rules/data-accuracy.md`).

Path shorthand: `HELP` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/` · `VOS` = `/Users/anjanpathak/work/vc-os/vfit-os/` · `DASH` = `/Users/anjanpathak/work/gitcode/vc-dashboard-design/`

Precedence applied throughout: dedicated help article beats generic help article beats code-verified spec beats Draft spec beats dashboard repo.

### 2.1 The sentence the live page never says, and it is the whole product

> "Distance is calculated from step count, not GPS. Employees do not need to use GPS workouts or run specific routes. Their regular daily steps are automatically counted."
> `HELP/admin/challenges/admin-how-do-i-create-e-marathon.md:29`, repeated employee-side at `HELP/employee/challenges/what-is-an-e-marathon.md:25`

Every competitor virtual-race page in the category is built on GPS run tracking, which structurally excludes the warehouse worker, the nurse on a ward and the person who will not run. This one sentence converts a running event into a walking event that anyone finishes. It is public, checkable in one click, and it is on the page as a bordered pull quote captioned "From the Vantage Fit admin help center". The caption is the point: a checkable public sentence beats an adjective, and no comparable vendor publishes one.

### 2.2 The format is two fields, and the doc says so out loud

The E-Marathon wizard has exactly one format-unique step: **steps-to-distance ratio** (default 1,000 steps = 1 km, adjustable) and **distance unit** (km or miles). `admin-how-do-i-create-e-marathon.md:49-54`. The article closes Step 5 with the verbatim line "That is all the configuration needed. E-Marathons are intentionally simple." (`:79`). The production dashboard step graph agrees on shape: route `@fit/ui/pages/create-challenge/e-marathon-challenge`, steps `typeChooser → setup → duration → privacy → config → review` (`DASH/CRUD_FLOWS_AND_COMPONENTS.md:423-515`).

Two live conflicts were resolved against the help doc, not the dashboard repo: the dashboard labels the field "Target distance + unit" and prints "1 mile = 1,609 steps" (`DASH/crud-schema-spike/vc-data.js:1274-1275`), and it orders privacy before config. The page uses the help doc's field names and the help doc's order, and never prints 1,609.

### 2.3 Capabilities the live page under-sells or misses entirely

1. **Nobody signs up.** Two enrollment paths, both admin-driven, with the Quick Reference answer "Action Required? None, you're already in" (`HELP/employee/challenges/how-do-i-join-a-challenge.md:17-38`). Code-verified: "There is no browse-and-join flow" (`VOS/specs/product/02-challenges-gamification/challenges.md:42`). Two auto-enrollment modes exist, including **Enroll when active**, which catches people who install the app mid-event (`admin-how-do-i-set-target-audience.md:49-68`). On an *event* page this is worth more than on any other page in the group, because it removes the registration-drive risk that decides whether a one-off is worth running at all.
2. **Nothing can break.** Cumulative, no daily target, no streak: "missing a day does not reset anything. Your cumulative distance keeps growing whenever you are active" (`what-is-an-e-marathon.md:60`; `admin-how-do-i-create-e-marathon.md:26-27`). This is the exact inverse of the Streak format, where a missed day resets the streak. It is the structural retention argument and the live page never makes it.
3. **The distance unit is a documented motivation mechanic, not a design flourish.** "You want a format where progress feels tangible: seeing '42 km' is more motivating than '42,000 steps'" (`admin-how-do-i-create-e-marathon.md:17`), and the format is explicitly positioned for "engaging people who find step counts abstract".
4. **Time zones are described mechanically, not asserted.** Localized start at local midnight, localized end at local midnight, so "a 30-day step challenge that starts on May 1 is a true 30 calendar days for every participant"; plus rewards configured in USD, displayed in each employee's local currency, from a country-relevant gift-card catalog (`admin-can-i-run-challenges-across-time-zones.md:17-29`). The same doc supplies two caveats: push notifications land at each recipient's corresponding local time so sends should be staggered, and report date filters run on the **admin's** time zone (`:35-37`). Both caveats are printed on the page in visible type.
5. **A 3-day settle buffer with a stated reason.** Rankings, ranking bonuses and certificates wait three days after the end date because "wearable devices (especially Fitbit and Garmin) can take time to sync final step counts" (`admin-how-do-i-create-race-challenge.md:27-29`; `HELP/employee/challenges/how-do-i-get-my-certificate.md:17`). The same corpus also advises celebrating same-day (`admin-when-to-use-a-one-day-virtual-marathon.md:67`). The page publishes the reconciliation: share the company total the same day, settle winners after the buffer.
6. **The collective framing is the doc's own idea.** "Announce the total company distance", "Race to the Moon (384,400 km as a company)", "We just passed 5,000 km as a company!" (`admin-how-do-i-create-e-marathon.md:87-95`). It is the retention device for people who will never see the top of the board.
7. **The docs publish when NOT to run one.** Not for habit building, not for multi-modality programs, not when the workforce is on rest days, and "a single one-day event is a campaign, not a program" (`admin-when-to-use-a-one-day-virtual-marathon.md:41-46`). The page borrows the last line for its closer H2.
8. **Badges land at the bottom of the board.** Daily Steps badges, ten levels from 3,000 to 40,000 steps, **re-awarded every time the threshold is hit**, with a running achievement count, awarded automatically within minutes (`admin-how-do-badges-work.md:16-33,67-78`). Someone in last place on distance still collects something daily.

### 2.4 Live-page claims that could not survive

| Live claim (`content/en/pages/use-cases/virtual-marathon.yaml`) | Why it was dropped |
|---|---|
| **"Race levels": Beginner 5 KM / Intermediate 10 KM / Seasoned Runners 21 KM**, the largest block on the page | There is no tier field and no target-distance field in the E-Marathon wizard (`admin-how-do-i-create-e-marathon.md:49-79`). Tiered distance targets belong to the ops-only **Marathon Event** lineage (`VOS/specs/product/02-challenges-gamification/challenges.md:72`) and to a Draft spec whose example tiers are 1000/2000/5000 m, not 5/10/21 km (`VOS/specs/02-challenges-gamification/challenge-marathon.md:23-47`). Presenting them as self-serve product levels sells an account-manager engagement as a dashboard feature. |
| "Each participant earns points based on the distance they cover" | Contradicts every source. E-Marathon has "one implicit task" and no per-distance point scheme (`admin-how-do-i-create-e-marathon.md:26`). The Draft marathon spec scales reward by the tier achieved, halving per lower target, not per km. |
| "Participants earn badges for completing milestones (e.g., 5 km, 10 km, 21 km)" | The distance badge ladder is the **Runs** category at 1 / 3 / 5 / 10 / 42.2 km, and it is "Earned by completing **GPS-tracked runs**" (`admin-how-do-badges-work.md:35-45`). There is no 21 km badge, and an E-Marathon uses no GPS, so these badges cannot fire from marathon distance. |
| "Our platform automatically adjusts for time zone differences" | Directionally true, unverifiable as phrased. Replaced with the four documented behaviours and the two caveats. |
| Written entirely to the runner: "inspire runners of all levels", "Seasoned Runners" | Inverts the product's own differentiator. Sources say "You do not need to run an actual marathon, just walk or run as you normally would" (`what-is-an-e-marathon.md:12`). |
| "individual and team standings" on the live leaderboard | **E-Marathon teams are NOT FOUND IN SOURCES.** The format's setup article has no team step. The individual half is kept; the team half is dropped and handed to the Team Challenge page. |
| "HR managers can customize rewards through gift cards, wellness perks, or company specific incentives" | Point and monetary rewards on challenges are account-manager enabled, "currently only 1 company" (`challenges.md:173`). "Wellness perks" and "company specific incentives" are NOT FOUND IN SOURCES as product features. |
| "designed for simplicity—minimal setup with maximum impact" / "promote wellness—all at once" | Two body em-dashes, banned. "Maximum impact" is unsourced. |
| The shared **59 / 88 / 86** proof block carried onto this page | All three are **engagement rate** figures from physical-activity challenges at other customers, none attached to a marathon, and all three are mislabelled as participation on live pages today. |

### 2.5 Limits found in research that the page states out loud rather than hides

Printed on the page, deliberately: **no distance leaderboard for admins** (the admin views are Score and Steps only, `HELP/admin/reports/admin-how-do-i-view-leaderboard.md:24-51`), which is why the reconciliation sentence exists; **exports are a manual click, with no scheduled or emailed reports**; **challenge reminder emails are off by default and account-manager gated** (`admin-what-emails-does-vfit-send.md:36`); **report date filters run on the admin's time zone**; **push notifications land at each recipient's local time**; **results are provisional for 3 days**; **certificates only "if your admin enabled them"**; **a full marathon's worth of steps in one day is roughly 50,000 steps**, which the doc itself calls "prohibitive for most" (`admin-when-to-use-a-one-day-virtual-marathon.md:64`); and **Marathon Event needs a phone call**. Nine printed limits on an 1,150-word page. Naming a limit is what buys belief in the rest.

Not printed, and not claimed either way: **Lite Mode clients cannot run an E-Marathon** ("Only step challenges available, Race format with step_count task", `challenges.md:129-135`). It is a real constraint but it is a tenant-tier fact, not a format fact, and stating it on a marketing page would confuse more buyers than it protects.

### 2.6 Seven corrections applied against the foundation's own starter kit

The foundation index §3.4 supplied the starter kit for this page. Seven of its items were wrong or unsafe against primary sources and were corrected before the build. They are recorded here because a future editor working from §3.4 alone would reintroduce all seven.

| # | §3.4 said | Source actually says |
|---|---|---|
| K1 | Distance badges at 1 / 5 / 10 / 21.09 / 42.19 km | The Runs ladder is **1 / 3 / 5 / 10 / 42.2 km** and fires from **GPS-tracked runs**, so it cannot fire from an E-Marathon. `admin-how-do-badges-work.md:35-45` |
| K2 | Certificates auto-generate at the end, presented as an E-Marathon feature | The format's own setup article has no certificate step, and neither does the production wizard step graph. Usable only as "if your admin enabled certificates". `admin-how-do-i-create-e-marathon.md:77-79`; `DASH/CRUD_FLOWS_AND_COMPONENTS.md:511` |
| K3 | Implies a distance leaderboard HR can read | The admin leaderboard has **Score, Steps and Team** views. There is no distance view and no distance column in the export. `admin-how-do-i-view-leaderboard.md:24-51` |
| K4 | "Localized daily reset" as a marathon benefit | The daily reset governs daily-target tasks. An E-Marathon has no daily target, so the load-bearing localization is **start and end**. The page says start and end only. |
| K5 | Silent on Lite Mode | Lite Mode clients cannot run an E-Marathon. `challenges.md:129-135` |
| K6 | Silent on teams | **Teams on E-Marathon: NOT FOUND IN SOURCES.** Not claimed anywhere. |
| K7 | Silent on stride length | One summary article says distance uses "step count and stride length"; the two dedicated articles say a fixed configurable ratio. No per-person calibration exists, so the page never says stride. |

---

## 3. Why this structure

Eleven blocks. The spine is: **name the hook, make it arithmetic, remove the operational fear, remove the employee fear, answer the global objection, hand HR the artifacts, bring precedent, clear privacy, answer rollout questions, loop out, ask.**

| # | Block (`id`) | Surface | The belief it exists to create |
|---|---|---|---|
| S1 | Hero (`hero`) | Light gradient | "The name of this thing is not a filter. My warehouse and nursing staff are at the top of that board, and nobody had to sign up." |
| S2 | How distance is counted (`mechanic`) | `--canvas` | "This is arithmetic I can check, not a claim. And it is genuinely not my step challenge with a sticker on it." |
| S3 | The run book (`runbook`) | `#fff` | "One person can run this. The platform column is longer than mine." |
| S4 | Follow-through (`employees`) | `--canvas` | "The people I am worried about will still be in it on day 12, because there is nothing for them to keep up with." |
| S5 | Time zones (`timezones`) | `#fff`, dark card | "This vendor described the mechanism and then told me where it goes wrong. I believe the first part more because of the second." |
| S6 | Reporting (`report`) | `--canvas` | "I know exactly what file I walk out with, and I know why the export does not say what the app says." |
| S7 | Customer results (`proof`) | `#f6f7f4` | "Named enterprises have run this shape of event and reported participation, and nobody upgraded a walkathon into a marathon to impress me." |
| S8 | Security and privacy (`security`) | Dark full-bleed | "A public leaderboard is not a health-data disclosure, and being ranked is a separate decision from taking part." |
| S9 | FAQ (`faq`) | `#fff` | "The five questions I would have asked on the call are already answered." |
| S10 | Related (`related`) | `--canvas` | "This is a system, and the one thing this format cannot do has a page of its own." |
| S11 | Closer (`demo`) | Dark full-bleed | "One event is a campaign. I should decide what it starts, and I should book the call to decide it." |

### 3.1 The three placement decisions that carry the page

**S2 is the mechanic, and it sits second.** The buyer's first unspoken objection is not "will people join", it is "this is the step challenge I already run, renamed". The conversion strip (10,000 steps → 1,000 steps = 1 km → 10 km added to the total), the three chips (Cumulative, No daily target, No streak to break) and the two-field wizard mock answer that before it can be asked. The section also carries the checkable public pull quote, which is the single highest-leverage sentence available anywhere in this corpus.

**S3 is a five-stage `You do` / `Vantage Fit does` rail, and it is the page's original asset.** The native objection on an *event* page is operational, not conceptual: is a one-off worth the setup, and what happens the day after. A section that answers it in prose would be a paragraph nobody reads. Instead the answer is a shape. Five stages, two columns, the platform column tinted and the human column plain, so the eye reads the asymmetry before the words. Launch day reads "Nothing. There is no registration to chase." beside a filled tile listing three automatic actions.

**S5 is the objection band, and it publishes its own caveats at readable size.** The four mechanics would be a stronger-sounding section without the two caveats. It is a weaker-sounding, stronger-converting section with them, because the reader has been oversold on "global" before and can verify both caveats in a trial. The `.fair-fine` block is styled at 0.78rem on the dark card, which is deliberate: it is a conversion asset, not legal filler.

### 3.2 Departures from the Steps consolidated flow

| Steps page beat | What this page does instead, and why |
|---|---|
| S2 five-format explorer, the Steps page's signature asset | Cut to a **two-card format clarifier** inside S2: E-Marathon (self-serve) and Marathon Event (arranged with your account manager). Here it is a correction, not a menu. Reproducing five formats would repeat the sibling page, and the only distinction this page owes the buyer is which marathon needs a phone call. The 5K/10K/half/full keywords survive, on the correct card. |
| S4 standalone anti-cheat / data-integrity dark band | **Cut to three chips inside S6.** This format has one auto-tracked input and no manual logging, so the "self-reported wellness data is junk" objection is structurally weak here. The rulings also forbid the numbers that would make a band interesting (no step-cap number, no "no ceiling" claim). Three chips inside the reporting section, where integrity is a credibility question about the export, is the honest size. |
| The dark band itself | **Repointed from data integrity to time zones.** One dark band per page; this page's hardest objection is global fairness, not cheating. |
| S5 HR control room with `.tour-tabs` | **No tabs anywhere on this page.** S3 already owns the launch beat, so S6 is a short static `.tour-checks` list plus the report mock. Two admin components saying the same thing is bloat this page cannot afford. |
| S3 six-row employee experience | Kept as a pattern, re-aimed and cut to **five rows**. Rows now argue "nothing to sign up for, nothing to keep up with" rather than general delight. Rewards wallet, wheelchair mode and team scoring are all off the row set. |
| Employee-app CDN screenshot as the S3 media | **Replaced with a drawn `.notice-stack`** of three real system artifacts: the enrollment email, a badge toast, the weekly progress email. The CDN screenshot's own alt text names a team leaderboard, and this format has no teams. |
| Four result cards plus a video quote | **Three cards, two text-only quotes.** The only approved video asset is Rachel Arthur of Brazosport ISD, who is not approved for a marathon claim. |
| No FAQ (dropped at review on the Steps page) | **FAQ restored**, five questions, with FAQPage JSON-LD. The live page has neither, and each question maps to an objection the body already answered. |
| Hero `.dash` + `.phone` composition | Phone kept; the admin dash replaced by a **floating leaderboard card**, because the rank column is the argument. The two mocks are set not to overlap at any width for the same reason. |

### 3.3 Beats deliberately cut

- **A "why last year's marathon failed" diagnosis grid.** It presumes the buyer arrived disappointed rather than curious, and it pushes the product 250 pixels down the page. Its best line survives as the asymmetry in S3.
- **A standalone "nothing can break" section.** The content is right and fully sourced, but a whole section written in negatives does not read as a product. It lives as rows 3, 4 and 5 of S4.
- **A five-card formats explorer.** Belongs to the Steps page.
- **A rollout timeline with a duration on every stage.** The only sourced duration is "Creating a challenge takes 5-10 minutes" and it covers the wizard. S3 prints "about 10 minutes" on stage 1 as a ceiling and gives the other stages calendar labels, not durations.
- **The help doc's own planning ranges** (participation 25-60% of active users, completion 30-50% of registered participants, 1-2 week app-open uplift). They are planning guidance, not customer results, the doc caveats them itself, and the completion row is defined against 5K/10K/half/full tiers this format does not support. A 25% floor on a page whose north star is participation hands the buyer a weapon. They are parked behind the gated guide, which is the hero's secondary CTA.
- **Any competitor name, comparison table, or "unlike X" construction.**
- **Any commercial framing** (tier language, "included in your plan", "at no additional cost"). No sourced statement exists.

### 3.4 Design signature

Six drawn product surfaces make the same argument at six altitudes, and each is legible with the copy stripped out.

1. **Hero phone**: the E-Marathon detail screen in the order the app actually shows it. Challenge name, Ongoing pill, progress bar, total distance as the largest number, rank, days remaining, and a footer row converting today's steps into today's distance.
2. **Hero leaderboard card**: the argument. Rank 1 is Facilities, rank 2 is Nursing, rank 3 is Finance, and the viewer sits at #42 in Customer support. **The casting is load-bearing.** No competitor's race page puts a facilities worker at the top of a marathon board.
3. **S2 wizard mock**: the config step with exactly two rows, because that is the truth of the format.
4. **S4 notice stack**: three system artifacts stacked and offset, none of which the employee had to request.
5. **S5 final standings**: five participants in five cities, each closing at 11:59 PM on the same date, local.
6. **S6 report mock**: the admin leaderboard with exactly two tabs, Score and Steps, and one row drilled open.

**What is absent from every frame, deliberately:** no map, no route line, no GPS trace, no bib, no medal, no race tier, no finish-line ribbon, no runner silhouette, no podium, no confetti. Six visible `Illustrative data` tags across seven `role="img"` mocks; the seventh is the conversion strip, which carries arithmetic rather than fabricated figures. Every mock repeats its illustrative status inside its `aria-label`.

### 3.5 Divergences from the approved blueprint, applied during review and repair

Eleven, all of them corrections rather than preferences.

1. **Wizard mock reshaped.** Blueprint drew `Step 5 of 6 · Config` with the verbatim quote "That is all the configuration needed." The help doc's own numbering puts distance conversion at **Step 3 of 5**, and the quote belongs to Step 5. Shipped: `Step 3 of 5 · Distance conversion`, five pips with three filled, and the caption rewritten to "Two settings, then audience, then review and publish. E-Marathons are intentionally simple." **[shipped, not blueprint]**
2. **Every illustrative figure rebuilt from one pace.** Blueprint numbers were internally inconsistent with the 1,000:1 ratio. Shipped: hero at day 24 of 30 (231.4 / 224.6 / 218.9 km leaders at roughly 9,600 steps/day, viewer at 146.4 km), final standings at day 30 (288.6 down to 258.2 km, every figure above its day-24 counterpart), report totals exactly the final standings multiplied by 1,000. The help doc's own table gives 10,000 steps/day over 30 days = 300 km, so the leader sits just under it. **[shipped, not blueprint]**
3. **Per-week score breakdown removed from the report mock.** `admin-how-do-i-view-leaderboard.md:79` scopes it to multi-week Custom challenges, and an E-Marathon has no weekly themes. Shipped: a drill row carrying `Task Walk or run · Points 907 · Total steps 271,500 · Last active Sep 30`. **[shipped, not blueprint]**
4. **Wipro card rebuilt.** The blueprint made `30+` countries the headline stat under the named Step-a-thon. The case study attributes 30+ countries to the cumulative headline across all three 2025 challenges, not to that challenge. Shipped: stat is `550`, and the countries figure is carried in a separate clause that says "Across all three 2025 challenges". **[shipped, not blueprint]**
5. **S4 headline de-absolutised.** "Nobody signs up, and nothing can break" became "Nothing to sign up for, nothing to keep up with", and row 1 was retitled "No registration drive." so the headline does not repeat itself. **[shipped, not blueprint]**
6. **Surface alternation corrected.** S4 and S5 both sat on `--canvas` in the blueprint. Shipped: `.timezone-screen` is `#fff` and `.report-screen` is `--canvas`, giving canvas / #fff / canvas / #fff / canvas / #f6f7f4. **[shipped, not blueprint]**
7. **Hero progress bar relabelled.** An undecodable 68% distance bar became `Days elapsed · Day 24 of 30` at 80%, with 146.4 km carrying the total. An E-Marathon has no target distance, so a distance-completion bar would have implied one. **[shipped, not blueprint]**
8. **Trust card 4 rewritten** so it no longer repeats the S4 opt-out row verbatim: "Ranking visibility is an opt-out, so taking part in the event and appearing on the board are two separate decisions." **[shipped, not blueprint]**
9. **Single-day framing removed from S5 and the closer.** S5 eyebrow became "Every local clock"; the closer note became "One event everyone finishes. One number leadership recognizes." The page sells a 2-to-4-week run book, so "one day everyone remembers" contradicted its own S3. **[shipped, not blueprint]**
10. **Reconciliation sentence narrowed to the steps column.** Shipped: "The steps column ranks in exactly the same order, because distance is steps divided by one company-wide ratio." Score is not a monotone transform of distance, so the original phrasing would have claimed more than the sources support. **[shipped, not blueprint]**
11. **Closer H2 changed** from "Decide what it kicks off" to "Decide what it starts", to avoid a US sports metaphor in a page that will be translated into three languages. The doc's own word "kickoff" survives in the first final-check. **[shipped, not blueprint]**

Accessibility and layout repairs also shipped and are recorded in §9.3: a skip link, a scrollable mobile nav panel, CTA contrast lifts, `.format-card h4` margin reset, and a hero composition that stays inside the shell until the viewport has gutter to spare.

---

## 4. The objection this program raises

This page raises **two** objections, and they pull in opposite directions. The first is created by the program's own name. The second is created by its shape.

### 4.1 The name objection: "Our people are not runners. 'Marathon' reads as elitist, and most of the workforce opts out before it starts."

This is the objection the live page actively creates by writing to "Seasoned Runners". It is answered with product truth, not reassurance, and the answer is the spine of the whole rebuild.

| Sub-objection | Product answer on the page | Source |
|---|---|---|
| "They will have to run" | Distance is calculated from step count, not GPS. Employees do not need to use GPS workouts or run specific routes. Printed verbatim as a pull quote in S2, restated in the H1, the lead, hero note 1 and FAQ 1. | `admin-how-do-i-create-e-marathon.md:29` |
| "They will need a watch" | Steps sync in the background from Apple Health on iOS and Google Fit on Android. No wearable required. S4 row 2, FAQ 2. | `HELP/employee/getting-started/do-i-need-a-wearable.md`; `how-does-step-syncing-work.md` |
| "There will be a target they cannot hit" | One implicit task, no daily target, no target thresholds. S2 chips, S4 row 3. | `admin-how-do-i-create-e-marathon.md:26-27` |
| "They will drop out on day three" | Cumulative with no streak. Missing a day resets nothing, the total keeps growing. S2 chip note, S4 row 3. | `what-is-an-e-marathon.md:60` |
| "Only the front of the pack gets anything" | Daily step badges re-earn every time someone crosses a threshold, so last place still collects something. S4 row 4. | `admin-how-do-badges-work.md:16-33` |
| "Some of my people hate being ranked" | Leaderboard opt-out hides a person from the board while they keep participating and keep earning. S4 row 5, S8 card 4. | `HELP/employee/challenges/can-i-opt-out-of-leaderboard.md:15-33` |
| "The name still sets an unreachable bar" | The page prints the doc's own realism: a full marathon's worth of steps in one day is roughly 50,000 steps, so pick a distance most of your workforce can reach. | `admin-when-to-use-a-one-day-virtual-marathon.md:64` |

The hero leaderboard casting does the same work without a sentence: Facilities first, Nursing second.

### 4.2 The shape objection, and it is the native one: "Is a one-off event worth the setup, and what happens the day after?"

Every other page in this group sells a program. This one sells a moment, which means the buyer is not asking "does it work", they are asking "is it worth my week". The page answers structurally rather than rhetorically: S3 *is* the answer, and S11 sells the handoff rather than the event.

| Sub-objection | Product answer on the page | Source |
|---|---|---|
| "Setup will eat a week" | Two settings, then audience, then review and publish. About 10 minutes on stage 1 of the run book, presented as a ceiling on the generic wizard figure. | `admin-how-do-i-create-a-challenge.md:13`; `admin-how-do-i-create-e-marathon.md:49-79` |
| "I will have to run a registration drive" | Launch day: "Nothing. There is no registration to chase." An audience rule enrolls everyone who matches. | `how-do-i-join-a-challenge.md:17-38`; `challenges.md:42` |
| "The promotion is the real cost" | The page says so. Stage 2 is "start a week out", email plus push plus in-app banner plus one leader posting their own progress. Ten minutes of configuration, one week of promotion. | `admin-when-to-use-a-one-day-virtual-marathon.md:56,65` |
| "I will spend the following week doing fulfilment" | Badges are automatic within minutes; the weekly progress email sends itself; rankings settle after the buffer. The only manual acts on the page are posting the company total and picking winners. | `admin-how-do-badges-work.md:69,78`; `admin-what-emails-does-vfit-send.md:33`; `what-happens-when-challenge-ends.md:45-53` |
| "My leaderboard will still be moving on Monday" | Pre-answered rather than discovered: 3-day buffer for late Fitbit and Garmin syncs, stated in S3, S5, S6, the standings caption and FAQ 5. | `admin-how-do-i-create-race-challenge.md:27-29` |
| "And then what?" | The closer, verbatim from the docs' own positioning: kickoff for a 30-day challenge, midpoint energizer, program finale. The H2 borrows the doc's line: "One event is a campaign." | `admin-when-to-use-a-one-day-virtual-marathon.md` §Combining with Other Programs, `:46` |

### 4.3 The objection this page cannot answer, and says so

**"Can region compete against region, department against department, with a scored team leaderboard?"** For this format there is no answer. The E-Marathon setup article has no team step, and teams on E-Marathon are NOT FOUND IN SOURCES. The page does three things instead of inventing one: it never draws a Team tab in any mock; it offers the collective device the docs do support ("Announce the total company distance", plus the audience filter for scoping a region); and the S10 Team Challenge row says plainly "Scored teams and team averages, which a virtual marathon does not have." That row is the honest destination for the question, and it is the most load-bearing internal link on the page.

### 4.4 What the page refuses to claim on integrity

No step-cap number (three sources give three different answers, and the code-verified spec says step normalization is currently disabled). No "no ceiling" claim, for the same reason. No "fraud-proof", no "every step verified", no "verified logging". No GPS pace validation or vehicle detection, because no GPS is involved in this format and citing them would be borrowed credibility. Integrity is three chips naming three real mechanisms with zero thresholds, and nothing more.

---

## 5. Full copy deck (as shipped)

Every visible string on the page, in section order. `<em>` marks the coral-gradient span. Two em-dashes exist on the entire page, both in `— Name, Title, Company` attributions.

### Page furniture

- **Meta title:** `Corporate Virtual Marathon for Employees | Vantage Fit`
- **Meta description:** `Run a corporate virtual marathon where steps become distance, so every employee can finish by walking. One event, every time zone. Book a demo.`
- **Nav:** Solutions (marked current) · Features · Resources · Pricing · **Book a demo**
- **Solutions mega, Run a challenge column:** Steps Challenge · Team Challenge · Multi-activity Challenge · Mental Health & Wellbeing · **Virtual Marathon** (marked `is-page`, `aria-current="page"`)
- **Mega banner:** `See every program on one page: the Solutions overview`
- **Skip link:** `Skip to main content`

### S1 Hero (`#hero`)

- **Eyebrow:** `Solutions · Virtual Marathon`
- **H1:** `A virtual marathon your whole workforce can finish by <em>walking</em>.`
- **Lead:** `Vantage Fit counts distance from the steps people already take, so nobody opens a GPS workout and nobody signs up. Every region runs the same event on its own local clock.`
- **CTAs:** `Book a demo` (primary) · `Get the virtual marathon guide` (outline)
- **Hero notes:** `Distance from steps, not GPS` · `Nobody signs up, everyone is enrolled` · `One event, every local clock`
- **Leaderboard card:** title `Leaderboard` · tag `Illustrative data` · toggle `Weekly` / `Overall` (Overall active) · chip `Department` · columns `#` `Employee` `Distance`
  - `1 · Marisol R. · Facilities · 231.4 km`
  - `2 · Dele A. · Nursing · 224.6 km`
  - `3 · Anouk V. · Finance · 218.9 km`
  - `···`
  - `42 · Theo M. (You) · Customer support · 146.4 km`
- **Phone:** `Vantage Fit` · `E-MARATHON` · `Ongoing` · `Race to the Moon` · `Days elapsed` / `Day 24 of 30` · `Your total distance` `146.4 km` · `#42 of 610` `Rank` · `6` `Days remaining` · `Steps today` `8,240` → `8.2 km` · tag `Illustrative data`
- **Logo band:** `Trusted by 100+ organizations worldwide` · TATA MOTORS · WIPRO · TEVA · GODREJ · TEXAS INSTRUMENTS · HEIDRICK & STRUGGLES · BRAZOSPORT ISD

### S2 How the distance is counted (`#mechanic`)

- **Eyebrow:** `How distance is counted`
- **H2:** `Steps become distance. Nobody opens a GPS workout.`
- **Lead:** `One setting decides how steps convert. Everything else about a virtual marathon is dates and audience.`
- **Conversion strip:** `10,000 steps` → `1,000 steps = 1 km` → `10 km added to the total`
- **Strip caption:** `Set the ratio once at setup. Choose kilometers or miles.`
- **Chips:** `Cumulative` · `No daily target` · `No streak to break`
- **Chip note:** `Missing a day resets nothing. The total keeps growing.`
- **Pull quote:** `"Employees do not need to use GPS workouts or run specific routes. Their regular daily steps are automatically counted."`
- **Pull quote caption:** `From the Vantage Fit admin help center`
- **Wizard mock:** `Create challenge` · `Step 3 of 5 · Distance conversion` · `Steps to distance ratio` → `1,000 steps = 1 km` · `Distance unit` → `Kilometers` · note `Two settings, then audience, then review and publish. E-Marathons are intentionally simple.` · tag `Illustrative data`
- **H3:** `Two ways to run a marathon here. Only one needs a phone call.`
- **Card 1 — E-Marathon:** `Steps convert to distance at a ratio you set. Ranked by total distance, cumulative, no GPS. 2 to 4 weeks, or a single day.` · `Self-serve` / `Built from the admin dashboard, like any other challenge.`
- **Card 2 — Marathon Event** (drawn quieter): `A real GPS-tracked race with distance tiers, including 5K, 10K, half and full.` · `Arranged with your account manager` / `For an on-site or GPS-timed race alongside the step event.`
- **Format note:** `A full marathon's worth of steps in one day is roughly 50,000 steps, so pick a distance most of your workforce can reach.`

### S3 The run book (`#runbook`)

- **Eyebrow:** `The run book`
- **H2:** `Your four weeks, and what the platform does without you.`
- **Lead:** `10 minutes of configuration. One week of promotion. The rest runs itself.`
- **Column labels:** `You do` / `Vantage Fit does`

| Stage | You do | Vantage Fit does |
|---|---|---|
| **1 Configure** · `about 10 minutes` | Set the dates, keep the default 1,000 steps = 1 km, pick kilometers or miles, pick the audience. | Marks the challenge private the moment you filter the audience, so it stays invisible outside that group. |
| **2 Promote** · `start a week out` | Email, push and an in-app banner, plus one leader posting their own progress. | Sends the enrollment email as people are enrolled. |
| **3 Launch day** · `zero minutes` | Nothing. There is no registration to chase. | Enrolls everyone the rule matches, moves the challenge from Upcoming to Ongoing, and sends the start email. |
| **4 Mid-event** · `weeks two and three` | Post the running company total. Add late joiners by search or CSV. | Sends the weekly progress email, awards daily step badges within minutes, and tells people when their rank moves. Late joiners score from their join date. |
| **5 Finish and settle** · `plus 3 days` | Share the company total the same day. Pick your winners after the buffer. | Holds a 3-day buffer for late Fitbit and Garmin syncs, then settles rankings. Results stay in the Past tab. |

- **Note 1:** `Announce the total company distance while it climbs. Something like "We just passed 5,000 km as a company!"`
- **Note 2:** `Reminder emails are off by default and switched on by your account manager.`

### S4 Follow-through (`#employees`)

- **Eyebrow:** `Follow-through`
- **H2:** `Nothing to sign up for, nothing to keep up with.`
- **Rows:**
  1. `No registration drive.` — `An audience rule enrolls everyone who matches, or you add people by search or CSV upload.`
  2. `Nothing to log.` — `Steps sync in the background from Apple Health on iOS and Google Fit on Android. No wearable required.`
  3. `Nothing to fall behind on.` — `No daily target and no streak, so a missed day resets nothing.`
  4. `Badges land all the way down the board.` — `Daily step badges re-earn each time someone crosses a threshold, so last place still collects something.`
  5. `Anyone can leave the rankings without leaving the event.` — `Leaderboard opt-out hides a person from the board while they keep participating and keep earning.`
- **Notice stack:** `Vantage Fit` / `Challenge enrollment` · `You're in. No action needed.` · `Race to the Moon opens on your local clock. Your steps start counting on day one.` — `Daily steps · 10,000` / `Earned 4 times` — `Vantage Fit` / `Weekly progress` · `Your week 3 summary` · `Distance this week 41.2 km` · `Rank #58` · tag `Illustrative data`

### S5 Time zones (`#timezones`)

- **Eyebrow:** `Every local clock`
- **H2:** `One event. Every time zone gets a full local day.`
- **Lead:** `The last global event probably ran on headquarters' clock. Here are the four behaviors that decide it, and the two places to be careful.`
- **Items:**
  1. `Localized start` — `The event opens at local midnight on the start date, wherever the person is.`
  2. `Localized end` — `It closes at local midnight on the end date, so a 30-day event is a true 30 calendar days for every participant.`
  3. `Rewards in local currency` — `Values are configured in USD and shown in each employee's local currency, from a country-relevant gift card catalog.`
  4. `A 3-day sync buffer` — `Late Fitbit and Garmin syncs still land before rankings settle.`
- **Caveats (`.fair-fine`):** `Push notifications arrive at each recipient's corresponding local time, so stagger your sends. Report date filters run on the admin's time zone, not the participant's.`
- **Final standings panel:** `Final standings` · tag `Illustrative data` · columns `#` `Employee` `Distance`
  - `1 · Marisol R. · Manila · closes 11:59 PM, Sep 30 local · 288.6 km`
  - `2 · Dele A. · Bengaluru · closes 11:59 PM, Sep 30 local · 279.1 km`
  - `3 · Anouk V. · Kraków · closes 11:59 PM, Sep 30 local · 271.5 km`
  - `4 · Ines B. · London · closes 11:59 PM, Sep 30 local · 264.8 km`
  - `5 · Sena O. · Chicago · closes 11:59 PM, Sep 30 local · 258.2 km`
- **Panel caption:** `One end date. Five local clocks. Provisional until Oct 3 while late device syncs land.`

### S6 Reporting (`#report`)

- **Eyebrow:** `Reporting`
- **H2:** `What you take into the Monday review.`
- **Checks:**
  1. `Score and Steps leaderboards` — `Per-person score breakdown, opened from any row.`
  2. `Participation rate on the challenge card` — `Shown next to status, type and date range.`
  3. `Employee Report` — `Active, Inactive and Dormant enrollment status.`
  4. `Export CSV on every report` — `Your filters travel with the export.`
- **Reconciliation line:** `Employees rank by distance. Your export comes out in steps and score. The steps column ranks in exactly the same order, because distance is steps divided by one company-wide ratio.`
- **Integrity chips:** `Recognized apps and devices only` · `One primary device at a time, so nothing double counts` · `Nothing final until the 3-day buffer closes`
- **Fine print:** `Exports are a manual click. Vantage Fit does not schedule or email reports.`
- **Report mock:** `Race to the Moon · Leaderboard` · tag `Illustrative data` · badges `Private` `E-Marathon` · `Sep 1 – Sep 30, 2026` · `Participation rate` `61%` · tabs `Score` `Steps` · filters `Date range: Sep 1 – Sep 30` `Department: All` `Country: All` · columns `Rank` `Employee` `Department` `Score` `Total steps`
  - `1 · Marisol R. · Facilities · 964 · 288,600`
  - `2 · Dele A. · Nursing · 928 · 279,100`
  - `3 · Anouk V. · Finance · 907 · 271,500` (expanded)
  - Drill row: `Task Walk or run` · `Points 907` · `Total steps 271,500` · `Last active Sep 30`
  - Foot: `610 participants` · `Export CSV`

### S7 Customer results (`#proof`)

- **Eyebrow:** `Customer results`
- **H2:** `Named programs, and the numbers their sources reported.`
- **Cards:**
  1. `97%` — `participation in a two-week walkathon with 72+ participants and 11M+ steps` — `POSOCO · Walking Miles, Losing Inches` / `Dec 6 – 19, 2021`
  2. `5,000+` — `participants across 6 in-house teams in a 30-day virtual walkathon` — `Landmark Group` / `Feb 8 – Mar 9, 2021`
  3. `550` — `active users in a global step-a-thon, with 87.33% step growth versus the first challenge. Across all three 2025 challenges, 30+ countries took part` — `Wipro · Spirit of Wipro Global Step-a-thon` / `Jul 28 – Aug 17, 2025`
- **Quote 1:** `"Our employees highly appreciated the gamification elements integrated into the platform, which added an element of fun to the Walkathon."` — Aishwarya Verma, Assistant Manager HR, Grid India
- **Quote 2 (text-only, quieter):** `"This was our second year with them and we will return back next year as well. Their platform is simple and easy to use both as a user and as an admin."` — Padmini Rudrapatna, Compare & Connect
- **Fine print:** `Results from named customer programs, labeled the way each source measured them. Outcomes vary by workforce and program design.`
- **Link:** `Read customer stories →`

### S8 Security and privacy (`#security`)

- **Eyebrow:** `Enterprise security & compliance`
- **H2:** `A public leaderboard does not mean public health data.`
- **Lead:** `Employees see their own data. HR sees aggregate trends.`
- **Actions:** `Book a demo` · `Explore security & compliance →`
- **Cards:**
  1. `Follows HIPAA guidelines` — `A virtual marathon puts step data in play and nothing else, and that data is handled under HIPAA guidelines.`
  2. `SOC 2 Type II` — `An independently audited control set your security team can review.`
  3. `Secured regional data hosting` — `India, the US, the EU and the UAE, chosen at signup, with no cross-region sharing.`
  4. `Visible by choice` — `Ranking visibility is an opt-out, so taking part in the event and appearing on the board are two separate decisions.`
- **Plaque alt:** `Vantage Fit security and compliance badges`
- **Plaque support line:** `Security documentation is available during evaluation.`

### S9 FAQ (`#faq`)

- **H2:** `Questions before you put a date on the calendar.`
1. **`Do employees need to run, or use GPS?`** — `No. Distance is calculated from step count, not GPS. Employees do not need to use GPS workouts or run specific routes. Their regular daily steps are counted automatically, which is why a walker finishes the same event as a runner.`
2. **`Do employees need a wearable?`** — `No. The phone tracks steps through Apple Health on iOS and Google Fit on Android. Fitbit or Garmin take over when connected, and Vantage Fit uses one primary device at a time so nothing is counted twice.`
3. **`Do employees have to sign up?`** — `No. An audience rule enrolls everyone who matches, or you add people by search or CSV upload. There is no browse-and-join flow, so your participation number does not depend on a registration drive.`
4. **`How does it work across time zones?`** — `The event opens at local midnight on the start date and closes at local midnight on the end date, so every participant gets the same number of full days. Rewards are shown in each employee's local currency.`
5. **`When are results final?`** — `Results stay provisional for 3 days after the end date while late Fitbit and Garmin syncs land. Rankings, ranking bonuses, and certificates if your admin enabled them, settle after that buffer.`

FAQPage JSON-LD is emitted and matches these five answers character for character.

### S10 Related (`#related`)

- **Eyebrow:** `Keep exploring`
- **H2:** `Where this event leads next`
  - `Steps Challenge` — `The format most programs already run, in five variations.`
  - `Team Challenge` — `Scored teams and team averages, which a virtual marathon does not have.`
  - `All Vantage Fit solutions` — `Every program on one page, and how they sequence.`

### S11 Closer (`#demo`)

- **H2:** `One event is a campaign. Decide what it starts.`
- **Body:** `In a 30-minute demo we will set up an E-Marathon against a date you already have, and show you the leaderboard and the export it produces.`
- **CTAs:** `Book a demo` · `See pricing`
- **Checks:** `Kickoff for a 30-day challenge` · `Midpoint energizer` · `Program finale`
- **Note:** `One event everyone finishes. One number leadership recognizes.`

### Footer

`Inclusive wellness that turns participation into measurable progress.`
Product: How distance is counted · HR analytics · Security · Pricing
Solutions: Step challenges · Team challenges · **Virtual marathon** (current) · Wellness program · Remote teams · Global engagement · Analytics
Company: About · Customer results · Case studies · Contact sales
Bottom: `© 2026 Vantage Circle. All rights reserved.` · `HIPAA guidelines · SOC 2 Type II` · `Wellness built for participation.`

---

## 6. Claims ledger

Status key: **A** = dedicated or generic help doc, current shipped behaviour, verifiable by the buyer during a trial · **B** = shipped but gated or qualified, with the gate stated on the page · **C** = dashboard repo only, lowest precedence, used for interface shape rather than as a claim · **P** = approved customer proof, cited from `VOS/.claude/rules/data-accuracy.md` · **I** = illustrative, visibly labelled, asserts nothing.

Path shorthand: `HELP` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/` · `VOS` = `/Users/anjanpathak/work/vc-os/vfit-os/` · `DASH` = `/Users/anjanpathak/work/gitcode/vc-dashboard-design/`

| # | Claim / figure on the page | Where | Source | Status |
|---|---|---|---|---|
| 1 | Steps are converted to distance; ranked by total distance covered | H1, S1 lead, S2 strip, S2 card 1, S6 reconcile | `HELP/admin/challenges/admin-how-do-i-create-e-marathon.md:23-25`; `HELP/employee/challenges/what-is-an-e-marathon.md:27-29` | A |
| 2 | Default conversion 1,000 steps = 1 km, adjustable at setup | S2 strip, S2 wizard mock, S3 stage 1, S6 reconcile | `admin-how-do-i-create-e-marathon.md:24,53` | A |
| 3 | Distance unit is km or miles | S2 strip caption, S2 wizard mock | `admin-how-do-i-create-e-marathon.md:54` | A |
| 4 | "Employees do not need to use GPS workouts or run specific routes. Their regular daily steps are automatically counted." (verbatim) | S2 pull quote, FAQ 1 | `admin-how-do-i-create-e-marathon.md:29` | A |
| 5 | Cumulative, no daily target, no target thresholds, no streak mechanic | S2 chips, S2 card 1, S4 row 3 | `admin-how-do-i-create-e-marathon.md:26-27` | A |
| 6 | Missing a day resets nothing; the total keeps growing | S2 chip note, S4 row 3 | `what-is-an-e-marathon.md:60` | A |
| 7 | "E-Marathons are intentionally simple." (verbatim fragment) | S2 wizard note | `admin-how-do-i-create-e-marathon.md:79` | A |
| 8 | Distance conversion is Step 3 of the setup flow; audience then review and publish follow | S2 wizard mock header and note | `admin-how-do-i-create-e-marathon.md:31-79` (Steps 1 to 5) | A |
| 9 | Two to four weeks is the doc's own duration guidance | S2 card 1 | `admin-how-do-i-create-e-marathon.md:45` | A |
| 10 | A single-day virtual marathon is a supported use | S2 card 1 | `admin-when-to-use-a-one-day-virtual-marathon.md` (whole doc) | A |
| 11 | Marathon Event is a GPS-tracked race with distance tiers including 5K, 10K, half and full, arranged with an account manager | S2 card 2 | `VOS/specs/product/02-challenges-gamification/challenges.md:72`; `HELP/admin/challenges/admin-what-challenge-formats.md:84` | **B** |
| 12 | A full marathon's worth of steps in one day is roughly 50,000 steps | S2 format note | `admin-when-to-use-a-one-day-virtual-marathon.md:64` | A |
| 13 | Creating a challenge takes 5 to 10 minutes from the admin dashboard, presented as "about 10 minutes" | S3 lead, S3 stage 1 | `admin-how-do-i-create-a-challenge.md:13` | A |
| 14 | Promote one week ahead using email, push and an in-app banner, with a leadership champion sharing their own progress | S3 lead, S3 stage 2 | `admin-when-to-use-a-one-day-virtual-marathon.md:55,65` | A |
| 15 | Audience filters are department, country, city or other attributes | S3 stage 1 | `admin-how-do-i-create-e-marathon.md:69-71` | A |
| 16 | Any audience filter automatically marks the challenge Private | S3 stage 1 | `admin-how-do-i-create-e-marathon.md:73` | A |
| 17 | Enrollment email sends automatically as people are enrolled | S3 stage 2, S4 notice 1 | `HELP/admin/communication/admin-what-emails-does-vfit-send.md:29` | A |
| 18 | An audience rule enrolls everyone who matches; there is no browse-and-join flow | S1 lead, S1 note 2, S3 stage 3, S4 row 1, FAQ 3 | `HELP/employee/challenges/how-do-i-join-a-challenge.md:17-38`; `VOS/specs/product/02-challenges-gamification/challenges.md:42` | A |
| 19 | The challenge moves from Upcoming to Ongoing at the start date | S3 stage 3, S1 phone pill | `admin-how-do-i-create-a-challenge.md:102` | A |
| 20 | Challenge start email sends automatically | S3 stage 3 | `admin-what-emails-does-vfit-send.md:30` | A |
| 21 | Participants can be added individually, by search, or by CSV bulk upload | S3 stage 4, S4 row 1, FAQ 3 | `admin-how-do-i-create-e-marathon.md:84`; `admin-how-do-i-add-remove-participants.md` | A |
| 22 | Weekly progress email sends automatically during an active challenge, carrying progress and ranking | S3 stage 4, S4 notice 3 | `admin-what-emails-does-vfit-send.md:33` | A |
| 23 | Daily step badges are awarded automatically within minutes and re-earn every time a threshold is hit | S3 stage 4, S4 row 4, S4 notice 2 | `admin-how-do-badges-work.md:16-33,67-78` | A |
| 24 | A push notification tells an employee when their leaderboard position changes | S3 stage 4 | `HELP/employee/getting-started/what-notifications-will-i-receive.md` §Rewards & Achievements | A |
| 25 | Late joiners score from their join date forward | S3 stage 4 | `admin-how-do-i-add-remove-participants.md:61-69`; `challenges.md:49` | A |
| 26 | Announce the total company distance; "We just passed 5,000 km as a company!" | S3 note 1 | `admin-how-do-i-create-e-marathon.md:87,92` | A |
| 27 | Challenge reminder emails are off by default and switched on by the account manager | S3 note 2 | `admin-what-emails-does-vfit-send.md:36` | **B** |
| 28 | A 3-day buffer holds for late Fitbit and Garmin syncs before rankings settle | S3 stage 5, S5 item 4, S5 caption, S6 chip 3, FAQ 5 | `admin-how-do-i-create-race-challenge.md:27-29`; `how-do-i-get-my-certificate.md:17` | A |
| 29 | Results are stored in the Past tab | S3 stage 5 | `HELP/employee/challenges/what-happens-when-challenge-ends.md:34` | A |
| 30 | Winner selection is a manual admin act after the buffer | S3 stage 5 | `what-happens-when-challenge-ends.md:45-53` | A |
| 31 | Steps sync in the background from Apple Health on iOS and Google Fit on Android; no wearable required | S4 row 2, FAQ 2 | `HELP/employee/getting-started/do-i-need-a-wearable.md`; `how-does-step-syncing-work.md` | A |
| 32 | Fitbit or Garmin take over when connected; one primary device at a time so nothing double counts | S6 chip 2, FAQ 2 | `do-i-need-a-wearable.md` §One Device at a Time; `VOS/specs/product/10-integrations/device-integrations.md` | A |
| 33 | Leaderboard opt-out hides a person from the board while they keep participating and keep earning | S4 row 5, S8 card 4 | `HELP/employee/challenges/can-i-opt-out-of-leaderboard.md:15-33` | A |
| 34 | The employee screen shows total distance, rank and days remaining, with a distance progress bar | S1 phone | `what-is-an-e-marathon.md:43-48`; `what-challenge-formats-exist.md:91` | A |
| 35 | Leaderboard has a Weekly / Overall toggle and a department filter | S1 leaderboard card | `HELP/employee/challenges/how-does-the-leaderboard-work.md:28-33,58` | A |
| 36 | The event opens at local midnight on the start date | S5 item 1, FAQ 4 | `admin-can-i-run-challenges-across-time-zones.md:19` | A |
| 37 | It closes at local midnight on the end date, so a 30-day event is a true 30 calendar days for every participant | S5 item 2, S5 board, FAQ 4 | `admin-can-i-run-challenges-across-time-zones.md:21-23` | A |
| 38 | Rewards are configured in USD, displayed in each employee's local currency, from a country-relevant gift card catalog | S5 item 3, FAQ 4 | `admin-can-i-run-challenges-across-time-zones.md:27-29` | A |
| 39 | Push notifications arrive at each recipient's corresponding local time, so stagger sends | S5 caveats | `admin-can-i-run-challenges-across-time-zones.md:35` | A |
| 40 | Report date filters run on the admin's time zone, not the participant's | S5 caveats | `admin-can-i-run-challenges-across-time-zones.md:37` | A |
| 41 | Admin leaderboard views are Score and Steps | S6 check 1, S6 mock tabs | `HELP/admin/reports/admin-how-do-i-view-leaderboard.md:24-51` | A |
| 42 | A per-person score breakdown opens from any leaderboard row | S6 check 1, S6 mock drill row | `admin-how-do-i-view-leaderboard.md:72-83` | A |
| 43 | Participation rate appears on the challenge card alongside status, type and date range | S6 check 2, S6 mock header | `DASH/CRUD_FLOWS_AND_COMPONENTS.md:430` | **C** |
| 44 | Employee Report carries Active, Inactive and Dormant enrollment status | S6 check 3 | `HELP/admin/reports/admin-what-reports-are-available.md:17-38` | A |
| 45 | Export CSV exists on every report and filters apply before export | S6 check 4, S6 mock | `admin-what-reports-are-available.md:129-144`; `admin-how-do-i-view-leaderboard.md:88-102` | A |
| 46 | Exports are manual; Vantage Fit does not schedule or email reports | S6 fine print | `admin-how-do-i-view-leaderboard.md:88-102` (stated as a limit, deliberately) | A |
| 47 | Steps are accepted only from recognized apps and devices | S6 chip 1 | `VOS/specs/product/01-core-tracking/activity-tracking.md:162` | **B** |
| 48 | Distance ranking and step ranking are the same order, because distance is steps divided by one company-wide ratio | S6 reconciliation line | Arithmetic consequence of `admin-how-do-i-create-e-marathon.md:53` plus `what-is-an-e-marathon.md:27-29` | A |
| 49 | Follows HIPAA guidelines · SOC 2 Type II | S8 cards 1 and 2, footer | `VOS/sources/VFit-Marketing-Content-Compacted.md:161-162` (exact approved strings only) | A |
| 50 | Secured regional data hosting in India, the US, the EU and the UAE, chosen at signup, no cross-region sharing | S8 card 3 | `VOS/specs/product/03-health-wellness/onboarding-health-profile.md:178`; `VFit-Marketing-Content-Compacted.md:284` | A |
| 51 | "Employees see their own data. HR sees aggregate trends." | S8 lead | `VOS/.claude/rules/hr-buyer-lens.md:44` (approved verbatim translation) | A |
| 52 | Certificates, "if your admin enabled them", settle after the buffer | FAQ 5 only | `how-do-i-get-my-certificate.md:17`; hedged because the E-Marathon setup article has no certificate step | **B** |
| 53 | Kickoff for a 30-day challenge / midpoint energizer / program finale | S11 checks | `admin-when-to-use-a-one-day-virtual-marathon.md` §Combining with Other Programs | A |
| 54 | "One event is a campaign." | S11 H2 | `admin-when-to-use-a-one-day-virtual-marathon.md:46` ("A single one-day event is a campaign, not a program") | A |
| 55 | POSOCO, Walking Miles, Losing Inches: **97% participation**, **72+ participants**, **11M+ steps**, two-week walkathon, Dec 6-19 2021 | S7 card 1 | `VOS/.claude/rules/data-accuracy.md:191`; `vantagefit-astro/content/en/casestudy/posoco-walkathon-challenge.md` | **P** |
| 56 | Landmark Group: **5,000+ participants across 6 in-house teams**, 30-day virtual walkathon, Feb 8 - Mar 9 2021 | S7 card 2 | `data-accuracy.md:154-166` | **P** |
| 57 | Wipro, Spirit of Wipro Global Step-a-thon: **550 active users**, **87.33% step growth versus the first challenge**, Jul 28 - Aug 17 2025; **30+ countries across all three 2025 challenges** | S7 card 3 | `data-accuracy.md:85-129`; `content/en/casestudy/wipro-global-wellbeing.md` §The Results | **P** |
| 58 | Grid India quote, exact string, "— Aishwarya Verma, Assistant Manager HR, Grid India" | S7 quote 1 | `data-accuracy.md:212` | **P** |
| 59 | Compare & Connect quote, exact string, "— Padmini Rudrapatna, Compare & Connect" (no title in source) | S7 quote 2 | `data-accuracy.md:233` | **P** |
| 60 | "Trusted by 100+ organizations worldwide" | S1 logo band | `data-accuracy.md:256-261` (the only approved aggregate scale claim) | **P** |
| 61 | Logo band names: Tata Motors, Wipro, Teva, Godrej, Texas Instruments, Heidrick & Struggles, Brazosport ISD | S1 logo band | `data-accuracy.md:22` approved client list | **P** |
| 62 | Every name, distance, score, step total, rank, participation rate, city, date and challenge name inside a mock: Race to the Moon; Marisol R. / Dele A. / Anouk V. / Theo M. / Ines B. / Sena O.; 231.4 / 224.6 / 218.9 / 146.4 km; 288.6 / 279.1 / 271.5 / 264.8 / 258.2 km; 964 / 928 / 907; 288,600 / 279,100 / 271,500; #42 of 610; day 24 of 30; 8,240 steps → 8.2 km; 41.2 km / rank #58; 61% participation rate; Sep 1 - Sep 30, 2026; Manila / Bengaluru / Kraków / London / Chicago | S1 (x2), S2, S4, S5, S6 | **Invented.** Every mock carries a visible `Illustrative data` tag and repeats that status in its `aria-label`. All figures were rebuilt against a single 1,000 steps = 1 km pace so no two mocks contradict each other. `Race to the Moon` is the help doc's own example name (`admin-how-do-i-create-e-marathon.md:91`). | **I** |

### 6.1 Claims cut, and why

| Cut | Reason |
|---|---|
| Race levels: Beginner 5 KM / Intermediate 10 KM / Seasoned Runners 21 KM as self-serve product tiers | No tier field and no target-distance field exist in the E-Marathon wizard. The tiers survive only on the Marathon Event card, where they are true. |
| "Each participant earns points based on the distance they cover" | Contradicts every source. One implicit task, no per-distance point scheme. |
| Distance badges at 5, 10 or 21 km, and any 42.2 km marathon badge | The Runs ladder is 1 / 3 / 5 / 10 / 42.2 km and fires from GPS-tracked runs. There is no 21 km badge, and a 42.2 km badge sitting three sections below "no GPS needed" is a self-contradiction a buyer would catch. |
| Teams, team standings, team averages, region-versus-region scored teams | NOT FOUND IN SOURCES for this format. No mock draws a Team tab. The question is handed to the Team Challenge row in S10. |
| "Localized daily reset at local midnight" | True for daily-target formats. An E-Marathon has no daily target, so it is not load-bearing here. Start and end only. |
| Stride length as the distance input | One summary article says it; the two dedicated articles say a fixed configurable ratio. No per-person calibration exists. |
| "1 mile = 1,609 steps" | Dashboard repo only, lowest precedence, and it contradicts the help doc's ratio model. |
| Any step cap number, and equally any "no ceiling" claim | Three sources give three answers, and the code-verified spec says step normalization is currently disabled. |
| GPS pace validation, vehicle detection | Real mechanisms, irrelevant to a format with no GPS. Citing them would be borrowed credibility. |
| "Fraud-proof", "every step verified", "verified logging" | Never permitted. |
| Wheelchair Mode as this page's inclusion proof | Real feature, wrong page. Wheelchair workouts do not convert into E-Marathon distance, which is derived from steps. An accessibility-minded buyer verifies this in a trial and never forgives it. |
| Certificates as an unqualified E-Marathon feature | The format's own setup article has no certificate step. Appears once, hedged, in FAQ 5 only. |
| Race bibs, medals, finisher kits, race numbers, finish-line ribbons | A grep of the whole help corpus returns nothing. We do not compete in that category, and silence beats imitation. |
| A Distance tab or a distance column in any admin mock | The single most likely way this page could have shipped a lie. |
| Scheduled reports, an emailed exec digest, a shareable dashboard link | Do not exist. The page states the opposite. |
| Automatic reminder emails as a momentum feature | Off by default and account-manager gated. Named honestly in a run-book note instead. |
| Point and monetary rewards for challenge tasks, "wellness perks", "company specific incentives" | AM-enabled, "currently only 1 company". The two unsourced phrases are live-page invention. |
| Participation 25-60%, completion 30-50%, 1-2 week app-open uplift | Help-doc planning guidance, not customer results, and the completion row is defined against tiers this format does not support. Parked behind the gated guide. |
| The Global Corporate Walkathon (3,700+ participants, 74 teams, 24 countries, "84% boost") | Vantage Fit's own marketing event, not customer proof. The single most tempting item for this page. |
| The shared 59 / 88 / 86 proof block | Engagement figures from other programs, none attached to a marathon, all three mislabelled as participation on live pages today. |
| Any distance-marathon result, finisher count or race-tier completion rate | NOT FOUND IN SOURCES. |
| POSOCO's "825,810+ average steps" | Does not reconcile with 11M+ across 72+ participants. |
| Landmark's 4.3M+ steps | Approved only as the **top team's** total. Generalising it is the classic misread, so it was omitted rather than caveated. |
| The Puneet Arora / ArtKhoj quote | The only approved quote that names a virtual marathon, but ArtKhoj is a program facilitator running the program for a corporate client, not the end employer. The attribution caveat costs more than the quote returns. |
| Allston Trading and Compare & Connect numbers, Accenture, Hershey, Serum Institute, the "$250 savings" stat, the Indian physical-inactivity stats | Barred for this page by the approved-proof gate. |
| ISO 27001, ISO 27701, GDPR anywhere including alt text; "HIPAA compliant"; "SOC 2 certified" | No product-KB support. The plaque alt asserts nothing. |
| Lite Mode compatibility, either way | Lite Mode clients cannot run an E-Marathon, but it is a tenant-tier fact rather than a format fact. Not claimed in either direction. |

### 6.2 Pre-ship gates, re-run against the shipped file

`Book a demo` 4 on-page instances plus the meta description, identical label · `See pricing` 1 · `Get the virtual marathon guide` 1 · `Illustrative data` 6 visible tags across 7 `role="img"` mocks (the seventh is the conversion strip, which carries arithmetic, not fabricated figures) · em-dashes 2, both in quote attributions, zero `&mdash;`, zero `&#8212;` · one `<h1>` with one `<em>` · heading run h1 → 10× h2 → 13× h3 → 2× h4 with no skips · 10 `<section>` plus the `<header>` hero, all with `id` and `aria-labelledby` · zero hits for ISO 27001, ISO 27701, GDPR, "HIPAA compliant", Slack, Microsoft Teams, Health Connect, "any device", 25,000, bib, medal, finisher kit, 1,609, stride, POSCO, 4.3M, Global Corporate Walkathon, Accenture, Hershey, "scheduled report", and the banned-word list · FAQPage JSON-LD parses and matches the five visible answers character for character · meta title 54 characters, meta description 143 characters · zero horizontal overflow and zero nowrap overflow at 390px, verified in headless Chrome at 390 / 1101 / 1152 / 1200 / 1279 / 1339 / 1440.

---

## 7. Proof decision

**The page carries a full customer-result section.** The approved-proof gate says run one, and participation is this page's north-star metric type, so the pool is used for participation and scale only. **No distance figure appears anywhere in S7.**

**The terminology gate is the hardest rule in this section, and it is absolute.** Every result keeps the source's own noun. POSOCO ran a **walkathon**. Landmark Group ran a **virtual walkathon**. Wipro ran a **step-a-thon**. None of them is upgraded to "marathon" to fit the page, and the cards say so in plain sight. Upgrading any one of them would be the exact failure mode the live page commits when it relabels engagement as participation.

**What is cited and why:**

- **POSOCO, Walking Miles, Losing Inches** leads because 97% is the highest approved participation figure tied to a named, time-boxed virtual event, and it is labelled **participation**, not engagement, in the source. Two weeks, 72+ participants, 11M+ steps. Spelled POSOCO, never POSCO. The "825,810+ average steps" figure in the same case study is excluded because it does not reconcile with 11M+ across 72+ participants.
- **Landmark Group** supplies scale in the unit an event buyer thinks in: 5,000+ participants in a 30-day virtual walkathon. The "6 in-house teams" detail is retained because it is the source's own description of how that program was organised, not a claim about E-Marathon team scoring. Landmark's top-team 4.3M+ steps is approved but only as a top-team figure, and generalising it is the classic misread, so it was omitted entirely rather than caveated.
- **Wipro, Spirit of Wipro Global Step-a-thon** answers the global question that S5 raises. The card leads on **550 active users** and **87.33% step growth versus the first challenge**, both of which the case study attributes to that named challenge. **30+ countries is carried in a separate clause explicitly scoped to all three 2025 challenges**, because the case study's own results heading reads "Across all three challenges" and `data-accuracy.md:85-100` files the countries figure under the cumulative headline rather than the Step-a-thon table. This was a shipped correction to the blueprint, which had made 30+ the card's headline stat under the named challenge. Wipro step totals are not stacked.
- **Grid India** (Aishwarya Verma, Assistant Manager HR) supplies the employee-side sentence about gamification in a walkathon: the only approved quote that names both the mechanic and the event type.
- **Compare & Connect** (Padmini Rudrapatna, no title in source) is placed second on purpose and rendered visually quieter, because it is the only approved sentence in the entire pool that answers this page's native objection: is a one-off worth repeating. "This was our second year with them and we will return back next year as well." It carries zero numbers, which is why it is text-only.

**What no approved proof exists for, and the page therefore does not claim.** There is no marathon-specific customer result anywhere in the corpus: no finisher count, no race-tier completion rate, no distance total from a customer program, no "X employees completed our virtual marathon". `04-proof-map.md:363` states it plainly as NOT FOUND IN SOURCES. The page's proof section is therefore adjacent evidence, honestly labelled, rather than direct evidence. A buyer who asks "show me a virtual marathon you ran" gets the demo call, not a card.

**No video quote.** The only approved video asset in the repo is Rachel Arthur of Brazosport ISD, who is not approved for a marathon claim, so both quotes are text-only and neither carries an avatar.

---

## 8. Meta title and meta description

**Title (54 characters), shipped:**
`Corporate Virtual Marathon for Employees | Vantage Fit`

Head term first, then the two buyer modifiers the live title lacks ("corporate", "employees"), ends `| Vantage Fit`, colon-free and em-dash-free. The live title is `Virtual Marathon - One Day, One Global Workforce | Vantage Fit` at 62 characters, graded over length. Its distinctive SERP line "One day, one global workforce" is preserved **in spirit in the hero sub-promise** ("Every region runs the same event on its own local clock") rather than in the title, where it costs too many characters. Alternate considered: `Virtual Marathon Challenge for Employees | Vantage Fit` (54, keeps "challenge" but loses "corporate", which is the stronger enterprise modifier).

**Description (143 characters), shipped:**
`Run a corporate virtual marathon where steps become distance, so every employee can finish by walking. One event, every time zone. Book a demo.`

It leads with the mechanism, states the benefit in the page's own words, and closes with the verb-led CTA. A stat variant was drafted and rejected: `Run a corporate virtual marathon where steps become distance. POSOCO reached 97% participation in a 2-week walkathon. Book a demo with Vantage Fit.` (146 characters). It is accurate and correctly labelled, but mixing "walkathon" into a "virtual marathon" description muddies SERP intent for the head term this page has to own.

**Other SEO decisions carried into the build.** URL stays `/virtual-marathon/` exactly; no redirect proposed. Hreflang alternates `/fr/marathon-virtuel/`, `/es/maraton-virtual/`, `/de/virtueller-marathon/` must keep resolving. The primary keyword appears in the title, the single H1, the meta description and the first 100 words. Three internal links close the loop: `/steps-challenge/` (the format the buyer already runs), the Team Challenge sibling (where scored teams actually live), and the Solutions hub. The hero secondary CTA finally links the gated guide `/guides/the-step-by-step-virtual-marathon-guide/`, which exists in the repo and which nothing on the site currently points at. FAQPage JSON-LD is emitted, which the live page does not have anywhere. `noindex, nofollow` stays on the mock.

---

## 9. Assumptions and open questions

### 9.1 The assumption everything else rests on

**The page is built on E-Marathon, not Marathon Event.** The live `/virtual-marathon/` page describes a tiered GPS race, which in the product is Marathon Event, and Marathon Event is "Request via account manager" (`challenges.md:72`; `admin-what-challenge-formats.md:84`). A self-serve marketing page cannot be built on an ops-only format without selling an engagement as a feature. So the page was rebuilt on the self-serve format, and Marathon Event is named once, on a deliberately quieter card, with its gate stated. **If the business intends `/virtual-marathon/` to sell the managed GPS race, this page is the wrong page and the pass must be re-run.** Everything from the H1 down assumes the opposite.

### 9.2 Things a human needs to confirm

1. **The certifications plaque image.** It is reused from the approved baseline for visual continuity, but the badges it depicts include ISO and GDPR marks with no product-KB support. The alt text was rewritten to assert nothing (`Vantage Fit security and compliance badges`) and the copy claims only SOC 2 Type II and "follows HIPAA guidelines". **Confirm with the security team before production.**
2. **Certificates on E-Marathon.** The format's own setup article has no certificate step and the production wizard step graph has none either, yet the generic wizard article and the code-verified admin spec both list certificates as shared setup. The page hedges it into FAQ 5 as "if your admin enabled them". **One product answer would settle whether it can be stated plainly.**
3. **The illustrative Score column.** The report mock shows scores of 964 / 928 / 907 beside step totals, deliberately not a constant multiple. Nothing on the page explains what produces a score on a single-task format, because no source describes E-Marathon scoring. The mock is tagged and the reconciliation sentence claims order-equivalence only for the **steps** column. **Confirm with product how score is computed on an E-Marathon before this mock is reused anywhere non-illustrative.**
4. **The nav mega sub-label for this page still reads "One-day events that unite a global workforce"**, which contradicts the four-week run book the page sells. The string is byte-identical across all seven sibling pages, so it was deliberately **not** patched here; changing it on one page would create exactly the drift the design-system audit checks for. **It needs a single edit in `05-design-system.md` §3.1 applied across all pages at once.**
5. **The gated guide's contents.** The hero's secondary CTA sends the buyer to `/guides/the-step-by-step-virtual-marathon-guide/`, and this brief recommends parking the 25-60% / 30-50% planning ranges behind that gate. **Confirm the guide is current and that it does not itself repeat the race-tier or distance-badge claims this rebuild removed.**
6. **Whether "Race to the Moon" is safe as a mock challenge name.** It is the help doc's own example (`admin-how-do-i-create-e-marathon.md:91`), which is why it was chosen, but it should be checked against any trademark or partner sensitivity before production.

### 9.3 Assumptions stated

- Sibling links in the related row point at local mock files so a reviewer can navigate the set; the mega banner does the same. All other links point at live URLs. Production hrefs for the related row are `https://www.vantagefit.io/steps-challenge/` and `https://www.vantagefit.io/team-challenges/`.
- All product-UI figures in the six mocks are interface fiction, not outcome claims. Every outcome claim on the page lives in S7 with a named source. The illustrative dataset was rebuilt so that every figure is derivable from one 1,000 steps = 1 km pace and no two mocks contradict each other.
- The five mock participant names were chosen to avoid reusing the `vc-data.js` roster, and the hero leaderboard casting (Facilities, Nursing, Finance, Customer support) is an argument, not decoration. Any future edit that reorders those departments removes the page's most efficient inclusion proof.
- The page ships several **page-scoped CSS overrides that are genuinely design-system-level problems**: `.btn-primary` and `.rm-export` gradient lightening to clear AA on white text, `nav.nav:not(.lit) .nav-cta` colour, `.eyebrow` and `.proof-hub .text-link` coral lift, `.logos-label` / `.logo-word` / `.trust-plaque .trust-support` contrast, the skip link, and the `@media (max-width: 860px) .nav-links.open` scroll fix that stops the mobile mega panel stranding the CTA below the fold. All of them still fail or are absent on the three sibling pages. **They need an owner decision in `enterprise.css`, not four copies.**
- `.mock-tag` remains at 9.28px, below the type floor applied elsewhere on the page. It was left alone deliberately because it is byte-identical across all four sibling pages and changing it here alone would create drift. It should be raised across the batch.
- The hero composition sits inside the shell at every width below 1340px and only takes the negative overhang above it, where the gutter can hold it. This is a departure from the shared hero pattern and is scoped to `.marathon-hero`.

---

## 10. Known gaps

Things no source in the corpus could answer, which are therefore absent from the page rather than guessed at.

1. **Tie-breaking on identical distance or score.** Nothing anywhere in the corpus describes a tie-break rule for this format. The page invents none. On a cumulative distance race with hundreds of participants, ties at the top are unlikely but ties in the middle are certain, and a buyer running prize tiers will ask.
2. **Any E-Marathon-specific setup timing.** The only sourced duration is the generic "Creating a challenge takes 5-10 minutes", which covers a wizard with task and team steps that E-Marathon skips. The page presents "about 10 minutes" as a ceiling and never claims a format-specific figure.
3. **How score is computed on a single-task format.** The admin leaderboard defaults to Score, and an E-Marathon has one implicit task with no thresholds. No document explains what the score is. The page shows a Score tab because the product has one, and never explains it.
4. **Whether teams can be enabled on an E-Marathon at all.** Not "no", but **not found**. One summary article loosely mentions "team-building around a shared distance goal" and one management article is conditional ("If your challenge supports team participation"), while the format's own setup article has no team step. The page treats this as unanswerable and routes the question to the Team Challenge page.
5. **Any distance figure for HR.** There is no distance leaderboard view, no distance column in the export, and no distance report. The page states the reconciliation instead, which is the honest workaround, but a buyer who wants "total company kilometres" as a reportable number is getting it from the employee-facing surface or from arithmetic, not from a report.
6. **What the E-Marathon does at the finish line.** There is no target-distance field, so there is no system concept of finishing. "Finish line" is a naming and communications device the docs themselves recommend, and the page uses it that way, but no source describes a completion state, a finisher list, or a DNF.
7. **Whether the Auto-Announce Winners on Social Feed toggle is real.** It appears in the production wizard's Setup step in the dashboard repo (`DASH/CRUD_FLOWS_AND_COMPONENTS.md:464`) and nowhere in the help corpus. It would materially improve S3 stage 5 if confirmed. It is off the page.
8. **Marathon Event's actual self-serve roadmap.** Moving it self-serve is on the Backlog (`challenges.md:216`). The page states today's truth, which will need an edit the day that ships.
9. **A US-recognisable marathon-shaped customer result.** The approved event-proof pool is India, the Gulf and Malaysia. There is no US named customer with a participation figure attached to a walkathon, step-a-thon or marathon. That gap goes to sales for the demo call, and it is the reason S7 carries no geography framing at all.
10. **What happens to an E-Marathon when a participant switches primary device mid-event.** One primary device at a time is documented and Garmin connections expire after 60 days, but no source describes what happens to accumulated distance at the switch. Buyers with large Fitbit populations will hit this.
