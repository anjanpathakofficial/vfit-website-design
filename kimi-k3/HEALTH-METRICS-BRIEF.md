# Health Metrics — page brief

Intended URL: `/features/health-metrics/` · Mock: `vantage-fit-health-metrics-v1.html`

## Research takeaways

- Facts lock is the authority. Through-line: every vitals, sleep, or weight update auto-creates an activity-log entry, so the health update is another log on the same participation surface as steps, not a second product.
- Sleep is bedtime + wake-time via date pickers, not a duration field. Wearable sleep coexists with manual entries behind a confirm-before-overwrite prompt, and a source field distinguishes "apple-health" from "manual." Sleep and its trend graph are Full-Mode only.
- Camera heart-rate is positioned honestly: awareness-level, not medical-grade. Wearable sync is the other path.
- Vitals: BP parsed as systolic / diastolic ("120/80"), cholesterol, diabetes status boolean, weight stored in grams and shown in the user's unit, BMI with four bands plus an ideal-weight range.
- Fitness goals (Lose Weight / Reduce Belly Fat / Gain Muscle / Be Fitter) compare current weight to the ideal range and highlight a suggestion without restricting choice. Activity level stays a personal calorie input, never a targeting dimension.
- HRA is separate, optional, and skippable without penalty: a deeper questionnaire returning a personal 0–100% fitness score, a 7-band status (Critical to Excellent), and tips. Not in Lite Mode, not required for calorie targets.
- Health Connect on Android legitimately imports weight, sleep, heart rate, calories, distance here. It is never the step source, and this page says nothing about steps via Health Connect.
- Lab reports / Workforce Health are a different whitelist page; cross-link only, never pitched as standard.

## Why this structure

Hero pairs the overview shot with a metrics-review photo and a chip carrying the through-line ("logged once, counts like a workout"). Then: vitals with BMI bands beside the HRA shot, a sleep + heart-rate pair (bedtime / wake-time pickers, source field, awareness-level camera HR), goals and activity level (highlighted, not forced; calorie input, not targeting), the optional HRA with its personal score framing, the two assigned VERIFY stats, a compact limits band (Full Mode, mobile, aggregates-only privacy, lab reports elsewhere), FAQ, done. No score story beyond the personal HRA result.

## Copy deck (as shipped)

- H1: "Sleep, heart rate, and weight, next to the step count."
- Lead: employee health metrics tracking platform where every health update auto-logs.
- Sections: "Vitals, without a second form." / "Sleep is a schedule. Heart rate has two paths." / "A suggested goal, not a forced one." / "The HRA is optional. Skipping costs nothing." / proof band / "Where this lives." / FAQ / final "The fuller picture, on the same count."
- Full copy is in the HTML; marketing copy is ~620 words outside nav, footer, and mock labels.

## Sources

- All mechanics, tier flags, do-not-claim list, proof assignment: `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` (Health Metrics card, platform guardrails, score table).
- Tata Motors average BMI 24 tracked: assigned proof, single program, marked VERIFY on the page.
- HRA roughly 20% completion: single-cohort, marked VERIFY on the page.
- "100+ organizations" approved aggregate, used once in the final band.

## Meta drafts

- Title: `Employee health metrics tracking platform | Vantage Fit`
- Description: `Vantage Fit's employee health metrics tracking platform logs sleep, heart rate, weight, and vitals next to the step count, with an optional health risk assessment.`

## Critic result

Pass. Checked: no Org Wellness Score or mix formula; camera heart-rate called awareness-level, never accurate or clinical; HRA optional, personal 0–100% plus 7 bands only, not required for anything; activity level framed as a calorie input only; no Health Connect as step source; vitals / sleep / HRA Full-Mode and mobile only; lab reports cross-linked as a separate enterprise page, not standard; no HIPAA / SOC2 / ISO / GDPR claim; both assigned stats labeled to their program and marked VERIFY; one product shot plus one photograph minimum met (two shots, one photo); no em-dashes, exclamation marks, or banned filler; copy under 750 words.
