# Activity Tracking

**URL:** `/features/activity-tracking/`  
**Mock:** `vantage-fit-activity-tracking-v1.html`  
**Angle:** The logging surface everything counts on.

## Page job

Prove the employee activity log is real: no wearable required, 65 types, three sources, two rings, honest step math. This is the surface Fitness and Nutrition later write onto. Not a Solutions outcome page. Not a help catalog.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See the rings.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **65 types (lock + OS activity-logging):** IDs 1–65. Help sometimes says 65+. Page uses 65.
- **Three sources (lock):** automatic device sync, manual logging, camera (squat pose-detection, finger-on-camera heart rate). Camera HR is awareness-level, not medical-grade. Help squat article says “AI.” Lock: pose-detection. Page does not call rings, calories, or logging AI.
- **Step sources (lock + help devices):** Apple Health (iOS), Google Fit / selected Android source, Fitbit, Garmin. Health Connect is for supported *imports*, not the Android step pipeline. Help confirms this split.
- **Formula (lock + OS steps-tracking):** `TOTAL_STEPS = device steps + manual steps (Activity ID 63, company-toggle) + active-minute-derived steps`.
- **Active minutes (lock + OS):** 100 steps = 1 active minute, hardcoded. Used as `move_min`. WHO 150 min/week is context, not a certification.
- **Rings (lock + help rings / summary):** Ring 1 = steps always. Ring 2 = Active Calories or Active Minutes. Lock: company-configured via **VC Support**. Help: “HR admin chooses.” Flagged, page follows lock. Defaults 10,000 steps / 250 active calories with no challenge. Diary + 7-day trends. Mindful-minute and sleep graphs Full-Mode only. Rings / trends are not on web.
- **Integrity (lock + OS):** Duplicate-detection 95–105% of prior day within 18h (iOS 1.5.4–1.5.7). Sync floor 15 seconds. Normalization / capping exists and is **disabled globally**.
- **Custom / a11y / 7-Minute (lock):** Self-serve loggable vs adherence activities. Wheelchair ID 58, GPS-trackable. 7-Minute Workout: fixed 12-exercise routine, VFit-built, bundled GIFs. Help says video. Page follows lock (GIFs).
- **Lite / gates (lock):** Lite = steps only. VC Support: active-minutes ring, manual steps, prevent overlapping activities, Lite enablement. Self-serve: custom activities, activity reports.
- **Proof (this page only):** Tata Motors 6,400+ activities logged (VERIFY). Case study body says 6,464 on Step Up & Elevate. Page uses lock 6,400+ and labels VERIFY. IBS Software 100+ → 236 (VERIFY). Case study: 236 employees at 30,000+ steps/week by week three. Do not use Tata 472 GPS or Wipro squat / yoga.

### Conflicts left unresolved (not silently fixed)

1. Help rings: HR admin sets Ring 2. Lock: VC Support. Page uses VC Support.
2. Help 7-Minute: video demos. Lock: bundled GIFs. Page uses GIFs.
3. Help squat tracker: “AI-powered.” Lock: camera pose-detection. Page does not say AI.
4. Help / OS still mention Wellness Score. Lock: retired. Left off.
5. Tata case study 6,464 vs lock 6,400+. Page uses lock + VERIFY.

## Why this structure

No required spine. Must-cover folded into UI, a formula strip, and one-line labels.

| Section | Job |
|---|---|
| Hero + running photo + formula chip | First screen: phone is enough, and the conversion is specific. |
| Three sources | Device / manual / camera. Health Connect named only as import. |
| 100 steps = 1 AM | The mechanic only this product can say. Formula, not an essay. |
| Two rings + active-minutes shot | Home surface. VC Support on ring 2. Web has no rings. |
| 65 types + logging shot | Catalog lives in the screenshot. Custom, wheelchair, 7-Minute as one-liners. |
| Integrity + Lite / gates | Honest measurement. Tier flags visible. |
| Compact proof | Assigned Tata / IBS only, VERIFY labeled. |
| 3 FAQs + sibling links | Rollout objections. Fitness and Nutrition inherit this surface. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** `../styles/enterprise.css`, Noto Sans, coral / ink / mint, homepage nav/footer, `logo.png` / `logo-white.png`. Features mega-menu is the locked IA. Current item: Activity tracking. No SOC 2 / GDPR / ISO.

## Copy deck

**Title:** Employee activity tracking software | Vantage Fit  
**Meta:** Phone sensors count steps. 65 activity types. Two rings. No wearable required. See how employee activity tracking software feeds one participation number.

**Eyebrow:** Features · For employees  
**H1:** Employee activity tracking, without a wearable.  
**Lead:** Phone sensors feed the same participation number as a later workout or meal. 65 activity types. Two rings. Step math you can explain upstairs.  
**Hero notes:** No wearable required · 65 activity types · 100+ organizations  
**CTAs:** Book a walkthrough · See the rings

**H2:** Phone, log, or camera.  
Automatic device sync. Manual logging. Camera for squat pose-detection and finger-on-camera heart rate. Heart rate is awareness-level, not medical-grade.  
Step sources: Apple Health, Google Fit or the selected Android source, Fitbit, Garmin. Health Connect is for supported imports, not Android steps.

**H2:** 100 steps. One active minute.  
`TOTAL_STEPS = device + manual (ID 63, company toggle) + active-minute-derived`. Hardcoded 100:1. The `move_min` challenge task. WHO 150 min/week is context, not a certification.

**H2:** Two rings. Steps always.  
Ring 1 = steps. Ring 2 = active calories or active minutes via VC Support. Defaults 10,000 / 250 when no challenge runs. Diary and 7-day trends. Mindful and sleep graphs Full-Mode only. Not on web.

**H2:** 65 types. Plus the ones you name.  
Screenshot carries the catalog. Custom loggable (Office Yoga) and adherence (Avoid Sugar), self-serve. Wheelchair, GPS-trackable. 7-Minute Workout, 12 VFit GIFs.

**H2:** Honest logs. Not inflated ones.  
Duplicate-detection 95–105% of the prior day within 18 hours. Sync floor 15 seconds. Capping exists in code and is off.

**H2:** Lite Mode is steps only.  
VC Support: active-minutes ring, manual steps, prevent overlapping activities, Lite enablement. Self-serve: custom activities, activity reports.

**Proof:** Tata Motors 6,400+ activities logged `[VERIFY]`. IBS Software 100+ → 236 employees `[VERIFY]`.

**FAQ**  
1. Do employees need a wearable?  
2. Can HR open someone’s heart-rate sample?  
3. What disappears in Lite Mode?

**Close H2:** Put every log on the number you take upstairs.

## Sources

- `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` platform rules + page 1
- `vc-os/vfit-os/specs/01-core-tracking/steps-tracking.md`
- `vc-os/vfit-os/specs/01-core-tracking/active-minutes.md`
- `vc-os/vfit-os/specs/01-core-tracking/activity-logging.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/what-are-activity-rings.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-read-my-dashboard.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/what-activities-can-i-track.md`
- `vantagefit-astro/content/en/help/employee/getting-started/do-i-need-a-wearable.md`
- `vantagefit-astro/content/en/help/employee/getting-started/what-is-lite-mode.md`
- `vantagefit-astro/content/en/help/employee/getting-started/using-vantage-fit-on-web.md`
- Case studies: `tata-motors-step-up-elevate.md` (6,464 in body; lock 6,400+); `ibs-software-case-study.md` (236 by week three)

## Assumptions

- Ring 2 copy follows the lock (VC Support), not help’s “HR admin.”
- 7-Minute media follows the lock (bundled GIFs).
- Tata figure stays 6,400+ with VERIFY, not the 6,464 case-study body number.
- Formula numbers in the hero chip are labeled illustrative.
- Android auto-tracked *task* sync source omitted (live contradiction).

## Critic

Run after the mock. Failures found in draft and fixed:

- Did not name Health Connect as the Android step source.
- Did not call rings, calories, or logging AI. Camera HR not medical-grade.
- Did not claim capping is on. Did not claim web rings / trends.
- Lite Mode and VC Support gates are on the page, not buried.
- Tata 472 GPS and Wipro squat / yoga not used.
- Org Wellness Score not shown.
- No em-dashes, exclamation marks, or banned filler.
- `../styles/enterprise.css` linked. Product shot + photograph present.

**Pass.** Marketing copy in `<main>` is ~689 words including labels (in the 450–750 band). `../styles/enterprise.css` is linked. Images: two CDN product shots + running photograph + logos. No em-dashes or exclamation marks. Health Connect named only as import. Org Wellness Score absent. Visual chrome matches Admin Dashboard / `styled-homepage`.
