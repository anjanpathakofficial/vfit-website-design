# Fitness & Exercise

**URL:** `/features/fitness-exercise/`  
**Mock:** `vantage-fit-fitness-exercise-v1.html`  
**Angle:** Beyond steps. Dozens of ways to count a workout.

## Page job

Prove a workout is another log on the same participation surface: strength as rep or minute logging, GPS for four types only, honest anti-cheat, wearable import, squat pose-detection, one primary device. Full-Mode only. Not a programming app. Not a second Activity page.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See a GPS workout.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Strength (lock + help activities):** Bench Press, Squats, Deadlifts, Leg Press, Rowing, plus Weight Training Session. Rep-based or minute-based. Not sets / RPE / progressive overload.
- **Sports / cardio (lock):** Named a scannable set, not the 65 dump. Activity already owns the catalog.
- **GPS (lock + help GPS):** Run / Walk / Cycle / Wheelchair only. Live distance / pace / duration / calories, per-km or mile splits, route + pace graph, optional share, iOS Live Activity.
- **Anti-cheat (lock):** iOS filters points under 100 m horizontal accuracy. Android uses a 4-method vehicle-detection system. Min 10 m / 1 s gap. Backend rejects average pace under 3.5 min/km for running and walking, each split too. **No cycling pace limit.** Help GPS article is vaguer (“unrealistic pace,” “vehicle travel”). Page uses lock specifics.
- **Import (lock + help import):** iOS via Apple Health, **manual tap**, not automatic. Android via **Health Connect** (legitimate here). Duplicates auto-prevented. Help says no import is automatic on any platform. Page does not claim Android is silent.
- **Squat Tracker (lock):** Camera pose-detection, no equipment. Help says “AI-powered.” Page does not say AI.
- **Devices (lock + help devices / Garmin / OS Garmin):** Fitbit and Garmin direct (iOS + Android). Garmin real-time push, access tokens **expire at 60 days** (OS Garmin). Apple Watch automatic via Apple Health. Samsung Watch as an Android device. 70+ trusted third-party apps via Apple Health (Amazfit / Zepp, Mi Band, Huawei, Nike Run Club, Strava). One primary device. Fitbit / Garmin override Apple Health / Google Fit as the step source.
- **Tiers (lock):** Full-Mode only. Garmin / Fitbit are employee self-service. Prevent simultaneous activities and Lite Mode require VC Support. 7-Minute Workout stays on Activity; one-line cross-link only.
- **Proof (this page only):** Tata Motors **472 outdoor GPS workouts** (VERIFY). Wipro **12,236 squats** (VERIFY). Optional Wipro 163 yoga unused. Do not use Tata 6,400+ or IBS.

### Conflicts left unresolved (not silently fixed)

1. Help GPS anti-cheat is high-level. Lock is specific. Page uses lock. No cycling pace cap.
2. Help squat tracker: AI. Lock: pose-detection. Page does not say AI.
3. Help import: nothing imports automatically. Lock singles out iOS as a manual tap and names Health Connect for Android. Page states both facts; does not claim Android auto-imports.
4. OS / help still mention Wellness Score. Retired. Left off.

## Why this structure

Different hero and proof from Activity. No rings, no step formula, no 65-type reprint.

| Section | Job |
|---|---|
| Hero + gym photo + GPS chips | First screen: a workout, not a step ring. |
| Strength + sports | Rep or minute logging. Scannable sports set. |
| GPS + anti-cheat + route shot | Four types. Exact anti-cheat. No cycling pace cap. |
| Import | iOS tap vs Android Health Connect. |
| Devices + connections shot | Catalog lives here. One primary device. Garmin 60 days. |
| Squat + Full-Mode | Camera pose-detection. Lite Mode out. |
| Compact proof | Tata 472 GPS and Wipro squats only, VERIFY. |
| 3 FAQs + siblings | Rollout objections. Activity owns rings. Nutrition owns food. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** Same chrome as Activity / Admin Dashboard. `../styles/enterprise.css`. Features mega-menu locked IA. Current item: Fitness & exercise. Generated gym photograph in the model folder plus the two assigned CDN shots.

## Copy deck

**Title:** Employee fitness tracking app | Vantage Fit  
**Meta:** Log strength, sports, and GPS workouts on the same participation number as steps. Corporate workout tracking software with honest anti-cheat. Full-Mode.

**Eyebrow:** Features · For employees  
**H1:** Beyond steps. A workout still counts.  
**Lead:** Strength, sports, GPS, and a camera squat session land on the same participation number. No wearable required. Full-Mode only.  
**Hero notes:** Four GPS types · One primary device · 100+ organizations  
**CTAs:** Book a walkthrough · See a GPS workout

**H2:** Reps or minutes. Not a program.  
Bench Press, Squats, Deadlifts, Leg Press, Rowing, Weight Training Session.  
Sports / cardio named as a scan list.

**H2:** Run, walk, cycle, wheelchair.  
GPS only for those four. Live stats, splits, route, pace graph, optional share, iOS Live Activity.  
Anti-cheat: iOS accuracy filter, Android vehicle detection, 3.5 min/km floor for run and walk. No cycling pace cap.

**H2:** A tap to import. Not a silent sync.  
iOS: Apple Health, manual tap. Android: Health Connect. Duplicates blocked.

**H2:** One primary device.  
Fitbit and Garmin direct. Garmin tokens expire at 60 days. Apple Watch via Apple Health. Samsung as an Android device. 70+ apps via Apple Health.

**H2:** The camera counts the squat.  
Pose-detection. No equipment. Full-Mode. 7-Minute Workout lives on Activity tracking.

**Proof:** Tata Motors 472 outdoor GPS workouts `[VERIFY]`. Wipro 12,236 squats `[VERIFY]`.

**FAQ**  
1. Does GPS anti-cheat cap cycling pace?  
2. Do Apple Watch workouts import on their own?  
3. Can Lite Mode employees log a squat session?

**Close H2:** Same surface as steps. More ways to count.

## Sources

- `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` platform rules + page 2
- `vc-os/vfit-os/specs/01-core-tracking/activity-logging.md` (GPS types, strength IDs)
- `vc-os/vfit-os/specs/10-integrations/garmin-integration.md` (60-day access tokens)
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-track-a-gps-workout.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-import-workouts.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-use-squat-tracker.md`
- `vantagefit-astro/content/en/help/employee/getting-started/can-i-connect-multiple-devices.md`
- `vantagefit-astro/content/en/help/employee/getting-started/do-i-need-a-wearable.md`
- Case studies: `tata-motors-step-up-elevate.md` (472 outdoor workouts); `wipro-global-wellbeing.md` (12,236 squats)

## Assumptions

- Android import is via Health Connect and still requires the employee to accept the workout. Not described as automatic.
- “70+ trusted third-party apps” follows the lock. Named examples from the lock / help.
- Wipro 163 yoga omitted to keep the proof band on GPS and squats.
- Generated gym photo is brand photography, not a product UI.

## Critic

Run after the mock. Failures found in draft and fixed:

- Did not claim a cycling pace cap.
- Did not call iOS import automatic.
- Did not name Health Connect as the Android step source.
- Did not call squat tracker AI.
- Did not imply Lite Mode or a wearable requirement.
- Did not reprint Activity’s 65-type / rings / formula story.
- Tata 6,400+ and IBS not used.
- Org Wellness Score not shown.
- `../styles/enterprise.css` linked. Product shots + photograph present.

**Pass.** Marketing copy in `<main>` is ~685 words including labels (in the 450–750 band). `../styles/enterprise.css` linked. Images: GPS shot, devices shot, gym photograph. No cycling pace cap. iOS import is a tap. Squat tracker is pose-detection, not AI. Lite Mode gated. Tata 6,400+ unused.
