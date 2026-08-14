# Fitness & Exercise page brief

## Page job

Show an HR buyer how Vantage Fit counts workouts that are not represented by passive steps. The page must feel like the next layer of the Activity Tracking surface, not a standalone training app or a challenge-program pitch.

## Research takeaways

- Strength is logging, not programming. Bench Press, Squats, Deadlifts, Leg Press, and Rowing accept reps or minutes; Weight Training Session is the broader timed option.
- GPS is limited to Run, Walk, Cycle, and Wheelchair. It records distance, pace, duration, calories, splits, route, and pace graph on mobile.
- Running and walking pace validation rejects averages or splits faster than 3.5 min/km. Cycling has no pace cap. Android adds four vehicle-detection methods; iOS filters points with less than 100 m horizontal accuracy.
- Apple Health workout import requires an employee tap on iOS. Health Connect is the correct Android workout-import path. Duplicate workouts are blocked.
- Fitbit and Garmin connect directly. Garmin pushes updates but its connection expires after 60 days. Apple Watch feeds through Apple Health; Samsung Watch is supported as an Android device; 70+ apps can feed through Apple Health.
- This entire page is Full Mode only. A wearable is optional, and only one primary step source is active.

## Structure and visual direction

The hero layers the real GPS route product shot over Vantage Fit movement photography. A coral route line becomes the page's one visual signature and continues into a four-workout GPS strip. Dense, compact proof panels cover strength, sport breadth, GPS integrity, imports, and devices without turning each fact into an essay.

Page flow: beyond-steps hero, strength and sports logging, GPS proof and integrity, import rules, connected-device surface, Full Mode boundary, sibling links, demo CTA.

## Full copy deck

**Meta title:** Employee fitness tracking app and GPS workouts | Vantage Fit

**Meta description:** Count strength, sports, GPS workouts, squat tracking, and wearable imports in one employee fitness tracking app built for participation.

**Eyebrow:** Features · For employees

**H1:** An employee fitness tracking app for workouts beyond steps.

**Lead:** A run, a set of squats, and a game of badminton can all become valid participation. Employees log the workout that happened, with or without a wearable.

**Hero notes:** Full Mode · Four GPS workout types · One primary device

### Strength counts the way it happened.

Employees can record Bench Press, Squats, Deadlifts, Leg Press, and Rowing by reps or minutes. A general Weight Training Session captures the broader workout. Vantage Fit records the completed effort; it is not a sets, RPE, or progressive-overload programming app.

Sports and cardio use the same participation surface. A scannable library includes Badminton, Basketball, Boxing, Cricket, Dancing, Football, Tennis, Table Tennis, Martial Arts, Golf, Pickleball, Bowling, Kayaking, Rock Climbing, Zumba, Aerobics, HIIT, Spinning, Elliptical, and Plogging.

Squat Tracker uses the phone camera for pose detection and needs no equipment. Its count becomes another workout log.

### Four workouts get the route.

Run, Walk, Cycle, and Wheelchair can use mobile GPS tracking. Employees see live distance, pace, duration, calories, per-kilometre or per-mile splits, a route map, and a pace graph. They can optionally share a result. On iOS, Live Activity can keep the workout visible on the Dynamic Island or Lock Screen.

### GPS integrity, stated precisely.

On iOS, Vantage Fit filters GPS points with less than 100 m horizontal accuracy. Android checks speed patterns, location consistency, high-pace percentage, and split behaviour, with a 10 m minimum distance and 1 second minimum gap between points.

The backend rejects running or walking averages faster than 3.5 min/km, and every split must clear the same threshold. Cycling has no pace limit, so the page does not imply one.

### Import by choice. Prevent duplicates.

iOS employees tap to import a supported Apple Health workout; the import is not automatic. Android imports supported workouts through Health Connect. Existing workout IDs and matching sessions are checked to prevent the same workout from being added twice.

### Connect the device an employee already uses.

Fitbit and Garmin connect directly on iOS and Android. Garmin supports real-time push and must be reconnected after its 60-day token expires. Apple Watch feeds automatically through Apple Health. Samsung Watch works as an Android device. More than 70 trusted third-party apps, including Amazfit or Zepp, Mi Band, Huawei, Nike Run Club, and Strava, can feed through Apple Health.

Only one primary device supplies steps. Connecting Fitbit or Garmin replaces Apple Health or Google Fit as the step source, so totals do not stack. Device connection is employee self-service; HR sees aggregate connection statistics, not an individual's route.

### Full Mode boundary

Fitness and exercise tools are unavailable in Lite Mode, which is steps only. Preventing simultaneous activities and changing the Lite Mode setting require VC Support.

**Sibling links:** Start with activity tracking · Add nutrition and hydration · View all features

**Final CTA headline:** See how every workout becomes participation.

**Final CTA body:** Walk through strength logs, GPS routes, workout imports, and device connections in the employee app.

## Sources

- `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md`, Fitness & Exercise card
- `vfit-os/specs/01-core-tracking/activity-logging.md`
- `vfit-os/specs/10-integrations/fitbit-integration.md`
- `vfit-os/specs/10-integrations/garmin-integration.md`
- Help: `what-activities-can-i-track.md`, `how-do-i-track-a-gps-workout.md`, `how-do-i-import-workouts.md`, `do-i-need-a-wearable.md`, `ts-garmin-stopped-syncing.md`

## Critic result

**Pass.** Removed an early claim that workout imports were automatic because iOS requires a manual tap. Kept Health Connect only in the Android import context, made the absence of a cycling pace limit explicit, avoided strength-programming claims, and skipped all client figures because each assigned result still requires currency verification.
