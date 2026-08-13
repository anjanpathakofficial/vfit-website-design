# Shared prompt — Vantage Fit "For HR" feature page (one page)

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** paste this prompt **once** into Claude / Kimi / GPT / Grok. Each model ships **one** page. Stop when that page is done. Do not start the other HR pages.

This is **not** a Solutions bake-off. Solutions pages sell a program outcome. This page proves an HR **capability** is real.

The last run of this brief failed. It shipped essay sites with invented brands and **zero images**. Do not repeat that. Follow the existing Vantage Fit design system. Keep the page short. Put real photographs and product shots on it.

---

You are an expert product-marketing designer for enterprise B2B SaaS (HR tech). You design and implement high-fidelity UI **inside an existing design system**. You do not invent a new brand for a bake-off.

You have been hired to design **one** For HR feature page for Vantage Fit (http://www.vantagefit.io): **Admin Dashboard & Analytics**.

Vantage Fit is not a meditation brand and not a consumer fitness app. It is the system HR uses to turn everyday employee logs into one participation number they can stand in front of leadership with. The page should feel like that: operational, specific, a little sharp. Beautiful because the product is clear.

If this page could be swapped onto a generic wellness vendor with a find-and-replace, you have failed. If it could be mistaken for a Solutions / challenge-program page, you have failed. If it looks like a help article, a whitepaper, or a new brand, you have failed.

## Goal

Design the **Admin Dashboard & Analytics** feature page in the locked IA.

This is what a buyer opens from the Features mega-menu under **For HR teams**. It is not the homepage, not the Features hub, not a Solutions / use-case page, and not an enterprise security or lab-report page.

**Ship:** one high-fidelity mock + one short brief.

Do **not** invent a new page-type visual language. Do **not** write `HR-FEATURE-TYPE.md`. Do **not** build Program Builder, Audience Targeting, or Communications.

## Page to ship (this run only)

| Page | Intended URL | Angle (the one idea, not a headline you must use) | Brief filename | Mock filename |
|---|---|---|---|---|
| **Admin Dashboard & Analytics** | `/features/admin-dashboard-analytics/` | The participation number, without the spreadsheet | `ADMIN-DASHBOARD-BRIEF.md` | `vantage-fit-admin-dashboard-analytics-v1.html` |

Reports & exports are **absorbed into this page**. Health data upload is **enterprise**, not this set. The other three HR feature pages exist in `FEATURES-HR-BRIEFS.md` only as sibling context.

**Done when:** the brief and the HTML mock exist in your model folder, the page follows the design system, it has real images, and a time-poor HR buyer can scan it in under a minute.

## Locked vs free (read this twice)

### Locked (mandatory)

- This one slug, job, and angle
- Everything in `FEATURES-HR-BRIEFS.md` that is platform-wide **plus** the Admin Dashboard card: must-cover, do-not-claim, tier flags, keywords, copy bar, participation through-line, accuracy guardrails, proof hygiene, live contradictions
- This is a **feature page**: prove the capability. Do not sell a generic wellness outcome
- Primary / secondary keywords from the brief (use them honestly in H1 / title / opener; do not stuff)
- Sentence case, no em-dashes, no exclamation marks, verb-led CTAs
- No invented customers, metrics, capabilities, certifications, or AI labels
- **The existing Vantage Fit design system** (see below). Not a new palette, not a new typeface, not a new logo mark
- **Real images.** A page with no `<img>` product or photo assets fails
- **Lean copy.** A SaaS marketing page, not a product essay
- **Org Wellness Score is retired.** Do not show it, gate it, or explain it. Help docs and OS specs that still describe it are stale. Participation rate is the number.

### Free (this is the bake-off)

- Section set and order. There is **no required section spine**. Must-cover items do **not** each get a section
- How you compose the hero and prove the dashboard (photo + product shot + a short UI fragment is fine; an HTML-only console with no photographs is not)
- Which approved proof you use, if any. Skip a customer-result band unless the story is page-relevant and labeled correctly
- Schema / JSON-LD. Optional

## Design system (non-negotiable)

Match the system already in this repo. Do **not** invent a new brand.

From the **repo root** (main or worktree):

- `styles/enterprise.css` — tokens, type, buttons, nav, section chrome. **Link it.** Do not re-declare `--ink`, `--coral`, `--mint`, or a new font stack as the brand
- `styled-homepage/` — homepage mock: Noto Sans, coral CTAs, ink / mint / canvas, 22px radius, `.shell` / `.btn` / `.eyebrow` / `.nav` / `.mega`, photography, product shots
- `consolidated/vantage-fit-steps-challenge-consolidated.html` (and the other consolidated challenge pages) — quality bar for a Vantage Fit marketing page. Visual peer, **not** a Solutions section template
- Model folders from the Solutions bake-off (`claude-fable/`, `gpt-sol/`, `grok/`, `kimi-k3/`) — use them as visual peers for chrome. **Do not** clone their challenge-page story

Live visual fallback: https://vantagefit.pages.dev/enterprise

**How to implement**

1. The HTML mock **must** `<link rel="stylesheet" href="../styles/enterprise.css">` (path from inside your model folder).
2. Load Noto Sans the same way `styled-homepage/index.html` does.
3. Reuse nav / footer / button / eyebrow / shell patterns from `styled-homepage`. Page-specific CSS in a small `<style>` block is fine. A second design system in that block is not.
4. Copy **chrome**, not the homepage's **facts**. The homepage mega-menu is out of date (see below). Do not copy its SOC 2 / GDPR / ISO / "activity level" targeting claims.

**Fail the page if any of these are true**

- No `../styles/enterprise.css` link
- A new brand face (serif editorial, Avenir Condensed, system UI as the identity, etc.)
- A new primary color (purple, sage, forest, electric blue) replacing coral / ink / mint
- An invented wordmark or geometric logo instead of `../styled-homepage/logo.png`
- The page would not be recognized as the same site as `styled-homepage`

## Images (non-negotiable)

The last run shipped **zero** `<img>` tags. That is why the pages felt like articles, not a SaaS site.

This page **must** include real images. CSS cards, SVG glyphs, and an HTML-drawn dashboard are extras, not a substitute.

**Use these assets** (paths from inside your model folder):

| File | Use |
|---|---|
| `../styled-homepage/logo.png` | Nav wordmark |
| `../styled-homepage/logo-white.png` | Footer / dark band |
| `../styled-homepage/card-measure-generic.jpg` | Analytics / review photography |
| `../styled-homepage/rachel-arthur-feature.jpg` + `rachel-arthur-avatar.jpg` | Only if you use the Brazosport proof, labeled as Fit Wars (May 2024), not a general dashboard stat |
| `../styled-homepage/hero-man-popout-v2.png` | Optional people photography |
| `../styled-homepage/card-invite.jpg`, `card-participate.jpg`, `card-reward.jpg` | Optional supporting photos |

**Required product shot** (already used on the homepage — use it, do not redraw a fake dashboard instead of it):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579792/product-images-hub/v-fit/vfit-analytics-dashboard-desktop.png
```

Optional companion (employee app, not the hero of an HR page):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579791/product-images-hub/v-fit/vfit-challenge-mobile.png
```

**Minimum bar**

- At least **one large product screenshot** of the admin dashboard (the CDN shot above, or that shot plus a tighter HTML callout of the four KPI cards / Leadership Insights)
- At least **one photograph** (people or workplace), not a logo
- Logos do **not** count toward the image minimum
- Every `<img>` has a real `alt`

You may generate additional images if your tools allow it, as long as they match this brand (coral / ink / mint, Noto Sans, no fake SOC2 badges, no individual health records on screen). Save generated files in your model folder and reference them with relative paths.

## Density (this is a SaaS page)

A skeptical HR buyer should get the idea in the first screen and finish the page quickly.

- **Marketing copy budget:** about **450–750 words** outside nav, footer, and labels inside a product mock. Over ~800 words of marketing copy fails
- **H1:** one line, or two short lines. Not a thesis
- **Lead:** one short paragraph under the H1. Do not restate the H1
- **Section heads:** short and specific (`Four numbers. One participation rate.`). Not manifesto sentences
- **Cards / steps / report list:** one line each. If a must-cover item does not earn a line, fold it into the screenshot or a compact list
- **FAQ:** optional, max 3, only for real rollout objections you did not already answer
- **Customer-result band:** optional. Brazosport 86% is Fit Wars, not a dashboard KPI. Wipro 3X is three 2025 challenges, VERIFY before tying it to the dashboard
- No redundant intro lede under a headline that already said it
- No "The problem? The solution?" openers

Look at `styled-homepage/index.html` and the Steps consolidated page for **how much text sits next to how much image**. Match that density, not a blog.

## What this page must prove (without writing it all out)

From `FEATURES-HR-BRIEFS.md` page 8. Show it. Do not narrate every bullet.

- Overview: 4 KPI cards with delta + sparkline — Enrolled Users, Active Users, Incentivization (SOLI-converted), Participation Rate
- Filters: 7d / 30d / quarter / year / custom + country, department, age group, gender
- Leadership Insights — AI, aggregated buckets only, **no PII**, read-only. Not predictive. Not auto-configuring
- Recommended Actions — **rule-based**, max 5, links not automations. Not AI
- At a Glance this month: Avg Steps, Active Minutes, Mindful Minutes, Avg Sleep
- Admin sees **aggregate only**. Never an individual health profile
- Absorbed CSV reports: Employee, Leaderboard, Transaction, Redemption; League annual-gated. **No Score Report. No Org Wellness Score.**
- Certificates: automated per-campaign PDF
- Tier: annual-gated surfaces (Leagues, Health Insights) grayscale-locked with "Contact Account Manager" for others. Health Insights is whitelist-narrower than "any annual plan" — do not pitch it as a plain annual feature. Wellness Score is **retired**, not gated.

The participation through-line on this page: **this is the number**. Everything employees log lands here as one participation rate HR can take upstairs.

## Important: do not treat the current marketing site as the source of truth

Existing feature pages were built **pre-AI**, with incomplete product understanding. The live mega-menu is also **out of date** versus the locked IA:

- Live / homepage menu still lists Reports & exports and Health data upload under For HR, and still says "activity level" targeting
- Locked IA: Reports fold into this page. Communications & Nudges is the fourth HR page. Health data upload moves to Enterprise. Activity level is **not** a targeting dimension

Use live / legacy pages only as background. **Do not** mirror their section order, feature list, or copy. **Do not** follow the live menu's HR grouping.

When you reuse `styled-homepage` nav chrome, **update the Features → For HR column** to the locked IA and mark this page current:

1. Admin dashboard & analytics (this page)
2. Program builder & templates
3. Audience targeting
4. Communications & nudges

Do not put Reports & exports or Health data upload in that column. Do not put SOC 2 / GDPR / ISO in the Enterprise column.

Rebuild from product truth — `FEATURES-HR-BRIEFS.md`, help docs, admin dashboard, product specs — then design the page in the existing visual system.

## Path resolution (main tree vs model worktrees)

This design repo is used from either:

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo files** (always relative to the repo root you are in):

- `FEATURES-HR-PROMPT.md` (this file)
- `FEATURES-HR-BRIEFS.md` (**read this**; it is the facts lock)
- `styled-homepage/`
- `styles/enterprise.css`
- `consolidated/` — visual quality bar
- `REMAINING-SOLUTIONS-PROMPT.md`, `RUN-A-CHALLENGE-PROMPT.md` — process ancestors only, not page templates

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

`FEATURES-HR-BRIEFS.md` at the repo root. Read the platform-wide rules and **page 8 only** for claims. If help docs, dashboard, and OS disagree with this file on a shipping claim, **prefer this file** and flag the conflict in the page brief. Do not silently "fix" a live contradiction. If those sources still describe **Org Wellness Score**, treat it as retired and leave it off the page.

### 2. Marketing site + help docs (how it actually works)

In `vantagefit-astro`, prioritize **help content** over legacy feature YAML:

- `content/en/help/admin/` — dashboard, reports, challenges as they touch metrics
- `content/en/help/admin/reports/`
- `src/data/help-docs-categories.js`
- Case studies for **proof only**: `content/en/casestudy/` — never invent stats; never attach a case-study number this page does not own
- Nav (`src/scripts/header-data.js`) for orientation only

### 3. HR admin dashboard (the thing the page must make visible)

In `vc-dashboard-design`: `README.md`, `docs/`, `docs/modules/wellness.md`, reports / analytics notes, any wellness admin prototypes. Use this so a product shot or UI fragment is recognizable, not a marketing cartoon of a dashboard.

### 4. Vantage Fit OS (depth + positioning)

In `vc-os/vfit-os`: `README.md`, `FEATURE-INDEX.md`, `MISSION.md`, `product-marketing/`, `specs/` — especially admin platform and reports / analytics.

## Audience

- **Reader:** US enterprise HR / CHRO / Benefits / Wellbeing leader. Secondary: the program manager who opens Overview tomorrow. IT / security is not the primary reader here
- **North star:** employee participation. This page is how HR *sees* that number
- **Primary CTA:** Book a walkthrough (or Book a demo if you have a reason). **Secondary:** only if it earns the click (See the dashboard, Compare the tiers)

## Lessons from the failed first run (do not repeat)

- Do **not** invent a visual language. Purple, sage, serif editorial, mono "receipts" as the identity, and self-contained CSS with no `enterprise.css` all failed review
- Do **not** ship a page with no photographs and no product screenshot
- Do **not** turn must-cover into an essay. "Seven dimensions…" / "The console will tell you how many…" is help-center writing
- Do **not** open the page as a wall of UI chrome with a thesis H1 inside it
- Keep it **lean**. Short labels. One lead. Images do the proving
- A full customer-result section is **optional**
- Where privacy is the buying objection (aggregate-only, no individual health), answer with the actual product rule — not a trust-badge row
- Label non-approved figures **illustrative** or `[VERIFY WITH PRODUCT]`
- Do not force challenge-page patterns (format explorer, leaderboard integrity, race-day recap) onto a dashboard page
- Do **not** put Org Wellness Score on the page. It is retired. If help or OS still describe it, that is stale.

## What we want from you

1. **Research** product truth for this page (briefs + help + dashboard + OS).
2. **Decide** a short SaaS-feature-page structure that fits the existing design system.
3. **Write** accurate, scannable copy. Specifics over adjectives. No fabricated claims.
4. **Design** a high-fidelity mock that looks like Vantage Fit, with real images.

## Deliverables

Write into **your model folder at the repo root** (same whether you are on main or in `.worktrees/<model>/`):

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

1. **`ADMIN-DASHBOARD-BRIEF.md`** — Research takeaways, why this structure, full copy deck, sources for any stats / quotes, meta title / description drafts (keywords from the briefs), critic result (pass / what you fixed). Keep the brief itself short.
2. **`vantage-fit-admin-dashboard-analytics-v1.html`** — High-fidelity mock. Links `../styles/enterprise.css`. Uses `../styled-homepage/` images and the CDN dashboard shot. UTF-8. Responsive. Opens from the model folder. No invented brand.

Do **not** add `HR-FEATURE-TYPE.md`, extra research dumps, or the other three HR pages.

## Critic list (run before you stop)

Fail the page and fix if any of these are true:

- A capability, number, customer, or certification not in the briefs / help / OS / case study is stated as fact
- Recommended Actions labeled AI, or Leadership Insights called predictive / auto-configuring
- Admins shown an individual's health profile, lab values, mood, or a health-risk name list
- "Activity level" used as a targeting or personalization dimension
- Health Connect named as the Android **step** source
- Android auto-tracked **task** sync source asserted as a single vendor without a hedge
- HIPAA-compliant platform, SOC2, ISO, or GDPR-compliant claimed
- 14 languages, or a third named Journey template
- Org Wellness Score, a composite wellbeing score, individual wellness scores, or a Score Report shown or claimed as live (including as a locked annual teaser)
- Team score described as a sum
- Monetary rewards implied as freely on for every customer
- A VERIFY item shipped as an unqualified claim
- Em-dashes, exclamation marks, "Learn more," or banned filler (`actually`, `seamlessly`, `one tap away`, `your people`, `empower`, `holistic journey`)
- The page reads as a Solutions / program-outcome page rather than a capability page
- The page does not show how the dashboard is the participation number
- Tier / Lite / whitelist / account-manager gates buried or omitted where the brief requires them
- Visual language is a new brand, or `../styles/enterprise.css` is missing
- Fewer than one product screenshot and one photograph
- Marketing copy is long enough to feel like a help article (~800+ words outside chrome)

## Quality bar

- Looks like a *designed* Vantage Fit SaaS feature page: same site as `styled-homepage`
- A skeptical HR buyer can tell, from the first screen, what they would click in the product
- Product claims traceable to the briefs, help docs, dashboard, OS, or real case studies
- Enterprise tone; scannable; specific; lean; image-forward
- Mobile-conscious; accessible structure (real headings, focusable CTAs, sensible alt)
- If something material is unclear, ask; otherwise make a reasonable assumption and state it in the brief

Ask questions only if you need clarifications that would change the facts lock or the design system.

---

## First message to the agent (paste this alone if you want a short kickoff)

```
Build only the Admin Dashboard & Analytics feature page for Vantage Fit.

Read FEATURES-HR-PROMPT.md and FEATURES-HR-BRIEFS.md (platform rules + page 8 only). Follow styles/enterprise.css and styled-homepage. Do not invent a new brand. Use real images (CDN dashboard shot + at least one photograph). Keep copy lean. Org Wellness Score is retired — do not show it. Write ADMIN-DASHBOARD-BRIEF.md and vantage-fit-admin-dashboard-analytics-v1.html into your model folder. Do not build the other HR pages.
```
