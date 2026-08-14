# Fitness & Exercise — page brief

**URL:** `/features/fitness-exercise/`
**Mock:** `claude-fable/vantage-fit-fitness-exercise-v1.html`
**Angle:** beyond steps, dozens of ways to count a workout.
**Page type:** feature page. Proves a capability. Not a program outcome.

---

## 1. Research takeaways

Read: `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (facts lock), help docs for GPS workouts, workout import, squat tracker, devices and wearables, plus `vfit-os/specs/01-core-tracking/connected-devices-sync.md` and `specs/10-integrations/{garmin,fitbit}-integration.md`.

What actually differentiates this page:

1. **The GPS validation rules are the strongest thing on the page.** iOS discards points below 100 m horizontal accuracy. Android runs a four-method vehicle check (speed patterns, location consistency, share of high-pace samples, split analysis) with a 10 m distance and 1 s gap floor. The backend rejects a run or walk averaging faster than 3.5 min/km, and every split has to clear the same bar. Naming the rule beats saying "anti-cheat."
2. **The honest gap is part of the proof.** There is no cycling pace limit, because a real cyclist would trip a runner's threshold. Printing that is more persuasive to a skeptical buyer than an unqualified "all workouts are validated."
3. **Import is not automatic on iOS.** Apple Health surfaces the workout, a notification appears, and the employee taps Import. Android import runs through Health Connect, which is legitimate here because this is workout import, not the step pipeline. Only Running, Walking, Cycling and Wheelchair import. Duplicates are blocked.
4. **Strength is rep-based or minute-based**, not programming. Bench Press, Squats, Deadlifts, Leg Press, Rowing and a general Weight Training Session. `STRENGTH_ACTIVITY_ID = {20,21,22,23,45,46,47,48,49,50,51}` in the spec.
5. **Garmin tokens expire at 60 days.** That is a support ticket waiting to happen, so it belongs on the page rather than in a help article.

### Conflicts found and how they were resolved

| Conflict | Resolution |
|---|---|
| `how-do-i-use-squat-tracker.md` calls the squat tracker "AI-powered" throughout | Facts lock permits **camera pose-detection** and no more. Page says camera pose-detection, on-device, never AI. The same doc's genuinely useful fact, that the video is processed on the device and only the rep count and duration are saved, is on the page. |
| `how-do-i-track-a-gps-workout.md` describes pace validation generically, implying it covers every GPS type | Facts lock is explicit: **no cycling pace limit exists.** The page states the 3.5 min/km rule as running and walking only, and names the cycling gap. |
| `what-activities-can-i-track.md` says imports arrive with a notification, which reads as automatic | Same doc later says imports are never automatic. Page says the employee taps to import on iOS. |
| Garmin spec markets "real-time webhook vs competitors' polling" | Kept the mechanic (real-time push), dropped the competitor comparison. No invented benchmark. |
| OS spec still routes activity into "wellness score" | Org Wellness Score is retired. Not shown, not gated, not explained. |

### Gaps

- The **70+ trusted apps** figure comes from `specs/product/01-core-tracking/activity-tracking.md`. It is a count of the trusted-source list, so the page says "70+ trusted apps feed through Apple Health," never "70+ integrations."
- Trusted-source filtering is a company-level flag (`checkTrustedSources`), not always-on. The page does not claim it is universally enforced.
- All three customer figures ship with a visible **VERIFY** label.

## 2. Why this structure

Nine short sections, roughly 700 words of marketing copy. It answers the objections in the order a buyer raises them: *what else counts → how far does GPS go → can I trust a GPS number → what about the watch they already own → which devices → who has done it → what will break in month two.*

- **Hero** is composed differently from Activity tracking on purpose: a photograph is the dominant panel with the GPS workout summary overlapping it. Shared chrome, different hero, per the system-consistency rule.
- **The validation gate (S4)** is this page's signature and belongs to no sibling. Activity owns the step ledger; Fitness owns the GPS rules.
- **Import and the squat tracker (S5)** sit as a pair because both are "the phone or the watch did the work, not the app."
- **Devices (S6)** is a table, not prose. A device catalog written as body copy is exactly the help-center failure the last run shipped.
- Deliberately **not** here: the 65-type catalog and the step formula (Activity owns both, referenced in one line each), the 7-Minute Workout (Activity owns it), food and water (Nutrition owns them).

## 3. Copy deck

**Meta title:** Employee Fitness Tracking App | Vantage Fit
**Meta description:** Strength by reps or by minutes, GPS runs with per-km splits, and workouts imported from Fitbit, Garmin and Apple Watch. Every one counts the way a step does.
**Primary keyword:** employee fitness tracking app (H1, title)
**Secondary:** corporate workout tracking software (S2 opener), GPS workout tracking (S3), wearable integration (S6)

### S1 Hero
- Eyebrow: Features · For employees
- H1: An employee fitness tracking app **that counts more than steps.**
- Lead: Log a bench press by reps or by minutes. Track a run on GPS with per-km splits. Import the ride a Garmin already recorded. Each one lands on the same participation surface as a step.
- CTAs: Book a walkthrough · See the validation rules
- Hero note: Full Mode only · One primary device · No wearable required

### S2 Beyond steps
- Eyebrow: Breadth
- H2: Strength by reps, or by minutes.
- Lead: Corporate workout tracking software usually means cardio. Bench press, squats, deadlifts, leg press and rowing take a rep count or a duration, whichever the employee counted.
- Honesty line: This is logging, not programming. No sets, no RPE, no progressive overload plan.
- Chips: Badminton, Basketball, Boxing, Cricket, Dancing, Football, Tennis, Table tennis, Martial arts, Golf, Pickleball, Bowling, Kayaking, Rock climbing, Zumba, Aerobics, HIIT, Spinning, Elliptical, Plogging
- Cross-link: The full list of 65 types sits on activity tracking.

### S3 GPS workouts
- Eyebrow: Outdoor
- H2: Run, walk, cycle, wheelchair. Those four.
- Lead: GPS workout tracking is scoped on purpose. Live distance, pace, duration and calories while the workout runs, then a route map, a per-km split table and a pace graph when it stops.
- Two lines: On iPhone, a Live Activity keeps distance and pace in the Dynamic Island and on the lock screen. · Sharing to the social feed is optional, one workout at a time.
- Visual: a drawn "while it runs" panel with distance, pace, duration and calories, labelled **Illustrative values**. The hero already carries the real Workout Summary screenshot, so this section shows the other half of the story rather than reprinting the same image.

### S4 The validation gate
- Eyebrow: Anti-cheat
- H2: What gets a workout thrown out.
- Lead: A leaderboard is only worth running if a car ride cannot win it.
- Rules: iOS drops any point below 100 m horizontal accuracy before the route is drawn. · Android runs a four-method vehicle check across speed patterns, location consistency, the share of high-pace samples, and split analysis. Points need 10 m of distance and one second of gap. · The backend rejects a run or walk averaging faster than 3.5 min/km, and every split has to clear the same bar.
- Honest gap card: There is no pace limit on cycling. A real cyclist is faster than the running threshold, so applying it would throw out legitimate rides. We would rather say that than claim a check we do not run.

### S5 Import and the camera
- Panel A, Import a workout already recorded: On iPhone, Apple Health surfaces the workout and a notification appears. The employee taps Import. It is never automatic. · On Android, workout import runs through Health Connect. · Running, walking, cycling and wheelchair import with distance, duration, calories, route and splits. Duplicates are blocked.
- Panel B, Squat tracker: Camera pose-detection counts reps with no equipment. The camera feed is processed on the device and is never recorded. The only things saved are the rep count and the session length.

### S6 Devices
- Eyebrow: Connections
- H2: One primary device at a time.
- Lead: Connecting Fitbit or Garmin overrides Apple Health or Google Fit as the step source, so a wrist and a pocket never both count.
- Table: Fitbit, direct connection on iOS and Android. · Garmin, direct connection with real-time push, and the connection expires after 60 days. · Apple Watch, automatic through Apple Health with nothing to connect. · Samsung Watch, connected as the selected Android device. · 70+ trusted apps, Amazfit and Zepp, Mi Band, Huawei, Nike Run Club and Strava, feeding through Apple Health.
- Privacy line: Employees connect their own devices. Admins see how many people connected one, never what one person's device recorded.

### S7 Proof
- Tata Motors: 472 outdoor GPS workouts tracked. `[VERIFY]`
- Wipro: 12,236 squats counted. `[VERIFY]`
- Wipro: 163 yoga sessions logged. `[VERIFY]`

### S8 Tier gate and FAQ
- Gate bar: Everything on this page is Full Mode. Lite Mode is steps only, so none of it appears.
1. Does any of this need a wearable? No. GPS workouts, the squat tracker and strength logging all run on the phone. A wearable adds import and better step accuracy.
2. A Garmin stopped syncing after two months. Why? Garmin access tokens expire at 60 days. The employee reconnects from Settings, Device Management, and a manual sync backfills the last seven days.
3. Can someone import a swim from an Apple Watch? Not today. Import covers running, walking, cycling and wheelchair.

### S9 Closer
- H2: Watch a run become a leaderboard row.
- p: Thirty minutes on GPS tracking, device connections and the validation rules, against your own program.
- CTAs: Book a walkthrough · See activity tracking
- Checks: Full Mode feature set · Four GPS types · 100+ organizations

## 4. Sources

| Claim | Source |
|---|---|
| GPS types Run / Walk / Cycle / Wheelchair; live stats; splits; route map; pace graph; iOS Live Activity; optional share | `help/employee/health-tracking/how-do-i-track-a-gps-workout.md`; `activity-logging.md` `TRACKABLE_DISTANCE_ACTIVITY_ID = {26,27,28,58}` |
| iOS 100 m accuracy filter; Android four-method vehicle detection, 10 m / 1 s; 3.5 min/km backend reject per run and per split; no cycling limit | facts lock, GPS anti-cheat section |
| iOS import is a manual tap; Android import via Health Connect; four importable types; duplicates blocked | `help/employee/health-tracking/how-do-i-import-workouts.md` |
| Strength by reps or minutes; the named lifts | `activity-logging.md` §4.3 `STRENGTH_ACTIVITY_ID`; `what-activities-can-i-track.md` |
| Squat tracker is camera pose-detection, processed on device, only count and duration saved | `help/employee/health-tracking/how-do-i-use-squat-tracker.md` (its "AI" framing not used) |
| Fitbit and Garmin direct; Garmin real-time webhook push; 60-day token expiry; 7-day backfill on manual sync | `specs/10-integrations/garmin-integration.md`, `specs/01-core-tracking/connected-devices-sync.md` |
| Apple Watch automatic via Apple Health; Samsung Watch as the selected Android device; 70+ trusted apps | `help/employee/getting-started/do-i-need-a-wearable.md`; `specs/product/01-core-tracking/activity-tracking.md` |
| One primary device, no double-counting | `do-i-need-a-wearable.md`; facts lock shared physics |
| Full Mode only, Lite Mode is steps | `help/employee/getting-started/what-is-lite-mode.md` |
| Tata 472 GPS workouts; Wipro 12,236 squats; Wipro 163 yoga | `activity-logging.md` §7.3 — all three shipped with VERIFY |

## 5. Critic result

Run against the full critic list in `FEATURES-EMPLOYEE-LOGGING-PROMPT.md`. **Pass.**

Checked and clear: Health Connect appears only as the **Android workout import** path and never near steps, and the sentence names workout import explicitly. Squat tracking is camera pose-detection, never AI. No GPS anti-cheat claimed for cycling, and the gap is stated. iOS import is described as a manual tap. Nothing on this page is implied available in Lite Mode; the Full Mode gate is a labelled bar. No 65-type catalog, no step formula restated, no food or water, no rings. No Org Wellness Score. No HRA. No SOC 2 / ISO / GDPR / HIPAA claim. No 14 languages. No activity-level targeting. No mood. Camera heart rate is not on this page at all. Proof is Tata 472 and the two Wipro figures, all VERIFY-labelled, and Tata 6,400+ and the IBS figures stay on Activity. No em-dashes, no exclamation marks, no "Learn more", no banned filler. `../styles/enterprise.css` is linked and no token is redeclared.

Fixed during the pass:

1. First draft of S4 said "GPS workouts are validated against vehicle travel," which reads as covering cycling. Rewritten to name running and walking, with the cycling gap as its own card.
2. An early S6 draft listed devices as prose paragraphs. Converted to a five-row table so the catalog scans rather than reads.
3. The squat tracker section originally borrowed the help doc's "AI-powered" wording. Replaced with camera pose-detection, and the on-device processing fact was promoted since it is the part an HR buyer cares about.
4. The hero originally reused Activity tracking's stacked product-shot composition. Rebuilt as a photograph-led panel with the GPS Workout Summary beneath it, so the two pages share chrome without sharing a hero.
5. The GPS section originally repeated the hero's Workout Summary screenshot. Replaced with a drawn live-stats panel carrying an **Illustrative values** tag, so the page shows the workout running and the workout finished rather than the same image twice.
6. Both CDN composites sit on a wide white plate, which renders the phone UI too small at natural ratio. The image cards hold their own aspect ratio and the image covers them, trimming the plate rather than the interface.
