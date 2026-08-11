# Workforce Health Insights: Solutions Page Brief

**Page:** Workforce health insights (Section ② · Data out)  
**Intended URL:** `/solutions/workforce-health-insights/`  
**Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary program managers; IT cares about trust  
**North star:** One board-readable view of workforce wellness so leaders can act on participation, not guess from spreadsheets  
**Visual baseline:** `styled-homepage/` + `styles/enterprise.css` + Grok challenge peers  
**Primary CTA:** Book a demo · **Secondary:** See pricing  
**Chain role:** Fed by HRA (Data in) → this page (Data out) → Wellness rewards (Action)

---

## 1. Research takeaways (product truth)

Sources prioritized: help (`admin/workforce-health/`, `admin/reports/`), `vfit-os` specs (`wellness-score.md`, `reports-analytics.md`, product `workforce-health.md`), shared research. Live marketing analytics pages are **not** blueprint.

### 1.1 What this page is

**One** Solutions page that unifies what used to look like three separate “insights” stories:

| Lens | What HR gets | Source |
|------|--------------|--------|
| **Org Wellness Score** | Single 0-100 org number + 4 weighted components | Workforce Health help |
| **Participation** | Daily engagement: app open, logs, challenge join | Component 30% + reports |
| **Activity** | Effort and improvement: steps, workouts, calories, trends | Component 30% |
| **Challenge / adherence** | Completing assigned tasks and habits | Component 20% (Adherence) |
| **Baseline health signal** | HRA-driven fundamentals (BMI, BP, lifestyle) | Component 20% (Baseline) |
| **AI insights** | Streamed observations (drops, dept patterns, weekday patterns) | Workforce Health help |
| **Drill-downs** | Employee, department, team, location | Workforce Health help |
| **Exports** | CSV for scores and reports | Help + reports |
| **Lab aggregates** | Prevalence-style biomarker insights (anonymized) | Workforce Health + OS |

**Not three pages.** Participation, challenge, and activity analytics share one narrative: how healthy and engaged is the workforce, and where to intervene.

### 1.2 Org Wellness Score (hero product)

| Component | Weight | Measures |
|-----------|--------|----------|
| **Baseline** | 20% | HRA fundamentals (BMI, BP, chronic/lifestyle factors) |
| **Participation** | 30% | Daily engagement (open app, log, join) |
| **Activity** | 30% | Physical effort and improvement over time |
| **Adherence** | 20% | Challenge/task compliance and habits |

- Each component scored 0-100; weighted average = Org Wellness Score  
- Balanced components beat a high score driven by one pillar  
- Without HRA, baseline is less meaningful (product defaults baseline to neutral 50 when no HRA)  
- Allow **2-4 weeks** of data after activation for a reliable baseline  
- Review **monthly**, not daily (trend indicator)

### 1.3 AI streamed insights (examples from help)

Illustrative product-style observations (do not present as customer metrics):

- Participation dropped vs prior week  
- Engineering highest Activity, lowest Adherence  
- Monday strongest day; Friday engagement drops  
- Departments with no active challenge participants  

**Job:** prompt program action without spreadsheet analysis.

### 1.4 Drill-downs and reports

| View | Use |
|------|-----|
| Employee wellness report | Individual 0-100 + 4 components; export CSV (name, email, scores, dept, country) |
| Department | Compare engagement; target weak areas |
| Team | When team challenges run |
| Location | Country/city for global orgs |
| Trends | Weekly / monthly; component trends |
| Broader reports | Employee enrollment (active/inactive/dormant), challenge leaderboards, transactions, redemptions |

**Privacy rule (non-negotiable):** Individual wellness scores are for **aggregate program analysis and targeted interventions**, not performance evaluation or HR discipline.

### 1.5 Lab reports path (complementary)

- Employee self-upload or HR bulk upload (AM-setup for org-wide check-ups)  
- AI extracts biomarkers; employees see own reports  
- Admins see **aggregate, anonymized** prevalence (org / department / country per help) - never individual biomarker values  
- Optional health-risk targeting for private challenges shows **count only**, not identities (OS workforce-health)

### 1.6 Activation honesty

> The Workforce Health dashboard is **not fully self-serve**. A Vantage Fit account manager activates it.

- After enable, data accumulates immediately; 2-4 weeks for reliable score  
- Enable HRA alongside for meaningful Baseline (20%)  
- Premium / gated for lab intelligence in some deployments (AM)

### 1.7 Claim boundaries

**Do claim**
- Board-readable Org Wellness Score with four explainable components  
- Participation + activity + challenge adherence in one admin surface  
- AI-generated streamed insights for program design  
- Drill-down and CSV export for leadership reporting  
- Aggregate lab insights when lab path is enabled  
- Privacy: program design, not performance management  

**Do not claim**
- Clinical diagnosis, medical surveillance, or clinical ROI  
- That insights auto-launch challenges without admin action  
- Self-serve toggle for Workforce Health for every company  
- Individual lab values visible to HR  
- Fabricated board metrics or “industry benchmark” as real customer data (mark illustrative)  
- Marketplace redemptions confusion (belongs on Rewards page)

### 1.8 Proof

No dedicated “insights ROI” case study required. Optional light proof only if using named participation outcomes from multi-activity programs (BISD, Tata) as **engagement context**, not as score algorithm proof. Prefer **omit heavy customer-result section** if it distracts from product education; use a capability strip instead.

---

## 2. Page strategy

### Job of this page

Help an enterprise HR buyer answer:
1. Can leadership see **one number** that reflects workforce wellness, not a pile of exports?
2. Can we diagnose **why** the number moved (baseline vs participation vs activity vs adherence)?
3. Can we act without turning wellness into **surveillance or performance management**?
→ Book a demo (and AM activation conversation).

### Positioning line

> Board-readable workforce health insights: one Org Wellness Score, four components, AI observations, and drill-downs so HR designs better programs, not performance cases.

### Narrative arc (insights archetype, not challenge formats)

| # | Section | Intent |
|---|---------|--------|
| 1 | **Hero** | Data-out promise + large admin dashboard mock (score + components + insight chips) |
| 2 | **Chain strip** | HRA → Insights → Rewards (light sibling links) |
| 3 | **Score anatomy** | Signature: 4 components with weights and “what to do when weak” |
| 4 | **AI insights → action** | Streamed insights as operational cues |
| 5 | **Unified lenses** | Participation + challenge + activity (+ baseline) in one story |
| 6 | **Drill-down + export** | Dept / team / location / employee + CSV |
| 7 | **Privacy + AM honesty** | Program design use; aggregate labs; account manager activation |
| 8 | **How HR runs it** | Monthly review → diagnose component → challenge/rewards → export for board |
| 9 | **FAQ** | Activation, privacy, HRA dependency, not three products |
| 10 | **Related chain + trust + final CTA** | Sibling links; security; Book a demo |

**Signature element:** Admin dashboard mock featuring Org Wellness Score ring + four component bars + AI insight stream (product-real UI, illustrative figures).

### Deliberate de-emphasis

- Challenge format explorer / fraud leaderboard patterns  
- Employee phone UI as hero (admin is the buyer job here)  
- Heavy customer ROI carousel  
- Clinical language  

---

## 3. Full copy deck

### Meta

- **Title:** Workforce Health Insights for HR | Vantage Fit  
- **Description:** See Org Wellness Score, participation, activity, and challenge adherence in one dashboard. AI insights, drill-downs, and CSV export for program design. Book a demo.

### Nav

Solutions current. Mega updated for signed-off IA:  
① Wellness challenges · ② Workforce health & rewards (HRA, **Insights current**, Rewards) · Platform · Hub links where useful.

### S1 - Hero

**Eyebrow:** Solutions · Workforce health insights · Data out  

**H1:** Workforce health insights your **board** can read.  

**Lead:** One Org Wellness Score (0-100), four explainable components, and AI observations that turn participation, activity, and challenge data into program decisions. Built for HR leadership reporting, not clinical surveillance.  

**CTAs:** Book a demo · See pricing  

**Micro trust:** Org Wellness Score · AI insights · Drill-down + CSV  

**Hero mock caption:** Illustrative Workforce Health dashboard · Org score, components, and streamed insights  

### S2 - Chain strip

**Label:** Workforce health & rewards  

1. **Data in** - Health Risk Assessment → feeds Baseline (20%) · link `vantage-fit-health-risk-assessment-v1.html`  
2. **Data out** - Workforce health insights (this page)  
3. **Action** - Wellness rewards program · link `vantage-fit-wellness-rewards-v1.html`  

### S3 - Score anatomy

**Eyebrow:** Org Wellness Score  
**H2:** One number. Four levers you can pull.  
**Lead:** The score is a weighted blend of health baseline and daily behavior. Diagnose which component moved, then design the next challenge or communication.

| Component | Weight | When it is weak, try… |
|-----------|--------|------------------------|
| Baseline | 20% | Drive HRA completion; pair with annual check-up programs |
| Participation | 30% | Reminders, simpler entry challenges, broader audience rules |
| Activity | 30% | Race / movement challenges; improve effort trends |
| Adherence | 20% | Streaks and habit tasks; clearer challenge commitments |

**Note:** A balanced profile is healthier than a high score driven by one pillar.

### S4 - AI insights

**Eyebrow:** Streamed insights  
**H2:** Spot the pattern before the quarter ends.  
**Lead:** AI-generated observations stream from your wellness data so program managers act without building a manual analysis deck.

Example insight cards (illustrative wording, product-aligned):
- Participation dropped vs last week  
- Engineering: high Activity, low Adherence  
- Monday peaks; Friday dips  
- Three departments with no active challenge participants  

**Footer:** Insights cue action. You still launch challenges, communications, and rewards.

### S5 - Unified lenses

**Eyebrow:** One analytics story  
**H2:** Participation, challenges, and activity in one place.  
**Lead:** Stop hopping across three reports to answer one leadership question.

Cards:
1. **Participation** - Who is showing up daily and who has gone dormant  
2. **Activity** - Effort trends: steps, workouts, improvement over time  
3. **Challenge health** - Adherence to tasks and habits in live programs  
4. **Baseline signal** - Aggregate HRA fundamentals feeding the score  

### S6 - Drill-down + export

**Eyebrow:** From board pack to program detail  
**H2:** Drill down without losing the plot.  

- Department, team, and location comparisons  
- Employee wellness list with component breakdowns  
- Weekly and monthly trends for quarterly storytelling  
- Export CSV for scores and standard admin reports  

**Callout:** Use employee-level scores to improve program design and targeting, not performance reviews.

### S7 - Privacy + activation

**Eyebrow:** Trust and access  
**H2:** Insights for program design. Not performance management.  

Three cards:
1. **Use policy** - Individual scores support aggregate analysis and interventions; not HR discipline  
2. **Lab privacy** - When lab reports are enabled, HR sees anonymized prevalence, never one person’s biomarkers  
3. **AM activation** - Workforce Health is enabled by your Vantage Fit account manager; plan 2-4 weeks of data for a stable score  

### S8 - How HR runs it

1. Activate Workforce Health with your account manager; enable HRA for Baseline  
2. Review Org Score monthly; ignore daily noise  
3. Read component bars + streamed insights  
4. Launch or retarget challenges (and rewards) at weak levers  
5. Export CSV for leadership and quarterly wellness reporting  

### S9 - FAQ

1. **Is Workforce Health available on every plan out of the box?** - Account manager activates it for your company.  
2. **Can we use scores for performance or promotion decisions?** - No. Intended for program design and aggregate analysis.  
3. **Do we need HRA for the score to work?** - Score runs without HRA, but Baseline is less meaningful (neutral default). Pair them.  
4. **Is this three products (participation, challenge, activity reports)?** - One Workforce Health story unifies those lenses. Standard Reports remain available for enrollment, leaderboards, and rewards audits.  
5. **Can HR see individual lab values?** - No. Aggregate / anonymized insights only.  

### S10 - Related + trust + final CTA

Related: HRA · Rewards · Wellness challenges library · Platform · Solutions hub  
Trust: HIPAA · SOC 2 · GDPR · ISO 27001 · ISO 27701  
Final: Book a demo / See pricing · checks: Org score · AI insights · Drill-down · Privacy-aware  

---

## 4. Mega-menu fit

| Column | Items |
|--------|--------|
| ① Wellness challenges | Library + format pages (steps, multi-activity, team, marathon) |
| ② Workforce health & rewards | HRA (Data in) · **Insights (Data out, current)** · Rewards (Action) |
| Featured | Platform · Solutions hub |

Banner CTA: Book a demo focused on leadership reporting walkthrough.

---

## 5. Design notes for HTML mock

- `../styles/enterprise.css` + Noto Sans 400-800  
- No em-dashes anywhere  
- Hero: left copy, right **desktop admin mock** (not phone-first)  
- Illustrative figures only; caption says so  
- Sibling relative links for chain and related  
- Lean density; enterprise, calm, mint/coral accents  
- Mobile: stack hero, collapse component grid  

---

## 6. Sources

- `vantagefit-astro/.../admin-what-is-workforce-health.md`  
- `vantagefit-astro/.../admin-what-is-org-wellness-score.md`  
- `vantagefit-astro/.../admin-how-do-i-view-employee-reports.md`  
- `vc-os/vfit-os/specs/03-health-wellness/wellness-score.md`  
- `vc-os/vfit-os/specs/09-admin-platform/reports-analytics.md`  
- `vc-os/vfit-os/specs/product/03-health-wellness/workforce-health.md`  
- `vc-dashboard-design/docs/modules/wellness.md` (context; marketing follows help/OS score story)  
- `grok/_SHARED-RESEARCH-AND-SYSTEM.md`  
- Menu: `menu/vantage-fit-solutions-menu-preview.html`  

---

## 7. Gaps / assumptions

| Item | Status |
|------|--------|
| Dashboard redesign notes retire composite score in a prototype branch | Marketing page follows **help + OS + signed-off research** (Org Wellness Score still shipped story) |
| Industry benchmark constant in some dashboards | Not claimed as real customer proof; omit or label illustrative |
| Lab department slicing | Help mentions org/dept/country aggregate; OS product note is stricter org-level for prevalence. Copy stays high-level: aggregate only, never individual |
| Named insights ROI case study | None dedicated; omit heavy outcomes section |
| Self-serve vs AM | Honest: AM-activated |
| Sibling HRA/Rewards/Platform HTML may not exist yet | Link relative filenames per shared table anyway |

---

## 8. Decisions log (for handoff)

1. **Admin dashboard as hero mock** (score + components + AI stream), not employee phone.  
2. **One unified page** for participation + challenge + activity (explicit anti-split).  
3. **Privacy + AM activation** as first-class section, not buried FAQ only.  
