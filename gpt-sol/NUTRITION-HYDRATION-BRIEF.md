# Nutrition & Hydration page brief

## Page job

Prove that Vantage Fit has a rigorous, usable employee nutrition tracking app rather than a decorative food database. The buyer should understand how targets are calculated, how employees recover when search misses a food, and how a meal or glass of water becomes participation.

## Research takeaways

- Daily calorie targets start with Mifflin-St Jeor BMR, apply Harris-Benedict activity multipliers, then adjust by ±550 calories for the selected goal.
- Minimum daily floors are 1,800 calories for males and 1,200 for females. Meal guidance splits the daily total 25 / 35 / 10 / 30 across breakfast, lunch, snacks, and dinner.
- Macro ratios change by goal. Only the basic onboarding profile is needed; the full HRA is not required.
- Food logging uses Algolia search or Quick Tray, then serving and quantity. Employees see calories, protein, carbs, and fat before saving. Manual food and macro entry is the honest fallback.
- The live database contains a few thousand foods and still has regional gaps. No food logging, barcode scanning, or calorie target is described as AI.
- One water tap is a fixed 250 ml glass. The default is eight glasses, with exact litres or fluid ounces available and custom challenge targets supported.
- Food and water are mobile, Full Mode features. HR receives aggregate participation, not individual food diaries.

## Structure and visual direction

The hero pairs the real food-logging screen with workplace photography that includes a visible glass of water. The page's signature is a brand-color meal plate divided into the exact 25 / 35 / 10 / 30 distribution. It makes the calculation tangible while staying within the existing coral, mint, amber, ink, Noto Sans system.

Page flow: formula-led hero, calculation chain and safety floors, meal and macro split, food logging path, fixed water mechanic, Full Mode and privacy boundary, sibling links, demo CTA.

## Full copy deck

**Meta title:** Employee nutrition tracking app and hydration | Vantage Fit

**Meta description:** Calculate calorie and macro targets, log meals, and track fixed 250 ml water glasses in one employee nutrition and hydration app.

**Eyebrow:** Features · For employees

**H1:** An employee nutrition tracking app built on clear math.

**Lead:** Vantage Fit turns a basic health profile into calorie and macro targets employees can inspect, then gives every meal and glass of water a direct path into participation.

**Hero notes:** Full Mode · Mobile only · HRA not required

### Start with BMR, not a database count.

Vantage Fit calculates BMR with the Mifflin-St Jeor formula. It applies a Harris-Benedict activity multiplier: Sedentary ×1.2, Light ×1.375, Moderate ×1.55, Heavy ×1.725, or Very Heavy ×1.9. The selected goal then adjusts the result by up to 550 calories per day, approximately 0.5 kg per week.

Safety floors keep daily targets from dropping below 1,800 calories for males or 1,200 for females. The calculation needs only height, weight, date of birth, gender, goal, and personal activity level from the basic onboarding profile. The full HRA is not required. Activity level is a personal calculation input, not an HR targeting dimension.

### Give every meal a share of the day.

Daily calorie guidance is distributed across Breakfast 25%, Lunch 35%, Snacks 10%, and Dinner 30%. Employees see a meal-level allowance instead of one number they must mentally divide.

Macro targets change with the selected goal. Protein, carbs, and fat are Maintain 30 / 50 / 20, Gain 40 / 40 / 20, Lose 30 / 40 / 30, and Lose Belly Fat 40 / 30 / 30.

### Search fast. Enter manually when search misses.

Employees choose a meal time, search through Algolia or open Quick Tray, set a serving and quantity, review calories, protein, carbs, and fat, then save against the target. Quick Tray brings frequent foods back for a faster repeat log.

The database contains a few thousand items today and regional coverage is still improving. Manual entry lets an employee add the food name, calories, and macros without depending on the database. Employees can also submit a food suggestion for possible inclusion.

The honest fallback matters: the log can still become participation even when the exact dish is not in search.

### One water tap is always 250 ml.

The plus or minus control changes intake by one fixed 250 ml glass. The default target is eight glasses. Employees can type an exact amount in litres or fluid ounces, and a challenge task can set a custom target such as 3.0 L on four days of the week.

### Full Mode, mobile, and private by design.

Food and water logging are available in the mobile app for Full Mode clients. They are absent in Lite Mode and are not available on the web. Employees manage their own entries. HR sees aggregate participation, not an individual's food diary.

**Sibling links:** Start with activity tracking · Count fitness and exercise · View all features

**Final CTA headline:** See how daily habits become participation.

**Final CTA body:** Walk through calorie targets, meal logging, Quick Tray, manual entry, and hydration in the employee app.

## Sources

- `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md`, Nutrition & Hydration card
- `vfit-os/specs/04-nutrition/calorie-tracking.md`
- `vfit-os/specs/04-nutrition/food-logging.md`
- Help: `how-do-i-log-meals.md`, `how-do-i-log-food-manually.md`, `how-does-food-search-work.md`, `how-do-i-log-water.md`

## Critic result

**Pass.** Reframed the hero around BMR and macros instead of database size, described the database limits directly, kept manual entry visible, omitted GreenScore, barcode scanning, and all AI language, and followed the facts lock over a conflicting help reference by keeping food and water off the web.
