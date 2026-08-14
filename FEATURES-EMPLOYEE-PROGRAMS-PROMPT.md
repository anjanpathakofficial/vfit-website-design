# Shared prompt — Vantage Fit employee programs feature pages (Group B)

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** paste this prompt **once** into Claude / Kimi / GPT / Grok. Each model ships **all four** pages in this group. Research shared rules once, then **loop page by page**. Stop when the four rows are done. Do not rebuild Group A. Do not start remaining HR, enterprise, or the hub.

This is **not** a Solutions bake-off. These pages prove an employee **capability** is real to an HR buyer.

The failed feature run shipped essay sites with invented brands and zero images. Admin Dashboard and Group A recovered by staying inside the design system, keeping copy lean, and putting real photographs and product shots on the page. Repeat that. Do not write essays.

This is the highest-trap group in the IA. Mood is not the story. Org Wellness Score is retired. Leagues are not leaderboards. Training Plans are not HR challenges. Read the facts lock twice.

---

You are an expert product-marketing designer for enterprise B2B SaaS (HR tech). You design and implement high-fidelity UI **inside an existing design system**. You do not invent a new brand for a bake-off.

You have been hired to design **Group B** of the Features IA for Vantage Fit (http://www.vantagefit.io): the four remaining **For employees** pages.

Vantage Fit is not a meditation brand and not a consumer fitness app. It is the system HR uses to turn everyday employee logs into one participation number. These four pages prove the rest of that surface: the fuller health picture, mindfulness minutes that count, always-on leagues, and a personal plan plus content.

If a page could be swapped onto Calm, Headspace, or a generic wellness vendor with a find-and-replace, you have failed. If it could be mistaken for a Solutions / challenge-program page, you have failed. If mood, Org Wellness Score, or "AI-personalized plans" appear as live facts, you have failed.

## Goal

Design the four For-employees pages that are not logging surfaces.

This is what a buyer opens from Features → **For employees** after Activity / Fitness / Nutrition. It is not the homepage, not the hub, not a Solutions page, and not Group A.

**Ship:** four high-fidelity mocks + four short briefs.

Do **not** invent a new page-type visual language. Do **not** write a page-type theory file. Do **not** rebuild Activity, Fitness, Nutrition, or Admin Dashboard.

## Pages to ship (this run only)

Work **in this order**. Finish brief + HTML for a page before starting the next.

| # | Page | Intended URL | Angle (the one idea, not a headline you must use) | Brief filename | Mock filename |
|---|---|---|---|---|---|
| 1 | **Health Metrics** | `/features/health-metrics/` | Sleep, heart rate and weight, next to the step count | `HEALTH-METRICS-BRIEF.md` | `vantage-fit-health-metrics-v1.html` |
| 2 | **Mental Wellbeing & Mindfulness** | `/features/mental-wellbeing/` | It counts as participation (minutes, not mood) | `MENTAL-WELLBEING-BRIEF.md` | `vantage-fit-mental-wellbeing-v1.html` |
| 3 | **Wellness Leagues** | `/features/wellness-leagues/` | Always-on competition that outlasts any one challenge | `WELLNESS-LEAGUES-BRIEF.md` | `vantage-fit-wellness-leagues-v1.html` |
| 4 | **Personalized Programs** | `/features/personalized-programs/` | A plan, and the content to follow it | `PERSONALIZED-PROGRAMS-BRIEF.md` | `vantage-fit-personalized-programs-v1.html` |

Health Metrics owns vitals / HRA. Mental owns the audio library and activity_id 1010. Leagues own Gold / Silver / Bronze. Programs owns two systems (Training Plans vs Content Library) on one page. Do not merge them.

**Done when:** all **4** briefs and **4** HTML mocks exist in your model folder, each page follows the design system, each has real images, and a time-poor HR buyer can scan each page in under a minute.

## Loop workflow (required)

1. **Shared research first (once)**  
   Read `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` (all of it). Especially the **"How to talk about score"** table. Skim help + OS listed below. Open a Group A page reviewers already have (`grok/vantage-fit-activity-tracking-v1.html` or `grok/vantage-fit-admin-dashboard-analytics-v1.html`) so you know the visual density to match.

2. **Then loop pages 1 → 4**  
   For each row in the table:
   - Re-read only that page card in the briefs file.
   - Decide a short SaaS structure. Must-cover is a checklist, not a section outline.
   - Write the brief.
   - Build the HTML mock.
   - Cross-link the other three slugs in this set plus `/features/`. Group A slugs may be hrefs.
   - Move on only after both deliverables for the current page exist.

3. **System consistency, not sameness**  
   Share nav, footer, tokens, type, and buttons. Vary hero and proof by page. Do not clone the dashboard KPI story onto Mental. Do not clone Leagues' shields onto Programs. On Personalized Programs, **Training Plans and Content Library must look like two systems**, not one blended catalog.

4. **If you run long**  
   Prefer finishing all four at solid quality over over-polishing page 1. If interrupted, resume from the first missing filename in the table.

## Locked vs free (read this twice)

### Locked (mandatory)

- These four slugs, jobs, and angles. This order.
- Everything in `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md`: platform-wide rules **plus** each page card
- Feature pages, not Solutions pages
- Keywords from the brief (honest use in H1 / title / opener; do not stuff)
- Sentence case, no em-dashes, no exclamation marks, verb-led CTAs
- No invented customers, metrics, capabilities, certifications, or AI labels
- **The existing Vantage Fit design system.** Not a new palette, typeface, or logo
- **Real images.** A page with no `<img>` product or photo assets fails
- **Lean copy.** 450–750 words of marketing copy. The original 11-section / 1,300-word spine is **off**
- **Org Wellness Score is retired.** Do not show it, gate it, or explain it
- **Mental angle is locked:** minutes count as participation. Mood does not
- **Proof assignment.** Do not reuse Group A stats. Do not put Wipro mindfulness minutes on Programs. Leagues and Programs get no invented client stats

### Free (this is the bake-off)

- Section set and order. No required spine
- How you compose each hero (photo + product shot + a short UI fragment is fine)
- Which assigned proof you use, if any
- Schema / JSON-LD. Optional

## Design system (non-negotiable)

Match the system already in this repo. Do **not** invent a new brand.

From the **repo root** (main or worktree):

- `styles/enterprise.css` — tokens, type, buttons, nav, section chrome. **Link it.** Do not re-declare `--ink`, `--coral`, `--mint`, or a new font stack as the brand
- `styled-homepage/` — Noto Sans, coral CTAs, ink / mint / canvas, 22px radius, `.shell` / `.btn` / `.eyebrow` / `.nav` / `.mega`
- `grok/vantage-fit-activity-tracking-v1.html` and `grok/vantage-fit-admin-dashboard-analytics-v1.html` — visual peers for density and chrome. Clone nav / footer / type / buttons. Do **not** clone their stories
- Your own Group A pages in your model folder — also valid chrome donors
- `consolidated/vantage-fit-steps-challenge-consolidated.html` — quality bar. Not a Solutions template

Live visual fallback: https://vantagefit.pages.dev/enterprise

**How to implement**

1. Each HTML mock **must** `<link rel="stylesheet" href="../styles/enterprise.css">`.
2. Load Noto Sans the same way `styled-homepage/index.html` does.
3. Reuse nav / footer / button / eyebrow / shell. Page-specific CSS in a small `<style>` block is fine. A second design system is not.
4. Copy **chrome**, not homepage **facts**. Update the Features mega-menu to the locked IA (below). No SOC 2 / GDPR / ISO. No "activity level" targeting.

**Fail the page if any of these are true**

- No `../styles/enterprise.css` link
- A new brand face or a new primary color replacing coral / ink / mint
- An invented wordmark instead of `../styled-homepage/logo.png`
- The page would not be recognized as the same site as Group A / Admin Dashboard

## Images (non-negotiable)

A page with zero `<img>` tags fails. CSS cards and SVG shields are extras, not a substitute for a photograph + a product shot.

**Local assets** (paths from inside your model folder):

| File | Use |
|---|---|
| `../styled-homepage/logo.png` | Nav wordmark |
| `../styled-homepage/logo-white.png` | Footer / dark band |
| `../styled-homepage/card-participate.jpg` | Movement photography |
| `../styled-homepage/card-measure-generic.jpg` | Review / metrics photography |
| `../styled-homepage/hero-man-popout-v2.png` | Optional people photography |
| `../styled-homepage/card-invite.jpg`, `card-reward.jpg` | Optional supporting photos |

**Required product shots** (CDN — use these, do not redraw a fake app instead of them):

Health Metrics:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194229/product-images-hub/v-fit/vantage-fit-health-risk-assessment-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579791/product-images-hub/v-fit/vfit-overview-mobile.png
```

Mental Wellbeing:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194232/product-images-hub/v-fit/vantage-fit-mindfulness-session-player-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579790/product-images-hub/v-fit/vfit-mental-welbeing-mobile.png
```

Wellness Leagues (no dedicated league screenshot in the library — prove tiers with HTML shields using the locked hex colors, plus a photograph; badges shot is supporting only, do not caption it as leagues):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772104742/product-images-hub/v-fit/vantage-fit-badges-achievements-mobile.png
```

Personalized Programs:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772104742/product-images-hub/v-fit/vantage-fit-challenge-journey-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579791/product-images-hub/v-fit/vfit-challenge-mobile.png
```

**Do not use** `vantage-fit-wellness-score-desktop.png` or `vantage-fit-wellness-score-trend-desktop.png`. That score is retired.

**Minimum bar, each page**

- At least **one large product screenshot** (or, on Leagues, a large HTML tier mock plus the badges shot)
- At least **one photograph** (people or workplace), not a logo
- Logos do not count toward the minimum
- Every `<img>` has a real `alt`
- Do not put an individual's HRA answers, BMI with a real name, mood log, or lab values on screen

You may generate additional images if your tools allow it, as long as they match this brand. Save them in your model folder.

## Density (this is a SaaS page)

- **Marketing copy budget:** about **450–750 words** outside nav, footer, and labels inside a product mock. Over ~800 words fails
- **H1:** one line, or two short lines
- **Lead:** one short paragraph. Do not restate the H1
- **Section heads:** short and specific (`Minutes count. Mood does not.`)
- **FAQ:** optional, max 3
- **Customer-result band:** optional, assigned proof only
- No "The problem? The solution?"

Match Group A / Admin Dashboard density, not a blog.

## What each page must prove (without writing it all out)

From `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md`. Show it. Do not narrate every bullet.

**Health Metrics**

- Sleep as bedtime + wake-time, not a duration field
- Camera HR is awareness-level, not medical-grade
- Weight / vitals auto-create an activity-log entry
- BMI bands + highlighted (not forced) goal
- Activity level is a calorie input, not targeting
- HRA is optional; personal 0–100% + 7 bands; ~20% completion is VERIFY
- Full-Mode / mobile-only. Lab reports are a different, whitelist page
- Through-line: the health update is another log, not a second product

**Mental Wellbeing**

- 30+ sessions, 7 categories, 1–34 min, offline MP3 + later sync
- Completing a session logs activity_id 1010 and can be a challenge task
- 13+ languages. Extra sessions via account manager
- Mood omitted or one private-perk line
- Not therapy. Not AI-curated. Not unlimited streaming
- Through-line: **minutes count as participation**

**Wellness Leagues**

- Gold / Silver / Bronze defaults, adjustable
- Configurable rolling window (7 or 30 days typical)
- Always-on vs start/end challenges
- Distinct from challenge leaderboards
- Admin standings / trends / department / country / CSV once enabled
- Annual / ops-configured. No employee web UI. No wearable required
- Through-line: the same steps that feed challenges also rank the league

**Personalized Programs**

- Two systems, visually separate
- Training Plans: 2 live (Couch to 5K, Walking Habit Plan), 7 coming soon
- 3 enrollment questions, starts next Monday, personal challenge, employee can quit, HR cannot
- No training-plan certificate
- Content Library: article / video / podcast / webinar / Health Bites / quizzes; content-as-task; activity_id 1015
- Targeting by health profile, not activity level
- Training Plans = select-partner. Content CRUD = self-serve once Programs is on
- Through-line: the plan is a personal challenge; watching / reading can be a challenge task

## Important: do not treat the current marketing site as the source of truth

Live / homepage menu is out of date. Locked Features mega-menu (mark the current page):

**For employees**

1. Activity tracking
2. Fitness & exercise
3. Nutrition & hydration
4. Health metrics
5. Mental wellbeing & mindfulness
6. Wellness leagues
7. Personalized programs

**For HR teams**

1. Admin dashboard & analytics
2. Program builder & templates
3. Audience targeting
4. Communications & nudges

**Enterprise**

1. Integrations & SSO
2. Security & compliance
3. Health data upload

Do not put Reports & exports or Health data upload in the HR column. Do not put SOC 2 / GDPR / ISO in Enterprise. Do not keep "Activity & health tracking" as one merged item.

Rebuild from `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md`, help, and OS.

## Path resolution (main tree vs model worktrees)

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo files** (relative to the repo root you are in):

- `FEATURES-EMPLOYEE-PROGRAMS-PROMPT.md` (this file)
- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` (**read this**; it is the facts lock)
- `grok/vantage-fit-activity-tracking-v1.html` and `grok/vantage-fit-admin-dashboard-analytics-v1.html`
- `styled-homepage/`, `styles/enterprise.css`, `consolidated/`
- Group A prompt / briefs — previous group only. Do not rebuild those pages

**Sibling research repos** (depth changes by one level under `.worktrees/`):

| Resource | From main tree | From `.worktrees/<model>/` | Remote |
|---|---|---|---|
| Marketing + help docs | `../vantagefit-astro` | `../../../vantagefit-astro` | https://github.com/VantageCircle/vantagefit-astro |
| HR admin dashboard | `../vc-dashboard-design` | `../../../vc-dashboard-design` | https://github.com/VantageCircle/vc-dashboard-design |
| Vantage Fit OS | `../vc-os/vfit-os` | `../../../vc-os/vfit-os` | https://github.com/VantageCircle/vfit-os |

If a sibling path does not exist, walk up until you find it (or clone it). Do not invent claims. Pull latest `main` on each research repo before you start.

## Research sources

### 1. The facts lock (start here)

`FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md`. If help or OS disagree on a shipping claim, **prefer this file** and flag the conflict in the page brief. If those sources still describe **Org Wellness Score**, it is retired.

### 2. Help docs

In `vantagefit-astro`:

- `content/en/help/employee/health-tracking/` — sleep, weight, heart rate, HRA, My Health, mood (to confirm it is private), wellness leagues
- `content/en/help/employee/programs/` — training plans, content, quizzes, Health Bites, marketplace
- Case studies for **assigned proof only**: `content/en/casestudy/`

### 3. Vantage Fit OS

- `FEATURE-INDEX.md`
- `specs/03-health-wellness/` — HRA, vitals, mindfulness. **`wellness-score.md` is stale for marketing.**
- `specs/02-challenges-gamification/leagues.md`
- `specs/06-content-education/`
- `specs/07-training-programs/personal-training-programs.md`

### 4. Admin dashboard (Leagues reporting only)

`vc-dashboard-design` / `docs/leagues-ux-prototype/` — what HR sees once leagues are enabled. Do not turn the employee Leagues page into a second Admin Dashboard.

## Audience

- **Reader:** US enterprise HR / CHRO / Benefits / Wellbeing leader
- **North star:** employee participation
- **Primary CTA:** Book a walkthrough. Secondary only if it earns the click

## Lessons (do not repeat)

- Do not invent a visual language or skip `enterprise.css`
- Do not ship a page with no photograph and no product screenshot
- Do not turn must-cover into an essay
- Do not put Org Wellness Score on any page
- Do not make mood the Mental Wellbeing story
- Do not call Training Plans AI-personalized
- Do not conflate leagues with leaderboards, or Training Plans with HR challenges
- Do not rebuild Group A inside this run
- Label VERIFY figures. Do not reuse Group A stats

## What we want from you

1. **Research** product truth for this group (briefs + help + OS).
2. **Decide** a short SaaS structure per page.
3. **Write** accurate, scannable copy.
4. **Design** four high-fidelity mocks that look like Vantage Fit, with real images.

## Deliverables

Write into **your model folder at the repo root**:

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

For **each** of the four pages:

1. **`{PAGE}-BRIEF.md`** — Research takeaways, why this structure, copy deck, sources, meta title / description, critic result. Keep it short.
2. **`vantage-fit-{slug}-v1.html`** — High-fidelity mock. Links `../styles/enterprise.css`. Uses `../styled-homepage/` images and the CDN shots for that page. UTF-8. Responsive. Opens from the model folder.

Do **not** add extra research dumps or any page outside the table.

## Critic list (run on every page before you stop)

Fail the page and fix if any of these are true:

- A capability, number, customer, or certification not in the briefs / help / OS / case study is stated as fact
- Org Wellness Score, a 20 / 30 / 30 / 20 mix, a 0–~108 ceiling, or the dailyIndex Wellness Score formula shown or claimed as live
- Mood treated as scored, HR-visible, or the Mental Wellbeing hero
- Camera heart-rate called accurate, clinical, or medical-grade
- Health Connect named as the Android **step** source
- Activity level used as an HR targeting or content-targeting dimension
- HRA required for calorie targets or any other feature
- Lab reports / Workforce Health pitched as standard
- Therapy / clinical claim on Mental Wellbeing
- Mindfulness library called unlimited / streaming / AI-curated
- League window stated as a fixed 21 days
- League thresholds stated as universal without "default, adjustable"
- Platinum / Diamond tiers, or a web employee league UI
- Training Plans implied as a large live catalog (must be 2 available / 7 coming soon)
- Admins can create / stop / customize training plans
- Training Plans given completion certificates
- Training Plans conflated with HR-run challenges
- AI-personalized training plans or AI content recommendations claimed as live
- HIPAA-compliant platform, SOC2, ISO, or GDPR-compliant claimed
- 14 languages
- A VERIFY item shipped as an unqualified claim
- Assigned proof used on the wrong page, or Group A stats reused
- IBS mood / mental challenge-task numbers used as Training Plan or Content Library proof
- Em-dashes, exclamation marks, "Learn more," or banned filler
- The page reads as a Solutions page rather than a capability page
- The page does not show how this becomes participation
- Tier / Lite / annual / account-manager gates buried or omitted
- Visual language is a new brand, or `../styles/enterprise.css` is missing
- Fewer than one product screenshot (or Leagues tier mock) and one photograph
- Marketing copy ~800+ words outside chrome
- You built a page that is not in the table

## Quality bar

- Same site as Group A and Admin Dashboard
- A skeptical HR buyer can tell, from the first screen, what this is and how it counts
- Claims traceable to the briefs, help, OS, or real case studies
- Four pages share chrome and do not repeat each other's catalogs
- Personalized Programs visibly separates Training Plans from Content Library
- If something material is unclear, ask; otherwise assume and state it in the brief

Ask questions only if you need clarifications that would change the facts lock or the design system.

---

## First message to the agent (paste this alone if you want a short kickoff)

```
Build Group B only: Health Metrics, Mental Wellbeing, Wellness Leagues, and Personalized Programs.

Read FEATURES-EMPLOYEE-PROGRAMS-PROMPT.md and FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md. Follow styles/enterprise.css and styled-homepage. Use grok/vantage-fit-activity-tracking-v1.html (or grok/vantage-fit-admin-dashboard-analytics-v1.html) as the visual density peer. Do not invent a new brand. Use the listed CDN product shots plus at least one photograph per page. Keep copy lean (450–750 words).

Org Wellness Score is retired. Mental Wellbeing is minutes-as-participation, not mood. Leagues are not leaderboards and are annual / ops-configured. Training Plans are 2 live / 7 coming soon, employee-quit-only, not HR challenges. Do not rebuild Activity, Fitness, Nutrition, or Admin Dashboard.

Work in order. Write both the brief and the HTML into your model folder for each page before starting the next. Stop after the four pages.
```
