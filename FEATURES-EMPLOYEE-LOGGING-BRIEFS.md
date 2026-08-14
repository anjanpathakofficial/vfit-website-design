# Vantage Fit — Employee logging feature pages (locked facts)

Companion to `FEATURES-EMPLOYEE-LOGGING-PROMPT.md`. This file is the **facts lock** for Group A: the three employee **logging** pages.

**This bake-off run ships only these three pages.** Do not build the hub, the other four employee pages, remaining HR pages, or enterprise pages.

Must-cover is a **proof checklist**, not a section outline. Fold items into the product UI, a photo, or a one-line label. Do not write a paragraph per bullet.

Section order is free. Word count, visual language, and images are locked by `FEATURES-EMPLOYEE-LOGGING-PROMPT.md` (existing design system, lean SaaS page, real `<img>` assets).

Source: Features Page Build Briefs (re-cut for variation bake-off), pages 1–3. Admin Dashboard is already shipped. Later groups will cover Health Metrics, Mental Wellbeing, Leagues, Personalized Programs, remaining HR, enterprise, and the hub.

---

## What kind of page this is

These are **feature pages**, not solution pages. A solution page sells an outcome ("cut absenteeism," "hit 70% participation"). A feature page proves a **capability** is real, specific, and honest. It answers "what exactly does this do, and can I trust it." Lead with the mechanic and the specific. Let the buyer connect it to their outcome. Do not turn a feature page into a generic benefits essay.

These three pages are what a buyer opens from Features → **For employees**. The reader is still **HR**. Write to a US HR / benefits leader evaluating whether employees can log honestly, without a wearable, in a way that feeds one participation number.

## The participation through-line

Vantage Fit's differentiator: **everything an employee logs counts toward the same participation score and the same challenges** — steps, a GPS run, a logged meal, a glass of water, a mindfulness session, a lab-report upload.

On these three pages that means:

- Activity Tracking is the logging surface the rest of the platform counts on.
- Fitness & Exercise is more ways to count a workout on that same surface.
- Nutrition & Hydration is food and water landing on that same surface.

A feature only earns its page by showing *how it becomes participation*. Do not tell three separate wellness stories.

## Copy bar (house rules)

- Lead with a specific insight, not a category truism. Open on something only Vantage Fit's actual mechanics let you say (e.g. "100 steps convert to one active minute," "each water tap is a fixed 250 ml glass"). Never "wellness matters."
- Banned filler: "actually," "seamlessly," "one tap away," "your people," "empower," "holistic journey." Cut them on sight.
- No formulaic problem → solution clichés. Do not open every section with "The problem? … The solution?"
- No symmetry for its own sake. Three benefits do not need three identical-length cards.
- Specifics do the work. "65 activity types" beats "comprehensive tracking."
- Sentence case for all headings and buttons. No em-dashes (use commas, periods, or restructure). No exclamation marks.
- HR is the reader. Precise, skeptical, time-poor.
- Verb-led CTAs: "Book a walkthrough," "See the dashboard," "Compare the tiers." Never "Learn more," never "Click here."
- Exact figures only. Use the spec-verified number. Never round up. Never soften a VERIFY flag into a hard claim.

## Accuracy guardrails (platform-wide)

- **Android steps** = Google Fit / selected Android device source, **not** Health Connect. Health Connect is legitimate for Android *import* of workouts, sleep, weight, heart rate, calories, distance — never for the live step pipeline.
- **Android auto-tracked task sync source** is a live contradiction (guardrail says Google Fit; code-verified challenges table says Health Connect). If a page would name the Android task-sync source, hedge or omit. Do not silently pick one.
- **HIPAA**: only "BAA provisions for HIPAA compliance," scoped to the lab-report pipeline. Write "HIPAA-guideline aligned," never "HIPAA-compliant platform."
- **SOC2 / ISO 27001**: zero spec mentions. Do not claim either.
- **GDPR**: zero spec mentions. "EU data residency available" is fine. "GDPR compliant" is not.
- **13+ languages**, never 14.
- **AI honesty**: only two platform features are genuinely AI today — the admin's **Leadership Insights** and the **lab-report extraction** pipeline. **Recommended Actions are rule-based.** Conversational AI food logging and AI content recommendations are roadmap, not live. **Squat Tracker** is camera pose-detection; you may say that. Do not call food logging, calorie targets, or activity rings "AI."
- **Camera heart-rate**: "awareness-level, not medical-grade." Never "accurate" or "clinical." It is a data source on Activity; do not build the Health Metrics page here.
- **Web-app parity**: most employee logging (food, water, GPS, squat tracker, camera HR, rings, trends) is **mobile-only**. Do not imply full web tracking. Lab-report *upload* works on web; that is an enterprise page, not this set.
- **Lite Mode** strips to steps-only. Tier-flag every Full-Mode-only feature. Fitness and Nutrition are Full-Mode only.
- **Encryption specifics** (AES-256, TLS versions): not in specs. Do not invent.
- **Activity level is not a targeting dimension.** Anywhere. It is a personal calorie input on Nutrition only.
- **Mood tracking** is private, not scored, not HR-visible. Do not mention mood on these three pages.
- **Org Wellness Score is retired.** Do not claim it, show it, explain a 20/30/30/20 mix, or publish a 0–100 / 0–~108 ceiling. Participation rate is the north-star number. Individual wellness scores are not a marketing object on these pages.
- Any research point marked **VERIFY** ships only after sign-off. If you want it, phrase as a hypothesis and flag `[VERIFY WITH PRODUCT]`.

## Shared logging physics (write once, reuse — do not contradict)

These rules are the same on all three pages. Activity states them. Fitness and Nutrition inherit them.

1. **No wearable required.** Phone sensors are enough for steps. Wearables add accuracy and extra data types.
2. **Three data sources:** automatic device sync, manual logging, camera-based tracking (squat pose detection, finger-on-camera heart rate).
3. **Step source stack:** Apple Health (iOS), Google Fit / selected Android source (Android steps), Fitbit, Garmin. Health Connect is **not** the Android step source.
4. **One primary device at a time.** Connecting Fitbit or Garmin overrides Apple Health / Google Fit as the step source. No double-counting.
5. **Step formula:** `TOTAL_STEPS = device steps + manual steps (Activity ID 63, company-toggle) + active-minute-derived steps`.
6. **Active minutes:** **100 steps = 1 active minute** (hardcoded). Used as the `move_min` challenge task. WHO 150 min/week is *context*, not a certification.
7. **Step sync** is rate-limited to a 15-second minimum. Duplicate-detection exists (95–105% of prior day within 18h; targets buggy iOS 1.5.4–1.5.7). Step normalization / capping exists in code but is **disabled globally** — do not claim it is active.
8. **Lite Mode** = steps only. Custom activities, GPS, squat tracker, food, water, rings beyond steps, and camera HR are Full-Mode.
9. **Admin sees aggregates**, never an individual's food log, GPS route, heart-rate sample, or weight.

## Proof hygiene (assigned — do not double-count)

- **100+ organizations** is the approved aggregate trust signal. Fine on any page, once, lightly.
- Every single-program client stat must be labeled to its exact program and marked VERIFY for currency before anyone would publish it.
- Do not invent customers, metrics, or capabilities.
- **Assigned for this run (do not reuse across the three pages):**
  - **Activity Tracking only:** Tata Motors **6,400+ activities logged** (VERIFY). IBS Software **100+ → 236 employees** progressive engagement (VERIFY).
  - **Fitness & Exercise only:** Tata Motors **472 outdoor GPS workouts** (VERIFY). Wipro **12,236 squats** (VERIFY). Wipro **163 yoga sessions** may sit here if you need a second labeled figure (VERIFY).
  - **Nutrition & Hydration:** no client-attributed meals or water stat. Do **not** borrow Tata / Wipro / IBS. Skip a customer-result band or mark `[Data point needed]`.
- Do **not** use Wipro mindfulness minutes on these pages (reserved for Mental Wellbeing).
- Do **not** use Brazosport 86% or Wipro 3X here (those are program / dashboard stats).

## Live contradictions (do not silently resolve)

1. **Android auto-tracked task sync source** — hedge or omit. (Step source is unambiguous: Google Fit / selected source.)
2. **Org Wellness Score** — retired. Help, OS, and old mocks still mention it. Do not ship it.
3. **Activity level as targeting** — not a dimension. Nutrition may say activity level feeds calorie math. Nobody may say HR targets by activity level.
4. **GreenScore** — proprietary quality metric. **VERIFY** whether it currently surfaces in the logging UI. Default: omit. If you mention it, one line + `[VERIFY WITH PRODUCT]`. Never call it clinically validated.
5. **47+ activity types** is a stray number. Use **65**.

## Split of ownership (so the three pages do not repeat)

| Topic | Owner page | Other two pages |
|---|---|---|
| 65 types, rings, step formula, 100 steps = 1 AM, custom activities, wheelchair, 7-Minute Workout, data integrity | Activity Tracking | Mention only if needed in one line |
| Strength, sports/cardio list, GPS + anti-cheat, workout import, squat tracker, device list (Fitbit / Garmin / Apple Watch / Samsung / 70+ apps), one-primary-device | Fitness & Exercise | Activity names the three sources; does not reprint the device catalog |
| Meal % split, BMR / macros, food search, manual food entry, water 250 ml, Quick Tray | Nutrition & Hydration | Do not preview food/water on Activity or Fitness |

## Not in this run (do not invent pages or claims from these)

- Health Metrics (vitals, sleep, HRA, BMI bands) — later employee group
- Mental Wellbeing, Wellness Leagues, Personalized Programs — later employee group
- Admin Dashboard (already built), Program Builder, Audience Targeting, Communications
- Integrations & SSO, Security & Compliance, Health Data Upload
- Features hub
- Surveys / eNPS, SOLI multi-wallet as standalone pages

---

# THE THREE PAGES

## 1. Activity Tracking — `/features/activity-tracking/`

**Covers:** The core logging surface — the three data sources, step aggregation, activity rings, custom activities, data integrity.

**Angle:** *The logging surface everything counts on.* No wearable required, and the data is honestly measured, not inflated.

**Primary keyword:** `employee activity tracking software`  
**Secondary:** "corporate wellness activity tracking app"

**Must cover**
- **65 activity types** (IDs 1–65) across Cardio & Fitness, Sports, Strength, Mind & Body, Health Logging, Nutrition, Custom, Other.
- Three data sources: automatic device sync (Apple Health, Google Fit / selected Android source, Fitbit, Garmin, Health Connect for supported *imports* only), manual logging, camera-based tracking (squat pose detection, finger-on-camera heart rate).
- Steps aggregation: `TOTAL_STEPS = device steps + manual steps (Activity ID 63, company-toggle) + active-minute-derived steps`.
- Active minutes: **100 steps = 1 active minute** (hardcoded); used as the `move_min` challenge task; WHO 150 min/week as *context*, not a certification.
- Home dashboard: 2 activity rings (Ring 1 = Steps always; Ring 2 = Active Calories **or** Active Minutes, company-configured via VC Support). Default targets 10,000 steps / 250 active calories when no challenge runs. Diary + 7-day trend graphs (mindful-minute and sleep graphs Full-Mode only).
- Data integrity: duplicate-detection (95–105% of prior day within 18h, targets buggy iOS 1.5.4–1.5.7); step sync rate-limited to a 15-second minimum.
- Custom activities (self-serve, Admin → Configuration → Activities): branded "loggable activities" (e.g. "Office Yoga") and separate adherence / habit activities (e.g. "Avoid Sugar").
- Wheelchair activity type (ID 58, GPS-trackable) — light accessibility mention.
- 7-Minute Workout: fixed 12-exercise routine, VFit-built, bundled GIFs.

**Do NOT claim**
- Android steps via Health Connect (it's Google Fit / selected source).
- "47+ activity types" — use 65.
- Step normalization / capping is active (it exists but is disabled globally).
- Full offline reliability across all logging types (only partially wired).
- Camera heart-rate as medical-grade (awareness-level only).
- Web parity for rings / trends (web has neither).
- Wearable required.

**Tier flags:** Self-serve — custom loggable / adherence activities, activity reports. **VC Support required** — active-minutes ring, manual step entry, preventing overlapping activities, Lite Mode enablement. **Lite Mode** reduces this whole surface to steps-only.

**Proof (this page only):** Tata Motors 6,400+ activities logged (VERIFY). IBS Software 100+ → 236 employees progressive engagement (VERIFY). Do not use Tata 472 GPS or Wipro squat / yoga figures here.

---

## 2. Fitness & Exercise — `/features/fitness-exercise/`

**Covers:** Strength logging, sports / cardio breadth, GPS workouts, wearable workout import, squat tracker, device connections.

**Angle:** *Beyond steps — dozens of ways to count a workout.*

**Primary keyword:** `employee fitness tracking app`  
**Secondary:** "corporate workout tracking software," "GPS workout tracking," "wearable integration"

**Must cover**
- Strength tracking, **rep-based or minute-based**: Bench Press, Squats, Deadlifts, Leg Press, Rowing, plus general Weight Training Session.
- Sports / cardio breadth (name a scannable set, not a dump): Badminton, Basketball, Boxing, Cricket, Dancing, Football, Tennis, Table Tennis, Martial Arts, Golf, Pickleball, Bowling, Kayaking, Rock Climbing, Zumba, Aerobics, HIIT, Spinning, Elliptical, Plogging.
- GPS workouts (**Run / Walk / Cycle / Wheelchair only**): live distance / pace / duration / calories, per-km / mile splits, route map + pace graph, optional social share, iOS Live Activity (Dynamic Island / Lock Screen widget).
- GPS anti-cheat, precisely: iOS filters points <100 m horizontal accuracy; Android uses a 4-method vehicle-detection system (speed patterns, location consistency, high-pace %, split analysis), min 10 m distance / 1 s gap; backend rejects average pace **< 3.5 min/km for running / walking** (each split must clear it too). **No cycling pace limit exists.**
- Workout import: iOS via Apple Health requires a **manual tap to import** (not automatic); Android via **Health Connect** (legitimate here — workout import, not step sync). Duplicate workouts auto-prevented.
- Squat Tracker: camera pose-detection, no equipment. Do not call the rest of this page AI.
- Devices: **Fitbit** and **Garmin** direct (iOS + Android); Garmin real-time push, connection **expires after 60 days**; **Apple Watch** automatic via Apple Health; **Samsung Watch** as an Android device; **70+ trusted third-party apps** feed via Apple Health (Amazfit / Zepp, Mi Band, Huawei, Nike Run Club, Strava, etc.).
- **One primary device at a time** — connecting Fitbit / Garmin overrides Apple Health / Google Fit as the step source (no double-counting).

**Do NOT claim**
- GPS / pace anti-cheat on cycling (no cycling pace limit).
- iOS workout import is automatic (manual tap required).
- Android workout import via Google Fit (it's Health Connect).
- Strength as "full workout programming" (it's rep / minute logging, not sets / RPE / progressive overload).
- Any of this in Lite Mode (steps only).
- Wearable required.
- 7-Minute Workout as a Fitness exclusive (Activity owns that bundled routine; a one-line cross-link is enough).

**Tier flags:** Full-Mode feature set; unavailable in Lite Mode. Garmin / Fitbit connections are employee self-service (admins see only aggregate device-connection stats). "Prevent simultaneous activities" and Lite Mode toggles require VC Support.

**Proof (this page only):** Tata Motors 472 outdoor GPS workouts (VERIFY). Wipro 12,236 squats (VERIFY). Optional: Wipro 163 yoga sessions (VERIFY). No multi-client benchmark — do not invent a "differentiator" stat.

---

## 3. Nutrition & Hydration — `/features/nutrition-hydration/`

**Covers:** Calorie / macro science, food logging, water logging. GreenScore only if you flag VERIFY.

**Angle:** *The wellness habit employees log most* — lead with the macro / BMR rigor, not database size.

**Primary keyword:** `employee nutrition tracking app`  
**Secondary:** "corporate wellness food logging," "employee hydration tracking"

**Must cover**
- Meal-level calorie distribution: Breakfast 25% / Lunch 35% / Snacks 10% / Dinner 30% — nutritionist-style guidance, not just a daily total.
- Science: Mifflin-St Jeor BMR; Harris-Benedict activity multipliers (Sedentary ×1.2, Light ×1.375, Moderate ×1.55, Heavy ×1.725, Very Heavy ×1.9); goal adjustment **±550 cal/day** (≈0.5 kg/week); minimum floors **Males 1,800 / Females 1,200 cal/day** (surface as a safety / trust point).
- Macro ratios by goal (P/C/F): Maintain 30/50/20, Gain 40/40/20, Lose 30/40/30, Lose Belly Fat 40/30/30.
- Calculated from the **basic onboarding health profile only** (height / weight / DOB / gender / goal / activity level) — **the full HRA is NOT required**.
- Food logging: meal-time → Algolia search or Quick Tray → serving / quantity → calories / protein / carbs / fat shown → saved against target. **Manual entry** (name + calories / macros, no DB dependency) as the candid fallback — DB is "a few thousand items currently, accuracy being improved."
- Water logging: +/− tap, each tap = **1 glass = 250 ml (fixed)**; can type an exact litres / fl-oz amount; default target **8 glasses**; challenge tasks can set custom targets (e.g. "Drink 3.0 L, 4 days this week").
- Quick Tray (frequent-foods one-tap re-log); food-suggestion submission for DB inclusion.

**Do NOT claim**
- Food DB is comprehensive (explicitly "a few thousand items," regional gaps).
- AI food logging / barcode scanning are live (both roadmap only).
- HRA is required for calorie / macro targets (it isn't).
- Food / water logging on web (both "No" on web).
- GreenScore is clinically validated. Default: omit until VERIFY.
- Any of this in Lite Mode (no food / water logging at all).
- Activity level as an HR targeting dimension (it is a personal calorie input only).

**Tier flags:** Full-Mode only; absent in Lite Mode. No admin self-serve controls specific to nutrition / hydration beyond general activity reports; no VC Support gate identified — employee-managed, always-on for Full-Mode clients.

**Proof:** None client-attributed. Do not fabricate logged-meals or water-glasses stats. Do not borrow Tata / Wipro / IBS.

---

## Sibling URLs (for internal links only — do not build these in this run)

**Hub:** `/features/`

**This set (build these):**  
`/features/activity-tracking/` · `/features/fitness-exercise/` · `/features/nutrition-hydration/`

**Other employee pages (href only):**  
`/features/health-metrics/` · `/features/mental-wellbeing/` · `/features/wellness-leagues/` · `/features/personalized-programs/`

**For HR (already built / later):**  
`/features/admin-dashboard-analytics/` · `/features/program-builder/` · `/features/audience-targeting/` · `/features/communications-nudges/`

**Enterprise (later):**  
`/features/integrations-sso/` · `/features/security-compliance/` · `/features/health-data-upload/`

Each child page should link up to `/features/` and laterally to 2–3 siblings when it earns the click. Prefer linking the other two pages in this set.
