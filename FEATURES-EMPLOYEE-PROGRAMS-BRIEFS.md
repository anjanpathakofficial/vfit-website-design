# Vantage Fit — Employee programs feature pages (locked facts)

Companion to `FEATURES-EMPLOYEE-PROGRAMS-PROMPT.md`. This file is the **facts lock** for Group B: the four remaining **For employees** pages.

**This bake-off run ships only these four pages.** Do not rebuild Group A (Activity / Fitness / Nutrition). Do not build remaining HR, enterprise, or the hub.

Must-cover is a **proof checklist**, not a section outline. Fold items into the product UI, a photo, or a one-line label. Do not write a paragraph per bullet.

Section order is free. Word count, visual language, and images are locked by `FEATURES-EMPLOYEE-PROGRAMS-PROMPT.md`.

Source: Features Page Build Briefs (re-cut for variation bake-off), pages 4–7, **overridden** where later locks retired Org Wellness Score. Prefer this file over help docs, OS specs, and the original long brief when they still describe a live org-level Wellness Score.

Already shipped (do not redo):

- Group A — Activity Tracking, Fitness & Exercise, Nutrition & Hydration
- For HR — Admin Dashboard & Analytics

---

## What kind of page this is

These are **feature pages**, not solution pages. A solution page sells an outcome. A feature page proves a **capability** is real, specific, and honest. Lead with the mechanic. Let the buyer connect it to the outcome.

These four pages sit under Features → **For employees**. The reader is still **HR**. Write to a US HR / benefits leader evaluating whether the fuller health picture, mindfulness minutes, persistent leagues, and personal plans are real, gated honestly, and plugged into the same participation surface as steps.

## The participation through-line

Everything an employee logs counts toward the **same participation score and the same challenges** — steps, a GPS run, a logged meal, a glass of water, a mindfulness session, a lab-report upload.

On these four pages that means:

- Health Metrics: a vitals / sleep / weight / HRA update auto-creates an activity-log entry. No second form.
- Mental Wellbeing: finishing a session logs a mindfulness activity that counts like steps. That is the locked idea. Not mood.
- Wellness Leagues: always-on step tiers that outlast any one challenge. They do not replace challenge leaderboards.
- Personalized Programs: a training plan runs as a **personal** challenge; content items can be challenge tasks. Keep those two systems separate.

A feature only earns its page by showing *how it becomes participation*.

## Copy bar (house rules)

- Lead with a specific insight, not a category truism. Never "wellness matters."
- Banned filler: "actually," "seamlessly," "one tap away," "your people," "empower," "holistic journey."
- No problem → solution openers. No symmetry for its own sake.
- Specifics do the work. "30+ sessions, 1–34 min" beats "a rich mindfulness library."
- Sentence case. No em-dashes. No exclamation marks.
- HR is the reader. Precise, skeptical, time-poor.
- Verb-led CTAs: "Book a walkthrough," "See the dashboard," "Compare the tiers." Never "Learn more."
- Exact figures only. Never soften a VERIFY flag into a hard claim.

## Accuracy guardrails (platform-wide)

- **Android steps** = Google Fit / selected Android device source, **not** Health Connect. Health Connect is legitimate for Android *import* of workouts, sleep, weight, heart rate, calories, distance — never for the live step pipeline.
- **Android auto-tracked task sync source** is a live contradiction. Hedge or omit. Do not silently pick one.
- **HIPAA**: only "BAA provisions for HIPAA compliance," scoped to the lab-report pipeline. Write "HIPAA-guideline aligned," never "HIPAA-compliant platform."
- **SOC2 / ISO 27001**: do not claim. **GDPR**: do not claim. "EU data residency available" is fine.
- **13+ languages**, never 14.
- **AI honesty**: only Leadership Insights and lab-report extraction are AI. Recommended Actions are rule-based. Do not call HRA scoring, league ranking, content recommendations, or training-plan pacing "AI." Squat Tracker (Group A) is camera pose-detection; it is not this set.
- **Camera heart-rate**: "awareness-level, not medical-grade." Never "accurate" or "clinical."
- **Web-app parity**: vitals, sleep, HRA, mindfulness play, employee league UI, food, GPS are **mobile-only**. Lab-report *upload* works on web (enterprise page, not this set). Content library has a limited web view; do not imply full web parity for logging.
- **Lite Mode** strips to steps-only. Health Metrics, Mental library extras, Leagues, and Programs are not default Lite surfaces.
- **Activity level is not a targeting dimension.** Personal calorie input only (Nutrition / Health Metrics). Content targeting is by **health profile**, not activity level.
- **Mood tracking** is private, not scored, not HR-visible. Default: omit. If mentioned, one line as a private perk. Never a Mental Wellbeing hero.
- **Org Wellness Score is retired.** Do not claim it, show it, gate it, or explain a 20 / 30 / 30 / 20 mix or a 0–100 / 0–~108 ceiling. Help, OS, and the original long brief still describe it — **ignore them**. North-star number is **participation rate**.
- Encryption specifics: not in specs. Do not invent.

## How to talk about "score" on this set

This is the trap that will fail review if you get it wrong.

| Phrase | Allowed? |
|---|---|
| Participation rate / participation score (the HR north star) | Yes |
| Challenge score / leaderboard score (inside a campaign) | Yes, on Leagues only as contrast |
| HRA **personal** 0–100% fitness score + 7-band status (Critical → Excellent) | Yes, **Health Metrics only**. This is the employee's HRA result, not an org score |
| Mindfulness minutes **log as an activity** and count toward challenges / participation | Yes, **Mental Wellbeing**. This is the locked angle |
| `dailyIndex = 0.7×movement + 0.2×workout + 0.1×meditation` or "10% of the activity index, 30% of the Wellness Score" | **No.** That formula marketed the retired org score |
| Org Wellness Score, composite wellbeing score, individual wellness scores as an HR object, Score Report | **No.** Retired |
| Leagues vs Wellness Score as a live comparison of two scoring systems | **No.** Compare leagues to **challenge leaderboards** instead |

## Proof hygiene (assigned — do not double-count)

Already used in Group A. **Do not reuse:** Tata 6,400+ activities, Tata 472 GPS workouts, Wipro 12,236 squats, Wipro 163 yoga, IBS 100+ → 236.

- **100+ organizations** is the approved aggregate. Fine once, lightly.
- Label every single-program stat to its exact program. Mark VERIFY.
- **Assigned for this run:**
  - **Health Metrics only:** Tata Motors avg BMI 24 tracked (VERIFY). HRA ~20% completion, single-cohort (VERIFY). **Default-omit** Brazosport BMI ~30 → ~27 unless you also state methodology + timeframe and mark `[VERIFY WITH PRODUCT]`.
  - **Mental Wellbeing only:** Wipro Wellbeing Fest **1,980 mindfulness minutes** (VERIFY). Optional second, labeled: Tata Step & Stride **7 min avg daily** (VERIFY). Do not also dump Inbox to Inner Peace 1,279 or Step Up & Elevate 9 min on the same page. WHO "12 billion working days" — **VERIFY sourcing/date**; if used, this page only, never Programs.
  - **Wellness Leagues:** no client-attributed tier-distribution stat. Do not invent one. "7,000+ steps/day associated with significant health benefits" is **VERIFY** — do not ship as an unqualified claim.
  - **Personalized Programs:** no named-client training-plan or content-library stat. IBS 95 mental-wellness / 130 daily-mood figures are **challenge-task** stats — do not imply they measure Training Plans or the Content Library.

## Live contradictions (do not silently resolve)

1. **League rolling-average window** — legacy 21-day vs code-verified "7 or 30 days typical." Use **"a configurable rolling average window (7 or 30 days typical)."** Do not pick 21.
2. **Org Wellness Score** — retired. OS `wellness-score.md` and help still describe it. Leave it off.
3. **Activity level as targeting** — not a dimension. Product spec ("health profile") wins over legacy Content Library copy.
4. **Mood as an engagement metric** — it is not. Minutes count. Mood does not.
5. **Android task-sync source** — hedge or omit.
6. **AI-generated training-plan pacing** — a single FAQ line exists. **VERIFY.** No "AI-personalized training plans" headline.

## Split of ownership (so the four pages do not repeat)

| Topic | Owner page | Other three |
|---|---|---|
| Vitals, sleep, camera HR, weight, BMI bands, fitness goals, HRA questionnaire + personal fitness score | Health Metrics | Do not rebuild HRA on Mental or Programs |
| 7-category audio library, offline MP3, activity_id 1010, challenge-task mindfulness | Mental Wellbeing | Programs may say a plan can include rest / mindful days; do not reprint the library |
| Gold / Silver / Bronze, rolling step window, vs leaderboards, admin CSV | Wellness Leagues | Do not call challenge leaderboards "leagues" |
| Training Plans (2 live / 7 coming soon) vs Content Library (articles, videos, bites, quizzes) | Personalized Programs | Two systems on one page, visually separate |

Do not reprint Group A's 65 types, GPS anti-cheat, meal-split math, or water 250 ml. One-line cross-links are enough.

## Not in this run

- Activity Tracking, Fitness & Exercise, Nutrition & Hydration (already built — href only)
- Admin Dashboard (already built), Program Builder, Audience Targeting, Communications
- Integrations & SSO, Security & Compliance, Health Data Upload
- Features hub
- Surveys / eNPS, SOLI as standalone pages

---

# THE FOUR PAGES

## 4. Health Metrics — `/features/health-metrics/`

**Covers:** Vitals, sleep, heart rate, weight, BMI, fitness goals, HRA. Not lab reports. Not Org Wellness Score.

**Angle:** *Sleep, heart rate and weight, next to the step count* — the fuller health picture, logged with no duplicate data entry.

**Primary keyword:** `employee health metrics tracking platform`  
**Secondary:** employee health data privacy / HIPAA intent — answer with BAA-for-lab-reports + "HIPAA-guideline aligned," never a platform certification.

**Must cover**
- Vitals: blood pressure (systolic / diastolic, "120/80" parse), cholesterol, diabetes status (boolean), weight (stored in grams, shown in the user's unit), **BMI** with bands (Underweight / Normal / Overweight / Obese) + ideal-weight range.
- Sleep: bedtime + wake-time via date pickers (not just a duration field); optional manual override; wearable sleep coexists with manual entries with a confirm-before-overwrite prompt; source field distinguishes "apple-health" vs "manual." Full-Mode only; sleep trend graph Full-Mode only.
- Heart rate: (1) auto-synced from wearable, (2) camera-based (finger on camera) — **"awareness-level, not medical-grade."**
- Weight: manual (scroll picker) or wearable sync; every vitals / weight update **auto-creates an activity-log entry** (no duplicate entry). That is the participation through-line.
- Fitness goals: Lose Weight / Reduce Belly Fat / Gain Muscle / Be Fitter; recommendation compares current to ideal-weight range and *highlights* (does not restrict) a suggested goal.
- Activity Level (Not Very / Slightly / Moderately / Very Active → Sedentary / Light / Moderate / Heavy) — a **personal calorie input only, never a targeting mechanism**.
- HRA — separate, optional, deeper questionnaire → **personal** 0–100% fitness score, 7-band status (Critical → Excellent), personalized tips. **~20% completion** (single-cohort, VERIFY). Not in Lite Mode. Skipping is allowed; no one is penalized.
- Health Connect (Android) legitimately imports weight, sleep, heart rate, calories, distance — fine here (distinct from the step-source rule).

**Do NOT claim**
- Camera heart-rate "accurate" / "medical-grade."
- Broad "HIPAA-compliant" / SOC2 / ISO / GDPR.
- Lab Reports / Workforce Health as standard (premium, whitelist — page 14). Cross-link only.
- Targeting by "activity level."
- HRA required for any other feature (calorie targets use the basic profile).
- Vitals / sleep / HRA in Lite Mode or on web.
- Org Wellness Score, a 9-factor org score, baseline 50 / multiplier 1.0, or "no one is penalized" framed as a *score* story. Keep the skip-without-penalty idea on **HRA**, not on a retired org score.

**Tier flags:** Full-Mode — vitals, BMI, weight, sleep, HRA. VC Support — enabling lab reports, custom T&C, feature toggles. Absent in Lite Mode.

**Proof (this page only):** Tata Motors avg BMI 24 tracked (VERIFY). HRA ~20% completion (VERIFY). Brazosport BMI change default-omit.

---

## 5. Mental Wellbeing & Mindfulness — `/features/mental-wellbeing/`

**Covers:** Guided audio library, offline play, mindfulness-as-activity.

**Angle (LOCKED):** *It counts as participation* — meditation minutes earn toward the same challenges and participation surface as steps.

**Primary keyword:** `corporate mindfulness meditation app`  
**Secondary:** "employee meditation wellness program"

**Must cover**
- Guided audio library: 7 categories — Top Picks, Meditation, Yoga, Relaxation, Sleep, White Noise, Self-Awareness. **30+ sessions, ~1–34 min each** (legacy per-category counts, for designers not for a wall of numbers: Top Picks 6, Yoga 2, White Noise 4, Self-Awareness 4, Meditation 3, Relaxation 3, Sleep 2).
- Delivered as MP3 via CDN; **playable offline, synced later** (batch sync).
- Completing a session logs a **mindfulness activity** (`activity_id 1010`, unit minute, 0 calories) — feeds challenges and participation. Frame as "meditation minutes count," not a standalone "minutes score," and **not** the retired Wellness Score.
- Assignable as a challenge task ("complete a mindfulness session").
- Content localized (13+ languages).
- Select organizations can request additional / tailored sessions via account manager (do not name the client).

**Do NOT claim**
- Mood feeds a score or is HR-visible. Mood (5-point scale, 9 reason categories, optional comment) is personal display only. Default: omit.
- Therapy / clinical claims. It is a content library, not therapy.
- AI-personalized meditation recommendations.
- Wearable dependence (phone / app only).
- "Unlimited" / streaming library (fixed, curated catalog of 30+, not Calm / Headspace-scale).
- The retired dailyIndex / 10%-of-activity-index Wellness Score formula.

**Tier flags:** Standard — core 7-category library, offline play + sync, activity logging, challenge-task use. Account-manager / select-partner — additional / tailored sessions.

**Proof (this page only):** 30+ sessions, 7 categories, 1–34 min (spec-verified, always safe). Wipro Wellbeing Fest 1,980 min (VERIFY). Optional: Tata Step & Stride 7 min avg daily (VERIFY). WHO 12B only with `[VERIFY WITH PRODUCT]`. Do not use Inbox to Inner Peace or Step Up & Elevate on this page if you already used the Fest / Step & Stride pair.

---

## 6. Wellness Leagues — `/features/wellness-leagues/`

**Covers:** The persistent tier system, how it differs from challenge leaderboards, admin reporting.

**Angle:** *Always-on competition that outlasts any one challenge* (annual, ops-configured).

**Primary keyword:** `employee wellness league system`  
**Secondary:** "corporate fitness tier ranking"

**Must cover**
- Tiers: **Gold (>7,000 avg daily steps), Silver (5,000–7,000), Bronze (<5,000)** — default, fully configurable per company. Always say "(default, adjustable by your HR admin)."
- Basis: rolling average of daily steps. Use **"a configurable rolling average window (7 or 30 days typical)."** Treat 21-day as legacy. Flag in the page brief.
- Always-on — recalculates on the rolling window, unlike a start / end challenge.
- Week-by-week navigation with history; visual tier badges / shields (Gold `#B9924E`, Silver `#798C92`, Bronze `#7F573D` — use these in the mock).
- Admin self-serve once enabled: standings, trends (weekly / monthly / yearly), distribution by department / country, paginated reports, CSV export.
- **How it differs from leaderboards:** leaderboards rank inside a time-bound challenge and reset each campaign; leagues are persistent, company-wide, always active while enabled.

**Do NOT claim**
- League steps via Health Connect.
- Wearable required (phone pedometer suffices).
- Fixed / universal thresholds without "default, adjustable."
- Platinum / Diamond or custom tier names (Backlog).
- Department-level wellness-score rankings (Planned, not live).
- A web league UI for employees (mobile-only; admin dashboard for reporting).
- A live comparison to Org Wellness Score, or the 20 / 30 / 30 / 20 mix.

**Tier flags:** **Annual / ops-configured** — enabling leagues, thresholds, and the rolling window require the account manager; not a day-one toggle. Standard — viewing standings / trends / distribution once enabled. Disabled in Lite Mode.

**Proof:** none client-attributed. Do not invent a tier-split stat. Skip the 7,000-steps health-benefits line unless marked `[VERIFY WITH PRODUCT]`.

---

## 7. Personalized Programs — `/features/personalized-programs/`

**Covers:** Two distinct systems, kept visually separate — **Training Plans** and the **Content Library**.

**Angle:** *A plan, and the content to follow it.* Lead with Training Plans. Content Library is supporting proof.

**Primary keyword:** `structured workplace wellness plans` / "corporate wellness training programs"  
**Secondary:** "corporate wellness content library"

**Must cover — Training Plans**
- Self-service catalog, browsed by category, **VFit-managed / curated, not admin-created**.
- **9 plans: 2 Available (Couch to 5K, Walking Habit Plan), 7 Coming Soon** (Shredded in 12 Weeks, Quit Smoking in 30 Days, Ride to Thrive, Mindful Moments, + 3 more). Use exactly this split. Do not imply a large live catalog.
- Tuned at enrollment via 3 questions: (1) weeks (4–8 slider), (2) training days / week (3–6 radio), (3) which days (checkboxes) → week-by-week preview → "Start Challenge." Starts next Monday.
- Couch to 5K: linear weekly progression (~1 km → 5–6 km) with a final-week taper; rest days on unselected days.
- Runs as a **personal challenge** in the Challenges tab, tracked the same way (auto-sync or manual).
- **Only the employee can stop / quit.** HR cannot stop it, cannot create / modify plans. Admin visibility is a read-only "ongoing programs" report.
- Enabled per-company via account manager (selectively enabled — do not publish the ~11-company internal figure).
- No completion certificate (personal, not competitive) — unlike HR-run challenges.

**Must cover — Content Library**
- Types: Article, Video, Podcast, Webinar, plus **Health Bites** (interactive micro-lessons, 2–3 min).
- Content-as-task: "Watch this video," "Read this article," "Complete bite-size content" are valid challenge tasks with automatic completion tracking. That is this page's participation through-line for content.
- Quizzes: optional; auto-evaluated (radio / checkbox, all-correct-to-pass); Health Bites completion logs `activity_id 1015`; pass or fail both still log.
- Targeting: by **demographics (age, gender, health profile)** — HRA / health-profile based. Not activity level.
- Admin self-serve: create / publish / unpublish articles, videos, podcasts; create quiz questions; manage categories (Programs → On-Demand Content).
- Marketplace (partner offerings, external links + disclaimer) — one brief mention.

**Do NOT claim**
- Targeting by "activity level."
- A program calendar / admin scheduling tool for training plans (does not exist).
- AI-generated pacing as generally available. No "AI-personalized training plans" headline.
- Admins can create / customize training plans (roadmap; they cannot even disable individual plans per company today).
- AI-driven content recommendations (Backlog — rule-based / curated only).
- Training Plans = HR-run Challenges (personal / non-competitive / no certificates vs admin-run / competitive / with certificates).
- IBS mood / mental challenge-task numbers as proof of this page.

**Tier flags:** Select-partner / ops-enabled — Training Plans as a whole. Self-serve — Content Library CRUD once Programs tab enabled. Ops-required inside Content Library — Marketplace, Health Bites creation (API-only, no dashboard UI), multi-language versions, demographic targeting. Lite Mode — Programs tab only if a section is enabled; Lite clients get none by default.

**Proof:** none for this page. Do not invent completion %. Do not reuse the WHO stat.

---

## Sibling URLs (for internal links only)

**Hub:** `/features/`

**This set (build these):**  
`/features/health-metrics/` · `/features/mental-wellbeing/` · `/features/wellness-leagues/` · `/features/personalized-programs/`

**Group A (already built — href only):**  
`/features/activity-tracking/` · `/features/fitness-exercise/` · `/features/nutrition-hydration/`

**For HR:**  
`/features/admin-dashboard-analytics/` · `/features/program-builder/` · `/features/audience-targeting/` · `/features/communications-nudges/`

**Enterprise (later):**  
`/features/integrations-sso/` · `/features/security-compliance/` · `/features/health-data-upload/`

Each child page should link up to `/features/` and laterally to 2–3 siblings. Prefer the other three pages in this set.
