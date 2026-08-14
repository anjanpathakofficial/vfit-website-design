# Activity Tracking — page brief

**URL:** `/features/activity-tracking/`
**Mock:** `claude-fable/vantage-fit-activity-tracking-v1.html`
**Angle:** the logging surface everything else counts on.
**Page type:** feature page. Proves a capability. Not a program outcome.

---

## 1. Research takeaways

Read: `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (facts lock), `vantagefit-astro/content/en/help/employee/health-tracking/` (activities, rings, summary page, 7-Minute Workout), `.../getting-started/` (step syncing, wearables, Lite Mode, wheelchair), `vfit-os/specs/01-core-tracking/` (steps-tracking, activity-logging, active-minutes).

What actually differentiates this page:

1. **Total steps is an addition, not a reading.** `TOTAL_STEPS = device steps + manual steps (Activity ID 63) + active-minute-derived steps`. Two of the three inputs are company toggles. Naming the formula is more convincing to a skeptical HR buyer than "accurate tracking."
2. **100 steps = 1 active minute is hardcoded** (`services/ActiveMinutesServices.scala`, `steps / 100`). It is the `move_min` challenge task. WHO's 150 min/week is context, not a certification.
3. **65 activity types, IDs 1 to 65**, and the categories are real (Cardio & Fitness 1–23, Tracking & Wellness 24–35, Health & Advanced 36–60, App-Only 61–65). Help docs say "65+"; the spec says 65 exactly. The facts lock says use 65. Used 65.
4. **The honest integrity story is stronger than an anti-cheat claim.** Duplicate detection (95–105% of the prior day inside 18h, written for iOS 1.5.4–1.5.7), a 15-second sync floor, and one primary device are live. Step normalization exists in `StepsNormalizer.scala` and is **disabled for every company**. Saying so on the page is the credibility move.
5. **Rings are two, and Ring 2 is a company setting.** Ring 1 steps always; Ring 2 active calories (default 250) or active minutes, set via VC Support. Default steps target 10,000 with no challenge running; a live challenge task overrides it.

### Conflicts found and how they were resolved

| Conflict | Resolution |
|---|---|
| Help doc `what-activities-can-i-track.md` says "65+" and calls Squat Tracker "AI pose detection" | Facts lock wins. Page says **65**, and squat tracking is described as **camera pose-detection**, never AI. |
| OS `activity-logging.md` lists `WEB_DOABLE_ACTIVITY_ID = {24,30,31,55,63}` (water, weight, mood, sleep, manual steps) | Facts lock says water is **not** on web and mood is off these pages entirely. Page claims no web logging beyond challenges and leaderboards, matching `do-i-need-a-wearable.md`. |
| OS spec still routes activity into "wellness score" | Org Wellness Score is retired. Not shown, not gated, not explained. Participation is the north star on the page. |
| OS spec header says Android steps flow from a device source; help doc says Google Fit | Both agree it is **not** Health Connect. Page says "Google Fit, or the Android source selected in Device Management." Health Connect is not named anywhere on this page. |

### Gaps

- The 7-Minute Workout's **12-exercise** count comes from the facts lock; the help article describes the format (30s work / 10s rest, bundled demonstrations) without a count. Page states the format, not a disputed count.
- Both customer figures ship with a visible **VERIFY** label, per proof hygiene.

## 2. Why this structure

Nine short sections, image-forward, roughly 640 words of marketing copy. It follows the buyer's actual sequence of doubt: *what is it → is the number real → does it cover my workforce → what does the employee see → can I trust it → has anyone done it → what will cost me a support ticket → what will they ask me in week one.*

- **Hero** puts the product screenshot and a photograph in the first screen, and states the through-line in the lead.
- **The step ledger (S2)** is this page's signature and belongs to no sibling. It is the only place in Group A that prints the aggregation formula. Fitness and Nutrition inherit it with a one-line reference instead of restating it.
- **65 types (S3)** is a chip cloud, not a catalog paragraph. That is the fix for the failed run's help-center writing.
- **Integrity (S5)** is where the page earns trust by naming what is switched **off**.
- **Gates (S7)** is a three-column strip because Lite Mode and VC Support are the two things that turn into a support ticket after signature.

Deliberately **not** here: food and water (Nutrition owns those), the device catalog and GPS anti-cheat (Fitness owns those), KPI cards (the Admin Dashboard page owns those). No Org Wellness Score anywhere.

## 3. Copy deck

**Meta title:** Employee Activity Tracking Software | Vantage Fit
**Meta description:** Sixty-five activity types, three data sources and no wearable required. See how steps, active minutes and logged activities become one participation number.
**Primary keyword:** employee activity tracking software (H1, title, opener)
**Secondary:** corporate wellness activity tracking app (S3 opener)

### S1 Hero
- Eyebrow: Features · For employees
- H1: Employee activity tracking software **everything else counts on.**
- Lead: A phone in a pocket is enough to start. Steps sync on their own, every 100 of them convert to one active minute, and 65 activity types land on the same surface your challenges, leaderboards and participation rate read.
- CTAs: Book a walkthrough · See the step math
- Hero note: No wearable required · 65 activity types · Aggregate reporting for HR

### S2 The step ledger
- Eyebrow: How a step becomes a number
- H2: 100 steps. One active minute.
- Lead: Total steps is an addition, not a reading. Three inputs, one number, and a conversion rate that is hardcoded rather than tuned per account.
- Ledger rows: Device steps (Apple Health on iOS, Google Fit or the selected Android source, Fitbit or Garmin once connected) · Manual steps (Activity ID 63, off until the company turns it on) · Active-minute steps (logged activity time converted back to steps, company toggle) · **Total steps** feeds challenge tasks, leaderboards and the participation rate.
- Callout: 100 steps convert to one active minute. The rate is hardcoded, it drives the `move_min` challenge task, and WHO's 150 minutes a week is context rather than a certification.
- Source strip: Automatic device sync · Manual logging · Camera-based tracking (squat pose detection and a finger-on-camera pulse reading, awareness-level rather than medical-grade)

### S3 Sixty-five types
- Eyebrow: Coverage
- H2: Sixty-five activity types, and room for yours.
- Lead: A corporate wellness activity tracking app is only inclusive if the list reaches past running. Cardio, sports, strength, mind and body, health logging, and whatever your program adds itself.
- Chips: Running · Swimming · Yoga · Badminton · Deadlift · Rock climbing · Boxing · Gardening · Meditation · Pickleball · Wheelchair · Plogging · Kayaking · Snow shovelling · Journaling · Weight training
- Add-your-own card: Loggable activities. Add "Office Yoga" from Admin → Configuration → Activities and it sits beside Running in the employee's list. Self-serve.
- Habits card: Adherence activities. Daily check-ins like "Avoid Sugar" live in the Plus menu's More section, and challenge tasks can require them. Self-serve.
- Two one-liners: Wheelchair (ID 58) is a GPS-trackable type behind a settings toggle. · The 7-Minute Workout is a built-in interval routine with bundled demonstrations, and it logs itself when it ends.

### S4 Two rings
- Eyebrow: What the employee opens
- H2: Two rings. One is always steps.
- Lead: Ring 1 is steps, for everyone. Ring 2 shows active calories or active minutes, and which one appears is a company-wide setting rather than an employee preference.
- Bullets: Default targets are 10,000 steps and 250 active calories when no challenge is running. · A live challenge task overrides the ring target, so the ring and the leaderboard never disagree. · Tapping the rings opens the diary and the 7-day trends. Mindful-minute and sleep trends are Full Mode.
- Gate line: Switching Ring 2 to active minutes is a VC Support change, not a dashboard toggle.

### S5 Integrity
- Eyebrow: Data integrity
- H2: Honest numbers, not flattering ones.
- Lead: A challenge result only holds up if the step data underneath it does.
- Four items:
  - Duplicate pushes are dropped. A sync landing at 95 to 105 percent of the previous day inside 18 hours is ignored, a rule written for iOS 1.5.4 through 1.5.7.
  - Step sync is rate-limited to one push every 15 seconds.
  - One primary device at a time. Connecting Fitbit or Garmin replaces Apple Health or Google Fit as the step source, so nothing is counted twice.
  - Step capping exists in the code and is switched off for every company today. We would rather print that than imply a ceiling you do not have.

### S6 Proof
- Tata Motors: 6,400+ activities logged across the program. `[VERIFY]`
- IBS Software: 100+ employees clearing 5,000 steps a day in week one, 236 clearing 30,000 by week three. `[VERIFY]`
- Trust line: 100+ organizations run wellness on Vantage Fit.

### S7 Gates
- H2: What is self-serve, what needs a ticket.
- Self-serve: Custom loggable activities, adherence activities, activity reports.
- VC Support: The active-minutes ring, manual step entry, preventing overlapping activities, Lite Mode.
- Lite Mode: Steps only. One ring, Race challenges, and a Plus menu that offers Sync.

### S8 FAQ
1. Do employees have to buy a tracker? No. Steps come off the phone through Apple Health on iOS and Google Fit, or the selected device, on Android. A wearable improves step accuracy and adds data types the phone cannot see.
2. Someone joins in week two. Do they start at zero? No. Historical step data uploads day by day with the hourly breakdown intact, so a late joiner is scored on the days they actually walked.
3. Does any of this work in a browser? The rings, the trends and the logging surface are in the mobile app. The web app covers challenges and leaderboards.

### S9 Closer
- H2: See a week of logs turn into one number.
- p: Thirty minutes on the logging surface, the step math and the reports that read them, against your own headcount.
- CTAs: Book a walkthrough · See the dashboard
- Checks: No wearable required · 65 activity types · 100+ organizations

## 4. Sources

| Claim | Source |
|---|---|
| `TOTAL_STEPS = device + manual (ID 63) + active-minute steps` | `vfit-os/specs/01-core-tracking/steps-tracking.md` §3.1 |
| 100 steps = 1 active minute, hardcoded | `vfit-os/specs/01-core-tracking/active-minutes.md` §3.2 |
| 65 activity types, ID ranges, GPS set {26,27,28,58} | `vfit-os/specs/01-core-tracking/activity-logging.md` §3.1, §4.3 |
| Duplicate detection 95–105% / 18h / iOS 1.5.4–1.5.7 | `steps-tracking.md` §3.2 |
| Normalization disabled globally | `steps-tracking.md` §3.2, §6 |
| 15-second sync floor | `help/employee/getting-started/how-does-step-syncing-work.md` |
| Two rings, 10,000 / 250 defaults, company-configured Ring 2 | `help/employee/health-tracking/what-are-activity-rings.md` |
| Mindful-minute and sleep trends are Full Mode | `help/employee/health-tracking/how-do-i-read-my-dashboard.md` |
| One primary device, no wearable required | `help/employee/getting-started/do-i-need-a-wearable.md` |
| Lite Mode = steps only, one ring, Sync-only Plus menu | `help/employee/getting-started/what-is-lite-mode.md` |
| Wheelchair type, settings toggle, GPS-trackable | `help/employee/getting-started/what-is-wheelchair-mode.md` |
| Custom loggable + adherence activities | facts lock, `what-activities-can-i-track.md` |
| Tata 6,400+, IBS 100+ → 236 | `activity-logging.md` §7.3, `steps-tracking.md` §7.3 — both shipped with VERIFY |

## 5. Critic result

Run against the full critic list in `FEATURES-EMPLOYEE-LOGGING-PROMPT.md`. **Pass.**

Checked and clear: Health Connect is not named on this page at all, so it cannot be read as the Android step source. Squat tracking is camera pose-detection, never AI. Camera pulse is labelled awareness-level. No GPS anti-cheat, no device catalog, no food or water (owned by the siblings). No 47+. Capping is stated as disabled. No HRA. No Org Wellness Score, no composite score, no score report. No SOC 2 / ISO / GDPR / HIPAA claim. No 14 languages. No activity-level targeting. No mood. Proof is Tata 6,400+ and IBS only, both VERIFY-labelled, and neither Tata 472 nor the Wipro figures appear. No em-dashes, no exclamation marks, no "Learn more", no banned filler. `../styles/enterprise.css` is linked and no token is redeclared.

Fixed during the pass:

1. First hero draft used a photograph only. The 65-type product screenshot was moved into the hero so the first screen carries both a photo and the employee surface.
2. An early S3 draft listed all 65 types as body copy, which is help-center writing. Cut to 16 scannable chips plus a category line.
3. The FAQ originally answered "can employees log water on the web," which contradicts the facts lock. Replaced with the web-app scope answer that matches the help doc.
4. Section count went from 11 to 9 and copy from roughly 900 words to roughly 640 by folding the three data sources into the ledger section and the tier flags into a single strip.
