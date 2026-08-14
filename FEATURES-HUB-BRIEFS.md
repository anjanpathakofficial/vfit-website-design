# Vantage Fit — Features hub (locked facts)

Companion to `FEATURES-HUB-PROMPT.md`. This file is the **facts lock** for Group E: the **Features hub** only.

**This bake-off run ships one page.** Do not rebuild any of the 14 child pages. Do not invent Surveys / eNPS or SOLI pages. Those capabilities exist in product but have no `/features/` slug in the locked IA.

Must-cover is a **proof checklist**, not a section outline. Fold items into the grid, a photo, or a one-line label.

Section order is free except the hub **must** show three groups of child links. Word count, visual language, and images are locked by `FEATURES-HUB-PROMPT.md`.

Source: Features Page Build Briefs (re-cut for variation bake-off), hub card, **overridden** by later locks (Org Wellness Score retired; no SOC2 / ISO / GDPR; Health Insights is whitelist-narrower than "any annual plan"). Prefer this file over live marketing.

Already shipped (href only — do not redo):

| Group | Pages |
|---|---|
| A | Activity Tracking, Fitness & Exercise, Nutrition & Hydration |
| B | Health Metrics, Mental Wellbeing, Wellness Leagues, Personalized Programs |
| HR | Admin Dashboard & Analytics, Program Builder, Audience Targeting, Communications & Nudges |
| D | Integrations & SSO, Security & Compliance, Health Data Upload |

This hub is the last page in the locked 15-page IA (1 hub + 14 children).

---

## What kind of page this is

This is a **feature hub**, not a Solutions hub and not a 15th essay. A buyer opens `/features/` from the mega-menu to see the whole platform and pick a child. It must make the **participation through-line** visible as the connective tissue across all 14 cards.

If this page could be a generic "our features" wallpaper with interchangeable cards, you have failed. If it papers over annual / whitelist / Lite gating, you have failed. If it claims an "AI-powered platform," you have failed.

## The participation through-line

Everything an employee logs counts toward the **same participation score and the same challenges** — steps, a GPS run, a logged meal, a glass of water, a mindfulness session, a lab-report upload.

The original long brief said those logs also feed "the Wellness Score." **Org Wellness Score is retired.** On the hub, the unifying idea is **one participation surface**, not a composite wellbeing score. Do not show, gate, or explain Org Wellness Score.

## Copy bar (house rules)

- Lead with a specific insight. Never "wellness matters."
- Banned filler: "actually," "seamlessly," "one tap away," "your people," "empower," "holistic journey."
- No problem → solution openers.
- Specifics do the work. Card lines carry numbers and mechanics, not adjectives.
- Sentence case. No em-dashes. No exclamation marks.
- HR is the primary reader. IT is secondary on the Enterprise column.
- Verb-led CTAs: "Book a walkthrough," "Compare the tiers." Never "Learn more."
- Exact figures only. Never soften a VERIFY flag into a hard claim.

## Accuracy guardrails (platform-wide)

- **Android steps** = Google Fit / selected source, **not** Health Connect.
- **HIPAA**: "BAA provisions for HIPAA compliance" on the lab pipeline only. "HIPAA-guideline aligned." Never "HIPAA-compliant platform."
- **SOC2 / ISO 27001 / GDPR**: do not claim. "EU data residency available" is fine.
- **13+ languages**, never 14.
- **AI honesty**: only Leadership Insights and lab-report extraction are AI. Do not call the platform AI-powered. Recommended Actions are rule-based.
- **Org Wellness Score is retired.**
- **Lite Mode** = steps only. Flag every Full-Mode-only card.
- **Web-app parity:** full experience on iOS / Android; web is limited (steps + limited manual logging + admin dashboard). Lab-report *upload* works on web (Health Data Upload only).
- **Activity level is not a targeting dimension.**
- **Mood** is private, not a hub card and not an HR metric.

## Availability model (state once, on the hub)

Use this legend. Reuse the same badge language on cards. Do not invent a fifth tier.

| Badge | Meaning | Cards that must show it |
|---|---|---|
| Self-serve | On for Full-Mode clients without an extra contract toggle | Activity (core), Fitness, Nutrition, Health Metrics (core), Mental (core library), Admin Dashboard (core), Program Builder (five formats), Targeting (standard dimensions), Communications (self-serve sends), Integrations (wearable connect) |
| Annual | Account-manager / annual-client | Wellness Leagues |
| Select-partner | Ops-enabled or whitelist, not day-one | Personalized Programs (Training Plans), health-risk targeting (needs Workforce Health), Health Data Upload, Health Insights (if mentioned at all) |
| Not in Lite Mode | Hidden or reduced to steps when Lite is on | Fitness, Nutrition, Health Metrics, Mental extras, Leagues, Programs, Health Data Upload |

**Do not** list Org Wellness Score in the annual column. **Health Insights** is whitelist-narrower than "any annual plan" — if the hub mentions it, say whitelist, not a plain annual feature.

Lite Mode: Race + `step_count` only in the builder; logging surface collapses to steps.

## Proof hygiene

- **100+ organizations** is the only approved hub stat.
- Do **not** put a single-program client figure on the hub (no Tata, Wipro, IBS, Brazosport, 3X, mindfulness minutes).
- Those stats live on child pages. The hub does not borrow them.

## Live contradictions (do not silently resolve)

1. Org Wellness Score — retired. Live site and help still mention it. Leave it off.
2. Health Insights vs "any annual plan" — whitelist-narrower. Do not pitch it as standard annual.
3. Do not add Surveys / eNPS or SOLI as 15th / 16th cards.

## The 14 cards (locked slugs + one-line descriptors)

Use these hrefs. One spec-true line each. Do not invent a 15th card. Do not merge Activity + Fitness + Nutrition back into "Activity & health tracking."

### For employees (7)

| Card | Href | One-line descriptor (you may tighten, not inflate) |
|---|---|---|
| Activity tracking | `/features/activity-tracking/` | 65 activity types. No wearable required. Honest step math. |
| Fitness & exercise | `/features/fitness-exercise/` | GPS, squat tracker, Fitbit and Garmin. One primary device. |
| Nutrition & hydration | `/features/nutrition-hydration/` | Meal targets from a basic profile. One tap = 250 ml. Full-Mode only. |
| Health metrics | `/features/health-metrics/` | Sleep, heart rate, weight, optional HRA. Next to the step count. |
| Mental wellbeing | `/features/mental-wellbeing/` | Guided sessions. Minutes count as participation, not mood. |
| Wellness leagues | `/features/wellness-leagues/` | Always-on Gold / Silver / Bronze. Annual / ops-configured. |
| Personalized programs | `/features/personalized-programs/` | Two live training plans plus a content library. Select-partner for plans. |

### For HR teams (4)

| Card | Href | One-line descriptor |
|---|---|---|
| Admin dashboard & analytics | `/features/admin-dashboard-analytics/` | Four KPI cards. The number you take upstairs is participation rate. |
| Program builder & templates | `/features/program-builder/` | Five formats. 27 task types. A challenge live before lunch. |
| Audience targeting | `/features/audience-targeting/` | Aim a challenge without seeing who is in the cohort. |
| Communications & nudges | `/features/communications-nudges/` | 29 email templates. 34+ push types. Account-manager owns the master switch. |

### Enterprise (3)

| Card | Href | One-line descriptor |
|---|---|---|
| Integrations & SSO | `/features/integrations-sso/` | Wearables employees connect. SAML and HRIS that IT sets up. |
| Security & compliance | `/features/security-compliance/` | Four regions. Aggregate-only for HR. No fake certification row. |
| Health data upload | `/features/health-data-upload/` | Lab PDF in. AI extraction. Annual / whitelist. HR sees prevalence, not people. |

---

# THE PAGE

## Hub — `/features/`

**Covers:** Every capability in one grid: For employees / For HR teams / Enterprise, linking to all 14 children. Master platform-scope page.

**Angle:** *Every capability, one platform — and everything an employee logs counts toward the same participation surface.*

**Primary keyword:** `employee wellness platform features`  
**Secondary:** "corporate wellness platform all features"

**Must cover**
- A scannable capability grid: **3 groups, 14 linked cards**, each with a one-line spec-true descriptor (table above).
- The unifying idea: one participation surface. Steps, workouts, nutrition, mindfulness, health metrics, and (where enabled) lab uploads feed the **same challenges and participation number**.
- Cross-platform reality, once: full experience on iOS / Android; web is limited (steps + limited manual logging + admin dashboard). Lab-report upload is the web exception, on the Health Data card only.
- **100+ organizations** (approved aggregate). No single-program stat.
- Availability model once at platform level, with the legend above: self-serve / annual / select-partner / not in Lite Mode.
- Health Data Upload and Leagues visibly gated in the grid. Do not let the hub look like every card is on for every client.

**Do NOT claim**
- SOC2 / ISO / GDPR / blanket-HIPAA badges.
- Every listed feature available to every client.
- "AI-powered platform."
- Org Wellness Score, individual wellness scores, or a Score Report.
- A third named Journey template, freely-on monetary rewards, or activity-level targeting.
- Surveys / eNPS or SOLI as hub cards.

**Tier flags:** The legend is required. Cards that are annual, select-partner, or not-in-Lite must wear a badge.

**Proof:** 100+ organizations only.

**Schema:** This is the **only** page that should carry `SoftwareApplication` JSON-LD (plus `WebPage` + `BreadcrumbList`; `FAQPage` if you include an FAQ). Do not put `SoftwareApplication` on a child. Optional to skip FAQ.

---

## Sibling URLs

All 14 children above. Hub is `/features/`.

Each card links down to its child. Children already link up to `/features/`. Do not build those children in this run.
