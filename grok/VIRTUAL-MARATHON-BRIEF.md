# Virtual Marathon — Solutions Page Brief

**Page:** Virtual Marathon (individual Solutions / use-case page)  
**Live URL (context only):** https://www.vantagefit.io/virtual-marathon/  
**Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; program managers who run company events  
**North star:** **Employee participation** — why a virtual marathon *event* mobilizes the company (distance goal, ceremony, finish recognition) vs always-on daily steps  
**Visual baseline:** `styled-homepage/` + `styles/enterprise.css` + prior `grok/vantage-fit-steps-challenge-v1.html`  
**Primary CTA:** Book a demo · **Secondary:** See pricing  

---

## 1. Research takeaways (product truth)

Sources prioritized: help docs (`vantagefit-astro/content/en/help/`), `vfit-os` challenge specs, named case studies. Legacy marketing YAML / live page was **not** used as the blueprint.

### 1.1 What “Virtual Marathon” actually is in product

| Product concept | What it is | Self-serve? | Source |
|-----------------|------------|-------------|--------|
| **E-Marathon** | Virtual marathon where **steps convert to distance** (km or miles). Leaderboard ranks by **total distance**. Default **1,000 steps = 1 km** (configurable). One implicit task: walk/run. Cumulative (no streak reset). | Yes — Create Challenge → E-Marathon | Admin: create e-marathon; Employee: what-is-an-e-marathon; Formats help |
| **One-day virtual marathon** | Same E-Marathon format constrained to a **single 24-hour window**. High-energy kickoff / wellness-day lever. | Yes (E-Marathon with same start/end date) | Admin: when-to-use one-day virtual marathon |
| **Marathon Event** | **GPS-tracked** real-world distance (live route). Used for physical running events. | **Ops-only** (account manager) | Formats help; employee formats (Marathon Event) |
| **OS `vfit_marathon`** | Spec for single-day multi-target distance event (tiered targets / rewards). Aligns with one-day event narrative. | Spec draft | `vc-os/vfit-os/specs/02-challenges-gamification/challenge-marathon.md` |

**Primary page story = E-Marathon** (self-serve virtual distance event).  
**Secondary = one-day guidance** (when to use a 24-hour company event).  
**Do not oversell** GPS Marathon Event as the default product — mention only as specialized ops-supported option if needed in FAQ, not hero.

**How E-Marathon differs from a Steps Race page:**

| | Race (Steps Challenge page) | E-Marathon (this page) |
|--|-----------------------------|-------------------------|
| Leaderboard metric | Total steps | **Distance (km / miles)** |
| Conversion | None | Fixed ratio (default 1,000 steps = 1 km) |
| Framing | Competition / sprint | **Marathon / finish-line event** |
| Best duration | 1–2 weeks | **2–4 weeks** typical; or **one day** for event energy |
| GPS required | No | **No** — steps only |

### 1.2 Capabilities this page should own (product-real)

| Capability | Why it matters to HR | Source |
|------------|----------------------|--------|
| **Steps → distance conversion** | Progress feels tangible (“42 km”) vs abstract step totals | Create e-marathon; employee e-marathon |
| **Default 1,000 steps = 1 km** (customizable) | Easy mental math; HR can tune | Create e-marathon |
| **km or miles display** | US + global workforces | Create e-marathon |
| **No GPS required** | Inclusive: walkers, hybrid, no route logistics | Employee e-marathon note |
| **Simple admin setup** | Name, dates, ratio, unit, audience — publish | Create e-marathon steps 1–5 |
| **Distance leaderboard** | Ceremony + ranking without physical finish line | Employee leaderboard section |
| **Collective company distance** | Shared goal (“we hit 5,000 km”) drives mobilization | Create e-marathon best practices |
| **Theme like a real event** | Banner, name, finish-line story | Create e-marathon best practices |
| **One-day or multi-week** | Kickoff day vs multi-week distance campaign | One-day help + create e-marathon |
| **Audience filters** | Pilot a region or company-wide | Target audience (linked from create flow) |
| **Timezone localization** | Global same-day or multi-week fairness | Time zones help |
| **Phone-first step sync** | Join without wearable mandate | Step syncing help |
| **Platform recognition** | Certificates (when enabled on challenges), badges (incl. marathon-distance levels) | Certificates help; badges help |

**Ops-only GPS Marathon Event:** leave off hero and primary feature grid. Optional FAQ note only: real GPS race logistics need account-manager setup.

### 1.3 Fairness / distance-tracking objections (answer with product proof)

| Objection | Product answer | Source |
|-----------|----------------|--------|
| “Is distance GPS / can people cheat routes?” | Distance is from **step count**, not GPS. Same rules for walkers and runners. No route required. | Employee e-marathon |
| “Is 1,000 steps really 1 km?” | **Default conversion is fixed and company-configurable** — it is a fair, transparent ratio, not individual GPS. | Create e-marathon |
| “Will late syncs break the podium?” | Sync late-data behavior is platform-wide; Race documents a **3-day buffer** for winner selection. E-Marathon is cumulative distance; advise syncing and fair close. Don’t invent an E-Marathon-only buffer if not documented. | Race help (buffer); step sync help |
| “Can non-runners finish?” | Yes — **regular daily steps count**. Walking accumulates distance. | Employee e-marathon |
| “One-day full marathon impossible for most” | One-day help: offer **realistic distance tiers** (5K / 10K / half / full messaging in program design); full marathon ~50k steps in one day is only for very active employees. | One-day virtual marathon help |

**Note on formats help “standard distances (5K, 10K, half, full)”:** formats overview lists these as E-Marathon options. Create-e-marathon focuses on conversion ratio + duration rather than a multi-tier target UI. Page copy treats **distance framing / finish-line goals** as program design (admin theme + communication), and cites standard race distances as **illustrative** event framing where not proven as forced product tiers in the create wizard.

### 1.4 Live page weaknesses (audit notes, not source of truth)

1. Event narrative diluted into generic challenge feature list.  
2. Under-sells **steps→distance** as the product differentiator vs raw step races.  
3. Does not clarify **self-serve E-Marathon vs ops-only GPS**.  
4. Weak or vague proof; Embrace Pet Insurance marathon case study is unused.  
5. Fairness / “do walkers count?” not answered with product truth.

### 1.5 Proof we can cite (named, published)

| Outcome | Org | Context | Source |
|---------|-----|---------|--------|
| **94%** workforce engagement | Embrace Pet Insurance (EPI) | 8-week “Fitness Guru” **marathon**; 71+ participants; 19M+ steps; ~20 km avg distance; Cleveland, OH insurance | Case study: `embrace-pet-insurance-marathon` |
| **89%** engagement (title); 540+ participants | Cotiviti | Week-long **virtual walkathon** (distance-adjacent event energy) | Case study: `cotiviti-virtual-walkathon` |
| One-day **typical ranges** (participation 25–60% of active users, etc.) | Help guidance | **Illustrative / typical ranges**, not guarantees | One-day virtual marathon help |

**Rule:** Pair metric with org + program context. *Customer experiences vary by workforce and program design.*  
Label help-doc typical ranges **illustrative**.

### 1.6 Assumptions (stated)

- SEO URL `/virtual-marathon/` maps primarily to **E-Marathon** demand, not GPS race logistics.  
- US enterprise buyers want a **flagship event** they can brand (wellness week, anniversary, World Heart Day) without road-closure logistics.  
- Primary conversion is **Book a demo**.  
- Security trust strip reuses homepage claims (HIPAA, SOC 2, GDPR, ISO 27001/27701) without inventing certifications.  
- Certificates: platform can auto-generate completion certificates when enabled on challenges; E-Marathon create wizard docs do not walk certificate config explicitly — page uses “finish recognition” + optional certificates carefully, not a certificate-only promise.

### 1.7 Gaps / unknowns

- Exact E-Marathon certificate toggle UI in create wizard (not documented on create-e-marathon page).  
- Whether multi-tier 5K/10K/half/full are first-class targets in self-serve E-Marathon vs program messaging only.  
- Dedicated E-Marathon end-buffer / winner-selection flow (Race documents 3-day buffer explicitly).  
- GPS Marathon Event setup depth (ops-only — intentionally de-emphasized).

---

## 2. Page strategy

### Job of this page

Help an enterprise HR buyer answer:  
1. Will a **virtual marathon** get people to show up (event energy, not another step spreadsheet)?  
2. Is progress **fair and inclusive** without GPS race day logistics?  
3. Can HR **launch and theme** it without a six-month project?  
→ Book a demo.

### Positioning line

> A virtual marathon turns company wellness into an **event** — steps become distance, finish lines feel real, and HR runs it from the dashboard without road closures or bib logistics.

### Distinguish from Steps Challenge page

| Steps Challenge page | Virtual Marathon page |
|----------------------|------------------------|
| Owns **four formats** (Race / Streak / Journey / E-Marathon) | Owns **marathon / distance event** narrative |
| Habit + competition + journey decision aid | Flagship **ceremony** + distance goal |
| E-Marathon is one card among four | E-Marathon is the **hero product** |

Related link only: Step challenges (and Team / multi-activity) at footer level.

### Narrative arc (decided — lean)

| # | Section | Intent |
|---|---------|--------|
| 1 | **Hero** | Event promise + dual CTAs + product-real distance UI mock |
| 2 | **Proof strip** | Early credibility (Embrace marathon + adjacent walkathon) |
| 3 | **How it works** | Steps → distance, leaderboard, no GPS required |
| 4 | **Event design** | Multi-week vs one-day; when each mobilizes |
| 5 | **Why people join** | Inclusive walkers, tangible km, collective goal, ceremony |
| 6 | **Built for HR** | Simple E-Marathon wizard → invite → leaderboard → close |
| 7 | **Customer result** | Embrace Pet Insurance (optional, real case study) |
| 8 | **FAQ** | Fairness, GPS, walkers, duration, global (~4–5) |
| 9 | **Trust + final CTA** | Security + Book a demo / pricing |

No encyclopedia. No full challenge catalog. No invented GPS race ops.

### What we deliberately de-emphasize

- Ops-only GPS Marathon Event logistics.  
- Full Race/Streak/Journey tutorial (belongs on Steps page).  
- Fabricated ROI or clinical outcomes.  
- Help-doc “typical range” metrics as guarantees (label illustrative if shown).

---

## 3. Full copy deck

### Meta

- **Title:** Corporate Virtual Marathon Platform for Teams | Vantage Fit  
- **Description:** Run a company virtual marathon employees finish — steps convert to distance, inclusive for walkers, live leaderboards, no race-day logistics. Book a demo.

### Nav (aligned with styled-homepage)

Solutions · Features · Resources · Pricing · **Book a demo**  
Solutions mega: By program — **Virtual marathons** current.

### S1 — Hero

- **Eyebrow:** Solutions · Virtual Marathon  
- **H1:** A company marathon without race-day logistics.  
- **Lead:** Launch a virtual marathon where employee steps convert to distance. Theme it like a real finish line, rank people fairly on km or miles, and mobilize the whole company from one admin dashboard.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** See pricing  
- **Micro line:** Steps convert to distance · Walkers count · No GPS routes required  

**Hero product UI (mock, product-real):**

- Challenge card: “Company Marathon 2026” · E-Marathon · 21 days  
- Conversion chip: Default **1,000 steps = 1 km**  
- Distance leaderboard rows (illustrative names/ranks): e.g. 87.4 km, 82.1 km, 79.6 km  
- Personal progress: “Your distance · Rank · Days left”  
- Label small: *Product UI concept · sample leaderboard data*

### S2 — Proof strip

- **Kicker:** Teams already running distance events with Vantage Fit  
- **Chips:**  
  - **94%** engagement · Embrace Pet Insurance · 8-week marathon  
  - **19M+** steps · Embrace Pet Insurance · published program total  
  - **540+** participants · Cotiviti · week-long virtual walkathon  
- **Disclaimer:** Customer experiences vary by workforce and program design.

### S3 — How it works

- **Eyebrow:** How E-Marathon works  
- **H2:** Steps become distance. Distance becomes the race.  
- **Lead:** Employees walk or run as they already do. Vantage Fit converts step counts into km or miles with a fixed company ratio — then ranks everyone on a distance leaderboard.

| Step | Title | Body |
|------|-------|------|
| 1 | Steps sync | Phones (Apple Health / Google Fit) or optional wearables feed step counts automatically. |
| 2 | Convert | Default **1,000 steps = 1 km**. Admins can customize the ratio and choose km or miles. |
| 3 | Rank by distance | Leaderboard shows total distance covered — not raw steps — so the marathon framing stays real. |
| 4 | Finish the story | Share individual ranks and **company-wide distance** milestones (“We just passed 5,000 km”). |

**Callout:** Distance comes from step count, not GPS. Employees do not need routes, race bibs, or a special workout mode for regular daily steps to count.

### S4 — Event design (multi-week vs one-day)

- **Eyebrow:** Design the event  
- **H2:** Multi-week distance campaign or one high-energy day.  
- **Lead:** E-Marathon duration is flexible. Match the format to the moment you need.

| Mode | Headline | Body | Best for |
|------|----------|------|----------|
| Multi-week | Steady accumulation | 2–4 weeks gives enough runway for meaningful distance and a visible leaderboard climb. Theme a finish line (“Walk the Pacific Coast,” company anniversary route). | Health month, quarterly flagship |
| One-day | Shared company moment | Single 24-hour window. Same-day results and celebration. Promote about a week ahead; push on the morning of. | Wellness day, World Heart Day, re-engagement spike |

**Foot note (illustrative):** One-day programs often see strong same-day energy when pre-promoted; help guidance cites typical participation ranges that **vary widely** — treat as planning context, not a guarantee.

**Foot CTA:** Want a 90-day calendar that pairs a marathon kickoff with habit challenges? Book a demo.

### S5 — Why people join

- **Eyebrow:** Built for participation  
- **H2:** Event energy people can actually finish.  
- **Cards:**  
  1. **Inclusive by design** — Walkers and runners both accumulate distance from daily steps. No GPS route, no “must run” gate.  
  2. **Tangible progress** — “I hit 100 km” is easier to feel than “I hit 100,000 steps.”  
  3. **Collective finish line** — Publish company-wide km as a shared goal so quiet participants still feel part of the ceremony.  
  4. **Live distance leaderboard** — Rank, search, and department filters keep competition visible without spreadsheets.  
  5. **Global-ready windows** — Start and end localize to each employee’s midnight so multi-region teams share one event fairly.  
  6. **Recognition that sticks** — Leaderboard finish plus platform badges (including marathon-distance achievements) and certificates when you enable them on a challenge.

### S6 — Built for HR

- **Eyebrow:** For HR & program managers  
- **H2:** Publish a marathon from the dashboard.  
- **Steps:**  
  1. **Create** — Choose **E-Marathon**. Name it like an event, set dates, add a marathon-themed banner.  
  2. **Configure distance** — Set steps-to-distance ratio (default 1,000:1) and unit (km or miles).  
  3. **Target** — All employees or filter by department, country, city.  
  4. **Invite & promote** — Email + in-app; for one-day events, plan ~1 week of pre-comms and a day-of push.  
  5. **Run & close** — Watch distance accumulate, share company milestones, celebrate finishers and ranks.  
- **Note:** E-Marathons are intentionally simple — no weekly themes or multi-task scoring required.  
- **Measure:** Enrollment and activity patterns, challenge leaderboard by distance, reward activity where configured — program health leadership can read.

### S7 — Customer result (Embrace)

- **Eyebrow:** Customer outcome  
- **H2:** A marathon program with a published result.  
- **Feature:** Embrace Pet Insurance — **94%** workforce engagement on an 8-week Fitness Guru marathon; 71+ participants; 19M+ steps; ~20 km average distance per participant.  
- **Secondary:** Cotiviti — 540+ participants in a week-long virtual walkathon (event-style energy).  
- **Disclaimer:** Customer experiences vary by workforce and program design. Metrics from published Vantage Fit case studies.

### S8 — FAQ

1. **Is distance tracked with GPS?**  
   No for E-Marathon. Distance is calculated from step count using your company’s conversion ratio. Employees do not need GPS workouts or fixed routes. (A separate ops-supported Marathon Event format exists for GPS-tracked physical races if you need that later.)

2. **Do walkers count the same as runners?**  
   Yes. Regular daily steps convert to distance. Walking accumulates the same way running does under the fixed ratio.

3. **How does the 1,000 steps = 1 km rule work?**  
   That is the default conversion. Admins can change the ratio during setup. Everyone in the challenge uses the same ratio, so ranking stays consistent.

4. **Should we run one day or several weeks?**  
   Use one day for a shared company moment (wellness day, launch, anniversary). Use 2–4 weeks when you want meaningful cumulative distance and a longer leaderboard story. One-day events are not habit programs — pair them with longer challenges if you need habits.

5. **Can global teams join one marathon?**  
   Yes. Challenge start and end localize to each employee’s midnight. Audience filters can also scope by country or site if you prefer regional heat races.

### S9 — Trust + final CTA

- **Security eyebrow:** Enterprise security  
- **H2:** Participation data your security team can review.  
- **Certs:** HIPAA · SOC 2 · GDPR · ISO 27001 · ISO 27701  
- **Final H2:** Ready to run a company virtual marathon?  
- **Final lead:** See E-Marathon setup, the employee distance experience, and HR reporting in a 30-minute walkthrough.  
- **CTAs:** Book a demo · See pricing  
- **Checks:** Self-serve E-Marathon · Phone-first · Walkers included · Global-ready  

### Related (light)

- Step challenges  
- Team challenges  
- Multi-activity challenges  
- Remote team wellness  
- Wellness rewards  

---

## 4. Structure rationale (summary)

1. **Event, not format catalog** — Buyers landing on “virtual marathon” want ceremony + distance, not four step format cards.  
2. **Product-real hero UI** — Distance leaderboard + conversion ratio beats stock “happy runners” photography as proof of product.  
3. **Fairness up front** — GPS objection is the #1 enterprise skeptic question; answer with step conversion truth.  
4. **One-day vs multi-week** — Unique strategic lever documented in help; differentiates from generic challenge pages.  
5. **Embrace only as real proof** — Optional customer block with named metrics; Cotiviti as secondary event-style proof.  
6. **Lean** — Nine sections max, FAQ ~5, no feature encyclopedia, GPS ops de-emphasized.

---

## 5. Sources

### Help docs (priority)

| File | Used for |
|------|----------|
| `.../admin/challenges/admin-how-do-i-create-e-marathon.md` | Setup, conversion default, duration, best practices, collective distance |
| `.../admin/challenges/admin-when-to-use-a-one-day-virtual-marathon.md` | One-day when/when-not, promotion, illustrative ranges |
| `.../admin/challenges/admin-what-challenge-formats.md` | E-Marathon vs Race vs ops Marathon Event |
| `.../employee/challenges/what-is-an-e-marathon.md` | Employee experience, no GPS, leaderboard by distance |
| `.../employee/challenges/how-does-the-leaderboard-work.md` | Leaderboard behavior, filters |
| `.../admin/challenges/admin-can-i-run-challenges-across-time-zones.md` | Global fairness |
| `.../admin/challenges/admin-how-do-i-configure-certificates.md` | Certificate platform capability (careful claim) |
| `.../admin/challenges/admin-how-do-badges-work.md` | Marathon-distance badge recognition |
| `.../employee/getting-started/how-does-step-syncing-work.md` | Phone-first sync |
| `.../admin/challenges/admin-how-do-i-create-race-challenge.md` | Contrast + 3-day buffer context (not over-attributed to E-Marathon) |

### Case studies

| File | Used for |
|------|----------|
| `.../casestudy/embrace-pet-insurance-marathon.md` | 94% engagement, 8-week marathon, steps/distance stats |
| `.../casestudy/cotiviti-virtual-walkathon.md` | Event-style walkathon participation proof |

### VFit OS

| File | Used for |
|------|----------|
| `vc-os/vfit-os/specs/02-challenges-gamification/challenge-marathon.md` | Single-day multi-target marathon event behavior (draft) |
| `vc-os/vfit-os/FEATURE-INDEX.md` | Challenge: Marathon entry |

### Design system

| Path | Used for |
|------|----------|
| `styles/enterprise.css` | Tokens, nav, buttons, shells |
| `styled-homepage/` | Nav mega, brand, enterprise rhythm |
| `grok/vantage-fit-steps-challenge-v1.html` | Solutions-page section quality bar |
| `consolidated/vantage-fit-steps-challenge-consolidated.html` | Leaner consolidation reference |

---

## 6. Meta drafts (SEO)

| Field | Draft |
|-------|--------|
| **Title** | Corporate Virtual Marathon Platform for Teams \| Vantage Fit |
| **Meta description** | Run a company virtual marathon employees finish — steps convert to distance, inclusive for walkers, live leaderboards, no race-day logistics. Book a demo. |
| **H1** | A company marathon without race-day logistics. |
| **Primary keyword cluster** | corporate virtual marathon, company virtual marathon challenge, employee virtual marathon, e-marathon wellness |

---

## 7. Deliverable checklist

- [x] `grok/VIRTUAL-MARATHON-BRIEF.md` (this file)  
- [x] `grok/vantage-fit-virtual-marathon-v1.html` — high-fidelity mock linking `../styles/enterprise.css`  
- [x] Product claims traceable; no invented customers/metrics  
- [x] Illustrative labels on sample UI / non-guaranteed ranges  
- [x] Primary CTA Book a demo · Secondary See pricing  
- [x] FAQ covers fairness / distance tracking with product proof  
- [x] GPS Marathon Event not oversold  
