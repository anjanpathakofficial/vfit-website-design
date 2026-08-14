# Nutrition & Hydration

**URL:** `/features/nutrition-hydration/`  
**Mock:** `vantage-fit-nutrition-hydration-v1.html`  
**Angle:** The habit employees log most. Lead with macro / BMR rigor, not database size.

## Page job

Prove food and water land on the same participation surface as a run: meal-level calorie split, Mifflin-St Jeor, macro ratios by goal, honest food search plus manual entry, a fixed 250 ml glass. Full-Mode. Mobile only. Not AI. No borrowed client stat.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See the meal split.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Meal split (lock + OS calorie-tracking + food-logging):** Breakfast 25% / Lunch 35% / Snacks 10% / Dinner 30%. Nutritionist-style guidance, not a daily total alone.
- **Science (lock + OS):** Mifflin-St Jeor BMR. Harris-Benedict multipliers: Sedentary ×1.2, Light ×1.375, Moderate ×1.55, Heavy ×1.725, Very Heavy ×1.9. Goal adjustment ±550 cal/day (≈0.5 kg/week). Floors Males 1,800 / Females 1,200.
- **Macros (lock + OS):** Maintain 30/50/20, Gain 40/40/20, Lose 30/40/30, Lose Belly Fat 40/30/30.
- **Inputs (lock):** Basic onboarding health profile only (height / weight / DOB / gender / goal / activity level). **HRA is not required.** OS calorie-tracking says users without HRA data cannot get personalized targets. Flagged. Page follows lock.
- **Activity level:** Personal calorie input. Not an HR targeting dimension.
- **Food logging (lock + help meals / search):** Meal time → Algolia search or Quick Tray → serving / quantity → calories / protein / carbs / fat → saved. Manual entry (name + calories / macros) as the candid fallback. DB is “a few thousand items currently, accuracy being improved.” Help says ~3,000–4,000. Page uses lock wording, not a bigger number.
- **Water (lock + help water):** +/− tap = 1 glass = 250 ml, fixed. Can type litres / fl-oz. Default 8 glasses. Challenge tasks can set custom targets (e.g. Drink 3.0 L, 4 days this week).
- **Not (lock):** Web food / water. Lite Mode. AI food logging. Barcode scanning. Comprehensive DB. GreenScore (omitted; VERIFY if it even surfaces).
- **Help contradiction:** Web Today page lists water logging. Lock: food and water are “No” on web. Page follows lock and flags the conflict.
- **Proof:** None client-attributed. Do not borrow Tata / Wipro / IBS. Skip a customer-result band.

### Conflicts left unresolved (not silently fixed)

1. OS: HRA required for personalized calorie targets. Lock: basic profile only, HRA not required. Page uses lock.
2. Help: water on web Today dialogs. Lock: not on web. Page uses lock.
3. Help search mentions upcoming AI-powered logging. Lock: AI food logging is roadmap. Page does not say AI.
4. GreenScore in OS food-logging. Lock: omit unless VERIFY. Omitted.
5. OS / help still mention Wellness Score. Retired. Left off.

## Why this structure

Different hero from rings (Activity) and GPS (Fitness). Signature is the 25 / 35 / 10 / 30 split.

| Section | Job |
|---|---|
| Hero + lunch photo + split bar | First screen: meal math, not a giant food DB. |
| BMR / macros / floors | Science a skeptical HR buyer can check. HRA not required. |
| Food search + food shot | Search, Quick Tray, manual entry. Few thousand items. |
| Water + calorie-balance shot | 250 ml glass. Challenge can set litres. |
| Gates | Full-Mode. Not on web. Not AI. Activity level is personal. |
| No proof band | Lock: no client meals/water stat. |
| 3 FAQs + siblings | HRA, web, DB size. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** Same chrome. `../styles/enterprise.css`. Current mega item: Nutrition & hydration. Generated desk-lunch photograph plus the two assigned CDN shots.

## Copy deck

**Title:** Employee nutrition tracking app | Vantage Fit  
**Meta:** Meal-level calorie splits, Mifflin-St Jeor targets, and a 250 ml water glass. Corporate wellness food logging on the same participation number as a run. Full-Mode.

**Eyebrow:** Features · For employees  
**H1:** The meal split, then the daily total.  
**Lead:** Breakfast 25, lunch 35, snacks 10, dinner 30. Mifflin-St Jeor. One water tap is 250 ml. Same participation surface as a run.  
**Hero notes:** Full-Mode · Mobile only · 100+ organizations  
**CTAs:** Book a walkthrough · See the meal split

**H2:** Mifflin-St Jeor. Then the floor.  
Multipliers. ±550 cal. 1,800 / 1,200 floors. Macros by goal. Basic profile only. HRA not required. Activity level is a personal input.

**H2:** Search, Quick Tray, or type it.  
Algolia search. Serving and quantity. Calories and macros shown. Manual entry when the item is missing. A few thousand items. Accuracy being improved.

**H2:** One tap is 250 ml.  
Fixed glass. Default 8. Challenge tasks can set litres. Type an exact amount if needed.

**H2:** Mobile. Full-Mode. Not a model.  
Not on web. Not in Lite Mode. Food logging is not AI.

**FAQ**  
1. Do employees need the full HRA for calorie targets?  
2. Can they log food on the web app?  
3. Is the food database comprehensive?

**Close H2:** A meal counts the same way a run does.

## Sources

- `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` platform rules + page 3
- `vc-os/vfit-os/specs/04-nutrition/calorie-tracking.md`
- `vc-os/vfit-os/specs/04-nutrition/food-logging.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/what-are-calorie-targets.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-log-meals.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-does-food-search-work.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-log-water.md`
- `vantagefit-astro/content/en/help/employee/getting-started/using-vantage-fit-on-web.md` (water-on-web conflict)
- `vantagefit-astro/content/en/help/employee/getting-started/what-is-lite-mode.md`

## Assumptions

- Calorie math copy follows the lock (no HRA required), not the OS line that HRA is required.
- Water and food are described as mobile-only per lock, not help’s web water dialog.
- GreenScore omitted.
- No invented meals-logged or glasses-logged figure.
- Product screenshot may show a “Reduce Belly Fat” goal label. That is a live goal name in the OS macro table. Caption treats on-screen numbers as an example diary, not a customer result.

## Critic

Run after the mock. Failures found in draft and fixed:

- Did not call food logging, calorie targets, or rings AI.
- Did not claim a comprehensive food DB.
- Did not require HRA.
- Did not claim web food / water.
- Did not imply Lite Mode.
- Did not use activity level as targeting.
- Did not borrow Tata / Wipro / IBS.
- Did not show GreenScore or Org Wellness Score.
- `../styles/enterprise.css` linked. Product shots + photograph present.

**Pass.** Marketing copy in `<main>` is ~610 words including labels (in the 450–750 band). `../styles/enterprise.css` linked. Images: food shot, calorie-balance shot, desk-lunch photograph. Food logging not called AI. HRA not required. No web claim. No borrowed client stat. GreenScore omitted.
