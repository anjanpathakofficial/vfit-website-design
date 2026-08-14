# Nutrition & Hydration — page brief

**URL:** `/features/nutrition-hydration/`
**Mock:** `claude-fable/vantage-fit-nutrition-hydration-v1.html`
**Angle:** the wellness habit employees log most. Lead with the macro and BMR rigor, not database size.
**Page type:** feature page. Proves a capability. Not a program outcome.

---

## 1. Research takeaways

Read: `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (facts lock), `vfit-os/specs/04-nutrition/{calorie-tracking,food-logging}.md`, and help docs for food search, calorie targets, manual food entry and water logging.

What actually differentiates this page:

1. **The target is derived, and the derivation is printable.** Mifflin-St Jeor BMR, then a Harris-Benedict activity multiplier (1.2 / 1.375 / 1.55 / 1.725 / 1.9), then ±550 cal/day for the goal, then a hard floor at 1,800 for men and 1,200 for women. A skeptical HR buyer trusts a formula with a safety floor more than "personalized nutrition."
2. **The meal split is the real product.** Breakfast 25%, Lunch 35%, Snacks 10%, Dinner 30%. It is what makes this nutritionist-style guidance rather than a daily calorie counter, and the product screenshot shows it working: "Recommended calories for lunch, 496."
3. **Macros change with the goal**, not with a subscription tier: Maintain 30/50/20, Gain 40/40/20, Lose 30/40/30, Lose Belly Fat 40/30/30.
4. **The honest database line is a feature.** Roughly 3,000 to 4,000 items, with regional dishes and home cooking as the known gaps, plus manual entry that needs no database at all. Leading with database size would be the weakest possible opening, which is exactly why the angle forbids it.
5. **A glass is fixed at 250 ml.** That is why eight glasses means the same thing for two different employees, and why a water challenge task is comparable across a workforce.

### Conflicts found and how they were resolved

| Conflict | Resolution |
|---|---|
| `how-does-food-search-work.md` front matter advertises "upcoming AI-powered logging" | Roadmap, not live. The page states plainly that none of this is AI: search is search and the target is a formula. |
| `calorie-tracking.md` §3.2 carries a **GreenScore** default target of 200 | Facts lock default is omit until VERIFY. GreenScore is not on the page. |
| The `vantage-fit-calorie-balance-mobile.png` screenshot shows a 275 kcal deficit and 0.25 kg per week, not the spec's ±550 and 0.5 kg | Both are real, for different goals. The caption describes the screen's structure and does not quote either number as the rule. The ±550 and 0.5 kg figures appear only in the derivation chain, where the spec supports them. |
| OS `activity-logging.md` lists Water (ID 24) as web-doable | Facts lock says food and water are both "No" on web. The page claims mobile only, and says so twice. |
| Spec frames activity level as a profile field; the live menu once used it for targeting | On this page activity level is a **personal calorie input** only. It is never described as something HR can target on. |

### Gaps

- **No client-attributed proof exists for this page.** Per proof hygiene, Tata, Wipro and IBS figures are not borrowed, and no meals-logged or glasses-logged number is invented. The customer-result band is skipped rather than filled with a placeholder. `[Data point needed]` if a nutrition or hydration figure is ever approved.
- The spec's ideal-weight formula and goal-recommendation logic are real but do not earn space on a lean page. Omitted.

## 2. Why this structure

Eight short sections, roughly 700 words of marketing copy, and no customer-result band. The order follows the one question this page has to answer first: *where does that number come from.*

- **Hero** is composed a third way: the food-logging screenshot as the dominant card with a photograph overlapping its corner. Activity tracking stacks the product shot over a photo row; Fitness leads with a photo banner. Shared chrome, three different heroes.
- **The derivation chain (S2)** is this page's signature and belongs to no sibling. Activity owns the step ledger, an addition. Fitness owns the validation gate, a rejection list. Nutrition owns a derivation with a safety floor.
- **The meal split (S3)** gets a drawn 25/35/10/30 bar because a percentage split is the one thing a screenshot cannot label clearly.
- **Honest limits (S5)** is where the database size finally appears, framed as a known gap with a working answer, which is the opposite of "comprehensive."
- **The through-line (S6)** is a short band, not a section, because the critic list requires this page to show how a meal becomes participation and one band does that.
- Deliberately **not** here: rings, the step formula, the 65-type catalog, GPS, devices, the squat tracker, GreenScore, HRA, Org Wellness Score.

## 3. Copy deck

**Meta title:** Employee Nutrition Tracking App | Vantage Fit
**Meta description:** Calorie targets from Mifflin-St Jeor, macros that move with the goal, and a day split 25/35/10/30 across four meals. Water logs one fixed 250 ml glass at a time.
**Primary keyword:** employee nutrition tracking app (H1, title)
**Secondary:** corporate wellness food logging (S3), employee hydration tracking (S4)

### S1 Hero
- Eyebrow: Features · For employees
- H1: An employee nutrition tracking app **that shows its working.**
- Lead: The daily target is not a round number somebody picked. It comes from Mifflin-St Jeor, an activity multiplier and the goal the employee chose, then splits across four meals. Water logs one fixed 250 ml glass at a time.
- CTAs: Book a walkthrough · See the calorie math
- Hero note: Full Mode only · Basic profile, no HRA · Mobile app

### S2 Where the target comes from
- Eyebrow: The math
- H2: Mifflin-St Jeor, then the goal.
- Lead: Four steps and a floor that stops the number going somewhere unsafe.
- Chain: **BMR** from height, weight, date of birth and gender. · **Activity multiplier**, sedentary 1.2 through very heavy 1.9. · **Goal**, plus or minus 550 calories a day, roughly 0.5 kg a week. · **Floor**, never below 1,800 for men or 1,200 for women.
- Macro table: Maintain 30/50/20 · Gain 40/40/20 · Lose 30/40/30 · Lose belly fat 40/30/30 (protein / carbs / fat)
- Note: All of it comes from the basic onboarding profile. The Health Risk Assessment is not required.
- Caption: The daily view. Meals against resting and active burn, with the deficit or surplus worked out on screen.

### S3 A day, split four ways
- Eyebrow: Food logging
- H2: Breakfast 25. Lunch 35. Snacks 10. Dinner 30.
- Lead: Corporate wellness food logging usually stops at a daily total. A day is lost at lunch, not at midnight, so the target is split before the employee opens the app.
- Split bar: drawn, four segments, labelled.
- Flow line: Pick the meal, search or tap the Quick Tray, set serving and quantity. Calories with protein, carbs and fat land against that meal's target.
- Caption: Log Meal by tab, a food with its macro breakdown, and the calorie summary for that meal.

### S4 Water
- Eyebrow: Hydration
- H2: One tap is one glass. 250 ml.
- Lead: The glass size is fixed, so two employees who logged eight glasses logged the same amount. That is what makes employee hydration tracking comparable across a workforce.
- Lines: The default target is 8 glasses, which is 2 litres. · An exact amount can be typed instead, in litres or fluid ounces. · A challenge task can set its own target, for example 3.0 litres on four days this week.

### S5 Honest limits
- Eyebrow: What it is not
- H2: A few thousand foods, and a way around it.
- Items: The database holds roughly 3,000 to 4,000 items and is being expanded. Regional dishes and home cooking are the gaps. · Manual entry needs no database. A name, a calorie count, and macros if they are known. · Suggest a food and the team reviews it for a later update. · None of this is AI. Search is search, and the target is a formula. · Food and water are mobile only, and neither exists in Lite Mode.

### S6 Through-line band
- A logged meal counts the way a run does. Water and nutrition tasks sit in the same challenge builder as steps and workouts, and land in the same participation rate.
- Links: activity tracking · fitness & exercise

### S7 FAQ
1. Does someone have to finish the Health Risk Assessment first? No. Height, weight, date of birth, gender, goal and activity level from onboarding are enough for a target and a macro split.
2. Can an employee log lunch from a laptop? No. Food and water logging are in the mobile app.
3. Does HR see what someone ate? No. Admins see aggregates. An individual food diary is never open to an admin.

### S8 Closer
- H2: See a lunch land in the participation rate.
- p: Thirty minutes on calorie targets, food and water logging, and the challenge tasks that read them.
- CTAs: Book a walkthrough · See activity tracking
- Checks: Full Mode only · Mobile app · 100+ organizations

## 4. Sources

| Claim | Source |
|---|---|
| Mifflin-St Jeor BMR formula, by gender | `vfit-os/specs/04-nutrition/calorie-tracking.md` §3.1 |
| Activity multipliers 1.2 / 1.375 / 1.55 / 1.725 / 1.9 | same, §3.1 |
| ±550 cal/day, roughly 0.5 kg per week | same, §3.1 |
| Floors: males 1,800, females 1,200 | same, §3.1 and §3.3 |
| Macro ratios by goal (30/50/20, 40/40/20, 30/40/30, 40/30/30) | same, §3.1 |
| Meal split 25 / 35 / 10 / 30 | same, §3.1; visible in `vantage-fit-food-logging-mobile.png` |
| Target derived from the basic profile, HRA not required | `help/employee/health-tracking/what-are-calorie-targets.md` |
| Food search, serving and quantity, calories plus macros, Quick Tray, manual entry, suggest a food | `help/employee/health-tracking/how-does-food-search-work.md` |
| Database is roughly 3,000 to 4,000 items, being expanded, regional gaps | same |
| Water: 1 tap = 1 glass = 250 ml fixed, exact amount typeable, default 8 glasses, challenge target overrides | `help/employee/health-tracking/how-do-i-log-water.md` |
| Food and water absent in Lite Mode, no web logging | `help/employee/getting-started/what-is-lite-mode.md`; facts lock web-parity rule |
| Admins see aggregates, never an individual food log | facts lock, shared logging physics rule 9 |

## 5. Critic result

Run against the full critic list in `FEATURES-EMPLOYEE-LOGGING-PROMPT.md`. **Pass.**

Checked and clear: food logging, calorie targets and search are never called AI, and the page says so outright. The database is described as roughly 3,000 to 4,000 items, never comprehensive. Barcode scanning is not mentioned. The HRA is explicitly not required. Food and water are stated as mobile only, twice, and as absent from Lite Mode. Activity level appears only as a personal calorie input, never as a targeting dimension. GreenScore is omitted. No Org Wellness Score, no composite score. No rings, no step formula, no GPS, no device catalog, no camera heart rate. No client-attributed proof: no Tata, no Wipro, no IBS, and no invented meals or glasses figure. No SOC 2 / ISO / GDPR / HIPAA claim. No 14 languages. No mood. No em-dashes, no exclamation marks, no "Learn more", no banned filler. `../styles/enterprise.css` is linked and no token is redeclared.

Fixed during the pass:

1. The first draft opened on the food database, which is exactly the angle the brief rules out. Rewritten to open on the derivation and the meal split, with database size demoted to the honest-limits section.
2. An early caption quoted the 275 kcal deficit visible in the calorie-balance screenshot as though it were the rule. Replaced with a structural caption, since that screen shows one employee's goal, not the ±550 standard.
3. A draft of S4 said water logging works "anywhere," which contradicts the mobile-only rule. Corrected, and the mobile-only line was added to the honest-limits list as well.
4. The customer-result band was cut rather than filled. This page owns no client figure, and borrowing one from the siblings is a named failure.
