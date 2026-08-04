# Shared prompt — Vantage Fit sample Solutions page mockup

Copy everything below the line into each model. Paths are **relative** (sibling clones / in-repo folders). Do not hardcode machine-specific home directories.

---

Work like an expert VP of Product Marketing with deep experience in enterprise B2B SaaS (HR tech), conversion websites, and SaaS solutions-page messaging. You also design modern, enterprise-grade UI.

## Goal

Design a **sample Solutions page** for Vantage Fit (http://www.vantagefit.io) — specifically the **Steps Challenge** page.

This is **one individual solutions / use-case page** (what a buyer opens from the Solutions mega-menu for a specific program). It is **not** the homepage and **not** a Solutions hub that lists every program.

**Ship:** a high-fidelity mock + a short brief that explains your decisions. You decide structure, narrative, sections, and copy — based on research, not on copying old marketing pages.

## Solution (locked)

- **Page:** Steps Challenge  
- **Live URL (context only):** https://www.vantagefit.io/steps-challenge/  
- Do not design other solution pages in this pass. Sibling programs may appear only as light related links if useful.

## Important: do not treat the current marketing page as the source of truth

The existing Steps Challenge (and other use-case) pages on the site were built **pre-AI**, with incomplete product understanding. They may miss capabilities, mis-weight what HR buyers care about, or under-sell how the product actually works today.

**Use the live page only as background** (what exists, weak spots, SEO URL). **Do not** mirror its section order, feature list, or copy as the blueprint.

Instead, **rebuild from product truth** — help docs, admin dashboard, and product specs — then package that into a best-in-class SaaS solutions page for a US enterprise HR buyer.

## Research sources (read these; decide what matters)

Pull latest `main` on each repo before you start. Resolve paths relative to this workspace (siblings / parent tree). Clone if missing.

### 1. Marketing site + **help docs** (how the product actually works)

Sibling: `../vantagefit-astro`  
Remote: `https://github.com/VantageCircle/vantagefit-astro`

Prioritize **help content** over legacy use-case marketing YAML:

- Help docs: `content/en/help/` — especially  
  - `admin/challenges/` (create race / streak / journey / custom, manage challenges, rewards, formats, time zones, parallel challenges)  
  - `employee/challenges/` (join, formats, leaderboards, tasks)  
  - step sync / tracking under employee getting-started  
  - rewards, reports / leaderboards as relevant  
- Help IA: `src/data/help-docs-categories.js`  
- Guides (if useful): `content/en/guides/`  
- Nav / site IA only for orientation: `src/scripts/header-data.js`  
- Case studies for **proof only** (named outcomes you can cite): `content/en/casestudy/` — walkathon / step stories preferred; never invent stats  

Legacy use-case file `content/en/pages/use-cases/steps-challenge.yaml` is **optional historical reference**, not the model for the new page.

### 2. HR admin dashboard (how HR runs and measures programs)

Sibling: `../vc-dashboard-design`  
Remote: `https://github.com/VantageCircle/vc-dashboard-design`

Use for: how admins launch challenges, see participation, leaderboards, program health, leagues / wellness modules — so the page reflects what HR can actually do and report.

Start from `README.md`, `docs/`, `docs/modules/` (e.g. wellness), and any challenge/league related prototypes or notes.

### 3. Vantage Fit OS (full product + marketing brain)

Path: `../../vc-os/vfit-os` (or sibling equivalent under your Vantage Circle OS tree)  
Remote: `https://github.com/VantageCircle/vfit-os`

Use for: current feature depth, challenge/gamification specs, admin platform, rewards, integrations, positioning.

Key entry points: `README.md`, `FEATURE-INDEX.md`, `MISSION.md`, `product-marketing/`, `specs/` (especially challenges / gamification, admin platform, rewards, core tracking).

### 4. This design repo (visual system only)

- `styled-homepage/` — enterprise homepage mock (nav, type, section rhythm, components)  
- `styles/enterprise.css` — tokens  

Match this visual system. Do not invent a new brand.

Live enterprise visual fallback if needed: https://vantagefit.pages.dev/enterprise  

## Audience & positioning spine

- **Buyers:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary: program managers who run challenges. Trust/security should not be an afterthought for IT.  
- **Homepage north star:** **employee participation**. Extend it for this page: why a step challenge gets people to join, stick, and give HR numbers leadership will believe.  
- **Primary CTA:** Book a demo · **Secondary:** See pricing (or another secondary only if it earns the click).

## What we want from you

Act as the strategist:

1. **Research** the product (help + dashboard + OS). Note capabilities the old marketing page under-sells or misses.  
2. **Decide** the best SaaS solutions-page story for Steps Challenge (IA, section set, proof, objections, CTAs). There is no required section checklist — use professional judgment.  
3. **Write** accurate, conversion-grade copy (benefits over feature dumps; no fabricated claims).  
4. **Design** a high-fidelity mock consistent with `styled-homepage`.

Rough length: a focused conversion page, not an encyclopedia and not a thin brochure.

## Deliverables

In `solutions-page/`:

1. **`SOLUTIONS-BRIEF.md`** — Your audit/research takeaways, why you structured the page the way you did, full copy deck, sources for any stats/quotes, meta title/description drafts.  
2. **`vantage-fit-steps-challenge-v1.html`** — High-fidelity mock (prefer `../styles/enterprise.css` + patterns from `../styled-homepage/`).

## Quality bar

- Looks and feels like a premium **SaaS solutions page**, not a blog post or feature catalog  
- Visually aligned with `styled-homepage` / `enterprise.css`  
- Product claims traceable to help docs, dashboard, OS, or real case studies — **never invent** customers, metrics, or capabilities  
- Enterprise tone; scannable; outcome-led  
- Mobile-conscious; accessible structure (real headings, focusable CTAs, sensible alt intent)  
- If something material is unclear, ask; otherwise make reasonable enterprise-SaaS assumptions and state them in the brief

Ask questions only if you need clarifications that would change strategy.
