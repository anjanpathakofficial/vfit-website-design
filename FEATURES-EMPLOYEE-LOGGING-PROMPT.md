# Shared prompt — Vantage Fit employee logging feature pages (Group A)

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** paste this prompt **once** into Claude / Kimi / GPT / Grok. Each model ships **all three** pages in this group. Research shared logging physics once, then **loop page by page**. Stop when the three rows are done. Do not start Health Metrics, Mental Wellbeing, Leagues, Programs, remaining HR, enterprise, or the hub.

This is **not** a Solutions bake-off. Solutions pages sell a program outcome. These pages prove an employee **capability** is real to an HR buyer.

The last failed feature run shipped essay sites with invented brands and **zero images**. The Admin Dashboard run recovered by staying inside the existing design system, keeping copy lean, and putting real photographs and product shots on the page. Repeat that recovery. Do not repeat the essay.

---

You are an expert product-marketing designer for enterprise B2B SaaS (HR tech). You design and implement high-fidelity UI **inside an existing design system**. You do not invent a new brand for a bake-off.

You have been hired to design **Group A** of the Features IA for Vantage Fit (http://www.vantagefit.io): the three **employee logging** pages.

Vantage Fit is not a meditation brand and not a consumer fitness app. It is the system HR uses to turn everyday employee logs into one participation number. These three pages prove the logs are real: steps and activities, workouts beyond steps, food and water. The pages should feel operational, specific, a little sharp. Beautiful because the product is clear.

If a page could be swapped onto a generic wellness vendor with a find-and-replace, you have failed. If it could be mistaken for a Solutions / challenge-program page, you have failed. If it looks like a help article, a whitepaper, or a new brand, you have failed. If the three pages tell three unrelated wellness stories, you have failed.

## Goal

Design the three For-employees logging pages in the locked IA.

This is what a buyer opens from the Features mega-menu under **For employees**. It is not the homepage, not the Features hub, not a Solutions / use-case page, and not Health Metrics / Mental / Leagues / Programs.

**Ship:** three high-fidelity mocks + three short briefs.

Do **not** invent a new page-type visual language. Do **not** write a page-type theory file. Do **not** build anything outside the table below.

## Pages to ship (this run only)

Work **in this order**. Finish brief + HTML for a page before starting the next.

| # | Page | Intended URL | Angle (the one idea, not a headline you must use) | Brief filename | Mock filename |
|---|---|---|---|---|---|
| 1 | **Activity Tracking** | `/features/activity-tracking/` | The logging surface everything counts on | `ACTIVITY-TRACKING-BRIEF.md` | `vantage-fit-activity-tracking-v1.html` |
| 2 | **Fitness & Exercise** | `/features/fitness-exercise/` | Beyond steps — dozens of ways to count a workout | `FITNESS-EXERCISE-BRIEF.md` | `vantage-fit-fitness-exercise-v1.html` |
| 3 | **Nutrition & Hydration** | `/features/nutrition-hydration/` | The habit employees log most — lead with macro / BMR rigor, not DB size | `NUTRITION-HYDRATION-BRIEF.md` | `vantage-fit-nutrition-hydration-v1.html` |

Activity is the source of truth for steps, rings, Lite Mode, and the three data sources. Fitness inherits those rules and adds workouts / GPS / devices. Nutrition inherits them and adds food / water. Do not rewrite the step-source stack three times.

**Done when:** all **3** briefs and **3** HTML mocks exist in your model folder, each page follows the design system, each has real images, and a time-poor HR buyer can scan each page in under a minute.

## Loop workflow (required)

1. **Shared research first (once)**  
   Read `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (all of it). Skim help + OS specs listed below for logging, devices, food, water, GPS. Open the Admin Dashboard page reviewers already liked (`grok/vantage-fit-admin-dashboard-analytics-v1.html`) so you know the visual density to match.

2. **Then loop pages 1 → 3**  
   For each row in the table:
   - Re-read only that page card in the briefs file.
   - Decide a short SaaS structure. Must-cover is a checklist, not a section outline.
   - Write the brief.
   - Build the HTML mock.
   - Cross-link the other two slugs in this set plus `/features/`.
   - Move on only after both deliverables for the current page exist.

3. **System consistency, not sameness**  
   Share nav, footer, tokens, type, and buttons. Vary hero and proof by page. Do not clone the dashboard KPI-card story onto a mobile logging page. Do not clone Activity's rings story onto Nutrition.

4. **If you run long**  
   Prefer finishing all three at solid quality over over-polishing page 1. If interrupted, resume from the first missing filename in the table.

## Locked vs free (read this twice)

### Locked (mandatory)

- These three slugs, jobs, and angles. This order.
- Everything in `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md`: platform-wide rules **plus** each page card (must-cover, do-not-claim, tier flags, keywords, proof assignment)
- These are **feature pages**: prove the capability. Do not sell a generic wellness outcome
- Primary / secondary keywords from the brief (use them honestly in H1 / title / opener; do not stuff)
- Sentence case, no em-dashes, no exclamation marks, verb-led CTAs
- No invented customers, metrics, capabilities, certifications, or AI labels
- **The existing Vantage Fit design system** (see below). Not a new palette, not a new typeface, not a new logo mark
- **Real images.** A page with no `<img>` product or photo assets fails
- **Lean copy.** A SaaS marketing page, not a product essay
- **Org Wellness Score is retired.** Do not show it, gate it, or explain it
- **Proof assignment.** Do not put Tata 472 GPS or Wipro squats on Activity. Do not put Tata 6,400+ activities on Fitness. Nutrition gets no borrowed client stat

### Free (this is the bake-off)

- Section set and order. There is **no required 11-section spine**. Must-cover items do **not** each get a section
- How you compose each hero (photo + product shot + a short UI fragment is fine; an HTML-only phone with no photographs is not)
- Which assigned proof you use, if any. Skip a customer-result band unless the story is page-relevant and labeled correctly
- Schema / JSON-LD. Optional

The original long brief asked for 900–1,300 words and a fixed 11-section spine. **Ignore that.** That is how the essay-site failure happened. Follow this file's density rules.

## Design system (non-negotiable)

Match the system already in this repo. Do **not** invent a new brand.

From the **repo root** (main or worktree):

- `styles/enterprise.css` — tokens, type, buttons, nav, section chrome. **Link it.** Do not re-declare `--ink`, `--coral`, `--mint`, or a new font stack as the brand
- `styled-homepage/` — homepage mock: Noto Sans, coral CTAs, ink / mint / canvas, 22px radius, `.shell` / `.btn` / `.eyebrow` / `.nav` / `.mega`, photography
- `grok/vantage-fit-admin-dashboard-analytics-v1.html` — the feature page reviewers liked. **Visual peer for density and chrome.** Clone nav / footer / type / buttons. Do **not** clone its dashboard story or KPI cards onto these employee pages
- Your own `*/vantage-fit-admin-dashboard-analytics-v1.html` if you already shipped one — also a valid chrome donor
- `consolidated/vantage-fit-steps-challenge-consolidated.html` — quality bar for a Vantage Fit marketing page. Visual peer, **not** a Solutions section template

Live visual fallback: https://vantagefit.pages.dev/enterprise

**How to implement**

1. Each HTML mock **must** `<link rel="stylesheet" href="../styles/enterprise.css">` (path from inside your model folder).
2. Load Noto Sans the same way `styled-homepage/index.html` does.
3. Reuse nav / footer / button / eyebrow / shell patterns from `styled-homepage` or the Admin Dashboard page. Page-specific CSS in a small `<style>` block is fine. A second design system in that block is not.
4. Copy **chrome**, not the homepage's **facts**. The homepage mega-menu is out of date (see below). Do not copy its SOC 2 / GDPR / ISO / "activity level" targeting claims.

**Fail the page if any of these are true**

- No `../styles/enterprise.css` link
- A new brand face (serif editorial, Avenir Condensed, system UI as the identity, etc.)
- A new primary color (purple, sage, forest, electric blue) replacing coral / ink / mint
- An invented wordmark or geometric logo instead of `../styled-homepage/logo.png`
- The page would not be recognized as the same site as `styled-homepage` or the Admin Dashboard feature page

## Images (non-negotiable)

A page with zero `<img>` tags fails. CSS cards, SVG glyphs, and an HTML-drawn phone are extras, not a substitute.

**Use these local assets** (paths from inside your model folder):

| File | Use |
|---|---|
| `../styled-homepage/logo.png` | Nav wordmark |
| `../styled-homepage/logo-white.png` | Footer / dark band |
| `../styled-homepage/card-participate.jpg` | Movement / logging photography |
| `../styled-homepage/hero-man-popout-v2.png` | Optional people photography |
| `../styled-homepage/card-invite.jpg`, `card-reward.jpg`, `card-measure-generic.jpg` | Optional supporting photos |

**Required product shots** (CDN — use these, do not redraw a fake app instead of them):

Activity Tracking:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772104742/product-images-hub/v-fit/vantage-fit-activity-logging-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194234/product-images-hub/v-fit/vantage-fit-active-minutes-mobile.png
```

Fitness & Exercise:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194233/product-images-hub/v-fit/vantage-fit-activity-logging-gps-route-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772104740/product-images-hub/v-fit/vantage-fit-connected-devices-sync-mobile.png
```

Nutrition & Hydration:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772104741/product-images-hub/v-fit/vantage-fit-food-logging-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194231/product-images-hub/v-fit/vantage-fit-calorie-balance-mobile.png
```

Optional companion (challenge / participation, not the hero of these pages):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579791/product-images-hub/v-fit/vfit-challenge-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579791/product-images-hub/v-fit/vfit-overview-mobile.png
```

**Do not use** the Wellness Score desktop shots (`vantage-fit-wellness-score-desktop.png`, `vantage-fit-wellness-score-trend-desktop.png`). That score is retired.

**Minimum bar, each page**

- At least **one large product screenshot** of the relevant employee surface (from the lists above)
- At least **one photograph** (people or workplace), not a logo
- Logos do **not** count toward the image minimum
- Every `<img>` has a real `alt`
- Do not put an individual's health record, food diary with a real employee name, or lab values on screen

You may generate additional images if your tools allow it, as long as they match this brand (coral / ink / mint, Noto Sans, no fake SOC2 badges). Save generated files in your model folder and reference them with relative paths.

## Density (this is a SaaS page)

A skeptical HR buyer should get the idea in the first screen and finish the page quickly.

- **Marketing copy budget:** about **450–750 words** outside nav, footer, and labels inside a product mock. Over ~800 words of marketing copy fails
- **H1:** one line, or two short lines. Not a thesis
- **Lead:** one short paragraph under the H1. Do not restate the H1
- **Section heads:** short and specific (`100 steps. One active minute.`). Not manifesto sentences
- **Cards / steps / type lists:** one line each. If a must-cover item does not earn a line, fold it into the screenshot or a compact list
- **FAQ:** optional, max 3, only for real rollout objections you did not already answer
- **Customer-result band:** optional, and only with the proof assigned to that page
- No redundant intro lede under a headline that already said it
- No "The problem? The solution?" openers

Look at `grok/vantage-fit-admin-dashboard-analytics-v1.html` and `styled-homepage/index.html` for **how much text sits next to how much image**. Match that density, not a blog.

## What each page must prove (without writing it all out)

From `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md`. Show it. Do not narrate every bullet.

**Activity Tracking**

- 65 activity types, three sources, no wearable required
- Step formula + 100 steps = 1 active minute
- Two rings (steps always; calories or active minutes via VC Support)
- Custom loggable + adherence activities, wheelchair type, 7-Minute Workout
- Honest integrity (duplicate-detection, 15 s sync floor). Capping is **not** on
- Lite Mode = steps only. Manual steps and the active-minutes ring need VC Support
- Through-line: this is the surface everything else counts on

**Fitness & Exercise**

- Strength as rep- or minute-logging, not a programming app
- GPS for Run / Walk / Cycle / Wheelchair only, with the real anti-cheat (no cycling pace cap)
- iOS import = manual tap; Android import = Health Connect
- Squat Tracker is camera pose-detection
- Fitbit / Garmin (Garmin tokens expire at 60 days) / Apple Watch / Samsung / 70+ via Apple Health
- One primary device. Full-Mode only
- Through-line: a workout is another log on the same participation surface

**Nutrition & Hydration**

- 25 / 35 / 10 / 30 meal split, Mifflin-St Jeor, ±550 cal, 1800 / 1200 floors
- Macros by goal. Basic profile only. HRA not required
- Food search + Quick Tray + candid manual entry. DB is a few thousand items
- Water: 1 tap = 250 ml, default 8 glasses, challenge tasks can set litres
- Not on web. Not in Lite Mode. Not AI
- Through-line: a meal and a glass of water count the same way a run does

## Important: do not treat the current marketing site as the source of truth

Existing feature pages were built **pre-AI**, with incomplete product understanding. The live mega-menu is also **out of date** versus the locked IA:

- Live / homepage menu still lists Activity & health tracking as one item, still puts Reports and Health data upload under For HR, still says "activity level" targeting, still claims SOC 2 / GDPR / ISO
- Locked IA: Activity Tracking, Fitness & Exercise, and Nutrition & Hydration are three pages. Health Metrics is a later page. Communications & Nudges is the fourth HR page. Health data upload is Enterprise. Activity level is **not** a targeting dimension. Wellness Score is **retired**

Use live / legacy pages only as background. **Do not** mirror their section order, feature list, or copy.

When you reuse `styled-homepage` nav chrome, **update the Features mega-menu** to the locked IA and mark the current page:

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

Do not put Reports & exports or Health data upload in the HR column. Do not put SOC 2 / GDPR / ISO in the Enterprise column. Do not keep "Activity & health tracking" as a single merged item.

Rebuild from product truth — `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md`, help docs, OS specs — then design the pages in the existing visual system.

## Path resolution (main tree vs model worktrees)

This design repo is used from either:

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo files** (always relative to the repo root you are in):

- `FEATURES-EMPLOYEE-LOGGING-PROMPT.md` (this file)
- `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (**read this**; it is the facts lock)
- `grok/vantage-fit-admin-dashboard-analytics-v1.html` (visual peer)
- `styled-homepage/`
- `styles/enterprise.css`
- `consolidated/` — visual quality bar
- `FEATURES-HR-PROMPT.md` / `FEATURES-HR-BRIEFS.md` — previous group only. Do not rebuild Admin Dashboard

**Sibling research repos** live next to `vfit-website-design` on disk, not inside it. Depth changes by one level under `.worktrees/`:

| Resource | From main tree | From `.worktrees/<model>/` | Remote (clone if missing) |
|---|---|---|---|
| Marketing + help docs | `../vantagefit-astro` | `../../../vantagefit-astro` | https://github.com/VantageCircle/vantagefit-astro |
| HR admin dashboard | `../vc-dashboard-design` | `../../../vc-dashboard-design` | https://github.com/VantageCircle/vc-dashboard-design |
| Vantage Fit OS | `../vc-os/vfit-os` | `../../../vc-os/vfit-os` | https://github.com/VantageCircle/vfit-os |

**Resolve rule:** if a sibling path does not exist, walk up parent directories until you find the sibling (or clone it). Do not invent product claims when a source is missing — note the gap in the brief.

Pull latest `main` on each research repo before you start.

## Research sources

### 1. The facts lock (start here)

`FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` at the repo root. Read the platform-wide rules and all three page cards before you design. If help docs and OS disagree with this file on a shipping claim, **prefer this file** and flag the conflict in the page brief. Do not silently "fix" a live contradiction. If those sources still describe **Org Wellness Score**, treat it as retired and leave it off the page.

### 2. Marketing site + help docs (how it actually works)

In `vantagefit-astro`, prioritize **help content** over legacy feature YAML:

- `content/en/help/employee/health-tracking/` — log activity, GPS, food, water, squat tracker, rings, diary, 7-minute workout, calorie targets
- `content/en/help/employee/getting-started/` — devices, Health Connect vs steps, Lite Mode, wheelchair, web limits
- Case studies for **proof only**: `content/en/casestudy/` — never invent stats; never attach a case-study number this page does not own
- Nav (`src/scripts/header-data.js`) for orientation only

### 3. Vantage Fit OS (depth)

In `vc-os/vfit-os`:

- `FEATURE-INDEX.md`
- `specs/01-core-tracking/` — steps, active minutes, activity logging, connected devices
- `specs/04-nutrition/` — food logging, calorie tracking
- `specs/10-integrations/` — Fitbit, Garmin
- `specs/03-health-wellness/` — only if you need to confirm what **not** to put on these pages (HRA, vitals, mindfulness)

### 4. Admin dashboard (context only)

`vc-dashboard-design` is useful for "what HR sees" (aggregates, not individual logs). Do not turn these employee pages into a second dashboard page.

## Audience

- **Reader:** US enterprise HR / CHRO / Benefits / Wellbeing leader. Secondary: the program manager who will tell employees which app to download. IT / security is not the primary reader here
- **North star:** employee participation. These pages prove the logs that feed that number
- **Primary CTA:** Book a walkthrough. **Secondary:** only if it earns the click (See the dashboard, Compare the tiers)

## Lessons from the failed first run (do not repeat)

- Do **not** invent a visual language. Purple, sage, serif editorial, mono "receipts" as the identity, and self-contained CSS with no `enterprise.css` all failed review
- Do **not** ship a page with no photographs and no product screenshot
- Do **not** turn must-cover into an essay. A 65-type catalog dumped as body copy is help-center writing
- Do **not** open the page as a wall of UI chrome with a thesis H1 inside it
- Keep it **lean**. Short labels. One lead. Images do the proving
- A full customer-result section is **optional**
- Label non-approved figures **illustrative** or `[VERIFY WITH PRODUCT]`
- Do not force challenge-page patterns (format explorer, leaderboard integrity, race-day recap) onto a logging page
- Do **not** put Org Wellness Score on the page
- Do **not** call food logging AI
- Do **not** say Android steps come from Health Connect
- Do **not** merge Activity + Fitness + Nutrition into one mega-page

## What we want from you

1. **Research** product truth for this group (briefs + help + OS).
2. **Decide** a short SaaS-feature-page structure per page that fits the existing design system.
3. **Write** accurate, scannable copy. Specifics over adjectives. No fabricated claims.
4. **Design** three high-fidelity mocks that look like Vantage Fit, with real images.

## Deliverables

Write into **your model folder at the repo root** (same whether you are on main or in `.worktrees/<model>/`):

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

For **each** of the three pages:

1. **`{PAGE}-BRIEF.md`** — Research takeaways, why this structure, full copy deck, sources for any stats / quotes, meta title / description drafts (keywords from the briefs), critic result (pass / what you fixed). Keep the brief itself short.
2. **`vantage-fit-{slug}-v1.html`** — High-fidelity mock. Links `../styles/enterprise.css`. Uses `../styled-homepage/` images and the CDN product shots for that page. UTF-8. Responsive. Opens from the model folder. No invented brand.

Do **not** add extra research dumps or any page outside the table.

## Critic list (run on every page before you stop)

Fail the page and fix if any of these are true:

- A capability, number, customer, or certification not in the briefs / help / OS / case study is stated as fact
- Health Connect named as the Android **step** source
- Android auto-tracked **task** sync source asserted as a single vendor without a hedge
- Food logging, calorie targets, or activity rings labeled AI
- Camera heart-rate called accurate, clinical, or medical-grade
- GPS anti-cheat claimed for cycling pace
- iOS workout import described as automatic
- Food / water / GPS / rings claimed on web
- Fitness or Nutrition implied available in Lite Mode
- "47+ activity types" instead of 65
- Step normalization / capping claimed as active
- HRA required for calorie / macro targets
- Food DB called comprehensive
- GreenScore featured as clinically validated or as a live UI fact without `[VERIFY WITH PRODUCT]`
- Activity level used as an HR targeting dimension
- Mood shown or implied as HR-visible
- Org Wellness Score, a composite wellbeing score, or individual wellness scores shown or claimed as live
- HIPAA-compliant platform, SOC2, ISO, or GDPR-compliant claimed
- 14 languages
- A VERIFY item shipped as an unqualified claim
- Assigned proof used on the wrong page (Tata 472 or Wipro squats on Activity; Tata 6,400+ on Fitness; any borrowed client stat on Nutrition)
- Em-dashes, exclamation marks, "Learn more," or banned filler (`actually`, `seamlessly`, `one tap away`, `your people`, `empower`, `holistic journey`)
- The page reads as a Solutions / program-outcome page rather than a capability page
- The page does not show how this log becomes participation
- Tier / Lite / VC Support gates buried or omitted where the brief requires them
- Visual language is a new brand, or `../styles/enterprise.css` is missing
- Fewer than one product screenshot and one photograph
- Marketing copy is long enough to feel like a help article (~800+ words outside chrome)
- You built a page that is not in the table

## Quality bar

- Looks like a *designed* Vantage Fit SaaS feature page: same site as `styled-homepage` and the Admin Dashboard feature page
- A skeptical HR buyer can tell, from the first screen, what employees would log and how it counts
- Product claims traceable to the briefs, help docs, OS, or real case studies
- Enterprise tone; scannable; specific; lean; image-forward
- Mobile-conscious; accessible structure (real headings, focusable CTAs, sensible alt)
- The three pages share chrome and logging physics, and they do not repeat the same catalog
- If something material is unclear, ask; otherwise make a reasonable assumption and state it in the brief

Ask questions only if you need clarifications that would change the facts lock or the design system.

---

## First message to the agent (paste this alone if you want a short kickoff)

```
Build Group A only: Activity Tracking, Fitness & Exercise, and Nutrition & Hydration.

Read FEATURES-EMPLOYEE-LOGGING-PROMPT.md and FEATURES-EMPLOYEE-LOGGING-BRIEFS.md. Follow styles/enterprise.css and styled-homepage. Use grok/vantage-fit-admin-dashboard-analytics-v1.html as the visual density peer. Do not invent a new brand. Use the listed CDN product shots plus at least one photograph per page. Keep copy lean (450–750 words). Org Wellness Score is retired. Health Connect is not the Android step source. Do not call food logging AI.

Work in order. Write both the brief and the HTML into your model folder for each page before starting the next. Stop after the three pages. Do not build Health Metrics, Mental Wellbeing, Leagues, Programs, remaining HR, enterprise, or the hub.
```
