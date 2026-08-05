# Multi-Activity Challenge solutions page — research + decisions brief

_Page: Multi-activity Challenge · Live URL (context only): https://www.vantagefit.io/multi-activity-challenges/ · Mock: `vantage-fit-multi-activity-challenge-v1.html`_
_Author: Kimi K3 · Date: 2026-08-05_

## 1. What this page is

The buyer opens this page asking one question: "Can Vantage Fit run a wellness program that is bigger than a step count?" The answer, per product truth, is that the **Custom (multi-week, multi-activity) challenge** is the platform's flagship format — the help docs literally say "if you are not sure which challenge format to use, Custom is almost always the right choice." The page's job is to make that format legible and desirable to a US enterprise HR buyer: one scored program covering movement, nutrition, sleep, mind, and preventive care, with weekly themes, per-task points, and reporting HR can defend.

## 2. Research takeaways (product truth)

Sources: `vantagefit-astro/content/en/help/` (admin/challenges, employee/challenges, admin/settings), `vc-os/vfit-os/specs/02-challenges-gamification/challenge-custom.md`, case studies `intrado-healthy-me-campaign.md` and `wipro-global-wellbeing.md`.

**Capabilities the old marketing page under-sells or misses entirely:**

- **27 task types across 7 categories** (`admin-what-tasks-can-i-include-in-a-custom-challenge.md`, updated 2026-05-19). The old page says "walking, running, and mindfulness." The real list spans auto-tracked movement (steps, distance, calories, active minutes), workouts (strength, HIIT, yoga, camera-based squat counter), mind and body (meditation, mindfulness, book reading), nutrition (water, meal log), health vitals (sleep, heart rate, weight, HRA, **lab report upload with automatic biomarker extraction**), mental health (mood log, private to the employee), content and learning (video workouts, articles, bite-size content), and habits (smoking cessation, custom loggable activities, custom adherence check-ins, doctor visits). The old page mentions almost none of this.
- **Weekly themes are the retention mechanic.** Each week gets its own name, logo, and color (`admin-how-do-i-create-custom-challenge.md`). The help docs' own example (Move → Nourish → Rest → Thrive) reads like a curated program, not a points race. This is the single best answer to "challenges fade by week two," and the old page never mentions themes.
- **Honest friction model.** Tasks are auto-tracked, one-tap manual log, or event-based (watch to the end, upload the file). The help docs explicitly coach admins to mix low-friction and engaged tasks for adoption. This is a sophisticated, true differentiator competitors' marketing rarely admits to.
- **Balanced scoring is configurable.** HR sets points per task; non-step tasks cap at 100% of target (no grinding), steps cap at 25k/day by default; team scores average member effort. Directly answers "won't the same athletes win?"
- **Daily vs weekly target modes.** Daily mode ("hit 5,000 steps on 4 days this week") builds habits; weekly mode ("35,000 steps total") rewards sustained effort. Product-real nuance worth surfacing.
- **Template library.** Pre-built challenges ship with format, tasks, targets, scoring, and weekly themes pre-set (e.g. "4-Week Holistic Wellness", "Mindful March"). Kills the "blank page" objection.
- **Custom branded activities + adherence habits** at Configuration → Activities ("Walking meeting", "Took vitamins"). Companies can make the program theirs. Old page: nothing.
- **Rewards are per-task and real.** Points per completed task, credited in real time for single-event tasks, redeemable for gift cards with country-relevant catalogs, values set in USD and displayed in local currency.
- **Privacy story is unusually strong for this page.** This program touches sleep, mood, weight, HRA, and lab reports. Help doc `admin-data-privacy-security.md` is explicit: admins see aggregate metrics only and CANNOT see individual weight, HRA answers, mood logs, food diary, or sleep patterns; mood data is never shown to admins or leaderboards; leaderboard opt-out is built in; regions are isolated.
- **Approved proof exists.** Intrado "Healthy Me" (2021): a real 5-week multi-activity campaign (steps + meal log + yoga + meditation, custom challenge builder), 1,100+ participants, 63M+ steps, and +1.7% average step increase in the final two weeks — sustained momentum instead of drop-off. Wipro (2025): three connected challenges including hydration, mindfulness, and yoga components, participation grew 3X (163 → 550). Both are published case studies.

**Old page's weak spots (legacy YAML `multi-activity-challenges.yaml`):** generic bullets ("variety of fitness tasks"), no task inventory, no themes, no scoring logic, no privacy answers, a steps-only testimonial that actually undercuts the multi-activity pitch, and no HR workflow story.

## 3. Structure rationale (IA)

The Steps consolidated skeleton generalizes, but its §3 "formats explorer" does not fit: this page **is** one format. The explorer analog here is the **task-type / weekly-theme explorer**, which becomes the centerpiece. Flow:

1. **Hero** — the promise: one challenge for every kind of healthy. Visual: employee phone (a themed week with a mixed task list) + admin dash (per-task completion, not just a step leaderboard). Real-stat chips (Intrado, Wipro).
2. **Problem** — step-only challenges exclude most of the workforce and fragment wellness into silos. Four pain cards + pivot line. (Kimi "familiar story" pattern from the Steps bake-off.)
3. **Task explorer (centerpiece)** — 27 task types framed as "if it's healthy, it can earn points," grouped by friction (auto-tracked / one-tap / event-based), with a tabbed weekly-theme explorer (Move / Nourish / Rest / Thrive) showing exactly what a 4-week program looks like. Product-real, scannable, and it is the section the old page most needed.
4. **Follow-through mechanics** — why week three still works: balanced scoring (caps), daily vs weekly modes, recognition for non-winners (badges, branded certificates), real per-task rewards, leaderboard opt-out.
5. **For HR** — launch and run it: template library, the build wizard (themes, drag-and-drop tasks, points), custom branded activities, audience targeting, parallel challenges, localized days, CSV reporting. Admin dashboard mock with a "next action" nudge.
6. **Proof** — Intrado + Wipro, real and approved. Included because a genuine multi-activity story exists (per the brief's OPTIONAL rule).
7. **Trust (dark)** — privacy for a program that touches sleep, mood, and lab reports. What HR sees vs what HR never sees. This is a real buying objection for this program specifically, answered with product rules, not generic badges.
8. **FAQ** — five rollout objections (manual logging burden, fair scoring across activities, branding, privacy, launch time).
9. **Closer** — demo CTA with callouts.

Deliberately omitted: a data-integrity/anti-fraud section (that was a Steps-specific objection; manual-log tasks make fraud framing murkier here and the privacy objection is the stronger one for this page); a customer quote band (the old page's testimonial is steps-specific and off-message).

## 4. Copy deck (as shipped in the mock)

Voice rules followed: sentence case, no em-dashes, verb-led CTAs ("Book a demo", "See pricing"), HR is the reader, short one-line card copy, mock figures labeled illustrative, case-study figures real and sourced.

### Meta
- **Title (chosen):** `Multi-Activity Wellness Challenges | Vantage Fit` (44 chars)
- Alternates: `Multi-Activity Challenges: 27 Ways to Earn | Vantage Fit` · `Corporate Wellness Challenges Beyond Steps | Vantage Fit`
- **Description (chosen):** `One challenge that scores steps, sleep, hydration, meditation, and 23 more activities. Weekly themes, automatic tracking, real rewards, and reporting HR can defend.` (162 chars)
- Alternate: `Run a multi-activity challenge your whole workforce can join. 27 task types, weekly themes, per-task points, and privacy built in. Book a Vantage Fit demo.`

### S1 Hero
- Eyebrow: `Solutions · Multi-activity challenge`
- H1: `One challenge for every kind of healthy.` (em on "every kind of healthy")
- Lead: `Vantage Fit's multi-activity challenges score 27 activity types in a single program: steps and distance, sleep and meditation, hydration, nutrition, even lab reports. Weekly themes keep it fresh, and everyone competes on effort they can actually put in.`
- CTAs: `Book a demo` · `See pricing`
- Hero notes: `No wearable required` · `27 task types` · `Weekly themed programs`
- Visual: admin dash "Spring Wellness Challenge" (participation 84%, week 2 of 4; per-task completion bars: Steps synced 81%, Water 68%, Meal log 54%, Mindful minutes 47%) + phone showing "Week 2: Nourish" task list (steps auto-synced, water 6/8, article read complete, meditation pending) + chips: `1,100+ participants · Intrado Healthy Me` and `3X participation growth · Wipro`. Mock numbers carry an "illustrative" caption.
- Logo band: `Trusted by 100+ organizations in 50+ countries` + wordmarks (Tata Motors, Wipro, Accenture, Teva, Texas Instruments, Hershey, Brazosport ISD), consistent with the Steps page.

### S2 Problem — "The familiar story"
- H2: `Step-only challenges leave most of the company out.`
- Lead: `Walking is a great start. It is not a wellness program. When one metric is all there is, most employees watch from the sidelines and the rest tune out by week two.`
- Pain cards:
  1. `Not everyone is a walker` — `Cyclists, swimmers, lifters, and yogis get zero credit for the healthy things they already do.`
  2. `One metric gets old fast` — `The same daily step target for four straight weeks is why launch-week energy fades into silence.`
  3. `Wellness lives in silos` — `Steps in one app, mindfulness in another, screenings in a spreadsheet. Nothing adds up to one program.`
  4. `HR runs it all by hand` — `Five separate initiatives means five launches, five reminder campaigns, and five reports to stitch together.`
- Pivot: `A multi-activity challenge folds all of it into one scored program. One launch, one leaderboard, one report, and a task list with something for every employee.`

### S3 Task explorer — centerpiece
- Eyebrow: `One program, 27 task types`
- H2: `If it is healthy, it can earn points.`
- Lead: `Every task has a target and a point value you set. Movement syncs itself, daily habits take one tap, and content completes when it is watched or read. Mix low-friction and engaged tasks so the whole company can play.`
- Friction groups (three cards):
  - `Auto-tracked` — `Steps, distance, calories, active minutes sync from the phone or wearable employees already carry.` Tag: `No employee effort`
  - `One-tap habits` — `Water, meals, sleep, meditation, mood, and custom check-ins log in seconds.` Tag: `Seconds per day`
  - `Event-based` — `Video workouts, health articles, HRAs, and lab report uploads complete when done. Biomarkers extract automatically.` Tag: `Proof built in`
- Weekly theme explorer (tabs: Move / Nourish / Rest / Thrive; each panel lists 4 tasks with target + points, e.g. Week 1 Move: 7,500 steps/day auto · 5K distance your way · 150 active minutes/week · 20 squats with the camera counter). Note under explorer: `Each week gets its own name, colors, and logo, so month-long programs feel curated, not repetitive.`

### S4 Follow-through — "Designed for follow-through"
- H2: `Built so week three feels like week one.`
- Four numbered cards:
  1. `Balanced by design` — `You set points per task. Non-step tasks cap at the target, and steps cap daily, so no single task or top athlete runs away with it.`
  2. `Habits or totals, your call` — `Daily mode ("hit the target on 4 days this week") builds consistency. Weekly mode ("35,000 steps total") rewards sustained effort.`
  3. `Recognition beyond the podium` — `Automatic badges and branded completion certificates with your logo and signature give every finisher something to keep.`
  4. `Rewards worth earning` — `Points credit the moment a task completes and redeem for gift cards from country-relevant catalogs, shown in local currency.`
- Reassurance line: `Competition optional. Employees can opt out of the leaderboard and still earn every point and badge.`

### S5 For HR
- Eyebrow: `For HR & program managers`
- H2: `A month-long program, launched before lunch.`
- Lead: `Start from a template, make it yours, and point it at exactly the right audience. The dashboard carries the proof.`
- Checks (2x2):
  - `Templates, not blank pages` — `Pre-built programs like "4-Week Holistic Wellness" ship with themes, tasks, targets, and scoring set. Pick dates and go.`
  - `Make it yours` — `Weekly theme names, logos, and colors, plus company-branded activities like "Walking meeting" or "Took vitamins" check-ins.`
  - `Aim it anywhere` — `Target by department, country, language, or age. Run as many challenges in parallel as you like; days localize to every time zone.`
  - `Report like you meant it` — `Live participation per task, leaderboard exports, and a full points ledger, all downloadable as CSV.`
- Visual: admin dashboard mock (template library + active challenge overview with per-task participation and a "next action" nudge). Figures labeled illustrative.

### S6 Proof
- Eyebrow: `Results`
- H2: `Holistic programs, measurable momentum.`
- Lead: `Named outcomes from multi-activity campaigns run on Vantage Fit.`
- Stat cards (all real, sourced):
  - `1,100+` — Intrado (Technology · Nebraska) — `employees joined the 5-week "Healthy Me" campaign spanning steps, meal logging, yoga, and meditation.`
  - `63M+` — Intrado — `steps logged collectively, with a 1.7% rise in average steps in the final two weeks. Momentum, not drop-off.`
  - `3X` — Wipro (IT services · 30+ countries) — `participation growth across three connected 2025 challenges, from 163 to 550 active users.`
  - `46.5M` — Wipro — `cumulative steps across a program that mixed steps, hydration, mindfulness, and yoga.`
- Links: `Read the customer stories →` · `Get results like these →`
- Note: `Results from published Vantage Fit customer case studies.`

### S7 Trust (dark)
- Eyebrow: `Enterprise trust`
- H2: `Wellness data this personal comes with rules.`
- Lead: `A multi-activity program touches sleep, mood, weight, and lab results. So the line between what HR sees and what stays private is drawn by the product, not by policy promises.`
- Four cards:
  1. `What HR sees` — `Participation, task completion, leaderboard positions, and aggregate, company or department-level trends.`
  2. `What HR never sees` — `Individual weight, mood logs, food diaries, sleep patterns, HRA answers, or lab reports.`
  3. `Private by choice` — `Leaderboard opt-out is built in, and mood data is never shown to admins or rankings.`
  4. `Compliance & residency` — `HIPAA-aligned and GDPR compliant, with employee data isolated in its assigned region.`

### S8 FAQ — "Questions before rollout"
1. `Do employees have to log everything by hand?` — No. Steps, distance, calories, and active minutes sync automatically from phones and wearables. Daily habits like water or meditation are one tap, and content tasks complete themselves when watched or read. Manual step entry exists only as a fallback if your company enables it.
2. `Can different activities really share one leaderboard?` — Yes. Each task is worth points you set, non-step tasks cap at 100% of target, and steps cap daily. Team scores average member effort, so a few power walkers cannot carry a squad.
3. `Can we brand the program and add our own activities?` — Yes. Name and theme every week with your own logos and colors, create custom activities like "Office stretch break," add daily adherence check-ins, and issue completion certificates with your logo and signature.
4. `What about privacy when sleep and mood are involved?` — Admins see participation and aggregate trends only. Individual mood logs, sleep patterns, weight, HRA answers, and lab reports are never visible to HR, and employees can opt out of leaderboards entirely.
5. `How long does it take to launch?` — Template programs carry themes, tasks, targets, and scoring, so most teams launch in days. Set dates, pick your audience, publish.

### S9 Closer
- H2: `See the program your whole workforce can actually join.`
- Sub: `Book a 30-minute walkthrough. We will sketch a themed multi-activity challenge for your workforce and show you the reporting behind it.`
- CTAs: `Book a demo` · `See pricing`
- Checks: `27 task types` · `Launch in days` · `No wearable required` · `Privacy built in`
- Final note: `One program. Every kind of healthy.`

## 5. Sources for stats and quotes

| Claim | Source |
|---|---|
| 27 task types, categories, friction model, Lite/Full mode | help: `admin-what-tasks-can-i-include-in-a-custom-challenge.md` (2026-05-19) |
| Weekly themes (name, logo, color), daily/weekly modes, score caps, team average scoring, certificates, audience filters | help: `admin-how-do-i-create-custom-challenge.md` (2026-05-12) |
| Template library ("4-Week Holistic Wellness", "Mindful March"), best-practice defaults | help: `admin-how-do-i-use-templates.md` |
| Custom activities & adherence habits (Configuration → Activities) | help: `admin-how-do-i-create-custom-activities.md`, `admin-how-do-i-create-adherence-activities.md` |
| Points per task, real-time crediting, USD config → local currency display, gift-card redemption | help: `admin-how-wellness-rewards-work.md` |
| Time-zone-localized start/end/daily reset; parallel challenges | help: `admin-can-i-run-challenges-across-time-zones.md`, `admin-what-challenge-formats.md` |
| Leaderboard opt-out | help: `employee/challenges/can-i-opt-out-of-leaderboard.md` |
| Admin visibility limits (aggregate only; no individual weight, mood, food diary, sleep, HRA, lab reports); regional isolation | help: `admin/settings/admin-data-privacy-security.md` |
| Mood data never shown to admins/leaderboards | help: `admin-what-tasks-can-i-include-in-a-custom-challenge.md` |
| Intrado: 1,100+ participants, 63M+ steps, 5-week holistic campaign (meal log, yoga, meditation, custom builder), +1.7% step growth in final two weeks | case study: `intrado-healthy-me-campaign.md` |
| Wipro: 3X participation (163 → 550), 46.53M cumulative steps, 30+ countries, three connected challenges incl. hydration/mindfulness/yoga | case study: `wipro-global-wellbeing.md` |
| "Custom is the go-to format for most clients" positioning | help: `admin-what-challenge-formats.md` + OS spec `challenge-custom.md` |

All dashboard/phone mock figures are fictional and labeled illustrative on-page. No invented customers or quotes.

## 6. Assumptions and gaps

- **Assumed** the "100+ organizations in 50+ countries" trust line and customer wordmark set from the Steps consolidated/prior Kimi page remain approved; reused unchanged for cross-page consistency.
- **Assumed** HIPAA-alignment + GDPR only in trust copy, per the Steps consolidated guardrails (did not repeat the older page's broader SOC 2/ISO claims).
- **Assumed** gift-card catalog phrasing "country-relevant catalogs, shown in local currency" (grounded in the rewards help doc) instead of the older "190+ countries" line, since the doc does not state a country count.
- **Gap:** no public pricing or packaging info on what unlocks Full Mode (all 27 task types) vs Lite Mode (steps only). The page deliberately avoids plan-gating language; flagged for PMM to place correctly later.
- **Gap:** the 27-type task list varies per company contract (help doc: "the exact list depends on your company's configuration"; OS spec shows company-gated tasks). Page says "27 task types" without enumerating all; the explorer shows a representative, grounded subset.
- **Gap:** no approved customer story yet that isolates non-step task completion rates (e.g. meditation or hydration adherence). If one appears, it belongs in S6.
- **Gap:** active minutes requires an account-manager feature flag; the page lists it among auto-tracked tasks without the caveat to keep copy lean. Acceptable for marketing, noted here.
