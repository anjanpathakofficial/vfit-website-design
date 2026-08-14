# Shared prompt — Vantage Fit Features hub (Group E)

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** paste this prompt **once** into Claude / Kimi / GPT / Grok. Each model ships **one** page: the Features hub. Stop when that page is done. Do not rebuild any child feature page. Do not invent Surveys / eNPS or SOLI pages.

This is **not** a Solutions hub. Solutions sell a program outcome. This page is the **index of capabilities** — 14 locked children, one participation through-line, honest gating.

The failed feature run shipped essay sites with invented brands, zero images, and fake certification badges. Groups A–D recovered by staying inside the design system, keeping copy lean, and putting real photographs and product shots on the page. Repeat that. The hub is a directory, not a 1,300-word platform essay.

This is the **last** page in the locked 15-page IA (1 hub + 14 children). All 14 children already exist in the model folders. Link them. Do not rewrite them.

---

You are an expert product-marketing designer for enterprise B2B SaaS (HR tech). You design and implement high-fidelity UI **inside an existing design system**. You do not invent a new brand for a bake-off.

You have been hired to design the **Features hub** for Vantage Fit (http://www.vantagefit.io).

Vantage Fit is not a meditation brand. It is the system HR uses to turn everyday employee logs into one participation number. The hub's job is to make that through-line visible across 14 cards, and to say which cards are self-serve, annual, select-partner, or absent in Lite Mode.

If this page could be swapped onto a generic wellness vendor with a find-and-replace, you have failed. If every card looks equally available, you have failed. If it claims an AI-powered platform or wears SOC2 / ISO / GDPR badges, you have failed.

## Goal

Design `/features/` — the master platform-scope page.

This is what a buyer opens from the Features mega-menu before picking a child. It is not the homepage, not a Solutions hub, and not a 15th feature essay.

**Ship:** one high-fidelity mock + one short brief.

Do **not** invent a new page-type visual language. Do **not** write a page-type theory file. Do **not** rebuild any child.

## Page to ship (this run only)

| Page | Intended URL | Angle (the one idea, not a headline you must use) | Brief filename | Mock filename |
|---|---|---|---|---|
| **Features hub** | `/features/` | Every capability, one platform — everything logged counts toward the same participation surface | `FEATURES-HUB-BRIEF.md` | `vantage-fit-features-hub-v1.html` |

**Done when:** the brief and the HTML mock exist in your model folder, the page follows the design system, it has real images, all 14 cards link to the locked slugs, the tier legend is visible, and a time-poor HR buyer can scan the grid in under a minute.

## Locked vs free (read this twice)

### Locked (mandatory)

- This one slug and job
- Everything in `FEATURES-HUB-BRIEFS.md`: 14 cards, descriptors, legend, guardrails, proof
- Feature hub, not a Solutions hub
- Keywords from the brief (honest use in H1 / title / opener; do not stuff)
- Sentence case, no em-dashes, no exclamation marks, verb-led CTAs
- No invented customers, metrics, capabilities, or certifications
- **The existing Vantage Fit design system**
- **Real images**
- **Lean copy.** 450–750 words outside nav, footer, and card labels. The original 11-section / 1,300-word spine is **off**
- **Org Wellness Score is retired** — do not show it in the through-line or the annual column
- **14 cards, 3 groups.** No 15th card
- **Tier legend** on the page
- **`SoftwareApplication` JSON-LD on this page only** (plus `WebPage` + `BreadcrumbList`)

### Free (this is the bake-off)

- How you compose the hero (photo + a short through-line + the grid starting in the first or second screen)
- Card layout (3 columns, stacked groups, etc.) as long as the three groups stay distinct
- FAQ: optional, max 3
- How you draw the tier badges

## Design system (non-negotiable)

Match the system already in this repo.

- `styles/enterprise.css` — **link it**. Do not re-declare `--ink`, `--coral`, `--mint`, or a new font stack
- `styled-homepage/` — Noto Sans, coral CTAs, ink / mint / canvas, 22px radius, `.shell` / `.btn` / `.eyebrow` / `.nav` / `.mega`
- `grok/vantage-fit-admin-dashboard-analytics-v1.html` — visual peer for chrome and density
- Child pages already in your model folder — **link them** with relative hrefs such as `vantage-fit-activity-tracking-v1.html` (and the other 13 mocks). The intended public URLs in the briefs are for copy / schema. The comparison mock must open the sibling HTML files.
- `consolidated/vantage-fit-steps-challenge-consolidated.html` — quality bar, not a Solutions template

Live visual fallback: https://vantagefit.pages.dev/enterprise

**How to implement**

1. The HTML mock **must** `<link rel="stylesheet" href="../styles/enterprise.css">`.
2. Load Noto Sans the same way `styled-homepage/index.html` does.
3. Reuse nav / footer / button / eyebrow / shell. Page-specific CSS in a small `<style>` block is fine. A second design system is not.
4. Update the Features mega-menu to the locked IA (below). Mark Features (or the hub) current. **No SOC 2 / GDPR / ISO** in Enterprise or footer. No "activity level" targeting.

**Fail the page if any of these are true**

- No `../styles/enterprise.css` link
- A new brand face or a new primary color
- An invented wordmark instead of `../styled-homepage/logo.png`
- A trust-badge row with SOC2 / ISO / GDPR / HIPAA-compliant-platform
- Fewer or more than 14 feature cards
- The page would not be recognized as the same site as Admin Dashboard

## Images (non-negotiable)

A page with zero `<img>` tags fails.

**Local assets** (from inside your model folder):

| File | Use |
|---|---|
| `../styled-homepage/logo.png` | Nav wordmark |
| `../styled-homepage/logo-white.png` | Footer / dark band |
| `../styled-homepage/card-participate.jpg` | Hero / through-line photography |
| `../styled-homepage/card-measure-generic.jpg` | Optional HR / review photography |
| `../styled-homepage/hero-man-popout-v2.png` | Optional |
| `../styled-homepage/card-invite.jpg`, `card-reward.jpg` | Optional |

**Product shots** (optional on the hub — the grid does the proving; one product shot is still welcome):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579791/product-images-hub/v-fit/vfit-overview-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579792/product-images-hub/v-fit/vfit-analytics-dashboard-desktop.png
```

**Do not use** Wellness Score desktop shots.

**Minimum bar**

- At least **one photograph** (people or workplace), not a logo
- A real product screenshot **or** a designed grid that is clearly the page (cards alone are not enough if there is no photo)
- Every `<img>` has a real `alt`
- No fake certification seals

## Density (this is a SaaS directory)

- **Marketing copy budget:** about **450–750 words** outside nav, footer, and the 14 card lines. Over ~800 words fails
- **H1:** one line, or two short lines
- **Lead:** one short paragraph that states the through-line. Do not restate the H1
- The **grid is the page**. Do not write a paragraph per card
- **FAQ:** optional, max 3 (web vs app, Lite Mode, who gets lab reports)
- No customer-result band except **100+ organizations**

Match Admin Dashboard / homepage density, not a blog.

## What this page must prove (without writing it all out)

From `FEATURES-HUB-BRIEFS.md`. Show it.

- 14 cards, 3 groups, locked slugs, spec-true one-liners
- One participation surface. Not Org Wellness Score
- iOS / Android full; web limited. Lab upload is the web exception
- 100+ organizations
- Legend: Self-serve / Annual / Select-partner / Not in Lite Mode
- Leagues = annual. Training Plans = select-partner. Health Data Upload = annual / whitelist. Lite Mode = steps
- Only two AI features exist in the platform; do not brand the hub as AI
- `SoftwareApplication` JSON-LD on this page

## Important: do not treat the current marketing site as the source of truth

Live Features menu is out of date (merged Activity & health tracking, Reports under HR, Health data upload under HR, SOC 2 / GDPR / ISO, activity-level targeting). Use the locked IA:

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

Rebuild from `FEATURES-HUB-BRIEFS.md`. Glance at child mocks in your model folder so card lines match what was actually shipped. If a child line and this lock disagree, **prefer this lock** and flag it in the brief.

## Path resolution (main tree vs model worktrees)

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo files:**

- `FEATURES-HUB-PROMPT.md` (this file)
- `FEATURES-HUB-BRIEFS.md` (**read this**)
- Your model folder's 14 child HTML mocks (link them)
- `grok/vantage-fit-admin-dashboard-analytics-v1.html`
- `styled-homepage/`, `styles/enterprise.css`, `consolidated/`

**Sibling research repos** (depth +1 under `.worktrees/`):

| Resource | From main tree | From `.worktrees/<model>/` | Remote |
|---|---|---|---|
| Marketing + help docs | `../vantagefit-astro` | `../../../vantagefit-astro` | https://github.com/VantageCircle/vantagefit-astro |
| Vantage Fit OS | `../vc-os/vfit-os` | `../../../vc-os/vfit-os` | https://github.com/VantageCircle/vfit-os |

You do not need a deep OS audit for the hub. The facts lock + the 14 shipped pages are enough. If a sibling path is missing, walk up or clone. Do not invent claims.

## Research sources

1. **`FEATURES-HUB-BRIEFS.md`** — start here.
2. The 14 child mocks and briefs already in your model folder — for tone and what each card should promise.
3. `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md`, `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md`, `FEATURES-HR-REMAINING-BRIEFS.md`, `FEATURES-ENTERPRISE-BRIEFS.md` — only if you need to check a descriptor. Do not rebuild those pages.

## Audience

- **Reader:** US enterprise HR / CHRO / Benefits. IT glances at the Enterprise column
- **North star:** employee participation
- **Primary CTA:** Book a walkthrough. Secondary: Compare the tiers

## Lessons (do not repeat)

- Do not invent a visual language or skip `enterprise.css`
- Do not ship a page with no photograph
- Do not write 14 mini-essays
- Do not invent SOC2 / ISO / GDPR / HIPAA-compliant-platform
- Do not put Org Wellness Score on the hub
- Do not call the platform AI-powered
- Do not hide annual / whitelist / Lite gating
- Do not merge the 14 cards back into the live site's old menu
- Do not add Surveys / eNPS or SOLI
- Do not rebuild a child page

## What we want from you

1. **Read** the facts lock and skim your 14 child mocks.
2. **Decide** a short hub structure (hero + legend + 3-group grid + close).
3. **Write** accurate, scannable copy.
4. **Design** one high-fidelity mock that looks like Vantage Fit, with real images and working relative links to the child mocks.

## Deliverables

Write into **your model folder at the repo root**:

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

1. **`FEATURES-HUB-BRIEF.md`** — Research takeaways, why this structure, copy deck (including the 14 card lines), sources, meta title / description, critic result. Keep it short.
2. **`vantage-fit-features-hub-v1.html`** — High-fidelity mock. Links `../styles/enterprise.css`. UTF-8. Responsive. Opens from the model folder. Cards link to the sibling child HTML files with relative paths.

Do **not** add extra research dumps or any page outside the table.

## Critic list (run before you stop)

Fail the page and fix if any of these are true:

- Fewer or more than 14 feature cards, or a Surveys / eNPS / SOLI / Reports card
- A card href that is not one of the 14 locked slugs (in schema / copy) or that 404s to a missing sibling mock
- Org Wellness Score shown, gated, or used as the through-line
- "AI-powered platform" or Recommended Actions labeled AI
- SOC2, ISO, GDPR-compliant, or HIPAA-compliant platform claimed or badged
- Every card implied available to every client (no legend, no Lite / annual / whitelist flags)
- Health Data Upload or Leagues looking like day-one self-serve
- 100+ organizations missing, or a Tata / Wipro / IBS / Brazosport stat on the hub
- Activity level used as targeting
- 14 languages
- Health Connect named as the Android step source
- SoftwareApplication schema missing, or dumped as a wall of fake reviews / ratings you invented
- Em-dashes, exclamation marks, "Learn more," or banned filler
- The page reads as a Solutions hub or a 1,300-word essay
- Visual language is a new brand, or `../styles/enterprise.css` is missing
- No photograph
- Marketing copy ~800+ words outside chrome and card labels
- You rebuilt a child page

## Quality bar

- Same site as Admin Dashboard and the child feature pages
- A skeptical HR buyer can see, from the first screen, that everything logs into one participation surface — and which cards they will not get on Lite or a non-annual plan
- All 14 relative links open a real mock from the model folder
- If something material is unclear, ask; otherwise assume and state it in the brief

Ask questions only if you need clarifications that would change the facts lock or the design system.

---

## First message to the agent (paste this alone if you want a short kickoff)

```
Build Group E only: the Features hub at /features/.

Read FEATURES-HUB-PROMPT.md and FEATURES-HUB-BRIEFS.md. Follow styles/enterprise.css and styled-homepage. Use grok/vantage-fit-admin-dashboard-analytics-v1.html as the visual density peer. Do not invent a new brand. Keep copy lean (450–750 words). The grid is the page: 14 cards, 3 groups, locked slugs, spec-true one-liners. Link the child HTML mocks already in your model folder with relative paths.

Org Wellness Score is retired — the through-line is one participation surface. No SOC2/ISO/GDPR/HIPAA-compliant-platform badges. No "AI-powered platform." Include a Self-serve / Annual / Select-partner / Not in Lite Mode legend. 100+ organizations only — no single-program stats. This page is the only one with SoftwareApplication JSON-LD. Do not rebuild any child page. Do not add Surveys/eNPS or SOLI.

Write FEATURES-HUB-BRIEF.md and vantage-fit-features-hub-v1.html into your model folder. Stop when that page is done.
```
