# Team Challenge — Solutions Page Brief

**Page:** Team Challenge (individual Solutions / use-case page)  
**Live URL (context only):** https://www.vantagefit.io/team-challenges/  
**Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary program managers  
**North star:** **Employee participation** — why *team* challenges get people to join, stick, and give HR credible numbers  
**Visual baseline:** `styled-homepage/` + `styles/enterprise.css` + prior Grok Steps page patterns  
**Primary CTA:** Book a demo · **Secondary:** See pricing  

---

## 1. Research takeaways (product truth)

Sources prioritized: help docs (`vantagefit-astro/content/en/help/`), `vfit-os` specs (`02-challenges-gamification`, `05-social-community/teams.md`), dashboard wellness docs, named case studies. Live marketing page and legacy `team-challenges.yaml` were **not** used as product source of truth.

### 1.1 What “Team Challenge” actually is in product

Teams are a **mode on challenges**, not a separate challenge type. HR enables teams during challenge creation (or manages them after publish). Documented team support:

| Format | Teams? | Notes | Source |
|--------|--------|-------|--------|
| **Custom** | Yes (optional) | Multi-week themes/tasks; admin or employee team creation; max size | Help: create custom challenge; manage teams |
| **Streak** | Yes (optional) | Team competition alongside individual streaks | Help: create streak challenge |
| **Journey** | Yes (optional); team-only mode exists | Members progress on map; team competes on average score; `isTeamOnly` flag in OS | Help: create journey; OS challenge-system-overview |
| **Race** | **No** | Pure individual step race; help explicitly says no team settings | Help: create race challenge |
| **E-Marathon** | Not documented in create flow | “Team-building” is marketing language only; no team config in help | Help: formats / e-marathon |

**Core scoring rule (non-negotiable product truth):**  
**Team score = average of all members’ individual scores** (not a sum). Inactive members pull the average down. Every contribution matters equally.

**Team formation paths:**
1. **Admin-created** — Manage Challenge → Teams → Create Team (name, image, add by search).
2. **Bulk CSV / Google Sheets** — team name + employee email rows; bulk create.
3. **Automated** — account-manager-assisted programmatic creation for large bases.
4. **Employee / captain-created** — captain names team, optional image + slogan, invites colleagues; company-level enablement via AM.

**Admin control after launch:** edit name/image, add/remove members, move members between teams, delete teams, max team size at create time. Recommended size in help: **4–6** (typical range 3–10).

**Employee experience:** invitation lifecycle (Pending / Joined / Rejected / Expired / Withdrawn). Dual leaderboards: **Individual** and **Team** toggle. Team LB shows name, image, average score, member count, rank.

**Ops extras (true, light mention):** team migration between campaigns; downloadable team leaderboard; captain assignment APIs; Redis-backed real-time ranks.

### 1.2 Capabilities the old marketing page under-sells

| Capability | Why it matters to HR buyers | Source |
|------------|----------------------------|--------|
| **Average scoring (not sum)** | Stops athlete domination; inactive seats hurt the team | Help: manage teams; how-do-teams-work |
| **Admin + CSV + captain paths** | Plant/site org charts vs voluntary squads | Help: manage teams; OS teams.md |
| **Max team size** | Balance fairness; keep accountability visible | Help: manage teams |
| **Teams on Custom / Streak / Journey** | Not one “team product” — mode across programs | Format help articles |
| **Dual leaderboards** | Peer pressure + personal progress in one challenge | Employee teams help; leaderboards.md |
| **Move members mid-challenge** | Org changes, fairness fixes without rebuild | Help: manage teams |
| **Team migration** | Reuse structure across quarterly programs | OS teams.md |
| **Audience filters + privacy** | Dept/site pilots then company-wide | Target audience help |
| **Certificates / points / badges** | Recognition beyond top-3 individuals | Create challenge; rewards help |

### 1.3 Live page weaknesses (background only)

1. Sells “team building” vibe without the **average-score fairness** story.  
2. Does not teach **formation paths** (admin vs captains vs CSV).  
3. Blurs teams into generic challenge marketing (formats unclear).  
4. Underplays HR ops: bulk upload, move members, dual LBs, max size.  
5. Weak or generic proof vs named team programs (Tata 43 teams).  
6. Feature catalog tone vs participation-led SaaS solutions narrative.

### 1.4 Proof we can cite (named, published, team-relevant)

| Outcome | Org | Context | Source |
|---------|-----|---------|--------|
| **70%** engagement · **43 teams** · **53%** of teams reduced average weight · 7,600+ avg daily steps | Tata Motors | Step Up & Elevate (team-based, ~6 months) | Case study: `tata-motors-step-up-elevate` |
| **5,000+** participants · **6** in-house teams · 30-day campaign | Landmark Group | Inter-team virtual wellness / e-marathon style | Case study: `landmark-group-walkathon` |
| **3,700+** participants · **74 teams** · **24 countries** · ~**84%** engagement boost claim | Global Corporate Walkathon (Vantage Fit-hosted) | 30-day multi-org team walkathon | Case study: `global-corporate-virtualwalkathon` |

**Rule:** Pair metric with org + program context. Add: *Customer experiences vary by workforce and program design.*  
**Optional deep proof:** Tata qualifies as a real team-program story → include a lean customer-result block (not a long case dump).

### 1.5 Assumptions (stated)

- US enterprise buyers want **department / site rivalry** and **peer accountability**, not only individual podiums.  
- “Team Challenge” SEO URL remains the entry page even though product implements **team mode on formats**.  
- Primary conversion is **Book a demo**.  
- Security strip reuses homepage claims (HIPAA, SOC 2, GDPR, ISO 27001/27701) without inventing certifications.  
- Race is **not** sold as a team format on this page.

---

## 2. Page strategy

### Job of this page

Help an enterprise HR buyer answer:  
1. Will **non-athletes** join and keep showing up because of their squad?  
2. Is scoring **fair** (not one marathon runner carrying a sum)?  
3. Can we **form and manage** teams at company scale without chaos?  
4. Can I **show leadership** department/site competition and participation?  
→ Book a demo.

### Positioning line

> Team challenges turn wellness into peer accountability — fair average scoring, flexible team formation, and dual leaderboards so whole squads participate, not just the fittest few.

### Narrative arc (decided for THIS program)

Re-evaluated vs Steps template. Steps centers formats + sync integrity. Team centers **fairness + formation + social stickiness**.

| # | Section | Intent |
|---|---------|--------|
| 1 | **Hero** | Outcome promise: whole workforce via teams; dual CTAs; product-real team LB mock |
| 2 | **Proof strip** | Early credibility (Tata 43 teams / Landmark / GCW) |
| 3 | **Fairness engine** | Average scoring as the differentiator (inclusion of non-athletes) |
| 4 | **Formation paths** | Admin · CSV bulk · captain invites — how teams get built |
| 5 | **Formats that support teams** | Custom, Streak, Journey (lean; not Race) |
| 6 | **Built for HR** | Enable teams → size → form → run dual LBs → report |
| 7 | **Customer result (lean)** | Tata Motors team program only |
| 8 | **FAQ** | Rollout objections (~4–5) |
| 9 | **Trust + final CTA** | Security + Book a demo / See pricing |
| — | Related links (light) | Sibling programs only |

### What we deliberately de-emphasize

- Race as a team vehicle (product false).  
- Ops-only formats.  
- Clinical / ROI fabrication.  
- Long feature laundry lists.  
- Abstract “team building” illustrations without product UI.  
- Invented customers or unapproved % lifts.

### Voice guardrails

- Sentence-case headings.  
- No em-dashes.  
- Verb-led CTAs: **Book a demo**, **See pricing**.  
- HR is the reader.  
- Non-approved figures labeled **illustrative**.  
- Lean: one-line card/step descriptions where possible.

---

## 3. Full copy deck

### Meta

- **Title:** Corporate Team Challenge Platform for HR | Vantage Fit  
- **Description:** Run team wellness challenges with fair average scoring, admin or captain-led teams, dual leaderboards, and HR reports. Book a demo.

### Nav (aligned with styled-homepage / Steps page)

Solutions · Features · Resources · Pricing · **Book a demo**  
Solutions mega: By program (Team challenges = current) / By need.

### S1 — Hero

- **Eyebrow:** Solutions · Team Challenge  
- **H1:** Team challenges that pull everyone in, not just top athletes.  
- **Lead:** Enable team mode on Custom, Streak, or Journey challenges. Form squads by department or captain invite. Rank teams by average score so every member counts.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** See pricing  
- **Micro line:** Average scoring · Admin or captain teams · Dual leaderboards  

**Hero visual:** Product-real mock — phone team leaderboard (rank, avg score, members) + small admin “Teams” panel card (CSV bulk, max size). Labels mark **illustrative** sample data.

### S2 — Proof strip

- **Kicker:** Teams already competing on Vantage Fit  
- **Chips:**  
  - **70%** engagement · Tata Motors · 43 teams (Step Up & Elevate)  
  - **43** teams · 53% reduced average weight · Tata Motors  
  - **5,000+** participants · Landmark Group · 6 in-house teams  
- **Disclaimer:** Customer experiences vary by workforce and program design.

### S3 — Fairness engine

- **Eyebrow:** Why team mode works  
- **H2:** Average scoring keeps non-athletes in the game.  
- **Lead:** Sum-based teams let one high performer mask silent seats. Vantage Fit ranks teams by the **average** of member scores.  
- **Cards (one line each):**  
  1. **Every seat matters** — Inactive members lower the team average.  
  2. **No superstar carry** — Consistent squads beat one hero + silent peers.  
  3. **Balanced size** — Set max members (help recommends 4–6) so effort stays visible.  
  4. **Personal + team ranks** — Employees still see individual standings beside the team board.  
- **Callout formula:** Team score = average of member scores (not sum).

### S4 — Formation paths

- **Eyebrow:** How teams form  
- **H2:** Build squads your way: org chart, spreadsheet, or captains.  
- **Three paths:**  
  | Path | Headline | One-line body |
  |------|----------|---------------|
  | Admin | Pre-assign departments & sites | Create teams in Manage Challenge → Teams; add members by name or email. |
  | Bulk | Scale with CSV or Sheets | Upload team name + email rows; create and assign in one pass. |
  | Captains | Let employees form squads | Captains name the team, invite colleagues; admins still edit, move, or delete. |
- **Foot note:** Employee team creation is a company setting coordinated with your account manager when needed. Automated team creation available for large programs via AM.

### S5 — Formats that support teams

- **Eyebrow:** Pair teams with the right format  
- **H2:** Team mode on the programs people stick with.  
- **Cards:**  
  - **Custom** — Multi-week themes and task mix; full team config. Best for company-wide or multi-activity team seasons.  
  - **Streak** — Daily target habit; optional team competition on averages. Best for 2–4 week consistency drives.  
  - **Journey** — Map milestones with optional team mode (team-only journeys available). Best for multi-week shared narratives.  
- **Honest note:** Pure **Race** challenges are individual-only. Want steps + teams? Use Custom, Streak, or Journey.  
- **Foot CTA:** Not sure which stack fits? Book a demo — we’ll map a 90-day team calendar.

### S6 — Built for HR

- **Eyebrow:** For HR & program managers  
- **H2:** Launch teams in the dashboard. Keep control after go-live.  
- **Steps:**  
  1. **Enable** — Toggle teams on create; set maximum team size.  
  2. **Form** — Admin create, bulk upload, or open captain invites.  
  3. **Target** — All employees or filter by department, site, country, and more.  
  4. **Run** — Dual leaderboards, invites, mid-challenge nudges; move members if needed.  
  5. **Report** — Team and individual boards, enrollment health, points activity.  
- **Measure note:** Population-level program health — not private clinical surveillance.  
- **Visual:** Admin dashboard / teams management mock (product-real styling; illustrative rows).

### S7 — Customer result (lean, approved)

- **Eyebrow:** Customer outcome  
- **H2:** A team program with named results.  
- **Feature:** Tata Motors — Step Up & Elevate  
  - **70%** employee engagement  
  - **43 teams** across plants and offices  
  - **53%** of teams reduced average weight  
  - **7,600+** average daily steps per person  
- **Secondary (compact):** Landmark Group — 5,000+ participants across 6 in-house teams (30 days).  
- **Links:** Read customer stories  
- **Disclaimer:** Customer experiences vary…

### S8 — FAQ

1. **How is team score calculated?**  
   Team score is the average of members’ individual scores, not the sum. Every member’s contribution counts equally; inactive members pull the average down.

2. **Who creates teams — HR or employees?**  
   Either. Admins can create teams one-by-one or via CSV/Sheets. If enabled for your company, captains can create teams and invite colleagues. Admins retain edit, move, and delete control either way.

3. **What team size works best?**  
   You set a maximum per challenge. Help guidance: 4–6 members keeps accountability high while still feeling social. Typical configurable range is roughly 3–10.

4. **Which challenge formats support teams?**  
   Custom, Streak, and Journey support optional team mode. Race is individual-only. For team step competition, choose Streak, Journey, or a Custom challenge with step tasks.

5. **Can we run department or multi-site team challenges?**  
   Yes. Pre-create teams by department or location, or filter the challenge audience by department, city, or country. One program can span time zones with local midnights for start, reset, and end.

### S9 — Trust + final CTA

- **Trust H2:** Participation data your security team can review.  
- **Certs:** HIPAA · SOC 2 · GDPR · ISO 27001 · ISO 27701  
- **Final H2:** Ready to run a team challenge people finish together?  
- **Final lead:** See team formation, average scoring, and dual leaderboards in a 30-minute walkthrough.  
- **CTAs:** Book a demo · See pricing  
- **Checks:** Average scoring · Bulk team upload · Dual leaderboards · Custom, Streak, or Journey  

### Related (light)

Steps Challenge · Multi-activity challenges · Virtual marathon · Remote team wellness · Measure program impact  

---

## 4. Visual / UI mock plan

Prefer product-real over abstract illustration.

| Placement | Mock | Notes |
|-----------|------|-------|
| Hero | iPhone-style **team leaderboard** | Ranks, avatars, avg score, member count; Individual/Team toggle chrome |
| Hero secondary | Admin **Teams** strip | Create Team, Bulk upload, max size chip — illustrative |
| Fairness | Simple **formula card** + two mini team compare rows | “Squad A avg 82 vs Squad B avg 71” — labeled illustrative |
| Formation | Three path cards with small icons | No stock photo people |
| HR section | Desktop **admin** panel | Team list, member count, avg, actions — CDN product image if available + caption |
| Proof | Metric chips only | No invented logos |

**Illustrative rule:** All mock names, scores, and dept labels are sample UI, not customer data.

---

## 5. Structure decisions (why this page)

1. **Lead with fairness (average scoring)** — Primary HR objection to team wellness is “athletes win for free.” Product truth answers it cleanly.  
2. **Formation before formats** — Buyers must believe they can *set up* teams at enterprise scale before they pick Custom vs Streak.  
3. **Formats are secondary and honest** — Only list formats that support teams; call out Race exclusion.  
4. **Lean customer block** — Tata is a real team-tagged case study; one deep card beats a generic proof wall.  
5. **Not a Steps clone** — Steps centers formats + phone sync + data integrity. Team centers social accountability + admin team ops. Shared chrome (nav, FAQ, trust, CTAs) only.  
6. **No unapproved participation “3x” claims** as hero proof; prefer named case studies. OS marketing brief mentions Wipro 3X — only use if a published case study on this page is linked; we did **not** lead with it here to stay conservative.

---

## 6. Sources index

### Help docs
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-manage-teams.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/employee/challenges/how-do-teams-work.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-a-challenge.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-custom-challenge.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-streak-challenge.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-journey-challenge.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-race-challenge.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-what-challenge-formats.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-manage-challenge.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-can-i-run-multiple-challenges-in-parallel.md`  

### Product OS
- `vc-os/vfit-os/specs/05-social-community/teams.md`  
- `vc-os/vfit-os/specs/02-challenges-gamification/challenge-system-overview.md`  
- `vc-os/vfit-os/specs/02-challenges-gamification/leaderboards.md`  
- `vc-os/vfit-os/specs/02-challenges-gamification/challenge-journey.md`  

### Dashboard
- `vc-dashboard-design/docs/modules/wellness.md` (top challenge teams, challenge wizard teams & audience)  
- `vc-dashboard-design/docs/superpowers/specs/2026-07-19-create-challenge-wizard-redesign-PROMPT.md` (Journey team-only toggle note)  

### Case studies
- `tata-motors-step-up-elevate.md`  
- `landmark-group-walkathon.md`  
- `global-corporate-virtualwalkathon.md` (secondary / multi-org context)  

### Design system
- `styled-homepage/`  
- `styles/enterprise.css`  
- `grok/vantage-fit-steps-challenge-v1.html` (chrome + CSS patterns)  
- `consolidated/STEPS-CHALLENGE-DECISIONS.md` (quality bar; structure re-evaluated)  

---

## 7. Gaps / watch-outs

| Gap | Handling on page |
|-----|------------------|
| Race has no teams | Explicit honest note in formats section |
| E-Marathon team config undocumented | Not claimed as a team format |
| Captain create needs company enablement | FAQ + formation footnote |
| Automated team creation is AM-assisted | Mention lightly, not self-serve claim |
| Weight-loss team outcomes (Tata 53%) are program-specific | Keep in customer block only; not universal claim |
| Live marketing may still over-claim “any challenge is a team challenge” | Page stays product-accurate |
| Illustrative UI scores | Always labeled |

---

## 8. File deliverables

| File | Role |
|------|------|
| `grok/TEAM-CHALLENGE-BRIEF.md` | This document |
| `grok/vantage-fit-team-challenge-v1.html` | High-fidelity mock; links `../styles/enterprise.css` |

---

_Research date: 2026-08-05 · Model bake-off deliverable (Grok)_
