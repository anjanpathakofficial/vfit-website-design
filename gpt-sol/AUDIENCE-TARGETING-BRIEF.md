# Audience Targeting

## Page job

Prove that HR can aim a challenge at a relevant employee cohort without opening a health-risk name list. The page must make targeting mechanics and privacy constraints equally concrete.

## Research takeaways

- Standard dimensions are country, city, department, gender, age range, and language. Activity level is not a targeting dimension.
- Health-risk-code targeting is available only to companies with Workforce Health. It operates at defined risk-code/category level and returns a count only.
- The required product disclaimer is: “The list of users is not displayed to protect individual privacy.” Admins do not see, screen, or export cohort identities.
- Any targeted challenge is automatically private and visible only to matching employees.
- Modern enrollment paths are direct admin add by search or bulk CSV, and immediate auto-enrollment from saved audience rules. The legacy email invite/accept path should not be promoted.
- Late joiners start scoring from the join or add date. They receive neither retroactive credit nor a penalty for time before enrollment.
- No targeting-specific client metric is approved.

## Structure and visual direction

1. Hero: count-only audience builder as the primary product moment, plus an HR workplace photograph.
2. Seven-dimension rule builder: show the complete and only approved targeting dimensions.
3. Privacy proof: health-risk categories disappear behind a visual privacy veil and resolve to an illustrative count with the exact disclaimer.
4. Enrollment routes: direct admin add and rule-based auto-enrollment, followed by a join-date-forward scoring timeline.
5. Product context: required campaign dashboard shot and a private-challenge status block.
6. CTA and links to Program Builder, Communications, and Admin Dashboard.

The signature element is the count-only privacy veil. It makes the buyer understand the product boundary at a glance without presenting fake health records. The rest of the page retains the existing Vantage Fit Noto Sans, coral, ink, mint, canvas, nav, footer, and rounded admin-panel language.

## Copy deck

- H1: Aim the challenge. Never expose the cohort.
- Lead: Combine company and demographic rules, see the eligible count, and enroll employees into a private challenge without opening their health profiles.
- Primary CTA: Book a walkthrough
- Secondary CTA: See count-only targeting
- Key heads: Seven dimensions. No activity-level shortcut. / Health-risk targeting ends at the count. / Two enrollment paths. No accept step. / Late joiners start on the day they join. / The challenge stays private by default.
- Closing: See how a brief becomes a private audience rule.

## Meta

- Title: Employee wellness program targeting | Vantage Fit
- Description: Target private wellness challenges by country, city, department, gender, age, language, or count-only health-risk code, then enroll by rule.

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md`, Audience Targeting card and shared HR physics
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md`, excluding stale activity-level copy
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-add-remove-participants.md`
- `vfit-os/specs/product/02-challenges-gamification/challenges.md`
- `vfit-os/specs/product/03-health-wellness/workforce-health.md`

## Critic result

Pass. The page uses exactly the seven approved dimensions, makes health-risk output count-only, includes the exact privacy disclaimer, marks targeted challenges private, avoids identity export and segment-from-report UI, and describes current enrollment paths plus join-date-forward scoring. It uses the assigned CDN product shot and workplace photography, links `enterprise.css`, includes no client statistic, and does not claim Org Wellness Score.
