# Health Metrics — page brief

**Slug:** `/features/health-metrics/`
**Mock:** `claude-fable/vantage-fit-health-metrics-v1.html`
**Group:** B, page 1 of 4. Feature page, not a Solutions page.

---

## 1. Research takeaways

**The angle is a plumbing fact, not a benefit.** Every vitals or weight update writes an
activity-log entry by itself (`health-vitals-goals.md` §3.2, `health-risk-assessment.md`
§3.3). That single line is what makes this page a Vantage Fit page instead of a generic
health-tracker page: the fuller health picture lands on the **same participation surface**
as a step. Everything else on the page is evidence for it.

**Three details a competitor page would get wrong, so they lead:**

1. **Sleep is a bedtime and a wake time**, not a duration box. Wearable sleep coexists with
   manual entries and prompts before it overwrites; the stored `source` field separates
   `apple-health` from `manual`.
2. **Camera heart rate is awareness-level, not medical-grade.** Help doc
   `how-do-i-measure-heart-rate.md` states this outright. Printing the limitation is more
   persuasive to a skeptical HR buyer than hiding it.
3. **Activity level is a personal calorie input.** It is not a targeting dimension, and the
   page says so in the same breath it names the four levels.

**HRA is deliberately de-risked.** Optional, not in onboarding, not in Lite Mode, skippable
with no penalty, and nothing else depends on it (calorie targets use the basic profile).
Result is a **personal** 0–100% fitness score with a status band. That is the employee's
number, not an HR object.

**Org Wellness Score is retired** and does not appear. Sources that still describe it
(`wellness-score.md`, `what-is-hra.md` "Baseline component (20%)", `how-do-i-log-my-weight.md`
"makes your Wellness Score more accurate") were ignored per the facts lock.

### Conflicts flagged

| Conflict | Sources | Resolution on the page |
|---|---|---|
| HRA band count | Facts lock says **7 bands** (Critical → Excellent). Help `what-is-hra.md` lists **5** (Excellent / Good / Average / Below Average / Critical). | Facts lock wins. Page says "a seven-band status ladder from Critical to Excellent" and does **not** name all seven, because five is all any source names. Worth a product check before publish. |
| Sleep input | Facts lock says **bedtime + wake-time date pickers**. Help `how-do-i-log-sleep.md` says "enter your sleep duration (hours and minutes)". | Facts lock wins. Page shows bedtime and wake time, and keeps manual override as a secondary line. Flagged. |
| HRA max points | Help says "maximum of 95 points across all nine components" but also "0 to 100%". | Omitted. Only the 0–100% personal score ships. |
| Org score | `wellness-score.md`, help docs, legacy brief. | Retired. Not shown, not gated, not explained. |

---

## 2. Why this structure

Nine short sections, no spine, no "problem / solution". The order is the order a skeptical
buyer's objections arrive in:

1. **Hero** — the angle in one line, with the product overview shot and a workplace photo.
2. **The health profile** — what it actually takes. A field list plus the BMI band scale,
   because a field list is not arguable.
3. **Sleep and heart rate** — the two most-faked features in this category, side by side,
   with the camera limitation printed on an ink panel rather than buried.
4. **The log** — the through-line, shown as a diary fragment. This is the page's centre.
5. **Goals** — highlighted, not enforced, plus the activity-level honesty line. The CDN
   "health risk assessment" shot lands here rather than in the HRA section, because what it
   actually shows is the profile setup and the Lifestyle & Goals screen: an ideal-weight
   scale, a BMI figure, and the same four goal tiles with one outlined. Pairing it with the
   goal chips makes the copy checkable against the screenshot.
6. **HRA** — optional and self-contained. The band ladder is **drawn in HTML**, not
   screenshotted, because no shipping screen in the asset library shows it and faking one
   would be a fabricated product shot.
7. **Who sees what** — the privacy / HIPAA-intent answer, scoped honestly.
8. **Proof** — two assigned figures, both VERIFY-labelled.
9. **FAQ (3) + closer.**

Density peer is `grok/vantage-fit-activity-tracking-v1.html` and this model's own
`vantage-fit-fitness-exercise-v1.html`. Chrome (nav, mega-menu IA, footer, buttons, reveal
script) is cloned from the sibling; the hero composition and the diary fragment are new so
the four Group B pages do not read as one template.

**Not repeated here:** the 65 activity types, GPS anti-cheat, meal maths, water glasses
(Group A owns those). The mindfulness library, leagues and training plans are one-line
cross-links only.

---

## 3. Copy deck

**H1** Sleep, heart rate and weight, next to the step count.

**Lead** An employee health metrics tracking platform where the update *is* the log. Change
a weight, record a blood pressure, and an activity entry is written for you. No second app,
no duplicate form.

**Hero note** Full Mode only · Mobile app · No wearable required

**S2 — The health profile / "What the profile actually takes."**
Employees fill in what they know. Partial data still works, and the calculated numbers
update from whatever is there.
Fields: blood pressure (systolic / diastolic), cholesterol, diabetes status, weight, height,
waist size. Blood pressure parses the way people write it, 120/80. Weight is stored once and
shown in the employee's own unit, kilograms or pounds. BMI is calculated from height and
weight and placed on a four-band scale with an ideal-weight range.

**S3 — Sleep and heart rate / "Sleep is a bedtime and a wake time."**
Sleep: two date pickers, not a duration box to estimate into. A connected wearable's sleep
coexists with manual entries and asks before it overwrites one. The record keeps its source,
so an Apple Health night and a typed night are never confused. Sleep trends are Full Mode.
Heart rate: sync it from a wearable, or hold a fingertip over the rear camera for 15 to 30
seconds.
Ink panel: **The camera reading is awareness-level, not medical-grade.** It is a convenience
tool for someone without a wearable. It is not a diagnostic, and Vantage Fit does not present
it as one. For continuous or exercise heart rate, connect a device.

**S4 — Participation / "The health update is another log, not a second product."**
A vitals or weight update creates an activity-log entry on its own. The fuller health picture
counts toward the same participation rate as a step, in the same diary, against the same
challenges.

**S5 — Goals / "Recommended, never enforced."**
Lose weight · Reduce belly fat · Gain muscle · Be fitter. The recommendation compares current
weight to the ideal range and highlights one. All four stay selectable.
Activity level (Not Very / Slightly / Moderately / Very Active) is a personal calorie input.
It is not an HR targeting dimension and never has been.

**S6 — HRA / "Optional, and skipping it costs nothing."**
A longer questionnaire across nine health areas returns a personal fitness score from 0 to
100% and a status band. It sits in the profile, not in onboarding. Calorie targets use the
basic profile, so nothing else on the page waits on it. Not available in Lite Mode.
Roughly 20% of employees complete it in a single-cohort read. [VERIFY]

**S7 — Who sees what**
Employees see their own complete profile. Admins see aggregate counts, never an individual's
answers, readings or reports. Lab-report upload is a separate premium capability with
BAA provisions for HIPAA compliance covering that pipeline, and it is HIPAA-guideline
aligned rather than a platform certification.

**S8 — Proof**
24 — average BMI tracked across the Tata Motors program. [VERIFY]
~20% — HRA completion in a single-cohort read. [VERIFY]

**FAQ**
- Does anyone at my company see my blood pressure? No. Admins see aggregate counts only.
- Is the HRA required to get calorie targets? No. Targets come from the basic profile.
- Can employees do this on the web? No. Vitals, sleep and the HRA are mobile only.

**Closer** Watch a weight update become a participation number.

**Meta title** Employee Health Metrics Tracking Platform | Vantage Fit
**Meta description** Sleep as a bedtime and a wake time, camera or wearable heart rate, weight and BMI bands. Every vitals update writes its own activity-log entry.

---

## 4. Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` — page 4 card, platform guardrails, proof assignment (facts lock, wins all conflicts)
- `vfit-os/specs/03-health-wellness/health-vitals-goals.md` — fields, BMI formula, goal recommendation logic, vitals auto-logging
- `vfit-os/specs/03-health-wellness/health-risk-assessment.md` — HRA fields, optionality, auto-logged weight
- `vantagefit-astro/.../health-tracking/what-is-hra.md` — 0–100%, nine areas, ~20% completion, not in onboarding, not in Lite Mode
- `vantagefit-astro/.../health-tracking/what-is-my-health.md` — My Health contents, Full Mode gate, privacy split
- `vantagefit-astro/.../health-tracking/how-do-i-measure-heart-rate.md` — camera method, 15–30 s, awareness-level wording
- `vantagefit-astro/.../health-tracking/how-do-i-log-my-weight.md`, `how-do-i-log-sleep.md` — logging flow, unit preference, wearable sync
- `styles/enterprise.css`, `styled-homepage/`, `claude-fable/vantage-fit-fitness-exercise-v1.html` — design system and chrome

---

## 5. Critic result

| Check | Result |
|---|---|
| Org Wellness Score / 20-30-30-20 / 0–108 ceiling | Absent. Retired sources ignored, conflict logged above |
| Camera HR called accurate or clinical | No. Printed as awareness-level on a dedicated ink panel |
| Health Connect as the Android step source | Not claimed. Health Connect is not named on this page at all |
| Activity level as a targeting dimension | Explicitly denied in copy |
| HRA required for another feature | Explicitly denied ("calorie targets use the basic profile") |
| Lab reports pitched as standard | No. One line, marked premium, cross-linked to the enterprise page |
| HIPAA / SOC 2 / ISO / GDPR platform claim | No. BAA provisions scoped to lab reports, "HIPAA-guideline aligned" |
| VERIFY figures shipped bare | No. Both carry a visible Verify tag |
| Group A stats reused | No. Only Tata BMI 24 and HRA ~20%, both assigned to this page |
| Individual health data on screen | No. Illustrative values only, no names, no lab values, no HRA answers |
| Em-dashes / exclamation marks / "Learn more" | None |
| `../styles/enterprise.css` linked, no new brand | Yes, linked. No new tokens, font or wordmark |
| Product screenshot + photograph | 2 CDN product shots (`vfit-overview-mobile` in the hero, `vantage-fit-health-risk-assessment-mobile` in Goals) + 2 photographs (`card-measure-generic.jpg` hero, `card-participate.jpg` proof band). Every alt describes what is actually on the screen, checked against the rendered page |
| Marketing copy budget | 777 words counted strictly (headings, eyebrows, figcaptions and FAQ included, in-mock labels excluded). Same measure puts the approved peers at 782 / 778 / 636 |
| Renders correctly | Yes. Walked the full page at 1440px in Chrome, all ten sections, hero through closer |
| Shows how it becomes participation | Yes, section 4 is the page's centre |
| Tier gates surfaced | Full Mode banner in the hero note and the FAQ head; Lite Mode exclusion stated twice |
