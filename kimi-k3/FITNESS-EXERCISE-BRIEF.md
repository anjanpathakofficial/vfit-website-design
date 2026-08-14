# Fitness & Exercise — page brief

Intended URL: `/features/fitness-exercise/` · Mock: `vantage-fit-fitness-exercise-v1.html`

## Research takeaways

- Facts lock is the authority; help confirmed GPS flow (`how-do-i-track-a-gps-workout.md`): Run / Walk / Cycle / Wheelchair only, live stats, per-km splits, route map, iOS Live Activity (16.1+).
- Anti-cheat is precise and asymmetric: iOS 100 m accuracy filter, Android 4-method vehicle detection, backend 3.5 min/km floor for run/walk including every split, and **no cycling pace cap**. The page states the no-cap openly as a trust beat.
- Import honesty: iOS workout import is a manual tap in Apple Health; Android import runs through Health Connect (legitimate here, never named as a step source). Garmin tokens expire at 60 days.
- Strength is rep- or minute-logging, explicitly not programming. Squat Tracker is camera pose-detection; nothing on this page is called AI.
- Full-Mode only; Lite Mode is steps. Device connections are employee self-service; admins see aggregate connection stats.

## Why this structure

Hero pairs the GPS route product shot with a running photo to anchor "beyond steps." Then: strength plus the sports catalog as one-line chips (breadth without a dump), GPS with the anti-cheat panel (the page's sharpest proof), devices and import rules beside the connected-devices shot, then proof band (Tata 472 GPS, Wipro squats and yoga, all VERIFY) with tier flags, FAQ for rollout objections. Logging physics (step stack, one-primary-device) is referenced in one line, not re-derived; Activity Tracking owns it.

## Copy deck (as shipped)

- H1: "Beyond steps. Dozens of ways to count a workout."
- Lead: employee fitness tracking app, workouts land on the same surface as steps.
- Sections: "Strength is a log, not a coach." / "GPS workouts, honestly paced." / "The watch they already own works." / proof band "Proven in the field." / FAQ / final "Count every workout, not just steps."
- Full copy is in the HTML; marketing copy is ~600 words outside nav, footer, and mock labels.

## Sources

- Strength modes, sports list, GPS scope and anti-cheat numbers, import mechanics, device list, Garmin 60-day expiry, one-primary-device, Lite Mode gate: `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (Fitness card, shared logging physics).
- GPS workout flow and Live Activity: help doc `content/en/help/employee/health-tracking/how-do-i-track-a-gps-workout.md`.
- Proof: Tata Motors 472 outdoor GPS workouts, Wipro 12,236 squats, Wipro 163 yoga sessions, all from the facts lock, all labeled `[VERIFY WITH PRODUCT]` on the page.
- "100+ organizations" aggregate trust signal (approved).

## Meta drafts

- Title: `Employee fitness tracking app | Vantage Fit`
- Description: `Vantage Fit's employee fitness tracking app logs strength, sports, GPS runs, and wearable workouts onto one participation surface. Fitbit, Garmin, Apple Watch, Samsung.`

## Critic result

Pass. Checked: no cycling pace cap claimed, iOS import described as manual tap, Health Connect only for Android workout import, squat tracker as pose detection not AI, no Lite Mode availability implied, strength not oversold as programming, no invented benchmark stat, Tata 6,400+ kept off this page, one product shot plus one photograph minimum met (two shots, one photo), no em-dashes or banned filler.
