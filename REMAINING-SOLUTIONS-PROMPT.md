# Shared prompt — remaining Vantage Fit Solutions pages

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** paste this prompt **once** into Claude / Kimi / GPT / Grok. Each model ships **all remaining Solutions pages** in a single run — research shared product truth once, then **loop page by page** until every row in the table is done.

Already shipped in this bake-off series (do **not** redo unless asked): Step challenges · Multi-activity challenges · Remote & hybrid team challenges (team-challenge files) · Virtual marathon (model v1s only).

**Menu orientation (sign-off preview in this repo):** `menu/vantage-fit-solutions-menu-preview.html`  
Solutions = two columns: **① Wellness challenges** + **② Workforce health & rewards** (data in → data out → action), plus platform + hub.

---

Work like an expert VP of Product Marketing with deep experience in enterprise B2B SaaS (HR tech), conversion websites, and SaaS solutions-page messaging. You also design modern, enterprise-grade UI.

## Goal

Design **every remaining** Solutions page for Vantage Fit (http://www.vantagefit.io) listed in the table below.

This is **not** the homepage. Across the set you will produce:

- **single-program / use-case** pages (HRA, insights, rewards),
- a **library / flagship** page (wellness challenges),
- a **platform** page (what the product is),
- and a **hub / directory** page (Solutions index).

**Ship for each page:** a high-fidelity mock + a short brief that explains your decisions. You decide structure, narrative, sections, density, and copy — based on research and buyer judgment, not on copying old marketing pages or cloning a prior challenge page.

## Pages to ship (complete set — loop through all)

Work **in order**. Finish brief + HTML for a page before starting the next. Do not skip rows. Do not stop after one page.

| # | Page | Role in Solutions IA | Intended URL | Brief filename | Mock filename |
|---|---|---|---|---|---|
| 1 | **Wellness challenges** (Library · flagship) | Flagship entry for the challenge library — browse / pick programs, not a single format | `/solutions/wellness-challenges/` | `WELLNESS-CHALLENGES-BRIEF.md` | `vantage-fit-wellness-challenges-v1.html` |
| 2 | **Health Risk Assessment** | Section ② **Data in** — baseline screening that feeds insights | `/solutions/health-risk-assessment/` | `HEALTH-RISK-ASSESSMENT-BRIEF.md` | `vantage-fit-health-risk-assessment-v1.html` |
| 3 | **Workforce health insights** | Section ② **Data out** — participation + challenge + activity (and related health signal) in **one** page; replaces three low-demand insights pages | `/solutions/workforce-health-insights/` | `WORKFORCE-HEALTH-INSIGHTS-BRIEF.md` | `vantage-fit-workforce-health-insights-v1.html` |
| 4 | **Wellness rewards program** | Section ② **Action** — points / catalog tied to real effort | `/solutions/wellness-rewards-program/` | `WELLNESS-REWARDS-BRIEF.md` | `vantage-fit-wellness-rewards-v1.html` |
| 5 | **Wellness platform** | Featured product page for the biggest search term (~850) — what Vantage Fit *is* as a platform | `/solutions/wellness-platform/` | `WELLNESS-PLATFORM-BRIEF.md` | `vantage-fit-wellness-platform-v1.html` |
| 6 | **Solutions hub** | Index / chooser for all Solutions pages | `/solutions/` | `SOLUTIONS-HUB-BRIEF.md` | `vantage-fit-solutions-hub-v1.html` |

**Done when:** all **6** briefs and **6** HTML mocks exist in your model folder, and each page is distinct for its job (not six clones of the same layout with different titles).

## Loop workflow (required)

1. **Shared research first (once)**  
   Read help docs, dashboard, OS, menu preview, and the consolidated quality bar. Build a mental model of product truth and the Solutions IA (two columns + platform + hub; data in → data out → action).

2. **Then loop pages 1 → 6**  
   For each page in the table:
   - Re-read only the sources that matter for *that* page (deep dive, not a full re-audit of the whole product).
   - Decide the story and structure for *that* page type.
   - Write the brief.
   - Build the high-fidelity mock.
   - Light-link siblings where useful (related cards, hub links, data-in/out/action chain) — but each page must still stand alone.
   - Move to the next page only after both deliverables for the current page are written.

3. **System consistency, not sameness**  
   Share visual system (tokens, type, nav, components) across all six. Vary section architecture by archetype. Challenge-page patterns (formats explorer, leaderboard integrity, etc.) apply only when product research says they belong — never force them onto HRA, insights, rewards, platform, or hub.

4. **If you run long**  
   Prefer finishing all six at solid quality over over-polishing page 1. If interrupted, resume from the first missing filename in the table.

## Important: do not treat the current marketing site as the source of truth

Many existing use-case and feature pages were built **pre-AI**, with incomplete product understanding. They may miss capabilities, mis-weight what HR buyers care about, or under-sell how the product works today.

**Use live / legacy pages only as background** (what exists, weak spots, SEO / search demand cues). **Do not** mirror their section order, feature list, or copy as the blueprint.

Instead, **rebuild from product truth** — help docs, admin dashboard, and product specs — then package each into a best-in-class SaaS page for a US enterprise HR buyer.

## Path resolution (main tree vs model worktrees)

This design repo is used from either:

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo design assets** (always relative to the repo root you are in):

- `REMAINING-SOLUTIONS-PROMPT.md` (this file)
- `menu/vantage-fit-solutions-menu-preview.html` — signed-off Solutions IA
- `styled-homepage/`
- `styles/enterprise.css`
- Consolidated quality bar (visual peer, not a forced template):
  - `consolidated/vantage-fit-steps-challenge-consolidated.html` + `consolidated/STEPS-CHALLENGE-DECISIONS.md`
  - `consolidated/vantage-fit-team-challenge-consolidated.html` + `consolidated/TEAM-CHALLENGE-DECISIONS.md`
  - `consolidated/vantage-fit-multi-activity-challenge-consolidated.html` + `consolidated/MULTI-ACTIVITY-CHALLENGE-DECISIONS.md`

**Sibling research repos** live next to `vfit-website-design` on disk, not inside it. Depth changes by one level under `.worktrees/`:

| Resource | From main tree | From `.worktrees/<model>/` | Remote (clone if missing) |
|---|---|---|---|
| Marketing + help docs | `../vantagefit-astro` | `../../../vantagefit-astro` | https://github.com/VantageCircle/vantagefit-astro |
| HR admin dashboard | `../vc-dashboard-design` | `../../../vc-dashboard-design` | https://github.com/VantageCircle/vc-dashboard-design |
| Vantage Fit OS | `../vc-os/vfit-os` | `../../../vc-os/vfit-os` | https://github.com/VantageCircle/vfit-os |

**Resolve rule:** if a sibling path does not exist, walk up parent directories until you find the sibling (or clone it). Do not invent product claims when a source is missing — note the gap in the brief.

Pull latest `main` on each research repo before you start.

## Research sources (read these; decide what matters)

### 1. Marketing site + **help docs** (how the product actually works)

Use the path table above for `vantagefit-astro`.

Prioritize **help content** over legacy marketing YAML:

- Help docs: `content/en/help/` — especially  
  - challenges (admin + employee): formats, teams, templates, tasks, e-marathon, badges, certificates, rewards  
  - `admin/workforce-health/` (workforce health, org wellness score, related)  
  - `admin/reports/` (what HR can see and export)  
  - `admin/programs/` (marketplace, training, leagues, content as relevant)  
  - employee health tracking (incl. HRA: e.g. `employee/health-tracking/what-is-hra.md`, vitals, “what is my health”)  
  - rewards / points / redemption paths as they appear in help  
- Help IA: `src/data/help-docs-categories.js`  
- Challenge library data (for the Wellness challenges page): `src/data/wellness-challenges.ts`, `src/data/wellness-challenge-thumbnails.js`, and any `wellness-challenges/` pages  
- Guides if useful: `content/en/guides/`  
- Nav / site IA for orientation: `src/scripts/header-data.js`  
- Case studies for **proof only** (named outcomes you can cite): `content/en/casestudy/` — never invent stats  

**Optional historical / SEO background only** (not the blueprint), when a file exists:

| Page | Legacy / live cues (context only) |
|---|---|
| Wellness challenges library | Challenge library data + any ads/pages about corporate wellness challenges; not a single-format use-case |
| Health Risk Assessment | Help HRA docs + OS HRA spec; live marketing may be thin or missing |
| Workforce health insights | `use-cases/health-fitness-analytics.yaml`, feature pages on lab upload / health data, admin reports help — **consolidate the story into one page** |
| Wellness rewards program | `use-cases/wellness-rewards-program.yaml` · live: https://www.vantagefit.io/wellness-rewards-program/ (if present) |
| Wellness platform | Homepage + holistic / platform-flavored pages; search demand for “wellness platform” is high — earn that intent without becoming a second homepage dump |
| Solutions hub | Current Solutions / use-case listings and the signed-off menu — design a **chooser**, not a wall of feature text |

### 2. HR admin dashboard (how HR runs and measures programs)

Use the path table above for `vc-dashboard-design`.

Use for: what admins actually launch, measure, reward, and report — so pages reflect real workflows and screens, not abstract claims.

Start from `README.md`, `docs/`, `docs/modules/` (e.g. wellness, reports, rewards, pulse), and relevant prototypes.

### 3. Vantage Fit OS (full product + marketing brain)

Use the path table above for `vc-os/vfit-os`.

Use for: feature depth, positioning, and specs that match each page.

Key entry points: `README.md`, `FEATURE-INDEX.md`, `MISSION.md`, `product-marketing/`, `specs/` — especially:

- `specs/03-health-wellness/` (HRA, vitals, lab reports / biomarkers, wellness score)
- `specs/08-rewards-marketplace/` (points, marketplace)
- `specs/09-admin-platform/` (dashboard, reports / analytics)
- `specs/02-challenges-gamification/` (for the challenges library)
- integrations / core tracking as needed for platform or insights pages

### 4. This design repo (visual system + quality bar)

Paths from the **repo root** (main or worktree):

- `styled-homepage/` — enterprise homepage mock (nav, type, section rhythm, components)
- `styles/enterprise.css` — tokens
- Consolidated challenge pages above — **quality bar and visual reference**, not a forced section template
- `menu/vantage-fit-solutions-menu-preview.html` — IA and labeling for Solutions

Match this visual system. Do not invent a new brand.

Live enterprise visual fallback if needed: https://vantagefit.pages.dev/enterprise

## Audience & positioning spine

- **Buyers:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary: program managers who run wellness. Trust / security should not be an afterthought for IT.
- **Homepage north star:** **employee participation**. Extend it for *each* page in the way that is honest for that product surface (e.g. join rates for challenges, completion for HRA, action on insights, redemption that drives habits, platform as the system that makes participation measurable).
- **Primary CTA:** Book a demo · **Secondary:** See pricing (or another secondary only if it earns the click). Hub and library pages may also lead into deeper Solutions pages.

## Page-type judgment (neutral — you choose the treatment per page)

Use professional judgment for each page. Examples of what *might* be right (not requirements):

- **Library / flagship (Wellness challenges):** help a buyer browse programs and pick a starting challenge type; showcase breadth without becoming a catalog dump.
- **Program page (HRA, insights, rewards):** problem → how it works → what HR controls → objections → CTA. Lean, conversion-focused.
- **Platform page:** product definition for “employee wellness platform” intent — clear system story, not every feature equally loud.
- **Hub:** scannable chooser aligned to the two Solutions columns; guide next click; keep copy light.

Do **not** force challenge-page patterns onto HRA, insights, rewards, platform, or hub unless product research shows they belong.

## Lessons from earlier bake-offs (apply to every page)

- Keep pages **lean, not text-heavy** — short one-line card / step descriptions; drop redundant intro ledes.
- A full **customer-result / proof section is OPTIONAL** — include only where a real, approved story exists for that topic. Do not invent or pad with generic stats.
- Prefer product-real UI (app, admin, dashboard, assessment flow, rewards catalog) over abstract illustration.
- Where privacy, aggregate-only reporting, fairness, or redemption friction is a real buying objection for *that* page, answer it with product proof — not generic trust copy.
- FAQ is fine when it handles real rollout objections (~3–5 concise Qs).
- Sentence-case, no em-dashes, verb-led CTAs, HR is the reader. Label non-approved figures **illustrative**.
- Section ② pages should respect the **data in → data out → action** story without repeating the other two pages wholesale — each page owns its job and links across the chain when useful.

## What we want from you

Act as the strategist for the full set:

1. **Research** product truth once (help + dashboard + OS), then deepen per page as you loop.
2. **Decide** the best SaaS story for each page type (IA, section set, proof, objections, CTAs, density). There is no required section checklist.
3. **Write** accurate, conversion-grade copy (benefits over feature dumps; no fabricated claims).
4. **Design** high-fidelity mocks consistent with `styled-homepage` / the consolidated quality bar, and coherent with each other as one Solutions system.

Rough length per page: a focused conversion or chooser page — not an encyclopedia and not a thin brochure. Platform and hub may be shorter or more modular than a deep program page; that is fine if the job is clear.

## Deliverables

Write into **your model folder at the repo root** (same whether you are on main or in `.worktrees/<model>/`):

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

**Per page (×6):**

1. **`[PAGE]-BRIEF.md`** — Research takeaways for this page, why you structured it this way, full copy deck, sources for any stats/quotes, meta title/description drafts, and how it fits the Solutions mega-menu (and, if relevant, the data-in / data-out / action chain).  
2. **`vantage-fit-[page]-v1.html`** — High-fidelity mock. Prefer linking `../styles/enterprise.css` and patterns from `../styled-homepage/` and `../consolidated/` (paths from inside the model folder).

**Filenames:** use the exact brief and mock names from the table (12 files total).

Optional but helpful: a short `REMAINING-SOLUTIONS-SET-NOTES.md` in your folder with the order you shipped and one-line cross-page design principles.

## Quality bar

- Each page looks and feels like a premium **SaaS marketing page** for its archetype (program, library, platform, or hub) — not a blog post or feature dump
- Visually aligned with `styled-homepage` / `enterprise.css` / consolidated challenge pages
- The six pages feel like one system (shared chrome and components) but **not** six copy-pastes
- Product claims traceable to help docs, dashboard, OS, or real case studies — **never invent** customers, metrics, or capabilities
- Enterprise tone; scannable; outcome-led; lean
- Mobile-conscious; accessible structure (real headings, focusable CTAs, sensible alt intent)
- Fits the signed-off Solutions IA without inventing extra top-level menu items
- If something material is unclear, ask; otherwise make reasonable enterprise-SaaS assumptions and state them in the relevant brief

Ask questions only if you need clarifications that would change strategy for the set.
