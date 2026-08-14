# Shared prompt — Vantage Fit remaining For-HR feature pages (Group C)

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** paste this prompt **once** into Claude / Kimi / GPT / Grok. Each model ships **all three** pages in this group. Research shared HR physics once, then **loop page by page**. Stop when the three rows are done. Do not rebuild Admin Dashboard. Do not rebuild employee pages. Do not start enterprise or the hub.

This is **not** a Solutions bake-off. These pages prove an HR **capability** is real.

The failed feature run shipped essay sites with invented brands and zero images. Admin Dashboard and the employee groups recovered by staying inside the design system, keeping copy lean, and putting real photographs and product shots on the page. Repeat that. These three pages should feel like siblings of **Admin Dashboard**, not like challenge-program Solutions pages.

Traps that will fail review: activity-level targeting, team score as a sum, three named Journey templates, freely-on monetary rewards, a calendar UI, a segment-from-report picker, Nudge as a confirmed one-click send, AI emails, Org Wellness Score, "quiet 40%" as a measured VFit stat.

---

You are an expert product-marketing designer for enterprise B2B SaaS (HR tech). You design and implement high-fidelity UI **inside an existing design system**. You do not invent a new brand for a bake-off.

You have been hired to design **Group C** of the Features IA for Vantage Fit (http://www.vantagefit.io): the three remaining **For HR teams** pages.

Vantage Fit is not a meditation brand and not a consumer fitness app. It is the system HR uses to turn everyday employee logs into one participation number. Admin Dashboard already showed that number. These pages show how HR launches, aims, and re-engages the same surface.

If a page could be swapped onto a generic wellness vendor with a find-and-replace, you have failed. If it could be mistaken for a Solutions / challenge-program page, you have failed. If it looks like a help article, a whitepaper, or a new brand, you have failed.

## Goal

Design the three For-HR pages that are not the Admin Dashboard.

This is what a buyer opens from Features → **For HR teams**. It is not the homepage, not the hub, not a Solutions page, and not Group A / B.

**Ship:** three high-fidelity mocks + three short briefs.

Do **not** invent a new page-type visual language. Do **not** write a page-type theory file. Do **not** rebuild Admin Dashboard or any employee page.

## Pages to ship (this run only)

Work **in this order**. Finish brief + HTML for a page before starting the next.

| # | Page | Intended URL | Angle (the one idea, not a headline you must use) | Brief filename | Mock filename |
|---|---|---|---|---|---|
| 1 | **Program Builder & Templates** | `/features/program-builder/` | A challenge live before lunch | `PROGRAM-BUILDER-BRIEF.md` | `vantage-fit-program-builder-v1.html` |
| 2 | **Audience Targeting** | `/features/audience-targeting/` | Aim a challenge at the right people without seeing who they are | `AUDIENCE-TARGETING-BRIEF.md` | `vantage-fit-audience-targeting-v1.html` |
| 3 | **Communications & Nudges** | `/features/communications-nudges/` | Re-engage the quiet 40% automatically (framing, not a measured stat) | `COMMUNICATIONS-NUDGES-BRIEF.md` | `vantage-fit-communications-nudges-v1.html` |

Builder owns formats / tasks / templates / lifecycle. Targeting owns dimensions / privacy / enrollment. Comms owns emails / push / branding. Do not reprint the 27 task types on Targeting or Comms.

**Done when:** all **3** briefs and **3** HTML mocks exist in your model folder, each page follows the design system, each has real images, and a time-poor HR buyer can scan each page in under a minute.

## Loop workflow (required)

1. **Shared research first (once)**  
   Read `FEATURES-HR-REMAINING-BRIEFS.md` (all of it). Open `grok/vantage-fit-admin-dashboard-analytics-v1.html` so you know the HR-page density to match.

2. **Then loop pages 1 → 3**  
   For each row:
   - Re-read only that page card.
   - Decide a short SaaS structure. Must-cover is a checklist, not a section outline.
   - Write the brief.
   - Build the HTML mock.
   - Cross-link the other two slugs in this set plus `/features/admin-dashboard-analytics/` and `/features/`.
   - Move on only after both deliverables exist.

3. **System consistency, not sameness**  
   Share nav, footer, tokens, type, and buttons with Admin Dashboard. Vary hero and proof. Do not clone the four KPI cards onto the builder. Do not clone the 27-task list onto Targeting.

4. **If you run long**  
   Prefer finishing all three at solid quality over over-polishing page 1. If interrupted, resume from the first missing filename.

## Locked vs free (read this twice)

### Locked (mandatory)

- These three slugs, jobs, and angles. This order.
- Everything in `FEATURES-HR-REMAINING-BRIEFS.md`
- Feature pages, not Solutions pages
- Keywords from the brief (honest use in H1 / title / opener; do not stuff)
- Sentence case, no em-dashes, no exclamation marks, verb-led CTAs
- No invented customers, metrics, capabilities, certifications, or AI labels
- **The existing Vantage Fit design system**
- **Real images.** A page with no `<img>` product or photo assets fails
- **Lean copy.** 450–750 words. The original 11-section / 1,300-word spine is **off**
- **Org Wellness Score is retired**
- **Proof assignment.** Quiet 40% is not a product stat. Do not reuse Group A / B client figures

### Free (this is the bake-off)

- Section set and order. No required spine
- How you compose each hero (photo + product shot + a short UI fragment is fine)
- Which assigned proof you use, if any
- Schema / JSON-LD. Optional

## Design system (non-negotiable)

Match the system already in this repo. Do **not** invent a new brand.

From the **repo root** (main or worktree):

- `styles/enterprise.css` — **link it**. Do not re-declare `--ink`, `--coral`, `--mint`, or a new font stack
- `styled-homepage/` — Noto Sans, coral CTAs, ink / mint / canvas, 22px radius, `.shell` / `.btn` / `.eyebrow` / `.nav` / `.mega`
- `grok/vantage-fit-admin-dashboard-analytics-v1.html` — the HR feature page reviewers liked. **Primary visual peer.** Clone nav / footer / type / buttons. Do **not** clone its KPI / Insights story
- Your own `*/vantage-fit-admin-dashboard-analytics-v1.html` — also a valid chrome donor
- Group A / B pages — same site, different reader surface. Do not clone a mobile-logging hero onto an HR builder page
- `consolidated/vantage-fit-steps-challenge-consolidated.html` — quality bar, not a Solutions template

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
- The page would not be recognized as the same site as Admin Dashboard

## Images (non-negotiable)

A page with zero `<img>` tags fails.

**Local assets** (paths from inside your model folder):

| File | Use |
|---|---|
| `../styled-homepage/logo.png` | Nav wordmark |
| `../styled-homepage/logo-white.png` | Footer / dark band |
| `../styled-homepage/card-measure-generic.jpg` | Admin / review photography |
| `../styled-homepage/card-invite.jpg` | Communications / invite photography |
| `../styled-homepage/card-participate.jpg` | Optional movement photography |
| `../styled-homepage/hero-man-popout-v2.png` | Optional people photography |
| `../styled-homepage/card-reward.jpg` | Optional |

**Required product shots** (CDN — use these, do not redraw a fake console instead of them):

Program Builder:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772104740/product-images-hub/v-fit/vantage-fit-challenge-system-overview-desktop.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194233/product-images-hub/v-fit/vantage-fit-campaign-management-dashboard-desktop.png
```

Audience Targeting (no dedicated targeting screenshot — prove count-only privacy with a short HTML fragment, plus a photograph; campaign shot is supporting only):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194233/product-images-hub/v-fit/vantage-fit-campaign-management-dashboard-desktop.png
```

Communications & Nudges (no dedicated inbox screenshot — use the campaign / challenge desktop shot plus a photograph; you may generate a branded-email mock that does **not** invent a segment-from-report picker):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579791/product-images-hub/v-fit/vfit-challenge-dashboard-desktop.png
```

Optional companion:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579792/product-images-hub/v-fit/vfit-analytics-dashboard-desktop.png
```

**Do not use** Wellness Score desktop shots. That score is retired.

**Minimum bar, each page**

- At least **one large product screenshot** (or, on Targeting, a large HTML count-only privacy mock plus the campaign shot)
- At least **one photograph** (people or workplace), not a logo
- Logos do not count toward the minimum
- Every `<img>` has a real `alt`
- Do not put a health-risk name list, an individual's HRA, or mood answers on screen

You may generate additional images if your tools allow it. Save them in your model folder.

## Density (this is a SaaS page)

- **Marketing copy budget:** about **450–750 words** outside nav, footer, and labels inside a product mock. Over ~800 words fails
- **H1:** one line, or two short lines
- **Lead:** one short paragraph. Do not restate the H1
- **Section heads:** short and specific (`Five formats. Twenty-seven tasks.`)
- **FAQ:** optional, max 3
- **Customer-result band:** optional, assigned proof only
- No "The problem? The solution?"

Match Admin Dashboard density, not a blog.

## What each page must prove (without writing it all out)

From `FEATURES-HR-REMAINING-BRIEFS.md`. Show it. Do not narrate every bullet.

**Program Builder**

- 5 self-serve formats. Drag-and-drop is Custom only
- 27 task types as a compact list or UI, not an essay
- 2 named Journey templates (Europe 70k, 7 Wonders 50k). Say 2+, not 3
- Shared setup includes audience, teams, points, certificates
- 6 lifecycle states + admin override. No calendar UI
- Lite Mode = Race + steps
- Points / money are gated (1 company). Team score is an average
- Training Plans / Level / Marathon / Weight Burn are not in this wizard
- Through-line: this is how HR launches the surface everything logs into

**Audience Targeting**

- Dimensions: country, city, department, gender, age, language, health-risk code
- Health-risk = count only + the privacy disclaimer
- Targeted challenges are private
- Admin-add or rule-enroll. Do not pitch email-invite as the modern flow
- Late joiners score from join date forward
- Health-risk targeting needs Workforce Health
- Through-line: HR aims the same participation surface without seeing names

**Communications & Nudges**

- 29 email templates; 13 named moments for triggers; 34+ push with deep links
- What is self-serve vs account-manager (toggles, branding, reminder timing)
- Nudge Inactive Users is a rule-based Recommended Action. Send path `[VERIFY]`
- No segment-from-report picker. No web push. No per-employee prefs. No AI copy
- 13+ languages
- Through-line: comms exist so the quiet people start logging again
- "Quiet 40%" is framing, not a VFit stat

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

Do not put Reports & exports or Health data upload in the HR column. Do not put SOC 2 / GDPR / ISO in Enterprise. Do not list "activity level" targeting.

Rebuild from `FEATURES-HR-REMAINING-BRIEFS.md`, help, and OS.

## Path resolution (main tree vs model worktrees)

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo files** (relative to the repo root you are in):

- `FEATURES-HR-REMAINING-PROMPT.md` (this file)
- `FEATURES-HR-REMAINING-BRIEFS.md` (**read this**; it is the facts lock)
- `grok/vantage-fit-admin-dashboard-analytics-v1.html`
- `styled-homepage/`, `styles/enterprise.css`, `consolidated/`
- `FEATURES-HR-PROMPT.md` / `FEATURES-HR-BRIEFS.md` — Admin Dashboard group. Do not rebuild that page

**Sibling research repos** (depth changes by one level under `.worktrees/`):

| Resource | From main tree | From `.worktrees/<model>/` | Remote |
|---|---|---|---|
| Marketing + help docs | `../vantagefit-astro` | `../../../vantagefit-astro` | https://github.com/VantageCircle/vantagefit-astro |
| HR admin dashboard | `../vc-dashboard-design` | `../../../vc-dashboard-design` | https://github.com/VantageCircle/vc-dashboard-design |
| Vantage Fit OS | `../vc-os/vfit-os` | `../../../vc-os/vfit-os` | https://github.com/VantageCircle/vfit-os |

If a sibling path does not exist, walk up until you find it (or clone it). Do not invent claims. Pull latest `main` on each research repo before you start.

## Research sources

### 1. The facts lock (start here)

`FEATURES-HR-REMAINING-BRIEFS.md`. If help or OS disagree on a shipping claim, **prefer this file** and flag the conflict in the page brief.

### 2. Help docs

In `vantagefit-astro`:

- `content/en/help/admin/challenges/` — create / formats / custom / race / journey / streak / e-marathon / templates / target audience / manage / certificates / teams
- `content/en/help/admin/communication/` — preview emails, custom emails, notifications, what emails VFit sends
- `content/en/help/admin/settings/` — branding, Lite Mode
- Case studies for **assigned proof only**

### 3. Vantage Fit OS

- `FEATURE-INDEX.md`
- `specs/02-challenges-gamification/` — system overview, custom, race, journey, streak, campaign management. Level / marathon / training are **ops**, not this wizard
- `specs/09-admin-platform/notifications.md`
- `specs/09-admin-platform/admin-dashboard.md` — Recommended Actions / Nudge context only

### 4. Admin dashboard prototype

`vc-dashboard-design` — create-challenge wizard, audience, communications studio notes if present. Use so a UI fragment is recognizable. Do not clone production Angular.

## Audience

- **Reader:** US enterprise HR / CHRO / Benefits / Wellbeing leader. Secondary: the program manager who opens the wizard tomorrow
- **North star:** employee participation
- **Primary CTA:** Book a walkthrough. Secondary only if it earns the click

## Lessons (do not repeat)

- Do not invent a visual language or skip `enterprise.css`
- Do not ship a page with no photograph and no product screenshot
- Do not turn must-cover into an essay (especially the 27 task types)
- Do not put Org Wellness Score on any page
- Do not use activity level as targeting
- Do not say team score is a sum
- Do not invent a third named Journey template
- Do not pitch monetary rewards as freely on
- Do not invent a calendar UI or a segment-from-report picker
- Do not call Nudge a confirmed one-click send
- Do not call emails AI
- Do not present "quiet 40%" as a measured VFit result
- Do not rebuild Admin Dashboard or employee pages

## What we want from you

1. **Research** product truth for this group (briefs + help + OS).
2. **Decide** a short SaaS structure per page.
3. **Write** accurate, scannable copy.
4. **Design** three high-fidelity mocks that look like Vantage Fit HR pages, with real images.

## Deliverables

Write into **your model folder at the repo root**:

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

For **each** of the three pages:

1. **`{PAGE}-BRIEF.md`** — Research takeaways, why this structure, copy deck, sources, meta title / description, critic result. Keep it short.
2. **`vantage-fit-{slug}-v1.html`** — High-fidelity mock. Links `../styles/enterprise.css`. Uses `../styled-homepage/` images and the CDN shots for that page. UTF-8. Responsive. Opens from the model folder.

Do **not** add extra research dumps or any page outside the table.

## Critic list (run on every page before you stop)

Fail the page and fix if any of these are true:

- A capability, number, customer, or certification not in the briefs / help / OS / case study is stated as fact
- Org Wellness Score shown or claimed as live
- Activity level used as a targeting dimension
- Health-risk cohort shown as a name list, or identities implied as exportable
- Team score described as a sum
- "3 named Journey templates" or a third named template invented
- Monetary / point rewards implied as freely on for every customer
- A visual scheduling calendar UI claimed as the product
- Training Plans / Level / Marathon Event / Weight Burn offered as self-serve builder formats
- Employees manage their own teams by default
- A wearable required for any format
- Health Connect named as the Android **step** source
- Android auto-tracked **task** sync source asserted without a hedge
- Segment-from-report picker designed or claimed as live
- Nudge Inactive Users described as one-click / automatic send without `[VERIFY]`
- Recommended Actions or emails labeled AI
- Self-serve per-type email toggles claimed as live
- Web push or in-app bell claimed as live
- "Quiet 40%" presented as a Vantage Fit measured stat
- HIPAA-compliant platform, SOC2, ISO, or GDPR-compliant claimed
- 14 languages
- A VERIFY item shipped as an unqualified claim
- Assigned proof used on the wrong page, or Group A / B stats reused
- Em-dashes, exclamation marks, "Learn more," or banned filler
- The page reads as a Solutions / program-outcome page rather than a capability page
- The page does not show how this admin action serves participation
- Tier / Lite / whitelist / account-manager gates buried or omitted
- Visual language is a new brand, or `../styles/enterprise.css` is missing
- Fewer than one product screenshot (or Targeting privacy mock) and one photograph
- Marketing copy ~800+ words outside chrome
- You built a page that is not in the table

## Quality bar

- Same site as Admin Dashboard
- A skeptical HR buyer can tell, from the first screen, what they would click in the product
- Claims traceable to the briefs, help, OS, or real case studies
- Three pages share chrome and do not repeat each other's catalogs
- If something material is unclear, ask; otherwise assume and state it in the brief

Ask questions only if you need clarifications that would change the facts lock or the design system.

---

## First message to the agent (paste this alone if you want a short kickoff)

```
Build Group C only: Program Builder & Templates, Audience Targeting, and Communications & Nudges.

Read FEATURES-HR-REMAINING-PROMPT.md and FEATURES-HR-REMAINING-BRIEFS.md. Follow styles/enterprise.css and styled-homepage. Use grok/vantage-fit-admin-dashboard-analytics-v1.html as the visual density peer. Do not invent a new brand. Use the listed CDN product shots plus at least one photograph per page. Keep copy lean (450–750 words).

Org Wellness Score is retired. Activity level is not a targeting dimension. Team score is an average. Journey templates: name only Europe and 7 Wonders (2+). Monetary rewards are gated (1 company). Nudge send path is [VERIFY]. Quiet 40% is framing, not a VFit stat. Do not rebuild Admin Dashboard or any employee page.

Work in order. Write both the brief and the HTML into your model folder for each page before starting the next. Stop after the three pages.
```
