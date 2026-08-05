# Vantage Fit — Multi-activity Challenge Solutions Page Brief (v1)

Model workspace: `claude-fable` · Deliverable pair: this brief + `vantage-fit-multi-activity-challenge-v1.html` (1,766 lines)
Target URL (unchanged): `/multi-activity-challenges/` · Stylesheet: `../styles/enterprise.css`
Siblings in this system: `vantage-fit-steps-challenge-v1.html`, `vantage-fit-team-challenge-v1.html`, `vantage-fit-virtual-marathon-v1.html`, `vantage-fit-mental-health-wellbeing-v1.html`, hub at `../solutions-page/vantage-fit-solutions-v1.html`

> This brief documents **what shipped**, not what was planned. Where the built page diverges
> from the blueprint it was built against, the divergence is called out inline and the page wins.

---

## 1. What this page is

The Multi-activity Challenge is the format the admin dashboard calls a **Custom Challenge** and the
product spec calls a **Multi-Activity, Multi-Week Challenge**: one challenge object that carries a
named theme per week, a different task set inside each week, and up to 27 scoreable task types drawn
from movement, workouts, mind and body, nutrition, vitals and content. The buyer is a US enterprise
HR, CHRO or benefits leader who **already runs a step challenge** and cannot get the second two
thirds of the workforce into the participation number, plus the program manager at roughly 20 percent
capacity who would have to build the thing.

The one job the page does: **prove that a challenge with many ways to score still produces a number
leadership will believe.** Everything else is subordinate. The page does not argue that wellness
matters, does not sell step formats (that is `/steps-challenge/`), and does not sell team formation
(that is `/team-challenges/`). It sells custom multi-week task design, the enrollment mechanic that
removes the sign-up drive, the published scoring rules that stop the fittest ten people from owning
the leaderboard, and the per-task evidence HR walks out with. Primary CTA is **Book a demo** in four
places with an identical label. Secondary is **See pricing**. One mid-page in-page anchor
("See the 27 task types") and two supporting links.

---

## 2. Research takeaways

Audited: the live page and its source YAML `vantagefit-astro/content/en/pages/use-cases/multi-activity-challenges.yaml`;
help docs under `vantagefit-astro/content/en/help/admin/challenges/`, `.../admin/reports/`,
`.../admin/settings/`, `.../employee/challenges/`, `.../employee/getting-started/`;
product specs under `vc-os/vfit-os/specs/product/`; dashboard designs under `vc-dashboard-design/`.

### 2.1 The naming problem is real and the sources settle it

Three names exist for one object. The dashboard create option is **"Custom Challenge"**
(`help/admin/challenges/admin-how-do-i-create-a-challenge.md:21`; `vc-dashboard-design/crud-schema-spike/challenge.schema.js`,
`challengeType: 'custom'`). The code-verified spec calls it **"Multi-Activity, Multi-Week Challenge
(dashboard create option: 'Custom Challenge')"** (`specs/product/02-challenges-gamification/challenges.md:61`).
The URL and the four hreflang alternates rank on "multi-activity". The page keeps
"multi-activity challenge" in the H1, title, description and first 100 words, and anchors
"custom challenge" as the secondary term in the S3 `.format-note`, the S7 H2, the S9 H2 and FAQ 5.
No redirect proposed.

### 2.2 What the product actually has, under-sold or unsaid on the live page

1. **Nobody signs up, and that is the participation argument.** Enrollment is an audience rule or an
   admin add by search or bulk CSV. *"Employees do not self-join challenges... There is no
   browse-and-join flow"* (`specs/product/02-challenges-gamification/challenges.md:42`;
   `help/employee/challenges/how-do-i-join-a-challenge.md:17-38`). The **Enroll when active** mode
   enrolls a matching employee the moment they become active, which matters most on a four-week-plus
   program (`help/admin/challenges/admin-how-do-i-set-target-audience.md:60-68`). The live page never
   makes this argument, and its "let employees log preferred exercises" line actively implies the
   opposite.
2. **27 task types, with a configuration qualifier that must travel with the number.**
   `help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md:13` states the 27.
   Line 100 of the same file gives the gate: *"Lite Mode | Step Count only"* vs *"Full Mode | All 27
   task types."* The live page names three (walking, running, mindfulness). That is a 3-of-27
   undersell, not an overclaim.
3. **Friction asymmetry is documented with the conclusion already drawn.** *"Auto-tracked tasks have
   very high completion rates because they require no friction. Manual-log tasks require employee
   remembering and engagement. Mix accordingly"* (same file, `:112`). This is the retention argument:
   include at least one auto-tracked task and nobody's score is zero for showing up.
4. **The weekly theme is a first-class object, editable mid-flight.** Each week carries its own name,
   theme logo, theme colour and task set; the week count derives from the start and end dates; tasks
   drag to reorder (`admin-how-do-i-create-custom-challenge.md:47-78`). Themes can be added, updated
   or deleted mid-challenge for weeks that have not started (`admin-how-do-i-manage-challenge.md:37-48`).
   The doc's own arc is Move / Nourish / Rest / Thrive. Competitor pages in this category ship one
   flat activity menu for the whole campaign.
5. **The one hard fairness rule, agreed across three separate help docs.** Non-step tasks earn points
   up to 100 percent of target and going over earns nothing extra:
   *"if a task requires logging 3 yoga sessions this week and you log 5, you still only earn points
   for 3"* (`help/employee/getting-started/ts-leaderboard-score-wrong.md:62-64`; same rule at
   `admin-how-do-i-create-custom-challenge.md:94` and `help/employee/challenges/how-does-the-leaderboard-work.md:45-47`).
   The employee doc draws the equity conclusion itself. Nobody in this category publishes their
   scoring rule; that is the opening this page takes.
6. **Per-task, per-week score breakdown, exportable.** Click any participant for points per task,
   performance per week, and **completed / partially completed / missed** per task
   (`help/admin/reports/admin-how-do-i-view-leaderboard.md`). The leaderboard CSV carries **per-task
   score columns for Custom challenges**. The docs draw the loop: *"It shows exactly which tasks
   employees are completing and which they are skipping, invaluable for designing better future
   challenges"* (`help/admin/reports/admin-what-reports-are-available.md:92`). This is the sharpest
   unused line in the corpus and the only reporting output a step challenge cannot produce.
7. **Employer-authored task types.** Custom Loggable Activities and Adherence habits are created by
   the admin and scoreable inside the challenge; adherence habits stay visible in the employee's
   Plus menu whether or not a challenge is running
   (`admin-how-do-i-create-custom-activities.md:29-61`; `admin-how-do-i-create-adherence-activities.md:29-54`).
8. **Templates ship the design decisions.** Pre-built templates preset format, tasks, targets,
   scoring and weekly themes with *"best-practice defaults based on what works well across Vantage
   Fit clients"*, and shortening the duration trims the last week's configuration
   (`admin-how-do-i-use-templates.md:23,54`). The live page promises "pre planned weekly tasks" and
   never mentions the library exists.
9. **The public CAN / CANNOT privacy table.** `help/admin/settings/admin-data-privacy-security.md`
   enumerates exactly what an admin can and cannot see. On a challenge that asks for sleep, mood and
   vitals this is a sales asset, not a compliance footnote.

### 2.3 What the live page claims that sources do not support

| Live claim | Verdict, and what the rebuild did |
|---|---|
| Testimonial "Elsa Robertson, Senior Associate at Heidrick & Struggles, Australia" | **Fabricated title, still live.** The approved index records "Title: Not stated". This page does not use the quote at all. |
| Shared proof block "88% Participation rate" (IBS) | **Mislabelled.** 88% is IBS Software's **engagement** rate. The page says engagement, never participation, for every figure that was measured as engagement. |
| "let employees log preferred exercises" | Reads as employee self-selection. The loggable-activity library is admin-authored and there is no self-join. Reframed as "habits and activities you name yourself". |
| "Unified health progress tracking in a single dashboard" | Ambiguous between the employee app and the HR dashboard, sourced for neither as written. Dropped; replaced with the concrete employee week view and the concrete admin breakdown. |
| "Realtime leaderboard" | Slightly ahead of the docs, which say "within minutes of syncing" with 15 to 60 minute wearable delays. Also the same card shipped on three sibling pages. Dropped as a card; the leaderboard appears only where it earns its place. |
| No FAQ, no page-specific proof, no structured data | The page adds a five-question FAQ with FAQPage JSON-LD, and the richest per-dimension proof in the approved set. |

The live page's failure mode is under-claiming. `foundation/07-live-page-audit.md:186` concludes
*"No claim on this page contradicts the specs."* The two defects that do exist are proof-attribution
defects, not capability defects.

---

## 3. Why this structure

Eleven sections. The spine departs from the Steps consolidated flow in three deliberate places,
each explained below.

| # | Section | The belief it is built to create |
|---|---|---|
| S1 | Hero, light gradient | "This page is going to explain machinery, not adjectives." The two mocks carry the argument before a word of body copy: an admin week table on one side, an employee week view on the other where one task row fills itself and the next has a Log button. |
| S2 | Nobody signs up, `--canvas` | "Participation here does not depend on my comms team." Kills the burned buyer's scar in the first scroll and folds the friction argument into the same six rows. |
| S3 | 27 task types, `#fff` | "There genuinely are many ways to score, and most of them ask nothing of the employee." Carries the keyword payload and the C5 configuration qualifier. Page centrepiece. |
| S4 | Weekly themes, `--canvas` | "This does not go stale in week three, and a slow start is recoverable." Establishes the week as an object, not a date range. |
| S5 | Scoring integrity, dark card on white | "The enthusiast cannot run away with this, and an inflated log earns nothing." The objection band. |
| S6 | Security, full-bleed dark | "Legal will not kill this." Published boundary, not a promise. |
| S7 | Control for HR, `--canvas` | "One person at 20 percent capacity can build it, and I leave with a renewal slide." |
| S8 | Customer results, `#f6f7f4` | Verification, not persuasion. The reader already believes the machine. |
| S9 | FAQ, `#fff` | Removes the four rollout blockers that would otherwise become demo-call surprises. |
| S10 | Related, `--canvas` | Sends step-format and team-formation intent to the siblings that own them. |
| S11 | Closer, full-bleed dark | Converts on the two screens the page argued for: the task builder and the score breakdown. |

### 3.1 The three deliberate departures from the Steps flow

**Departure 1: privacy moves ahead of reporting (S6 before S7).** Steps runs proof, then trust, at the
end. This page puts the security band immediately before the HR reporting section. On a challenge
that asks employees to log sleep, mood and vitals, "here is what HR gets" reads as surveillance if
the reader has not first been told what HR can never see. Reversed, the same reporting section reads
as bounded. It is also the only way to obey "IT/security must not be an afterthought" literally
rather than decoratively.

**Departure 2: the explorer splits into two beats (S3 and S4).** Task families and the weekly theme
arc answer two different questions and need two different visuals. Merged, the theme rail becomes
decoration under a card grid. Split, S3 answers "what can I score" and S4 answers "why does it stay
interesting", and the four coloured tiles get to be an artifact rather than a garnish.

**Departure 3: proof goes last, and leads with counts rather than a headline percentage.** Steps opens
its proof block with four percentage tiles. This page opens with IBS Software's per-dimension counts
(236 / 130 / 118 / 98 / 95) because that evidence *shape* matches this page's claim. Every vendor in
the category publishes one engagement number. Publishing five per-activity counts from a single
challenge is the rare artifact, and by S8 the mechanism is already believed, so the counts read as
texture rather than as the load-bearing claim.

### 3.2 Beats deliberately cut

| Cut | Why |
|---|---|
| A problem or "familiar story" grid | The hero sub-promise names the failure mode in one sentence. A grid indicts a program the buyer chose and defends. |
| A week-0-to-after rollout calendar rail | It promises operator tooling for weeks 2 to 4 that does not exist (challenge reminder emails are off by default and AM-gated), and it pushes the keyword payload down a section on a URL whose entire equity is that keyword. |
| A standalone employee-experience section | Merged into S2. On this page enrollment and friction are one argument; separating them says the same thing twice. |
| A five-format explorer | That is `/steps-challenge/`. The audit names team-challenges and multi-activity as the worst cannibalization pair on the site. |
| A teams section | One clause maximum. Team scoring by average belongs to `/team-challenges/`, and it appears here only inside the S7 leaderboard line and the S10 related row. |
| Badges, certificates, integrations grid, video testimonial modal, blog band, a hero stat band, a mid-page off-page CTA banner | Each would either restate a sibling page or spend words on a mechanic that does not move this buyer. Certificates specifically are cut because the completion threshold that triggers them is undefined in every source. |

### 3.3 Design signature

Three different visuals describe the week structure and none of them repeats a form: the hero admin
mock draws it as a **table** (Week / Theme / Tasks, with a colour swatch and an `+ Add week` ghost
row), S4 draws it as four **colour-banded tiles** with task chips, and the S7 report mock draws it as
a slim **W1 W2 W3 W4 breadcrumb** inside an expanded participant row. The S5 audit board is the
page's rhetorical centre: a four-row score table in which the yoga row is visibly capped at 3 of 5
logged and tinted amber, because a rule working correctly should not be coloured like an error. All
six drawn mocks carry a visible **Illustrative data** tag and a `role="img"` with a descriptive
`aria-label` that ends "Figures shown are illustrative."

### 3.4 Divergences from the blueprint that shipped

Documented so review does not have to diff two documents.

| Blueprint said | Page ships | Why |
|---|---|---|
| S5 audit board set in Week 2 Nourish | Set in **Week 4 Thrive** (Step count, Squat tracker, Yoga capped, Bite-size content) | The yoga 5-of-3 example is the help doc's verbatim example and the strongest sourced line in S5. Moving the cap demo to water would have cost it. Relabelling the week instead resolved a real contradiction: the hero table, the S4 rail and the audit board now describe one consistent 13-task, four-week program. |
| Hero week counts 3 / 3 / 2 / 3 | **3 / 3 / 3 / 4**, with a `DAYS 28 · WEEKS 4 · TASKS 13` metric row added under the title | The rail chips and the audit board have to add up to the table. The metric row also lifted the dash's column fill from 70 percent to 90 percent, fixing a hero geometry problem. |
| S3 card 5 includes doctor visits under "Event-based, cannot be self-logged" | Doctor-visit log **moved to card 6** ("Complete it, or log it") | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:92` puts Doctor Visit under Habits and Specialized; the `:110` event-based table enumerates exactly Video Workout, Content Reading, Bite-Size Content, Lab Report Upload and Health Vitals. The tag was false. |
| S3 cards 3 and 4 tagged "Log it, one tap" | Card 3 "**Manual log, a tap or a short form**", card 4 "**Manual log, water is one tap**" | Water genuinely is a tap. Mood is a 5-point rating plus a reason category, sleep is bedtime and wake-time entry, and meal logging is a 7-step search-and-save flow (`help/employee/health-tracking/how-do-i-log-meals.md:14-31`). "One tap" was wrong on both. |
| S2 honesty line "Daily tasks do not backfill, so a missed day stays missed" | "**Most challenges reset daily tasks at midnight, so a missed check-in stays missed.**" | Hedged. The source states the behaviour for daily check-in and adherence tasks, not universally. |
| S7 Tab B item 1 "Three leaderboards in one challenge" | "**Score and Steps in every challenge, plus Team when you enable teams**", and the mock tab reads `Team · if enabled` | Teams are an optional toggle at creation. "Three leaderboards" implied all three always exist. |
| S6 reuses the baseline certifications plaque raster | Raster **deleted**, replaced with a typeset `.mark-strip` of three inline-SVG chips | The baseline raster carries ISO 27001, ISO 27701 and GDPR marks that have zero support anywhere in the knowledge base. This was the blocker finding in review. See §9. |
| FAQ 4 answer included "include at least one auto-tracked task so nobody's score is zero" | Replaced with the sourced maximum-participation mix: step count plus a water log plus a content task | The "at least one auto-tracked task" rule was our inference, not a shipped guidance string. The mix recipe is the doc's own. |
| Body copy budget 950 to 1,000 words | Roughly **1,700 words of prose** excluding the six mocks | Honest overshoot, and the sections responsible are the ones the blueprint itself specified at that length: five FAQ answers at 40 to 55 words each (~279), two HR tabs (~303), and the security band (~177). The budget was not achievable with the specified section list. Cards and steps did stay to one line each. |
| `.final-note` "Turn participation into progress." | Cut | Duplicated the footer's about line one screen away. |

---

## 4. The objection this program raises

**The native objection, verbatim in the buyer's words:**

> "Adding yoga to the list doesn't make my sedentary population open the app. And even if they do,
> they're typing in numbers nobody checks. I'm not putting self-reported meditation minutes in front
> of my CFO."

That is two objections wearing one coat, and answering them together collapses the answer. The page
splits them across two sections.

**Part A, will they log anything? Answered in S2, before the objection is raised.** The strongest
available answer is that nobody has to decide to take part. Enrollment is an audience rule or an
admin add; there is no browse-and-join catalogue
(`specs/product/02-challenges-gamification/challenges.md:42`). Rolling enrollment catches people who
arrive mid-program. Then the friction ladder, in the same six rows: step count, distance and calorie
count fill themselves; content tasks complete at a desk and cannot be faked open, because *"skipping
through a video won't register as done"* (`help/employee/challenges/how-do-i-complete-challenge-tasks.md:60`);
manual logs take seconds and employees set their own reminders. S3 then tags every task family with
how it scores, so the reader can see that three of the six families need no employee action at all.

**Part B, is the data junk? Answered in S5, as design rather than reassurance.** The page does not
claim verification, because no verification mechanism exists for manual wellbeing logs and there is
no approval queue. The honest and stronger answer is that the scoring design makes an inflated log
*worthless* rather than claiming to detect it:

- **Non-step tasks cap at 100 percent of target.** Log five yoga sessions against a target of three
  and you earn points for three. The audit board draws exactly this, amber-tinted, with the caption
  "Logged 5 of 3 yoga sessions. Points for 3, which is 100% of target."
- **Step count is one task among many, and the admin authors what it is worth.** A step-only performer
  earns one task's points while somebody logging across the week's set earns across all of them. The
  page always names who decides. It never says "the system balances it".
- **Late joiners score from their join date**, so adding people mid-challenge gifts nobody a head start.
- **Steps come only from recognized apps and devices**, unrecognized sources are rejected, implausible
  counts are filtered, one primary device counts at a time. Mechanisms named, no thresholds printed.
- And the line that makes the section credible rather than defensive, kept visible in the band's fine
  print: **"Wellbeing logs like water, yoga and meditation are self-reported. The design answer is
  that over-logging earns nothing, not that we check it."**

**What the page refuses to say here, and why it matters.** No numeric step cap and equally no
"no ceiling" or "unlimited" claim: the help docs contradict each other at 25,000 a day and the
code-verified spec says the mechanism is effectively off today. No cross-type normalisation,
weighting, handicapping or per-capita adjustment: none exists, and the only equaliser is the admin's
own point values. No tie-break rule: none is sourced for this format. No "verified logging",
"proof-backed" or "every activity verified" anywhere on the page.

**Three objections that belong to sibling pages and are deliberately not raised here:** uneven teams
and ringers (`/team-challenges/`, answered by team score = average), stigma around mental health
(`/mental-health-and-wellbeing-challenges/`), and whether a one-off event is worth the setup
(`/virtual-marathon/`). Raising them here would recreate the cannibalization the audit already flags.

---

## 5. Full copy deck

Every string on the page, in document order. `<em>` marks the coral-gradient span. Strings inside a
drawn mock are marked **[mock UI]** and are illustrative, not claims.

### Meta and nav

- **Title:** `Custom Multi-Activity Wellness Challenges | Vantage Fit`
- **Description:** `Run one multi-activity challenge across steps, sleep, nutrition, mindfulness and habits, with a new theme every week. Book a Vantage Fit demo.`
- **Skip link:** `Skip to main content`
- **Nav:** Solutions (current) · Features · Resources · Pricing · **Book a demo**
- **Solutions mega, Run a challenge column:** Steps Challenge / *Company-wide step goals in five formats* · Team Challenge / *Departments and squads, competing together* · **Multi-activity Challenge (current page)** / *Custom challenges across any mix of activities* · Mental Health & Wellbeing / *Mindfulness, mood and stress support at work* · Virtual Marathon / *One-day events that unite a global workforce*
- **Solutions mega, Programs & needs column:** Year-round Wellness Program · Wellness Rewards · Remote & Hybrid Teams · Global Workforces · Measure Program Impact
- **Mega banner:** `See every program on one page: the Solutions overview`

### S1 · Hero

- **Eyebrow:** `Solutions · Multi-activity Challenge`
- **H1:** `Multi-activity challenges give everyone a <em>way to win</em>, not just the walkers.`
- **Lead:** `A step challenge has one way to score, so the people your program exists for drop out in week one. This one runs 27 task types, with a new theme every week.`
- **Buttons:** `Book a demo` · `See pricing`
- **Hero notes:**
  1. `27 task types, availability depends on your configuration`
  2. `Auto-enrolled by an audience rule, including people who arrive mid-challenge`
  3. `Weeks come from your start and end dates, each with its own task set`
- **[mock UI] Admin dash:** `Admin · Challenges` / `March Reset` / `Illustrative data` / `DAYS 28 · WEEKS 4 · TASKS 13` / columns `Week · Theme · Tasks` / `Week 1 · Move · 3 tasks` / `Week 2 · Nourish · 3 tasks` / `Week 3 · Rest · 3 tasks` / `Week 4 · Thrive · 4 tasks` / `+ Add week`
- **[mock UI] Employee phone:** `Vantage Fit` / `Week 2` / `Nourish` / week selector `1 2 3 4` (2 active) / `Challenge progress 61%` / `Today's progress` / `Step count · 6,500 / 10,000 · Auto` / `Water log · 4 / 8 glasses · Log` / `Read: build a better lunch · In progress` / `Illustrative data`
- **Logo band:** `Trusted by 100+ organizations worldwide` · TATA MOTORS · WIPRO · IBS SOFTWARE · TEVA · GODREJ · TEXAS INSTRUMENTS · BRAZOSPORT ISD

### S2 · Enrollment

- **Eyebrow:** `Enrollment`
- **H2:** `Nobody signs up. That is the participation mechanic.`
- **Lead:** `Enrollment is a rule you write, not a campaign you run.`
- **Rows:**
  1. `An audience rule enrolls them.` / `All employees, or filtered by country, city, department, gender, age range or language. Everyone who matches is in.`
  2. `Or you add them by search or bulk CSV.` / `There is no browse-and-join catalog, so participation never depends on a sign-up drive.`
  3. `People who arrive late still get pulled in.` / `Choose enroll when active and a matching employee is enrolled the moment they become active in the app.`
  4. `Some tasks fill themselves.` / `Step count, distance and calorie count need nothing but a phone in a pocket.`
  5. `Content tasks complete at a desk.` / `Reaching the end is what counts, and skipping through a video will not register as done.`
  6. `Manual logs take seconds, and employees set their own reminders.` / `Water, mood and meals, each with its own time and repeat days.`
- **Fine print:** `Most challenges reset daily tasks at midnight, so a missed check-in stays missed.`
- **Anchor CTA:** `See the 27 task types →` (to `#tasks`)
- **Image alt:** `Vantage Fit employee app showing a challenge journey with weekly tasks and a leaderboard`

### S3 · Task families

- **Eyebrow:** `Task families`
- **H2:** `27 task types, in any combination, in the same week.`
- **Cards** (title / line / `How it scores` tag):
  1. `Movement and fitness` / `Step count, distance and calorie count.` / `Auto-tracked, no action needed`
  2. `Workouts and strength` / `Squat Tracker with camera pose detection, video workouts and logged sessions.` / `Complete it, or log it`
  3. `Mind and body` / `Meditation, mindfulness, yoga, sleep and a daily mood check-in.` / *fine print:* `Mood is never shown to admins.` / `Manual log, a tap or a short form`
  4. `Nutrition and hydration` / `Water log and meal logging, the two habits people can start on a Tuesday.` / `Manual log, water is one tap`
  5. `Health tracking and vitals` / `Lab report upload and health vitals, for a screening campaign.` / `Event-based, cannot be self-logged`
  6. `Content, learning and habits` / `Articles, bite-size content and book reading, a doctor-visit log, plus habits and activities you name yourself.` / `Complete it, or log it`
- **Note under the grid:** `27 task types in total. Availability depends on your company's configuration: Lite Mode runs Step Count only, Full Mode runs all 27. In the admin dashboard this format is called a Custom Challenge.`

### S4 · Weekly themes

- **Eyebrow:** `Weekly themes`
- **H2:** `A different way to win every week.`
- **[mock UI] Week rail:** `Week 1 · Move` → Step count · Distance · Desk stretches | `Week 2 · Nourish` → Step count · Water log · Read: build a better lunch | `Week 3 · Rest` → Sleep tracker · Meditation · Mood check-in | `Week 4 · Thrive` → Step count · Squat tracker · Yoga · Bite-size content · `+ Add theme` | tag `Illustrative data`
- **Lines:**
  1. `The number of weeks comes from your start and end dates.`
  2. `Each week carries its own name, theme logo, theme color and task set.`
  3. `You can add a theme mid-challenge, or update or delete one for a week that has not started.`
- **Closer:** `The leaderboard carries a weekly view alongside the overall standings, so a slow first week is not the whole season. That is what makes it read as a program rather than a points race.`

### S5 · Scoring integrity

- **Eyebrow:** `Scoring integrity`
- **H2:** `The scoring rules, published.`
- **Lead:** `Your fittest ten people cannot win this on steps alone, and an inflated log earns nothing. Here is exactly why.`
- **Rules:**
  1. `Non-step tasks cap at 100% of target.` / `Someone who logs five yoga sessions against a target of three earns points for three. Going over earns nothing extra.`
  2. `Step count is one task among many, and you set what it is worth.` / `Points per task are yours to author, so a step-only performer earns one task's points while somebody logging across the week's set earns across all of them.`
  3. `Late joiners score from their join date.` / `Add people mid-challenge without gifting anyone a head start.`
  4. `Steps come only from recognized apps and devices.` / `Unrecognized sources are rejected, implausible counts are filtered, and one primary device counts at a time.`
- **Fine print:** `Wellbeing logs like water, yoga and meditation are self-reported. The design answer is that over-logging earns nothing, not that we check it.`
- **[mock UI] Audit board:** `Score breakdown · Week 4 Thrive` / `Live` / columns `Task · Target · Logged · Points` / `Step count · 5,000 on 4 days · Auto · 40` / `Squat tracker · 30 a day · 30 · 30` / `Yoga [Capped at 3] · 3 sessions · 5 · 30` / `Bite-size content · finish the lesson · Done · 20` / caption `Logged 5 of 3 yoga sessions. Points for 3, which is 100% of target.` / `Illustrative data`

### S6 · Security

- **Eyebrow:** `Enterprise security & compliance`
- **H2:** `Employees see their own data. HR sees aggregate trends.`
- **Lead:** `This challenge asks people to log sleep, mood and vitals, so the boundary is published rather than promised. An employee can also hide from the leaderboard and still take part, and still earn points.`
- **Actions:** `Book a demo` · `Explore security & compliance →`
- **Cards:**
  1. `What an admin can see` / `Aggregate metrics, challenge participation status, leaderboard rankings, team scores, registration status, last active date and device type.`
  2. `What an admin cannot see` / `Weight, BMI and body measurements, health risk answers and risk categories, lab biomarker values, mood logs, the food diary and sleep patterns.`
  3. `A mood check-in scores without being seen` / `The score shows the check-in happened. The mood itself is never shown to admins or on leaderboards.`
  4. `Where the data sits` / `Vantage Fit follows HIPAA guidelines, is SOC 2 Type II, and offers secured regional data hosting in India, the US, the EU and the UAE.`
- **Mark strip:** `Follows HIPAA guidelines` · `SOC 2 Type II` · `Secured regional data hosting`
- **Support line:** `Security documentation is available during evaluation.`

### S7 · Control for HR

- **Eyebrow:** `Control for HR`
- **H2:** `Build the custom challenge. Leave with per-task evidence.`
- **Tabs:** `Build it` · `Prove it`

**Tab A, Build it**
1. `Start from a pre-built template.` / `Format, tasks, targets, scoring and weekly themes come preset with best-practice defaults, and shortening the duration trims the last week's configuration.`
2. `Add weeks and themes.` / `The week count comes from your dates. Each week takes a name, a theme logo and a theme color.`
3. `Add tasks per week.` / `Task type, target value, daily or weekly mode, and points. Drag to reorder.`
4. `Set the audience and publish.` / `All employees or a filtered group, and any filter makes the challenge private. It sits in Upcoming and moves to Ongoing on the start date.`
- **Note:** `Creating a challenge takes 5 to 10 minutes from the admin dashboard. Challenges are created on the dashboard, not on mobile.`
- **[mock UI] Task configuration modal:** `Add task` / `Week 2 · Nourish` / `Water log` / `Nutrition and hydration` / `Select target type` → `Daily` (on) · `Weekly` / `Target value 8` / `No of days this week 5` / `Points 10` / `Task summary` → `Log 8 glasses of water on at least 5 days this week for 10 points.` / `Remove task` · `Add task` / `Illustrative data`

**Tab B, Prove it**
1. `Score and Steps in every challenge, plus Team when you enable teams.` / `Score ranks by total points across every task and week, Steps ranks by step count alone, and the Team view ranks teams by average score.`
2. `Open any participant for the breakdown.` / `Points per task, performance per week, and whether each task was completed, partially completed or missed.`
3. `Filter by department, search by name, then export.` / `Filters apply before the export.`
4. `The Custom leaderboard CSV carries per-task score columns.` / `It also carries name and email, department and country, total score and rank, and total step count.`
- **Closer:** `You can see which tasks people are completing and which they are skipping, which is what makes the next challenge's mix evidence-based.`
- **Note:** `Exports are manual CSV downloads from the dashboard. There is no scheduled report delivery.`
- **[mock UI] Leaderboard:** `March Reset · Leaderboard` / tabs `Score` (on) · `Steps` · `Team · if enabled` / `Filter by department` · `Search by name` / columns `Rank · Participant · Score · Total step count` / `1 · A. Rivera, Operations · 340 · 214,480` / `2 · P. Sharma, Engineering · 295 · 186,120` (expanded) → `W1 W2 W3 W4` (W2 open) → `Step count 10,000 a day · 50 / 50 pts · Completed` / `Water log 8 glasses · 40 / 50 pts · Partially completed` / `Read: build a better lunch · 0 / 20 pts · Missed` / `Export CSV` / `Illustrative data`

### S8 · Customer results

- **Eyebrow:** `Customer results`
- **H2:** `Inside one program, people did far more than walk.`
- **Lead stat:** `88%` / `IBS Software's 28-day March to Fitness challenge reached 88% engagement, with 500+ active participants averaging 5,000+ steps a day.` / `IBS Software · March to Fitness · March 1–28, 2024`
- **Count strip, `Inside that one challenge`:**
  - `236` / `of 660 participants hit 30,000+ steps a week by week 3`
  - `130` / `monitored their daily mood`
  - `118` / `tracked heart health`
  - `98` / `did squats`
  - `95` / `engaged in mental wellness activities`
- **Result card 1:** `59%` / `engagement across Tata Motors' six-month Step & Stride Challenge, with 1,248 active participants, 7,275 activities logged and 7,200+ meals logged.` / `Tata Motors · Step & Stride Challenge · Automotive`
- **Result card 2:** `1,980` / `mindfulness minutes logged in the two-week Wipro Wellbeing Fest, alongside 1,409 litres of water and 8,870 squats, with 163 active users.` / `Wipro · Wipro Wellbeing Fest · April 7–20, 2025`
- **Quote 1:** `"The activities were engaging, catering to different fitness levels and interests."` — Shraddha Mishra, HR Generalist & Operations, Checkmarx
- **Quote 2:** `"We love the Vantage Fit app! The wide variety of wellness options kept our team interested week by week."` — International School of Kuala Lumpur (ISKL)
- **Fine print:** `Results from named customer programs, labeled the way each customer measured them. Outcomes vary by workforce and program design.` · `Read customer stories →`

### S9 · FAQ

- **Eyebrow:** `Common questions` · **H2:** `What HR asks before the first custom challenge.`

1. **`Do we have to stop our step challenge to run this?`**
   `No. There is no limit on how many challenges run at once, and a single walk counts toward every challenge whose tasks it matches. The common pattern is one always-on challenge plus short bursts. Stagger the end dates so each set of results lands on its own day.`
2. **`Is every task type available to us?`**
   `Availability depends on your company's configuration. Lite Mode runs Step Count only, so a multi-activity challenge needs Full Mode, where all 27 task types are available. A few task types are switched on by your account manager rather than self-serve.`
3. **`Do employees need a wearable?`**
   `No. Steps come from Apple Health on iOS and Google Fit on Android. Fitbit, Garmin and Samsung Watch take over when connected, and only one primary device counts at a time so nothing is double counted. A wearable is optional.`
4. **`Who designs the weekly task mix?`**
   `Start from a pre-built template with best-practice defaults, then adjust. The guidance the product ships with is to keep targets achievable, at a level 60 to 70 percent of participants can hit, and the mix it recommends for maximum participation is step count plus a water log plus a content task, because auto-tracked tasks complete without friction.`
5. **`What can we export at the end?`**
   `The leaderboard exports to CSV with per-task score columns for a custom challenge, plus name and email, department and country, total score and rank, and total step count. Employee, transaction and redemption reports export the same way. Exports are manual downloads, not scheduled deliveries.`

> All five are mirrored character for character in FAQPage JSON-LD at the end of `<body>`. The live
> template emits zero structured data across all four use-case pages, so this is a free SERP win.

### S10 · Related

- **Eyebrow:** `Keep exploring` · **H2:** `Where teams go next.`
- `Steps Challenge` / `One metric, five formats, when a single number is the whole point.`
- `Team Challenge` / `Score teams on the average of their members, not the total.`
- `All Vantage Fit solutions` / `Every program on one page, from one-day events to year-round calendars.`

### S11 · Closer

- **H2:** `See the task builder and the score breakdown.`
- **Body:** `A 30-minute demo. We will build a four-week challenge in the dashboard and open one participant's per-task breakdown.`
- **Buttons:** `Book a demo` · `See pricing`
- **Checks:** `Live product walkthrough` · `Built in the live dashboard` · `No obligation`

### Footer

- **About line:** `Inclusive wellness that turns participation into measurable progress.`
- **Product:** Challenge tasks (`#tasks`) · HR analytics · Security · Pricing
- **Solutions:** **Multi-activity challenges (current)** · Step challenges · Team challenges · Wellness program · Remote teams · Analytics
- **Company:** About · Customer results (`#proof`) · Case studies · Contact sales
- **Bottom:** `© 2026 Vantage Circle. All rights reserved.` · `HIPAA guidelines · SOC 2 Type II` · `Wellness built for participation.`

### Alt text and accessibility strings

| Asset | Alt / aria-label |
|---|---|
| Nav and footer logo | `Vantage Fit` |
| Hero admin mock | `Vantage Fit admin dashboard showing a four-week custom challenge with a theme and task count per week. Figures shown are illustrative.` |
| Hero phone mock | `Vantage Fit employee app showing week 2 of a multi-activity challenge, with an auto-tracked step task, a water log with a Log button, and an article task in progress. Figures shown are illustrative.` |
| S2 product screenshot | `Vantage Fit employee app showing a challenge journey with weekly tasks and a leaderboard` |
| S4 week rail | `Four weekly themes in a Vantage Fit multi-activity challenge, each with its own color and task set...` (full week contents enumerated) `Figures shown are illustrative.` |
| S5 audit board | `Vantage Fit score breakdown showing yoga logged five times against a target of three, scoring points for three. Figures shown are illustrative.` |
| S7 launch mock | `Vantage Fit task configuration screen setting a daily water log target of 8 glasses on 5 days for 10 points. Figures shown are illustrative.` |
| S7 report mock | `Vantage Fit admin leaderboard with a participant expanded to show per-task points and completed, partially completed and missed status. Figures shown are illustrative.` |

---

## 6. Claims ledger

Path shorthand: `HELP` = `vantagefit-astro/content/en/help`, `SPECS` = `vc-os/vfit-os/specs`,
`DASH` = `vc-dashboard-design`, `PROOF` = `foundation/04-proof-map.md`, `IDX` = `foundation/00-INDEX.md`.
Status: **SOURCED** (product truth), **APPROVED** (cleared customer proof), **ILLUSTRATIVE** (drawn mock, visibly labeled).

| # | Claim or figure as it appears | Source | Status |
|---|---|---|---|
| 1 | 27 task types, any combination, same week | `HELP/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md:13` | SOURCED |
| 2 | Availability depends on configuration; Lite Mode Step Count only, Full Mode all 27 | same file `:97-102`; ruling C5 | SOURCED |
| 3 | Dashboard calls this format a Custom Challenge | `HELP/admin/challenges/admin-how-do-i-create-a-challenge.md:21`; `SPECS/product/02-challenges-gamification/challenges.md:61` | SOURCED |
| 4 | Audience rule filters: country, city, department, gender, age range, language | `HELP/admin/challenges/admin-how-do-i-set-target-audience.md` | SOURCED |
| 5 | No browse-and-join catalog; admin adds by search or bulk CSV | `HELP/employee/challenges/how-do-i-join-a-challenge.md:17-38`; `SPECS/.../challenges.md:42`; ruling C1 | SOURCED |
| 6 | Enroll when active enrolls a matching employee when they become active | `HELP/admin/challenges/admin-how-do-i-set-target-audience.md:60-68` | SOURCED |
| 7 | Step count, distance and calorie count are auto-tracked, phone only | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:108` | SOURCED |
| 8 | Content tasks require reaching the end; skipping a video will not register | `HELP/employee/challenges/how-do-i-complete-challenge-tasks.md:60` | SOURCED |
| 9 | Employees set their own reminders for water, mood and meals, with time and repeat days | `HELP/employee/getting-started/how-do-i-set-reminders.md` | SOURCED |
| 10 | Daily check-in and adherence tasks do not backfill | `how-do-i-complete-challenge-tasks.md:104` | SOURCED (hedged on page to "most challenges") |
| 11 | Squat Tracker is camera pose detection | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:51` | SOURCED |
| 12 | Lab report upload and health vitals are event-based, cannot be self-logged | same file `:110` | SOURCED |
| 13 | Doctor-visit log sits with habits and specialized, not event-based | same file `:92` | SOURCED |
| 14 | Water log is a tap; meals, mood and sleep are a short form | `HELP/employee/health-tracking/how-do-i-log-meals.md:14-31`; mood and sleep entry docs | SOURCED |
| 15 | Custom loggable activities and adherence habits are admin-authored and scoreable | `admin-how-do-i-create-custom-activities.md:29-61`; `admin-how-do-i-create-adherence-activities.md:29-54` | SOURCED |
| 16 | Mood scores as a task; the mood itself is never shown to admins or on leaderboards | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:75`; ruling C18 | SOURCED |
| 17 | Week count derives from start and end dates | `admin-how-do-i-create-custom-challenge.md:56` | SOURCED |
| 18 | Each week has its own name, theme logo, theme color and task set | same file `:47-78` | SOURCED |
| 19 | Themes can be added, updated or deleted mid-challenge for weeks not yet started | `admin-how-do-i-manage-challenge.md:37-48` | SOURCED |
| 20 | Leaderboard carries a weekly view alongside overall standings | `HELP/employee/challenges/how-does-the-leaderboard-work.md:30-33` | SOURCED (page deliberately does not claim the weekly window aligns with challenge weeks) |
| 21 | Non-step tasks cap at 100% of target; over-logging earns nothing extra | `admin-how-do-i-create-custom-challenge.md:94`; `how-does-the-leaderboard-work.md:45-47`; `HELP/employee/getting-started/ts-leaderboard-score-wrong.md:62-64`; ruling C6 | SOURCED |
| 22 | Admin authors the point value of each task | `admin-how-do-i-create-custom-challenge.md:73,93` | SOURCED |
| 23 | Late joiners score from their join date | `admin-how-do-i-add-remove-participants.md:65-69`; `SPECS/.../challenges.md:49` | SOURCED |
| 24 | Steps only from recognized sources; unrecognized rejected; implausible filtered; one primary device | `HELP/employee/getting-started/how-does-step-syncing-work.md`; `can-i-connect-multiple-devices.md`; ruling C15 | SOURCED (mechanisms only, no thresholds) |
| 25 | Manual wellbeing logs are self-reported with no verification (stated as a limit) | absence of any verification mechanism across `HELP`; `IDX` §2a item 29 | SOURCED as a limitation |
| 26 | Admin CAN see: aggregate metrics, participation status, rankings, team scores, registration status, last active date, device type | `HELP/admin/settings/admin-data-privacy-security.md` | SOURCED |
| 27 | Admin CANNOT see: weight, BMI, body measurements, health risk answers and categories, lab biomarkers, mood logs, food diary, sleep patterns | same file | SOURCED |
| 28 | Leaderboard opt-out preserves participation and points | `HELP/employee/challenges/can-i-opt-out-of-leaderboard.md` | SOURCED |
| 29 | Follows HIPAA guidelines; SOC 2 Type II; secured regional data hosting in India, US, EU, UAE | `vfit-os sources/VFit-Marketing-Content-Compacted.md:161-162,284`; ruling C9 | SOURCED (these three strings only) |
| 30 | Templates preset format, tasks, targets, scoring and themes; shortening trims the last week | `admin-how-do-i-use-templates.md:23,54` | SOURCED |
| 31 | Task fields: task type, target value, daily or weekly mode, points; drag to reorder | `admin-how-do-i-create-custom-challenge.md:63-75` | SOURCED |
| 32 | Any audience filter makes the challenge private; Upcoming to Ongoing on the start date | same file `:120,139` | SOURCED |
| 33 | Creating a challenge takes 5 to 10 minutes from the admin dashboard | `admin-how-do-i-create-a-challenge.md:13` (verbatim); ruling C7 | SOURCED (scoped to the creation wizard only) |
| 34 | No challenge creation from mobile | `SPECS/.../challenges.md:200` | SOURCED |
| 35 | Score and Steps leaderboards always; Team when teams are enabled; team score = average | `HELP/admin/reports/admin-how-do-i-view-leaderboard.md`; `admin-how-do-i-create-custom-challenge.md:103-108`; ruling C2 | SOURCED |
| 36 | Per-user breakdown: points per task, per-week performance, completed / partially completed / missed | `admin-how-do-i-view-leaderboard.md` | SOURCED |
| 37 | Filters apply before export; Custom leaderboard CSV carries per-task score columns plus name and email, department and country, total score and rank, total step count | `admin-how-do-i-view-leaderboard.md`; `admin-what-reports-are-available.md:129-144` | SOURCED |
| 38 | Exports are manual downloads; no scheduled report delivery | `admin-what-reports-are-available.md`; `IDX` §2a item 30 | SOURCED as a limitation |
| 39 | No limit on parallel challenges; one activity counts toward every matching challenge; always-on plus short bursts | `admin-can-i-run-multiple-challenges-in-parallel.md:13,21,30` | SOURCED |
| 40 | Steps from Apple Health on iOS and Google Fit on Android; Fitbit, Garmin, Samsung Watch override; one primary device | `HELP/employee/getting-started/do-i-need-a-wearable.md`; `SPECS/product/10-integrations/device-integrations.md:22` | SOURCED |
| 41 | Targets that 60 to 70 percent of participants can hit | `admin-how-do-i-create-custom-challenge.md:154` | SOURCED |
| 42 | Maximum-participation mix: step count + water log + a content task | `admin-what-tasks-can-i-include-in-a-custom-challenge.md` (task-mix recipes) | SOURCED |
| 43 | Auto-tracked tasks complete without friction | same file `:112` | SOURCED |
| 44 | **88%** IBS Software engagement, 28-day March to Fitness, 500+ active participants, 5,000+ avg daily steps | `PROOF` §3 Rank 1 | APPROVED, mandatory sentence used verbatim |
| 45 | **236** of 660 hit 30,000+ steps a week by week 3 | `PROOF` §3 Rank 1 | APPROVED |
| 46 | **130** monitored their daily mood | `PROOF` §3 Rank 1 | APPROVED |
| 47 | **118** tracked heart health | `PROOF` §3 Rank 1 | APPROVED |
| 48 | **98** did squats | `PROOF` §3 Rank 1 | APPROVED |
| 49 | **95** engaged in mental wellness activities | `PROOF` §3 Rank 1 | APPROVED |
| 50 | **59%** Tata Motors engagement, six-month Step & Stride Challenge, 1,248 active participants, 7,275 activities logged, 7,200+ meals logged | `PROOF` §3 Rank 2 | APPROVED, unrounded, program named |
| 51 | **1,980** mindfulness minutes, Wipro Wellbeing Fest, 1,409 litres of water, 8,870 squats, 163 active users, April 7–20 2025 | `PROOF` §3 Rank 3 | APPROVED |
| 52 | Checkmarx quote, Shraddha Mishra attribution | `PROOF` §6 (TESTIMONIAL-INDEX) | APPROVED, verbatim |
| 53 | ISKL quote, organisation-only attribution | `PROOF` §6 | APPROVED, verbatim, no individual name in source |
| 54 | `Trusted by 100+ organizations worldwide` and the seven logo wordmarks | `vfit-os .claude/rules/data-accuracy.md:256-261` | APPROVED (only permitted scale claim; no "50+ countries" suffix) |
| 55 | Hero dash: `March Reset`, 28 days, 4 weeks, 13 tasks, week names and task counts | drawn mock | ILLUSTRATIVE, tagged |
| 56 | Hero phone: 61% progress, 6,500 / 10,000 steps, 4 / 8 glasses | drawn mock | ILLUSTRATIVE, tagged |
| 57 | S4 week rail: Move / Nourish / Rest / Thrive and their chips | drawn mock, arc drawn from `admin-how-do-i-create-custom-challenge.md:80-85` | ILLUSTRATIVE, tagged |
| 58 | S5 audit board: 40 / 30 / 30 / 20 points, yoga 5 logged against a target of 3 | drawn mock; the cap behaviour it demonstrates is claim #21 | ILLUSTRATIVE, tagged |
| 59 | S7 launch mock: water log, 8 glasses, 5 days, 10 points, rebuilt task summary sentence | drawn mock; field names from `DASH/CRUD_FLOWS_AND_COMPONENTS.md` task-configuration modal | ILLUSTRATIVE, tagged |
| 60 | S7 report mock: A. Rivera 340 / 214,480, P. Sharma 295 / 186,120, per-task chips | drawn mock | ILLUSTRATIVE, tagged |

**Pre-ship gate, run against the shipped file and passing:**

| Check | Result |
|---|---|
| Literal em-dash `—` | 2 hits, both inside `.quote-who` attribution lines (lines 1368, 1374). Zero in our own voice. |
| `&mdash;` / `&#8212;` | 0 |
| ISO 27001 · ISO 27701 · GDPR · "HIPAA compliant" | 0 each, including alt text and markup |
| Slack · Microsoft Teams · Health Connect · "any device" · "25,000" · "verified" · "sign up" · "Active Minutes" · "20+ task" | 0 each |
| `Illustrative data` tags | 6, matching the 6 drawn mocks |
| `<h1>` | 1 · `<em>` | 1 |
| "27 task types" occurrences | 7, each within one scroll of the configuration qualifier; the S3 note carries it in full |
| FAQPage JSON-LD | Present, all 5 answers character-identical to the visible text |

---

## 7. Proof decision

**This page carries a full customer-result section (S8).** `foundation/04-proof-map.md` §3 names
Multi-activity as the best-evidenced of the four program pages, and the approved set needs no padding.

**What is cited and why:**

- **IBS Software, "March to Fitness", 28 days, March 1 to 28 2024** carries the section as the lead
  block. It is the only artifact in the approved set that shows **one challenge producing counts
  across several different activity types**: 236 of 660 on steps, 130 on mood, 118 on heart health,
  98 on squats, 95 on mental wellness. That evidence shape is the page's claim made in data. The 88
  percent headline is present but subordinate to the counts, and the mandatory sentence is used
  verbatim.
- **Tata Motors, "Step & Stride Challenge"** proves the format holds over six months rather than a
  sprint, with 1,248 active participants and 7,275 activities logged. The card was trimmed from the
  approved eight-figure chain to four figures because the full chain read as a wall.
- **Wipro, "Wipro Wellbeing Fest", April 7 to 20 2025** leads with 1,980 mindfulness minutes rather
  than a step total, which is the non-step evidence this page needs and the framing the proof map
  prefers.
- **Two quotes, both about variety:** Checkmarx (Shraddha Mishra, named) and ISKL (organisation-only,
  because the source records no individual name). Both speak directly to "different fitness levels
  and interests" and "week by week", which is this page's argument in a customer's words.

**What is deliberately absent:**

- **The 70 percent industry benchmark and the "+17% above" clause.** Valid only inside the IBS
  sentence, and this page's framing is the counts, not the benchmark. One framing per page.
- **JF Petroleum (38% to 65%, 81%) and William Grant & Sons (49.3% / 45.1%, 2,600+ employees, 48
  locations).** These are the perfect inclusion and coverage proofs and they are **AMBER**: present
  in live case studies, absent from `data-accuracy.md` approved tables. The page runs its inclusion
  argument on mechanics instead of numbers. If a data owner clears either, S6 and the results grid
  are where they would land.
- **Any IBS count converted to a percentage.** The section headline claims breadth of behaviour inside
  one program, never a coverage percentage, and the layout does not invite the division.
- **Wipro's 3X, any stacked Wipro step total, the Heidrick & Struggles quote and its fabricated title,
  Serum Institute, Decision Foundry, Beroe, Allston Trading, Compare & Connect, Accenture, Hershey.**

Every figure uses its source's own metric word. "Engagement" is never rewritten as "participation".
59 percent is never rounded. "28-day" is never written as "30-day" or "month-long".

---

## 8. Meta title and meta description

**Meta title (55 characters, within the 50 to 60 window):**

```
Custom Multi-Activity Wellness Challenges | Vantage Fit
```

Carries both anchor terms in one string: the existing equity term ("multi-activity", which the slug
and all four translated slugs rank for) and the re-anchor term ("custom", which is the nav label and
the spec filename). Ends `| Vantage Fit` per convention. Title Case, matching site meta convention
while the H1 and all on-page headings stay sentence case. The live title
("Multi-Activity Challenges for Total Fitness | Vantage Fit") is a fitness-consumer frame that the
audit standard grades as high HR-buyer-lens drift.

Alternates considered and not used: `Multi-Activity Challenges for Employees | Vantage Fit` (53,
safer and narrower) and `Multi-Activity Challenges: Beyond Steps | Vantage Fit` (53, highest SERP
differentiation, weakest keyword coverage).

**Meta description (142 characters, within the 140 to 155 window):**

```
Run one multi-activity challenge across steps, sleep, nutrition, mindfulness and habits, with a new theme every week. Book a Vantage Fit demo.
```

Verb-led, contains the primary keyword, names five task families, ends on the CTA. Carries **no
naked stat**, which keeps it clear of the unattributed-stat rule, and **no naked "27"**, which keeps
it clear of the C5 configuration-qualifier requirement (the qualifier cannot travel into a meta
description). The live description is 85 characters, under the floor, and is reused verbatim as the
hero sub-headline on the live page.

**URL: `/multi-activity-challenges/`, unchanged.** No redirect proposed. Four hreflang alternates
depend on it: `/fr/defis-multi-activites/`, `/es/desafios-multi-actividades/`,
`/de/multi-aktivitats-herausforderungen/`. The exact phrase "multi-activity challenge" appears in
the eyebrow, the H1, the title, the description and the first 100 words. "Custom challenge" appears
as the secondary anchor in the S3 note, the S7 H2, the S9 H2 and FAQ 5.

---

## 9. Assumptions and open questions

**Assumptions made**

1. **This is a review mock, not production markup.** `<meta name="robots" content="noindex, nofollow">`
   is set. Sibling pages link to live URLs and the mega banner links to the local hub file so a
   reviewer can navigate the set. Production would restore real hrefs and drop the robots tag.
2. **All mock numbers are interface fiction.** March Reset, 28 days, 13 tasks, 61 percent progress,
   the two leaderboard participants, the 40 / 30 / 30 / 20 point split. Six visible `Illustrative
   data` tags and six aria-labels ending "Figures shown are illustrative." Every outcome claim lives
   in S8 with a named client and program.
3. **The wizard is drawn as fields, never as a numbered stepper.** The help doc describes nine steps;
   `DASH/crud-schema-spike/challenge.schema.js` renders five. Precedence puts help docs above
   dashboard designs for shipped behaviour, but asserting a step count in a visual would pick a side
   the sources do not settle. The launch mock draws one task-configuration modal instead.
4. **"Manual logs take seconds" is a judgement call, not a sourced phrase.** Water genuinely is a tap.
   Meal logging is a documented search-and-save flow. The wording is defensible but a demo will show
   a multi-step meal logger, so a reviewer may prefer to soften it further.
5. **The Move / Nourish / Rest / Thrive arc** is the help doc's own worked example, reused as
   illustrative theme names rather than as a shipped template name.

**Open questions for a human**

1. **The plaque fix is one page of five.** This page deletes the certifications raster and replaces it
   with a typeset strip carrying only the three approved strings. The identical raster, which shows
   ISO 27001, ISO 27701 and GDPR marks with zero knowledge-base support, **still ships on
   `vantage-fit-steps-challenge-v1.html` (line 936), `-team-challenge-` (1158), `-virtual-marathon-`
   (1412) and `-mental-health-wellbeing-` (1195).** The `.mark-strip` block here is copy-paste
   portable. Until it lands on those four, the system is visually inconsistent and the C9 exposure is
   still live elsewhere. **This is the highest-priority follow-up in this workspace.**
2. **Clear or kill the two amber proofs.** JF Petroleum's 38 percent to 65 percent multi-activity
   participation lift and William Grant & Sons' 49.3 percent women / 45.1 percent men across 2,600+
   employees in 48 locations are the two best inclusion proofs in existence for this page and both
   are uncleared. A data owner decision would materially strengthen S6 and S8.
3. **Confirm the compliance strings with the security team** before production. The page claims
   exactly "follows HIPAA guidelines", "SOC 2 Type II" and "secured regional data hosting" naming
   India, the US, the EU and the UAE, and nothing else.
4. **Confirm the "27" is current.** The number is stated in two places in the help corpus, but the
   Set A draft spec `SPECS/02-challenges-gamification/challenge-custom.md` still says "20+ task
   types". Ruling C5 resolves it to 27; a product owner should confirm the count has not moved again
   before this goes live, because it is the single most checkable number on the page.
5. **Prose length.** The page ships roughly 1,700 words of prose against a 950 to 1,000 word target.
   Cards and steps are all one line. If a further cut is wanted, the two HR tab checklists and the
   S6 lead are the only places with slack that does not cost a sourced claim.
6. **The hero phone clips 15 to 31 pixels at viewports between 1228 and 1290 pixels.** Verified
   identical on the approved Steps page at the same widths, so it is house behaviour from the shared
   `.hero-visual { margin-right: -28px }` rather than a regression here. Worth a system-level fix.
7. **Three undefined classes carry no styles:** `.tour-copy`, `.trust-copy`, `.count-strip`. Layout
   comes from the parent grid, so there is no visual effect. Pre-existing across the sibling pages,
   not introduced here.

---

## 10. Known gaps

Things no source in the corpus could answer, and which the page therefore does not claim.

| Gap | Status in sources |
|---|---|
| **How long a multi-week, multi-task build actually takes** | NOT FOUND. Only the generic *"Creating a challenge takes 5-10 minutes from the Admin Dashboard"* exists, and it covers all five formats. The page prints it scoped to the creation wizard and never stretches it to "launch a wellness program in minutes". |
| **Any step cap, in either direction** | Irreconcilable. Two help docs say 25,000 a day, one says "no ceiling", and code-verified `SPECS/product/01-core-tracking/activity-tracking.md:150` says step normalization is *"currently disabled... effectively off today"*. Ruling C6 closes it: no number and no unlimited claim. The page prints neither. |
| **Cross-type score normalisation** | Does not exist. Step-family tasks accumulate as raw totals while every other task type scores as a percentage of target capped at 100 percent per day. The admin's own point values are the only equaliser. The page says "you set what it is worth" and never "the system balances it". |
| **Tie-breaking for a Custom challenge** | NOT FOUND. A grep of the whole help corpus and both spec trees returns tie-break language only for the Streak format. The page prints no tie-break rule. |
| **Whether the leaderboard's weekly window aligns with your challenge weeks** | Unreconciled. Challenge weeks derive from the start and end dates; the leaderboard's weekly view is documented as resetting each Monday. Sources never connect them. The page states only that a weekly view exists alongside overall standings. |
| **Maximum weeks, maximum tasks per week, maximum duration, maximum participants** | NOT FOUND. Only minimums are documented (weeks min 1, tasks min 1, and *"each week must have at least one task"*). The page makes no ceiling claims and the FAQ does not invite the question. |
| **Whether a partially completed challenge earns a certificate** | NOT FOUND. Certificates go to *"participants who complete the challenge"* but the completion threshold is never defined anywhere. Certificates are cut from the page entirely rather than hedged. |
| **Any verification of manual wellbeing logs** | Does not exist. No approval queue UI, and the only line in the corpus is *"Your admin may review uploads before marking them as approved"*. Squat Tracker (camera pose detection) and content completion are the only integrity mechanisms available, and both are named. |
| **Segment-level in-challenge nudging** | NOT FOUND. The only self-serve nudge is a manual Send Notification to all participants of a challenge. Challenge reminder emails are off by default and require the account manager, including any timing change. The page makes no reminder-automation claim. |
| **A named "completion rate" report object** | NOT FOUND. Completion status exists only inside the per-user score breakdown as completed / partially completed / missed. The page shows exactly that and calls it nothing else. |
| **Department, team or location breakdown of workforce health risk** | Organisation-level only, and Org Wellness Score, Wellness Leagues and Health Insights are annual-client gated behind contract negotiation and shown locked otherwise. All four stay off the page. |
| **Slack or Microsoft Teams integration** | Zero spec coverage in either tree. The page says push notification and email, and names neither vendor. |
| **A standalone Activities management screen** | Contradicted. The help doc navigates to Configuration → Activities; `DASH/CRUD_FLOWS_AND_COMPONENTS.md:675` records that in production activities exist only inside the Custom challenge config. The page describes admin-authored activities as a capability and never draws a management screen. |
| **SSO, provisioning and data-region specifics for this format** | Out of scope of the foundation files. The page uses only the C9-approved compliance strings and does not build an SSO or HRIS section, unlike the Steps page. |

---

*Prepared for internal review. Every claim above traces to a path in §6. Nothing on the page was
invented, and where a source went silent the page went silent with it.*
