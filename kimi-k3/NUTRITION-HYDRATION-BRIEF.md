# Nutrition & Hydration — page brief

Intended URL: `/features/nutrition-hydration/` · Mock: `vantage-fit-nutrition-hydration-v1.html`

## Research takeaways

- Facts lock is the authority; help confirmed mechanics: water tap = fixed 250 ml glass, 8-glass default, challenge targets override (`how-do-i-log-water.md`); calorie targets derive from the basic health profile with no HRA mentioned (`what-are-calorie-targets.md`).
- Rigor is the differentiator, so the page leads with it: Mifflin-St Jeor BMR, Harris-Benedict multipliers (×1.2 to ×1.9), ±550 cal/day goal adjustment, 1,800 / 1,200 safety floors, macro ratios per goal, 25 / 35 / 10 / 30 meal split.
- Candor beats size: DB is "a few thousand items, accuracy being improved," so manual entry (name + calories) is presented as a first-class path, and food-suggestion submission is mentioned. AI food logging and barcode scanning are roadmap, stated as not live. Nothing on the page is called AI.
- Mobile-only, Full-Mode only. No admin controls specific to nutrition; admins see aggregates. GreenScore omitted per default (VERIFY unresolved).
- No client-attributed proof exists for this page. No proof band shipped, per the facts lock.

## Why this structure

Hero pairs the food-logging shot with a workplace photo and the 250 ml tap as a chip. Then: the math (BMR, multipliers, floors, macros, meal split) beside the calorie-balance shot, logging flow (search, Quick Tray, candid manual entry), water (tap, exact entry, challenge litres), a compact limits band (mobile-only, Full Mode, aggregates), FAQ for rollout objections. No borrowed stats.

## Copy deck (as shipped)

- H1: "Meals and water, on the same count as a run."
- Lead: employee nutrition tracking app, BMR math, seconds to log.
- Sections: "Targets from BMR, not a template." / "Log a meal in seconds. Or just type it." / "Water is one tap." / "Where this lives." / FAQ / final "Count the habit employees already have."
- Full copy is in the HTML; marketing copy is ~600 words outside nav, footer, and mock labels.

## Sources

- Meal split, Mifflin-St Jeor, Harris-Benedict multipliers, ±550 cal, 1,800 / 1,200 floors, macro ratios, basic-profile-only, DB size candor, Quick Tray, water 250 ml / 8 glasses / challenge targets, web and Lite Mode limits: `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (Nutrition card, shared logging physics).
- Water tap mechanics and glass size: help doc `content/en/help/employee/health-tracking/how-do-i-log-water.md`.
- Calorie target inputs (profile-based, no HRA): help doc `content/en/help/employee/health-tracking/what-are-calorie-targets.md`.
- "100+ organizations" aggregate trust signal (approved). No client stat used.

## Meta drafts

- Title: `Employee nutrition tracking app | Vantage Fit`
- Description: `Vantage Fit's employee nutrition tracking app sets calorie and macro targets from Mifflin-St Jeor BMR math and logs meals and water in seconds. Full Mode, mobile.`

## Critic result

Pass. Checked: no AI label on food logging or targets, DB not called comprehensive, HRA not required (stated), no food or water on web, Lite Mode excludes nutrition, activity level framed as a personal calorie input only, no GreenScore, no borrowed Tata / Wipro / IBS stat, no Org Wellness Score, one product shot plus one photograph minimum met (two shots, one photo), no em-dashes or banned filler.
