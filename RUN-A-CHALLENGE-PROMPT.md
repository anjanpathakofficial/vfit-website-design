# Shared prompt — Vantage Fit "Run a Challenge" solutions pages

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** run **one page at a time** (same 4-model bake-off as Steps). Set the locked solution in the block below, then paste the full prompt into Claude / Kimi / GPT / Grok.

Remaining pages (after Steps Challenge):

| Page | Live URL (context only) | Suggested folder filename |
|---|---|---|
| Team Challenge | https://www.vantagefit.io/team-challenges/ | `vantage-fit-team-challenge-v1.html` |
| Multi-activity Challenge | https://www.vantagefit.io/multi-activity-challenges/ | `vantage-fit-multi-activity-challenge-v1.html` |
| Mental Health & Wellbeing | https://www.vantagefit.io/mental-health-and-wellbeing-challenges/ | `vantage-fit-mental-health-wellbeing-v1.html` |
| Virtual Marathon | https://www.vantagefit.io/virtual-marathon/ | `vantage-fit-virtual-marathon-v1.html` |

---

Work like an expert VP of Product Marketing with deep experience in enterprise B2B SaaS (HR tech), conversion websites, and SaaS solutions-page messaging. You also design modern, enterprise-grade UI.

## Goal

Design **one** individual Solutions / use-case page for Vantage Fit (http://www.vantagefit.io) under the **Run a Challenge** mega-menu group.

This is **not** the homepage and **not** a Solutions hub. It is the page a buyer opens for one specific program.

**Ship:** a high-fidelity mock + a short brief that explains your decisions. You decide structure, narrative, sections, and copy — based on research, not on copying old marketing pages.

## Solution (locked for this pass)

- **Page:** [TEAM CHALLENGE | MULTI-ACTIVITY CHALLENGE | MENTAL HEALTH & WELLBEING | VIRTUAL MARATHON]
- **Live URL (context only):** [matching URL from the table above]
- Do not design other solution pages in this pass. Sibling programs may appear only as light related links if useful.

## Important: do not treat the current marketing page as the source of truth

Existing use-case pages on the site were built **pre-AI**, with incomplete product understanding. They may miss capabilities, mis-weight what HR buyers care about, or under-sell how the product works today.

**Use the live page only as background** (what exists, weak spots, SEO URL). **Do not** mirror its section order, feature list, or copy as the blueprint.

Instead, **rebuild from product truth** — help docs, admin dashboard, and product specs — then package that into a best-in-class SaaS solutions page for a US enterprise HR buyer.

## Path resolution (main tree vs model worktrees)

This design repo is used from either:

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo design assets** (always relative to the repo root you are in — same for main and worktrees once the branch is current):

- `RUN-A-CHALLENGE-PROMPT.md` (this file)
- `styled-homepage/`
- `styles/enterprise.css`
- `consolidated/vantage-fit-steps-challenge-consolidated.html`
- `consolidated/STEPS-CHALLENGE-DECISIONS.md`

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

Prioritize **help content** over legacy use-case marketing YAML:

- Help docs: `content/en/help/` — especially  
  - `admin/challenges/` (create/manage challenges, formats, teams, audience, templates, time zones, parallel challenges, tasks, e-marathon, when to use a one-day virtual marathon, badges, certificates, rewards)  
  - `employee/challenges/` (join, formats, leaderboards, tasks)  
  - tracking / sync under employee getting-started  
  - rewards, reports / leaderboards as relevant  
- Help IA: `src/data/help-docs-categories.js`  
- Guides (if useful): `content/en/guides/`  
- Nav / site IA for orientation only: `src/scripts/header-data.js`  
- Case studies for **proof only** (named outcomes you can cite): `content/en/casestudy/` — never invent stats  

Legacy YAML under `content/en/pages/use-cases/` for this program is **optional historical reference**, not the model for the new page.

### 2. HR admin dashboard (how HR runs and measures programs)

Use the path table above for `vc-dashboard-design`.

Use for: how admins launch challenges, teams, participation, leaderboards, program health — so the page reflects what HR can actually do and report.

Start from `README.md`, `docs/`, `docs/modules/`, and challenge/league related prototypes or notes.

### 3. Vantage Fit OS (full product + marketing brain)

Use the path table above for `vc-os/vfit-os`.

Use for: feature depth, challenge/gamification specs, admin platform, rewards, integrations, positioning.

Key entry points: `README.md`, `FEATURE-INDEX.md`, `MISSION.md`, `product-marketing/`, `specs/` (challenges / gamification, admin platform, rewards, core tracking).

### 4. This design repo (visual system + quality reference)

Paths below are from the **repo root** (main or worktree):

- `styled-homepage/` — enterprise homepage mock (nav, type, section rhythm, components)
- `styles/enterprise.css` — tokens
- `consolidated/vantage-fit-steps-challenge-consolidated.html` + `consolidated/STEPS-CHALLENGE-DECISIONS.md` — **quality bar and visual reference** from the Steps bake-off (not a forced template; re-evaluate structure per page)

Match this visual system. Do not invent a new brand.

Live enterprise visual fallback if needed: https://vantagefit.pages.dev/enterprise

## Audience & positioning spine

- **Buyers:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary: program managers who run challenges. Trust/security should not be an afterthought for IT.
- **Homepage north star:** **employee participation**. Extend it for this page: why *this* challenge type gets people to join, stick, and give HR numbers leadership will believe.
- **Primary CTA:** Book a demo · **Secondary:** See pricing (or another secondary only if it earns the click).

## Lessons from the Steps Challenge bake-off (apply)

- Keep the page **lean, not text-heavy** — short one-line card/step descriptions; drop redundant intro ledes.
- A full **customer-result / proof section is OPTIONAL** — include only where a real, approved story exists for this program. Do not invent or pad with generic stats.
- Prefer product-real UI (phone mock, admin dashboard, leaderboard, format explorer) over abstract illustration.
- Where fairness / fraud / privacy is a real buying objection for *this* program, answer it with product proof — not generic trust copy.
- FAQ is fine on solution pages when it handles real rollout objections (~3–5 concise Qs).
- Sentence-case, no em-dashes, verb-led CTAs, HR is the reader. Label non-approved figures **illustrative**.

## What we want from you

Act as the strategist:

1. **Research** the product (help + dashboard + OS). Note capabilities the old marketing page under-sells or misses for *this* program.
2. **Decide** the best SaaS solutions-page story (IA, section set, proof, objections, CTAs). There is no required section checklist — use professional judgment for *this* program.
3. **Write** accurate, conversion-grade copy (benefits over feature dumps; no fabricated claims).
4. **Design** a high-fidelity mock consistent with `styled-homepage` / the Steps consolidated quality bar.

Rough length: a focused conversion page, not an encyclopedia and not a thin brochure.

## Deliverables

Write into **your model folder at the repo root** (same whether you are on main or in `.worktrees/<model>/`):

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

1. **`[PAGE]-BRIEF.md`** — Research takeaways, why you structured the page this way, full copy deck, sources for any stats/quotes, meta title/description drafts.  
   Examples: `TEAM-CHALLENGE-BRIEF.md`, `MULTI-ACTIVITY-BRIEF.md`, `MENTAL-HEALTH-BRIEF.md`, `VIRTUAL-MARATHON-BRIEF.md`
2. **`vantage-fit-[page]-v1.html`** — High-fidelity mock. Prefer linking `../styles/enterprise.css` and patterns from `../styled-homepage/` and `../consolidated/` (paths from inside the model folder).

## Quality bar

- Looks and feels like a premium **SaaS solutions page**, not a blog post or feature catalog
- Visually aligned with `styled-homepage` / `enterprise.css` / Steps consolidated
- Product claims traceable to help docs, dashboard, OS, or real case studies — **never invent** customers, metrics, or capabilities
- Enterprise tone; scannable; outcome-led; lean
- Mobile-conscious; accessible structure (real headings, focusable CTAs, sensible alt intent)
- If something material is unclear, ask; otherwise make reasonable enterprise-SaaS assumptions and state them in the brief

Ask questions only if you need clarifications that would change strategy.
