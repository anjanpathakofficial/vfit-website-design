# Steps Challenge — Solutions Page Brief

**Page:** Steps Challenge (individual Solutions / use-case page)  
**Live URL (context only):** https://www.vantagefit.io/steps-challenge/  
**Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; program managers who run challenges  
**North star:** **Employee participation** (homepage spine) — why a step challenge gets people to join, stick, and give HR numbers leadership believes  
**Visual baseline:** `styled-homepage/` + `styles/enterprise.css`  
**Primary CTA:** Book a demo · **Secondary:** See pricing  

---

## 1. Research takeaways (product truth)

Sources prioritized: help docs (`vantagefit-astro/content/en/help/`), `vc-dashboard-design` wellness admin, `vfit-os` challenge specs, named case studies. Legacy `steps-challenge.yaml` was **not** used as the blueprint.

### 1.1 What “Steps Challenge” actually is in product

Steps is not one fixed contest. Self-serve admin formats that are **steps-primary**:

| Format | What it is | Best for | Source |
|--------|------------|----------|--------|
| **Race** | Pure step competition; no daily target; leaderboard by total steps; admin picks top 3 after **3-day sync buffer** | 1–2 week energy bursts | Help: create race challenge |
| **Streak** | Daily step target; ranked by **days completed** (total steps as tiebreak); optional teams | 2–4 week habit building | Help: create streak challenge |
| **Journey** | Steps drive progress on a **visual map** with sequential milestones; 3 built-in templates (7 Wonders, Backpacking Europe, Everest Run) | 4–8 week immersive programs | Help: create journey challenge |
| **E-Marathon** | Steps converted to **distance** (default **1,000 steps = 1 km**); ranked by km/miles | Virtual marathon / distance events | Help: create e-marathon |

Related (not the hero of this page): Custom multi-activity challenges can include steps among other tasks; Virtual Marathon product URL may map to E-Marathon / event formats.

**Ops-only formats** (Level, GPS Marathon Event, Weight Burn, Training Plans) stay off the primary pitch — mention only if demo conversation needs depth.

### 1.2 Capabilities the old marketing page under-sells or misses

| Capability | Why it matters to HR buyers | Source |
|------------|----------------------------|--------|
| **Four self-serve step formats** (not one generic “step challenge”) | Buyers choose race vs habit vs journey vs distance | Formats help |
| **Phone-only participation** — no wearable required | Removes the #1 enrollment excuse | Help: “Do I need a fitness tracker?” |
| **Auto step sync** (Apple Health / Google Fit / Fitbit / Garmin) | Low friction = higher join + stick rates | Step syncing help |
| **3-day end buffer** before winner selection | Fair rankings when wearables lag | Race challenge help |
| **Audience filters** (dept, country, city, etc.) + public/private | Pilot a site or run company-wide | Target audience help |
| **Parallel challenges** with independent leaderboards | Always-on streak + quarterly race | Parallel challenges help |
| **Timezone localization** (local midnight start/reset/end) | Global HQ programs without four copies | Time zones help |
| **Teams** (streak/journey optional; team score = average) | Peer pressure for participation | Format docs |
| **Vantage Points → gift cards**, local currency display | Rewards that feel real, multi-country | Wellness rewards help |
| **Certificates / badges** | Recognition without only “top 3” | Certificates / badges help |
| **Admin reports** (employee enrollment status, transactions, redemptions, challenge leaderboard) | Board-ready participation story | Reports help |
| **Templates** (journey maps; challenge templates) | Launch without creative project | Formats / templates help |

### 1.3 Live page weaknesses (audit)

1. **Feature tour, not purchase path** — “types / leaderboards / rewards” without buyer jobs.  
2. **Format names listed without decision logic** — Race / Streak / E-marathon / Journey buried as bullets.  
3. **Participation not defined** — homepage north star absent.  
4. **Weak proof** — generic coach quote; stronger named outcomes exist (Allston, DLA+, Cotiviti, etc.).  
5. **Under-sells HR operations** — wizard, buffer, reports, timezone, parallel programs.  
6. **Inclusivity underplayed** — phone-first is a conversion lever for enterprise (desk workers, hybrid, no Fitbit mandate).  
7. **Copy tone** is catalog-like; not outcome-led SaaS solutions page.

### 1.4 Proof we can cite (named, published)

| Outcome | Org | Context | Source |
|---------|-----|---------|--------|
| **94%** employee engagement | Allston Trading | 4-week walkathon / annual fitness program; US + UK | Case study: `allston-trading-step-challenge` |
| **87%** employee engagement | DLA Plus | 3-week Winter Step Challenge (“Step It Up in 2022”) | Case study: `dla-winter-step-challenge` |
| **89%** engagement (title claim); 540+ participants | Cotiviti | Week-long virtual walkathon | Case study: `cotiviti-virtual-walkathon` |
| **94%** engagement | Embrace Pet Insurance | 8-week marathon (step/distance-adjacent) | Case study: `embrace-pet-insurance-marathon` |
| **86%** engagement | Brazosport ISD | Multi-activity campaign incl. steps | Case study / homepage |

**Rule:** Always pair metric with org + program context. Add: *Customer experiences vary by workforce and program design.*

### 1.5 Assumptions (stated)

- US enterprise buyers often start with a **step challenge pilot** before year-round wellness.  
- “Steps Challenge” URL remains the SEO/entry page for step-format demand even though product has multiple formats.  
- Primary conversion is **Book a demo**, not self-serve signup.  
- Security trust strip reuses homepage claims (HIPAA, SOC 2, GDPR, ISO 27001/27701) without inventing certifications.

---

## 2. Page strategy

### Job of this page

Help an enterprise HR buyer answer:  
1. Will people **join**?  
2. Can we **run it** without a six-month project?  
3. Can I **show leadership** who participated and what moved?  
→ Book a demo.

### Positioning line

> A corporate step challenge is the fastest way to make wellness **participatory** — multiple formats, phone-first tracking, rewards, and HR reporting so you can prove it.

### Narrative arc (decided)

| # | Section | Intent |
|---|---------|--------|
| 1 | **Hero** | Outcome promise + dual CTAs + micro trust |
| 2 | **Proof strip** | Early credibility (named % + orgs) |
| 3 | **Formats** | Decision aid: Race / Streak / Journey / E-Marathon |
| 4 | **Why people join** | Employee-side participation engine (sync, teams, rewards) |
| 5 | **Built for HR** | Launch → manage → measure (admin truth) |
| 6 | **Customer outcomes** | Deeper proof + quote-ready story |
| 7 | **FAQ** | Kill objections (wearable, remote, fairness, multi-site) |
| 8 | **Trust + final CTA** | Security + Book a demo / pricing |

No blog dump. No full feature catalog. Related links only at footer level.

### What we deliberately de-emphasize

- Detailed wearable model lists (link to product if needed).  
- Ops-only formats.  
- Clinical claims / ROI fabrication.  
- “Cue > Action > Reward” jargon without HR translation.

---

## 3. Full copy deck

### Meta

- **Title:** Corporate Step Challenge Platform for Teams | Vantage Fit  
- **Description:** Run a company step challenge employees join — Race, Streak, Journey, or E-Marathon formats, phone-first tracking, rewards, and HR analytics. Book a demo.

### Nav (aligned with styled-homepage)

Solutions · Features · Resources · Pricing · **Book a demo**  
Solutions mega: By program / By need (Steps Challenge current under By program).

### S1 — Hero

- **Eyebrow:** Solutions · Steps Challenge  
- **H1:** A step challenge employees actually join.  
- **Lead:** Launch a company-wide step challenge from the admin dashboard — phone-first tracking, live leaderboards, rewards people redeem, and participation reports leadership can read.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** See pricing  
- **Micro line:** No wearable required · Self-serve formats · Global-ready  

### S2 — Proof strip

- **Kicker:** Teams already running step challenges with Vantage Fit  
- **Chips:**  
  - **94%** engagement · Allston Trading · 4-week program  
  - **87%** engagement · DLA Plus · 3-week Winter Step Challenge  
  - **89%** engagement · Cotiviti · week-long virtual walkathon  
- **Disclaimer:** Customer experiences vary by workforce and program design.

### S3 — Formats

- **Eyebrow:** Choose your format  
- **H2:** One product. Four ways to run a step challenge.  
- **Lead:** Pick the structure that matches your goal — a short race, a daily habit streak, a visual journey, or a virtual distance event.

| Format | Headline | Body | Fit |
|--------|----------|------|-----|
| Race | Pure competition | Total steps on a live leaderboard. Best as a 1–2 week sprint. Admins confirm top finishers after a 3-day sync buffer so late wearable data counts. | Quick energy |
| Streak | Daily consistency | Set a daily step target (many teams start ~8,000). Rank by days completed. Optional teams. Ideal 2–4 weeks. | Habit building |
| Journey | Progress you can see | Steps move employees along a themed map with milestones. Built-in templates (7 Wonders, Europe, Everest). Strong for multi-week programs. | Immersion |
| E-Marathon | Distance from steps | Convert steps to km or miles (default 1,000 steps = 1 km). Feels like a marathon without GPS routes. | Virtual event |

**Foot CTA:** Not sure which format? Book a demo — we’ll map a 90-day challenge calendar.

### S4 — Why people join

- **Eyebrow:** Built for participation  
- **H2:** Lower the barrier. Raise the join rate.  
- **Cards:**  
  1. **Phone-first tracking** — Steps sync from the phone sensors employees already carry. Wearables optional for extra accuracy.  
  2. **Always-on leaderboards** — Real-time standings keep the challenge social and visible.  
  3. **Teams when you want them** — Optional team modes average individual scores so departments compete together.  
  4. **Rewards that cash out** — Vantage Points for progress and milestones; redeem for gift cards in local currency.  
  5. **Inclusive by design** — Audience filters for pilots; public company-wide when you’re ready.  

### S5 — Built for HR

- **Eyebrow:** For HR & program managers  
- **H2:** Launch in the dashboard. Measure what matters.  
- **Steps (process, not jargon):**  
  1. **Create** — Choose format in Create Challenge; set name, dates, image, privacy.  
  2. **Target** — All employees or filter by department, country, city, and more.  
  3. **Incentivize** — Attach point values and optional certificates.  
  4. **Run** — Invite, nudge mid-challenge, watch leaderboards.  
  5. **Close fairly** — 3-day buffer for final syncs on race-style finishes; select winners; export reports.  
- **Measure note:** Track enrollment and activity status (active / inactive / dormant), challenge leaderboards, and reward transactions — population-level program health, not private clinical surveillance.  
- **Global note:** One challenge can span time zones — start, daily reset, and end localize to each employee’s midnight.

### S6 — Deeper proof

- **Eyebrow:** Customer outcomes  
- **H2:** Step programs with named results.  
- **Feature story:** DLA Plus — **87%** engagement on a 3-week Winter Step Challenge; 1.49M+ steps.  
- **Secondary cards:** Allston Trading **94%** (4 weeks); Cotiviti **89%** / 540+ participants (1 week walkathon).  
- **Links:** Read customer stories · View testimonials  
- **Disclaimer:** Customer experiences vary…

### S7 — FAQ

1. **Do employees need a Fitbit or smartwatch?**  
   No. Phones track steps via Apple Health or Google Fit. Wearables (Fitbit, Garmin, Apple Watch, Samsung, etc.) are optional.

2. **Can remote and multi-office teams join the same challenge?**  
   Yes. Challenges are virtual. For global teams, daily resets and challenge windows localize by time zone.

3. **How do we keep rankings fair when devices sync late?**  
   Race-style challenges include a **3-day buffer** after the end date before admins confirm winners, so late syncs can settle.

4. **Can we run more than one challenge at a time?**  
   Yes. There is no platform limit on parallel challenges; scores and leaderboards stay independent.

5. **What can HR report to leadership?**  
   Enrollment and activity status, challenge leaderboards, points transactions, and redemptions — filterable and exportable as CSV.

6. **How do rewards work?**  
   Admins set point values on challenge tasks. Employees earn Vantage Points and redeem gift cards from a catalogue, with local-currency display for multi-country workforces.

### S8 — Trust + final CTA

- **Eyebrow:** Enterprise security  
- **H2:** Participation data your security team can review.  
- **Certs:** HIPAA · SOC 2 · GDPR · ISO 27001 · ISO 27701  
- **Final H2:** Ready to run your next step challenge?  
- **Lead:** See formats, employee experience, and HR reporting in a 30-minute walkthrough.  
- **Primary:** Book a demo · **Secondary:** See pricing  
- **Checks:** Self-serve formats · Phone-first · Global-ready · Single challenge or year-round calendar  

### Footer

Product / Solutions / Company columns; Solutions includes Steps Challenge (current), multi-activity, team challenges, remote teams.

---

## 4. Wireframe notes

```
[Nav — Solutions current]
[Hero — H1 + lead + CTAs | compact format chips visual]
[Proof strip — 3 metric chips]
[Formats — 4 equal cards, interactive highlight optional]
[Participation pillars — 2×2 or 5 card grid]
[HR ops — numbered rail + dashboard image]
[Outcomes — 1 feature + 2 support cards]
[FAQ — accordion]
[Trust band + Final CTA]
[Footer]
```

**Signature element:** Format decision cards (Race / Streak / Journey / E-Marathon) — product truth the old page buried; this page’s memorable core.

**Visual system:** Noto Sans, coral/mint/charcoal, pill CTAs, 22px radii, sticky nav + mega from homepage. Prefer product UI screenshots from CDN where available (challenge mobile, admin analytics).

---

## 5. Stats & quote source log

| Claim | Source path / URL |
|-------|-------------------|
| Allston 94% engagement, 4-week program | `content/en/casestudy/allston-trading-step-challenge.md` |
| DLA Plus 87%, 3 weeks, 1.49M steps | `content/en/casestudy/dla-winter-step-challenge.md` |
| Cotiviti 89% (title), 540+ participants, 1 week | `content/en/casestudy/cotiviti-virtual-walkathon.md` |
| Race buffer, formats, streak/journey/e-marathon rules | Help: `admin/challenges/*` |
| Phone-first, no wearable required | Help: `employee/getting-started/do-i-need-a-wearable.md` |
| Time zones, parallel challenges, rewards, reports | Help: corresponding admin articles |
| Security certs | Styled homepage / security feature page claims |

---

## 6. Deliverables

| File | Purpose |
|------|---------|
| `SOLUTIONS-BRIEF.md` | This document |
| `vantage-fit-steps-challenge-v1.html` | High-fidelity mock |

**Note:** An earlier hub mock (`vantage-fit-solutions-v1.html`) may remain in this folder from a prior prompt revision; **this brief and the Steps Challenge HTML are the deliverables for the current prompt.**

---

## 7. Open items (non-blocking)

1. Exact production URL for “Active Minutes → step equivalents” marketing claim needs product confirmation before promoting as a hero feature (help lists Active Minutes as a task type; conversion marketing copy on old page may overclaim).  
2. Cotiviti **89%** appears in title/meta; body emphasizes participant counts — keep with case-study attribution.  
3. Ship in Astro as refreshed `/steps-challenge/` when ready to replace legacy YAML-driven page.
