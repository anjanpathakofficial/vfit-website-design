# Health Metrics

**URL:** `/features/health-metrics/`  
**Mock:** `vantage-fit-health-metrics-v1.html`  
**Angle:** Sleep, heart rate and weight, next to the step count.

## Page job

Prove the fuller health picture is real and already on the activity log: bedtime + wake-time, awareness-level camera HR, weight / vitals that auto-create a log entry, BMI bands plus a highlighted goal, optional HRA with a personal 0–100% score. Full-Mode. Mobile only. Not lab reports. Not Org Wellness Score.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See the HRA.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Sleep (lock):** Bedtime + wake-time via date pickers, not a duration field. Optional manual override. Wearable sleep coexists with manual; confirm-before-overwrite. Source field distinguishes `apple-health` vs `manual`. Sleep trend graph is Full-Mode only. Help `how-do-i-log-sleep.md` still describes hours-and-minutes duration. Flagged. Page follows lock.
- **Heart rate (lock + help measure-heart-rate):** (1) auto-synced from a wearable, (2) finger-on-camera. Awareness-level, not medical-grade. Help agrees on the camera caveat.
- **Weight / vitals (lock + OS health-vitals-goals):** BP parsed as `120/80`. Cholesterol. Diabetes boolean. Weight stored in grams, shown in the user unit. Every vitals / weight update auto-creates an activity-log entry. That is the participation through-line.
- **BMI + goals (lock):** Bands Underweight / Normal / Overweight / Obese + ideal-weight range. Goals: Lose Weight / Reduce Belly Fat / Gain Muscle / Be Fitter. Recommendation highlights, does not restrict. OS also lists maintain / gain. Page uses the lock four.
- **Activity level (lock):** Personal calorie input only. Never a targeting dimension.
- **HRA (lock + OS onboarding-health-profile):** Separate, optional, deeper questionnaire. Personal 0–100% fitness score. 7 bands: Critical / Poor / Below Average / Average / Decent / Good / Excellent. Personalized tips. ~20% completion, single-cohort, VERIFY. Skip without penalty. Not required for calorie targets. Not in Lite Mode. Help `what-is-hra.md` lists 5 bands and still feeds the retired Wellness Score. Flagged. Page uses 7 bands and leaves the org score off.
- **Health Connect (lock):** Legitimate Android *import* of weight, sleep, heart rate, calories, distance. Not the Android step source.
- **Labs:** Different, whitelist page. Cross-link only. HIPAA: “HIPAA-guideline aligned” + BAA for the lab-report pipeline. Never “HIPAA-compliant platform.”
- **Proof (this page only):** Tata Motors avg BMI 24 tracked (VERIFY). Case study body: Tata Motors Step Up & Elevate, “Average organisational BMI of 24.” HRA ~20% completion (VERIFY). Brazosport BMI 30 → ~27 default-omitted.

### Conflicts left unresolved (not silently fixed)

1. Help sleep: duration field. Lock: bedtime + wake-time pickers. Page uses pickers.
2. Help HRA: 5 bands + Wellness Score baseline. Lock: 7 bands, org score retired. Page uses 7 bands, no org score.
3. OS goals include maintain / gain. Lock: four named goals. Page uses the lock four.
4. Help / OS still describe Org Wellness Score. Retired. Left off.

## Why this structure

No required spine. Must-cover folded into a sleep clock, a vitals strip, and one-line labels.

| Section | Job |
|---|---|
| Hero + morning photo + sleep clock | First screen: bedtime / wake, next to the step habit. |
| Sleep rules | Pickers, overwrite confirm, source field, Full-Mode trend. |
| Two heart rates + overview shot | Wearable vs camera. Awareness-level called out. |
| The update is a log + BMI / goals | Through-line. Bands and highlighted goal, not a second product. |
| Optional HRA + HRA shot | Personal 0–100%, 7 bands, ~20% VERIFY. Skip without penalty. |
| Full-Mode / mobile / labs | Honest gates. HIPAA scoped. Activity level is personal. |
| Compact proof | Assigned Tata BMI + HRA completion only, VERIFY labeled. |
| 3 FAQs + sibling links | HIPAA, HRA required, web. Lateral Group B. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** `../styles/enterprise.css`, Noto Sans, coral / ink / mint, homepage nav/footer, `logo.png` / `logo-white.png`. Features mega-menu is the locked IA. Current item: Health metrics. Generated morning photograph plus the two assigned CDN shots. No wellness-score screenshots.

## Copy deck

**Title:** Employee health metrics tracking platform | Vantage Fit  
**Meta:** Sleep, heart rate, and weight log next to the step count. Camera heart rate is awareness-level, not medical-grade. Optional HRA. Full-Mode.

**Eyebrow:** Features · For employees  
**H1:** Sleep, heart rate, and weight. Next to the step count.  
**Lead:** A bedtime and a wake time. A weight update. Each one writes an activity-log entry. No second form.  
**Hero notes:** Full-Mode · Mobile only · 100+ organizations  
**CTAs:** Book a walkthrough · See the HRA

**H2:** Bedtime and wake time. Not a duration field.  
Date pickers. Optional override. Wearable and manual coexist with a confirm-before-overwrite prompt. Source: apple-health or manual. Sleep trend is Full-Mode only.

**H2:** Two heart rates. Only one is a camera.  
Wearable auto-sync. Finger-on-camera is awareness-level, not medical-grade. Health Connect imports weight, sleep, heart rate, calories, distance. Not Android steps.

**H2:** The update is another log.  
BP `120/80`, cholesterol, diabetes, weight in the user unit. Auto-creates an activity-log entry. BMI bands + ideal-weight range. Four goals, highlighted not forced. Activity level is a calorie input.

**H2:** Optional. Personal. 0 to 100 percent.  
Seven bands, Critical to Excellent. Tips. ~20% completion [VERIFY]. Not required for calorie targets. Skip without penalty.

**H2:** Full-Mode. Phone only.  
Not on web. Not in Lite Mode. Labs are a whitelist page. VC Support: lab reports, custom T&C, feature toggles. HIPAA-guideline aligned. BAA on the lab-report pipeline.

**Proof:** Tata Motors avg BMI 24 tracked `[VERIFY]`. HRA ~20% completion, single-cohort `[VERIFY]`.

**FAQ**  
1. Is this a HIPAA-compliant platform?  
2. Must employees complete the HRA?  
3. Can they log sleep on the web app?

**Close H2:** Put the fuller picture on the same log.

## Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` platform rules + page 4
- `vc-os/vfit-os/specs/03-health-wellness/health-vitals-goals.md`
- `vc-os/vfit-os/specs/03-health-wellness/health-risk-assessment.md`
- `vc-os/vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` (7 bands)
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-log-sleep.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-log-my-weight.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-measure-heart-rate.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/what-is-hra.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/what-is-my-health.md`
- Case study: `tata-motors-step-up-elevate.md` (avg BMI 24)

## Assumptions

- Sleep UI follows the lock (bedtime / wake pickers), not help’s duration field.
- HRA bands follow the product spec’s seven labels, not help’s five.
- Tata BMI stays labeled VERIFY even though the case study states it.
- Hero clock times are illustrative, no named employee.
- Brazosport BMI change omitted (lock default-omit).
- Org Wellness Score, 20/30/30/20 mix, and Score Report are absent.

## Critic

Run after the mock. Failures found in draft and fixed:

- Camera HR not called accurate, clinical, or medical-grade.
- Health Connect named only as import, not the Android step source.
- Activity level is a calorie input, not targeting.
- HRA optional; not required for calorie targets.
- Labs cross-linked, not sold as standard.
- HIPAA scoped. No SOC2 / ISO / GDPR.
- Org Wellness Score not shown or gated.
- Assigned proof only, VERIFY labeled. Group A stats unused.
- No em-dashes, exclamation marks, or banned filler.
- `../styles/enterprise.css` linked. Product shots + photograph present.

**Pass.** Marketing copy in `<main>` is ~718 words including mock labels (in the 450–750 band). Images: two CDN product shots + morning photograph + logos. Visual chrome matches Activity Tracking / Admin Dashboard.
