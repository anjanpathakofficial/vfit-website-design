# Workforce health insights: page brief

**Page 3 of 6** in the Solutions set.
**URL:** `/solutions/workforce-health-insights/`
**Archetype:** Program page, Section ② "data out"
**Mock to build from this brief:** `claude-fable/vantage-fit-workforce-health-insights-v1.html`
**Menu badge:** `Data out`
**Written:** 2026-08-11

This page replaces three retired, low-demand pages: participation analytics, challenge analytics, and activity/health analytics. It must read as one product surface, not three pages stapled together.

---

## 0. The one-line strategy

**One admin console, three views, and an honest boundary around what HR can never see.**

Everything on the page is subordinate to that. The console is the page. The rest of the sections explain it, qualify it, and tell the reader what leaves the platform.

---

## 1. Research takeaways that decided the structure

Sources are cited with the dossier's aliases: `astro/` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/`, `vfit-os/` = `/Users/anjanpathak/work/gitcode/vc-os/vfit-os/`, `dash-design/` = `/Users/anjanpathak/work/gitcode/vc-dashboard-design/`. Dossier files are at `scratchpad/research/`.

### 1.1 The reporting layer is two products stacked, and that changes the whole page

The base layer ships to every client: the Overview with four KPI cards, At a Glance, Recommended Actions, and six CSV reports. The premium layer (Org Wellness Score, Wellness Leagues, Health Insights) is **entitlement-gated to annual clients, contract negotiated, and provisioned by the account manager after data indexing. It is not a toggle.** Non-entitled admins see greyed cards with a "Contact Account Manager" overlay.
`[vfit-os/specs/product/09-admin-platform/admin-dashboard.md]`, `[research/insights-reports.md §0, §5.2]`

**Structural consequence:** the console's third view carries a visible `Annual contract` chip on the three gated cards, and the page says so in plain copy twice (console note, FAQ 3). Pretending everyone gets health-risk prevalence would be the single biggest over-claim available on this page, and it is also unnecessary: the honesty is what answers "is this a vanity dashboard".

### 1.2 There are four data stories, not three, and they must not be blended into a fifth number

Adoption, program, behavior, outcome. Each has its own denominator, refresh cadence and entitlement. The dossier is explicit that they must be kept as four independent measures and never rolled into a blended composite.
`[research/insights-reports.md §2, §2 "How the four stories should be framed"]`

**Structural consequence:** the retired three pages map onto three console tabs, and the fourth story (health signal) rides inside tab 3 rather than becoming a fourth tab. Three tabs, because the merge story is "three pages, one console". A fourth tab would reintroduce the stapled feeling.

### 1.3 The strongest single privacy proof is a product string, not a policy statement

When an admin targets a challenge at a health-risk cohort, the system returns a **count only**, plus the literal on-screen disclaimer **"The list of users is not displayed to protect individual privacy."** Any audience filter automatically marks the challenge Private.
`[vfit-os/specs/product/03-health-wellness/workforce-health.md]`, `[astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md]`

**Structural consequence:** the privacy section renders that screen rather than drawing an abstract data-flow diagram. This is deliberately different in kind from page 2's firewall diagram: page 2 shows the architecture, page 3 shows the moment of use.

### 1.4 The CAN / CANNOT table is quotable verbatim, including the sentence HR says to employees

`[astro/content/en/help/admin/settings/admin-data-privacy-security.md]` gives HR this line verbatim: *"Your HR team sees whether you are participating and your challenge rankings, but we cannot see your weight, health assessment results, lab reports, or personal health data."*

**Structural consequence:** the privacy section is a two-column ledger, not prose. It is the only place on the page with a strike-through treatment.

### 1.5 The dimension list is shorter than a buyer expects, and saying so is an asset

Shipped dashboard-wide dimensions are exactly five: **Date range, Country / Location, Department, Age group, Gender**, served by a real endpoint returning `{countries, departments, genders, ageGroups}`.
There is **no business unit dimension** (BU belongs to Vantage Pulse, a different product), **no tenure, no manager or reporting-hierarchy rollup, no saved cohorts, no job level, no site or building beyond Country and City.**
`[research/insights-reports.md §4.1, §4.4]`, `[dash-design/docs/filters.md]`

**Structural consequence and a correction to the task brief:** the suggested architecture named "business unit" as an existing dimension. It does not exist in Vantage Fit. The segmentation section names the five that exist, names the three extra dimensions available only to challenge and notification audiences (City, Language, Health Risk Code), and then plainly lists what is absent. That list is a credibility instrument, not an apology.

### 1.6 Exports are manual, and there is no scheduled or emailed report

Every report has an Export CSV button and the file downloads to the browser. There is **no scheduled or recurring export, no emailed report delivery, no PDF dashboard export, and no BI or warehouse connector**. The help docs' own advice is "set a monthly reminder to export" and "archive exports monthly".
`[astro/content/en/help/admin/reports/admin-how-do-i-export-reports.md]`, `[vfit-os/specs/product/09-admin-platform/admin-dashboard.md §08]`

**Structural consequence:** section 7 exists and it states the limit out loud. A "board-ready output" section that implied scheduled delivery would fail the claims gate and would fail the buyer at implementation.

### 1.7 Two "participation" metrics exist in the same console and must never reconcile

The Overview KPI **Participation Rate** is `round(active ÷ enrolled × 100)`, an app-usage measure. The Wellness Score's **Participation** component is binary daily engagement over a 7-day window. They do not reconcile.
`[dash-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md §4]`, `[research/insights-reports.md §2 Story A]`

**Structural consequence:** because both strings appear inside my console, the console carries an explicit disambiguation note in pane 3. Most competitors would hide this. Printing it is the page's proof that this is measurement rather than decoration.

### 1.8 The per-task, per-week score breakdown is the most quotable analytic in the product

Verbatim from the help docs: *"The score breakdown per user is one of the most useful tools in the dashboard. It shows exactly which tasks employees are completing and which they are skipping, invaluable for designing better future challenges."*
`[astro/content/en/help/admin/reports/admin-what-reports-are-available.md]`
(The source sentence contains an em-dash before "invaluable"; the page must not reproduce it. Use the trimmed quote given in the copy deck, section 3, S3.)

**Structural consequence:** the Challenges pane's hero element is an expanded leaderboard row showing per-task and per-week decomposition, not a bar chart. It is the one thing on this page a competitor's screenshot will not have.

### 1.9 Conflicts I resolved, and the rule I applied

| Conflict | Sources | Ruling used on this page |
|---|---|---|
| Wellness Score range 0 to 100 vs 0 to ~108 | help docs + code-verified admin spec vs `leagues-wellness-score.md` | **0 to 100.** Settled ruling G3. The console prints `74 / 100`. |
| At a Glance metric count: 4 vs 5 | code-verified spec (4) vs production audit (adds Active Calories) | Render **4**: Avg Steps, Active Minutes, Mindful Minutes, Avg Sleep. Safe copy per `research/insights-reports.md §2 Story C`. |
| Wellness Score component labels | help-doc names vs production strings | Ruling D3. **Prose uses Baseline, Participation, Activity, Adherence. The admin mock uses Health Baselines (20%), Participation (30%), Activity Levels (30%), Program Adherence (20%).** |
| Health-risk insights granularity: org only vs org + department + country | code-verified `workforce-health.md` vs help doc | **Org level only.** Code-verified spec wins on what an admin can do. The health card carries an `Org level only` chip. |
| Delta chips across the dashboard | card anatomy specs vs the production audit | **Only the four Overview KPI cards get delta chips.** All other delta chips are disabled backend-side; rendering them would over-claim. At a Glance keeps its sparkline, loses its delta pill. |
| Overview KPI card set | code-verified (Enrolled Users, Active Users, Incentivization, Participation Rate) vs help doc (Active Users, Enrollment Rate, Completion Rate, Org Wellness Score) | **Code-verified four.** Settled ruling in `rewards.md` addendum E1. |
| "Export respects your filters" | help doc says yes; production audit found the League CSV ignores inline filters and Wellness Score export caps at 10,000 rows | Keep the claim **generic**: "filter, then export". No headline claim about filters carrying through, no uncapped-export claim. |
| Recommended Actions count: max 5 vs max 10 | code-verified vs production audit | Say **"a short, priority-ordered list"**. Render two rows in the mock, no count claim. |
| Insights Hub | named in the code-verified page list; production audit found blank iframes and commented-out nav | **Do not claim, draw, or link.** Absent from the sidebar mock. |

### 1.10 Proof traps specific to this page

- **Brazosport's 4/5 organisational mood score is unusable here.** Mood logs are explicitly on the admins-CANNOT-see list. Quoting a mood score on the page that promises HR never sees mood logs is a direct self-contradiction. Cut, do not soften. `[research/insights-reports.md §3.1]`, `[research/ia-claims-proof.md §3.2]`
- **Every figure in `dash-design/vc-data.js` is seeded fiction** for a fake tenant ("Acme", "Priya Sharma", 68% participation, 1,120 assessed, 77% coverage). None may appear, including as mock filler. `[research/insights-reports.md §7.1]`
- **Production dummy fixtures are real code paths serving fake data**: the Workforce Health Snapshot's 82% / 18% split and its Vitamin D 32% / Sleep Quality 28% / Stress Levels 22% deficiencies, the Industry Benchmark 74 constant, the challenge participation benchmark 70. None may appear. `[research/insights-reports.md §7.2]`
- **The shipped Health Insights screen renders the string "HIPAA Compliant"** in a Compliance card. That string must not be reproduced in copy or in any mock on this page. The Compliance card is simply omitted from my console. `[research/insights-reports.md §3.6]`
- **"Participation Report"** appears in production nav but not in the help-doc report table. Do not name it. KPI drill links read `View more →` only.

---

## 2. Strategy

### 2.1 The buyer

Primary: **CHRO or VP HR** who has to present a wellness program to an executive committee, and the **HR Director** who will have to produce the numbers. Secondary reader with veto power: **legal / privacy counsel**, and **CFO** on the cost line.

They arrive from a "prove it" search: corporate wellness dashboard, employee wellness ROI tracking. This is a conversion page, not a volume page.

### 2.2 The one thing this page must land

> **You will leave your next leadership review with a number you can defend, and you will be able to say exactly where it came from and what it does not include.**

Not "we have analytics". Not "insights that drive action". The promise is defensibility.

### 2.3 The defining objection and how the page answers it

**Objection:** "Is this real measurement or a vanity dashboard, and can we defend it to legal and to the board?"

Four answers, in this order:

1. **Real report names, real locations, real column sets.** The console renders `Reports → Employee Report`, `Challenges → Manage → Leaderboard`, the four code-verified KPI labels, the real filter chips, and the real empty-state select labels. Nothing invented.
2. **A number that decomposes.** The console's most distinctive element is an expanded leaderboard row showing per-task and per-week contribution that sums exactly to the row total. Vanity dashboards do not decompose.
3. **Named limits.** No business unit dimension. No scheduled reports. No warehouse connector. Org-level only for health risk. Two participation metrics that do not reconcile. Stating limits is the cheapest, strongest credibility available.
4. **A privacy boundary with a product string behind it.** Not a promise: a count-only cohort screen carrying the literal disclaimer, plus the verbatim CAN / CANNOT ledger.

### 2.4 Why this section order

- The **console comes third, not first**, because a console with no question attached is wallpaper. Section 2 hands the reader three questions in their own language, and the console's three tabs answer them one to one. The tab labels are the answer keys to the question cards. That is the merge, expressed structurally.
- **Segmentation follows the console** because a filter bar is meaningless until you have seen what it filters.
- **Privacy sits in the upper middle, not the footer.** For a legal-sensitive purchase, burying the boundary reads as hiding it. It is also the natural pivot: everything before it is "what you can see", everything after is "what you do with it".
- **Action, then exports** because the buyer's mental order is "what do I do about it" before "what do I hand upward".
- **Proof late and small.** The page's credibility is built from product truth, not logos. The customer strip is three cards and one quote, and it exists mainly to demonstrate the labelling discipline in public.

### 2.5 What I deliberately left out, and why

| Left out | Why |
|---|---|
| **Insights Hub** | Nav commented out in production, all five sub-pages blank iframes. Settled ruling: do not claim, draw, or link. |
| **A blended "wellness index" hero number** | The four stories have different denominators and different entitlements. A composite would be exactly the vanity dashboard the buyer is worried about. |
| **The Workforce Health Snapshot card** (Normal / Needs Attention bar, Top Deficiencies) | It is served from a Redis key with no writer and silently renders dummy fixtures in production on a cache miss. Drawing it would draw fiction. |
| **The Compliance card from the Health Insights screen** | It ships the banned string "HIPAA Compliant". |
| **Scheduled reports, emailed reports, PDF dashboard export, BI connector, cohort analysis, audit log** | None shipped. Two of them are roadmap. The page names the absence instead. |
| **n = 5 cohort suppression, versioned consent, 30-day erasure SLA, minimum audience of 20** | All design intent, all parked. The shipped suppression story is count-only cohort targeting plus org-level-only health data. |
| **Brazosport's 4/5 mood score** | Contradicts the page's own privacy claim. |
| **Department-level health risk breakdown** | Code-verified spec says org level only. |
| **A second product mock in the hero and a phone mock anywhere** | The subject is the admin console. A phone dilutes the page's one idea. The hero carries a compact `.dash` and one floating export chip, then the full console gets the width it needs. |
| **A formats explorer, a leaderboard-integrity band, a "how teams form" section** | Owned by the challenge pages. This page links to them; it does not rebuild them. |
| **The 20% HRA completion figure** | Real, documented, and a sales liability. Not an approved marketing stat. |

### 2.6 How this page is structurally different from its five siblings

| Sibling | Its signature | This page |
|---|---|---|
| Wellness challenges (library) | Browse-and-filter catalogue of 21 challenges | No catalogue |
| Health Risk Assessment | The data-in flow and a privacy firewall diagram | Privacy expressed as a **ledger plus a live screen**, never a flow diagram |
| Step challenges / Multi-activity / Remote & hybrid / Virtual marathon | Format explorers, task explorers, run books | No formats, no tasks |
| **Workforce health insights** | **One 1,100px admin console with three switchable views, real report names, real chart shapes, real axis labels** | This is the only page in the set with a console at this scale |

No other page in the set may use `.console`. That is the point.

---

## 3. Section-by-section copy deck

Voice rules that bind every string below: sentence case headings, terminal periods on H1 and H2, verb-led CTAs, no em-dashes, no banned words, numerals for measurable quantities, Oxford comma, US spelling in new copy, quotes verbatim.

Ground alternation, in order: cream gradient, `#fff`, `--canvas`, `#fff`, `--canvas` with a dark inset, `#fff`, `--canvas`, `#f6f7f4`, dark, `#fff`, `--canvas`, dark.

---

### S1. Hero

`<section class="hero insights-hero" id="hero" aria-labelledby="hero-heading">`

**Kicker pill** (`.kicker` with lime dot):
`Data out · Workforce health & rewards`

**H1** (`<em>` wraps the second clause for the coral gradient fill):
`The participation number your board asks for, <em>and the report behind it.</em>`

**Lead** (`.lead`):
`Participation, challenge and activity analytics live in one admin console. Every number is aggregate by design, and every report leaves as a CSV you can hand to leadership.`

**Buttons** (`.btn-row`):
- Primary: `Book a demo` → `https://www.vantagefit.io/request-demo/`
- Outline: `See pricing` → `https://www.vantagefit.io/pricing/`

**Text link** below the buttons:
`See what HR can and cannot see →` → `#privacy`

**Hero note** (`.hero-note`, lime dot):
`Aggregate by design. Admins never see HRA answers or lab results.`

**Hero visual:** the `.dash` mock, described in section 4.1.

**Logo band** (pinned to the bottom of the fold, `.logo-band`):
- `.logos-label`: `Trusted by 100+ organizations worldwide`
- `.logo-word` items, in this order: `Tata Motors` · `Wipro` · `IBS Software` · `Brazosport ISD` · `Landmark Group` · `POSOCO`

---

### S2. The three questions

`<section class="hub-section questions-screen" id="questions" aria-labelledby="questions-heading">` ground `#fff`

**Eyebrow:** `The merge`

**H2:** `Three questions HR has to answer, in one place.`

**Lead:** `These were three separate pages. They are three views of one console now, because they run on the same workforce, the same date range and the same filters.`

**Three cards** (`.format-card` shape with a 74×44 `.format-glyph`, `.best-for` footer relabelled):

| Card | H3 (the question) | One-line body | Footer label / value |
|---|---|---|---|
| 1 | `"Is anyone actually using it?"` | `Enrolled, active and participation rate, plus a named list of who has gone quiet.` | `Console view` / `Participation` |
| 2 | `"Did the program land?"` | `Participation per challenge, three leaderboards, and the per task breakdown of what people skipped.` | `Console view` / `Challenges` |
| 3 | `"Is behavior actually changing?"` | `Average steps, active minutes and sleep, league tiers, and the org wellness score.` | `Console view` / `Activity & health` |

**Trailing note** (`.format-note`, `.8rem`, muted):
`One workforce, one date range, three answers. Nothing has to be reconciled by hand afterwards.`

---

### S3. The console (page-defining section)

`<section class="hub-section console-screen" id="console" aria-labelledby="console-heading">` ground `--canvas`

**Eyebrow:** `The console`

**H2:** `One console, switched three ways.`

**Lead:** `Real screens, real report names, real columns. Switch the view, keep the filters.`

**The console mock:** full spec in section 4.2. Every string inside it is listed there.

**Trailing quote block** under the console (a single `.problem-quote`-style card with a 4px coral left rule, not a section of its own):

> `"The score breakdown per user is one of the most useful tools in the dashboard. It shows exactly which tasks employees are completing and which they are skipping."`

`<small>` attribution: `Vantage Fit Help Center, admin reports guide` (US spelling, and it matches the Resources menu label)

**Trailing note** (`.format-note`):
`Wellness Score, Wellness Leagues and Health Insights are included on annual contracts and set up with your account manager. Participation and challenge analytics ship with every plan.`

---

### S4. Segments

`<section class="hub-section segments-screen" id="segments" aria-labelledby="segments-heading">` ground `#fff`

**Eyebrow:** `Segments`

**H2:** `Slice it the way your organization is actually shaped.`

**Lead:** `Five dimensions apply across the console and across every report. The values come from the employee data you already load, so departments and countries match your own records.`

**Dimension chips** (`.dim-row`, five `.dim-chip` items, each a label plus a one-line value string):

| Chip label | Sub-line |
|---|---|
| `Date range` | `This Month, Last Quarter, Last 90 Days, This Year, Custom, Lifetime` |
| `Country` | `From your employee data` |
| `Department` | `From your employee data` |
| `Age group` | `Bucketed ranges` |
| `Gender` | `Male, female, other` |

**Two "what a segment view changes" cards** (`.seg-case`, 2-up):

| Card | H3 | Body (one line each, both documented) |
|---|---|---|
| 1 | `A department is lagging.` | `Filter the leaderboard by department, then send that department a targeted announcement.` (Do not name a "Community" section here: the console sidebar in 4.2.3 renders the group as `Engage`, and naming both on one page contradicts itself.) |
| 2 | `A department is 80% Bronze.` | `That group may need its own challenge or a walking group, not another company-wide announcement.` |

**Honest-limits note** (`.format-note`, and it should be visually a touch heavier than a normal trailing note, ink at 75% rather than muted):
`Vantage Fit does not carry a business unit, tenure, job level or manager hierarchy dimension, and filters are applied ad hoc rather than saved as cohorts. Challenge and notification audiences add three more: City, Language and Health Risk Code.`

---

### S5. Privacy

`<section class="hub-section privacy-screen" id="privacy" aria-labelledby="privacy-heading">` ground `--canvas`, containing one dark `.fairband` inset.

**Inside the fairband, left column:**

**Eyebrow** (lime on dark): `Privacy`

**H2** (`.fairband h2`, white): `HR sees who is participating. Never what the assessment said.`

**Lead:** `The boundary is set in the product, not in a policy document.`

**The ledger** (page-local `.ledger`, two sub-columns):

Left sub-column header: `HR can see`
- `Company and department enrollment rates`
- `Active user percentages and last active date`
- `Challenge participation, leaderboard rankings, team scores`
- `Wellness scores, where the feature is enabled`

Right sub-column header: `HR can never see`
- `Individual health data: weight, BMI, body measurements`
- `Health Risk Assessment answers and risk categories`
- `Lab report results and biomarker values`
- `Mood logs, food diary and sleep patterns`

Right-column items render with a strike glyph, not strike-through on the text itself (strike-through on 8-word lines is hard to read at `.86rem`).

**One-line precision note under the ledger** (`.ledger-note`):
`One nuance worth stating out loud: where wellness scores are enabled, an admin sees a score derived from the assessment, never the assessment. The help docs are explicit that individual scores are for program design, not for decisions about specific employees.`

**`.fair-fine`** (the verbatim line, in quotes, with attribution):
`"Your HR team sees whether you are participating and your challenge rankings, but we cannot see your weight, health assessment results, lab reports, or personal health data."`
`<small>` attribution: `The sentence Vantage Fit gives HR to tell employees, from the admin privacy guide`

**Inside the fairband, right column:** the count-only cohort mock, spec in section 4.3.

---

### S6. From insight to action

`<section class="hub-section action-screen" id="action" aria-labelledby="action-heading">` ground `#fff`

**Eyebrow:** `Insight to action`

**H2:** `The loop closes inside the same console.`

**Lead:** `Every number on this page has a next step attached to it, and the next step runs against the same segment you were just looking at.`

**Layout:** `.employee-cols` (`1.04fr .96fr`, gap 56px). Left: four `.join-point` rows. Right: the Recommended Actions mock, spec in section 4.4.

**Left column, four `.join-point` rows** (each `<b>` title plus one line):

| # | Title (`<b>`) | Line |
|---|---|---|
| 1 | `Spot the gap` | `The Overview flags who has gone quiet. The Employee Report names them, with department and last active date.` |
| 2 | `Target the exact segment` | `Audience rules enroll matching employees automatically. Any filter marks the challenge private, so nobody outside the group sees it.` |
| 3 | `Pick the format that fixes the weak component` | `A Streak lifts adherence, a Race lifts activity, and a content-led Custom challenge lifts participation.` |
| 4 | `Measure it the same way next quarter` | `Same reports, same denominators, so the before and after actually compare.` |

**Chain row** under the two columns (three `.text-link` items on one line, this is where the data in, data out, action chain is made explicit):
- `Where the data comes from: Health Risk Assessment →` → `/solutions/health-risk-assessment/`
- `What you run against it: Wellness challenges →` → `/solutions/wellness-challenges/`
- `What keeps people coming back: Wellness rewards program →` → `/solutions/wellness-rewards-program/`

---

### S7. What leaves the platform

`<section class="hub-section exports-screen" id="exports" aria-labelledby="exports-heading">` ground `--canvas`

**Eyebrow:** `Exports`

**H2:** `Six reports, and an honest account of what they do not do.`

**Lead:** `Filter first, then export. The CSV downloads straight to your browser with the columns you were looking at.`

**Layout:** two columns, `1.05fr .95fr`, gap 48px.

**Left column: the six reports** (`.report-list`, each row is a name plus its exact location string, and two rows carry an `Annual contract` chip):

| Report name | Location string | Chip |
|---|---|---|
| `Employee Report` | `Reports → Employee Report` | |
| `Transaction Report` | `Reports → Transaction Report` | |
| `Redemption Report` | `Reports → Redemption Report` | |
| `Challenge Leaderboard` | `Challenges → Manage → Leaderboard` | |
| `League Report` | `Reports → League Report` | `Annual contract` |
| `Wellness Score Report` | `Workforce Health → Employee report` | `Annual contract` |

**Right column: four `.limit-row` items** (each `<b>` title plus one line):

| Title | Line |
|---|---|
| `Exports are manual` | `There is no scheduled report and no emailed delivery today. The documented practice is a monthly reminder and a monthly archive.` |
| `Wait out the buffer` | `Export a Race challenge after the 3-day buffer so late-syncing wearable data is included.` |
| `CSV, not a data warehouse` | `Reports leave as CSV files. There is no warehouse connector today.` |
| `Reconcile two reports, not one` | `Cross-reference the Employee Report against the Transaction Report to find people who enrolled and then went quiet.` |

**Trailing note** (`.format-note`):
`Export rights are a role permission. Admins without them see the export button disabled.`

---

### S8. Proof

`<section class="hub-section proof-hub" id="proof" aria-labelledby="proof-heading">` ground `#f6f7f4`

**Eyebrow:** `Proof`

**H2:** `What one program looked like when it was measured over time.`

**Lead:** `Wipro ran three challenges between April and August 2025. These are the numbers the program left behind, each labelled with what it measured.`

**Results grid, three `.result-card` items** (`repeat(3,1fr)`, gap 14px):

| `.stat` | `<p>` (what it measured) | `.segment` |
|---|---|---|
| `3X` | `Participation increase, 163 to 550 active users, first challenge to third` | `Wipro · 3 challenges, Apr to Aug 2025`<br>`Active users, not enrolled` |
| `46.53M` | `Cumulative steps logged across the three challenges` | `Wipro · 3 challenges, Apr to Aug 2025`<br>`Program total` |
| `30+` | `Countries with participants in this program` | `Wipro · 3 challenges, Apr to Aug 2025`<br>`Participant footprint, not a customer footprint` |

**`.proof-fine`** under the grid:
- `<small>`: `Results from a named customer program. Outcomes vary by workforce and program design.`
- `.text-link`: `Read the Wipro story →` → `https://www.vantagefit.io/casestudy/wipro-global-wellbeing/`

**One text-only quote band** (`.quote-band.text-only`) under the proof fine:
> `"The app's analytics provided clear insights into participation levels and helped us recognize and celebrate achievements effectively."`

`.quote-who`: `Shubham Sanghavi, Consultant, Avalon Consulting`

---

### S9. Security and compliance

`<section class="screen trust-screen solutions-trust" id="security" aria-labelledby="security-heading">` dark gradient

**Eyebrow** (lime): `Enterprise security & compliance`

**H2:** `Built to survive a privacy review, not just a demo.`

**Lead:** `Vantage Fit operates under HIPAA guidelines and is SOC 2 Type II. The reporting layer is aggregate by design, and the data never leaves the region you pick.`

**Trust actions:**
- Primary: `Book a demo` → `https://www.vantagefit.io/request-demo/`
- Text link (lime variant): `Explore security & compliance →` → `https://www.vantagefit.io/features/security-and-compliance/`

**Four `.trust-card` items** (2×2 via `.solutions-trust`):

| Icon entity | H3 | Body |
|---|---|---|
| `&#9673;` | `Aggregate by design` | `Admins see company and department level metrics. No admin screen and no export exposes one person's assessment answers, lab values, mood logs or food diary.` |
| `&#9737;` | `Your data stays in your region` | `Four isolated regional instances: India, US, EU and UAE. Chosen at signup, with no cross-region sharing.` |
| `&#8644;` | `No personal data in the AI layer` | `Leadership Insights runs on aggregated signal buckets. No employee identifiers are sent to the insights service.` |
| `&#10003;` | `Employees hold the delete key` | `Employees delete their own lab reports, and delete their own account with OTP verification. An admin cannot do it on their behalf.` |

**Trust plaque:** the typeset `.mark-strip`, three marks only. **No certification raster.**
- `Operates under HIPAA guidelines` (the exact approved phrasing; do not paraphrase it to "Follows" or anything else)
- `SOC 2 Type II`
- `Secured regional data hosting`

`.trust-support`: `Security documentation is available during evaluation.`

---

### S10. FAQ

`<section class="hub-section faq-screen" id="faq" aria-labelledby="faq-heading">` ground `#fff`

**Eyebrow:** `Questions`

**H2:** `Questions HR asks before the first review.`

Five `<details class="faq-item">`. First one carries `open`. Question text goes in `summary > h3`.

**1. What are workforce health insights?** *(answer-first definitional item, mirrored in FAQPage schema)*
`Workforce health insights are the aggregate reports an HR team uses to see whether a wellness program is working: how many employees enrolled and stayed active, how each challenge performed and which tasks people skipped, and how average activity and wellness scores move over time. In Vantage Fit they live in one admin console, and every figure is company or department level rather than individual health data.`

**2. Can HR see an individual employee's health data?**
`No. Admins see aggregate metrics, challenge participation and leaderboard rankings, plus employee reports that show registration status and last active date. They cannot see weight, BMI, Health Risk Assessment answers or risk categories, lab report values, mood logs, food diaries or sleep patterns. Where wellness scores are enabled, an admin sees a score derived from the assessment, never the assessment itself, and the product documentation states that individual scores are for program design rather than decisions about specific employees.`

**3. Which analytics are included, and which need an annual contract?**
`Participation analytics, challenge analytics and the six CSV reports ship with every plan. Org Wellness Score, Wellness Leagues and Health Insights are included on annual contracts, are set up by your account manager rather than a toggle, and need 2 to 4 weeks of data collection before the baseline reads reliably.`

**4. Can reports be scheduled or emailed to leadership?**
`Not today. Every report has an Export CSV button and the file downloads to your browser with the filters you applied. The documented practice is to set a monthly reminder, export, and archive. There is no scheduled delivery, no emailed report and no data warehouse connector.`

**5. How do we know the activity behind the numbers is real?**
`Steps count only from approved apps and devices, one primary device at a time so nothing is double counted, and GPS workouts are checked for unrealistic pace and for vehicle travel. Flagged activity does not reach the rankings, source tracking supports investigation, and challenge results stay provisional for 3 days after the end date so late-syncing wearable data lands before winners are picked.`

---

### S11. Related

`<section class="related-screen" id="related" aria-labelledby="related-heading">` ground `--canvas`

**Eyebrow:** `Keep going`
**H2:** `Where this connects.`

Three `.related-row` cards:

| H3 | One line | href |
|---|---|---|
| `Health Risk Assessment` | `The baseline screening that feeds the wellness score.` | `/solutions/health-risk-assessment/` |
| `Wellness rewards program` | `Points and gift cards tied to the effort you just measured.` | `/solutions/wellness-rewards-program/` |
| `Wellness challenges` | `The full library of ready-to-run challenges.` | `/solutions/wellness-challenges/` |

---

### S12. Closer

`<section class="final" id="demo" aria-labelledby="final-heading">` dark gradient

**H2:** `Leave your next review with a number you can defend.`

**Paragraph:** `See the console with your own departments, your own date range, and the reports you would actually export.`

**Buttons:**
- Primary: `Book a demo` → `https://www.vantagefit.io/request-demo/`
- Outline (transparent on dark): `See pricing` → `https://www.vantagefit.io/pricing/`

**`.final-checks`** (three lime-dotted items):
`Aggregate by design` · `CSV exports on demand` · `Set up with your account manager`

**`.final-note`:**
`Wellness Score, Wellness Leagues and Health Insights are included on annual contracts.`

---

## 4. Product-real UI spec

Universal mock rules, all mandatory:
1. Every mock region that carries numbers gets `role="img"` and an `aria-label` that ends with **"Figures shown are illustrative."**
2. Every decorative child inside it gets `aria-hidden="true"`.
3. A visible `<span class="mock-tag">Illustrative data</span>` on every mock.
4. `font-variant-numeric: tabular-nums` on every column of digits.
5. Only product-real screen names, field names and button labels.

---

### 4.1 Hero mock: `.dash` (the Overview KPI card)

Position: inside `.hero-visual`, `top:6px; left:0; width:min(100%,470px)`, rotate `1.1deg`, shadow `0 30px 74px rgba(41,41,76,.18)`.

`aria-label`: `Admin overview card showing a 65 percent participation rate, up 4 points against the previous quarter, with an active users trend line. Figures shown are illustrative.`

Contents, top to bottom:

- `.dash-top`: three 8px grey dots plus a `.dash-url` pill containing the text `dashboard.vantagecircle.com`
- `.dash-title`: `<small>Admin · Overview</small>` and `<strong>Participation</strong>`, with `<span class="mock-tag">Illustrative data</span>` on the right
- `.metric-inline`, three cells:
  - `ENROLLED` / `4,820`
  - `ACTIVE` / `3,140`
  - `AS OF` / `Yesterday`
- `.metric-card.metric-main` (mint tint `#e8f7f1`):
  - `.metric-lab`: `Participation Rate`
  - `.metric-value`: `65%`
  - `.metric-delta`: `+4 pts vs Prev Quarter`
- `.chart-card`:
  - `.chart-head`: `Active users` plus `<span class="legend"><i></i> This quarter</span>`
  - `.chart` (height 84px, gridlines from `repeating-linear-gradient`), containing a 1px dashed coral reference line labelled `Prev quarter 61%`, and one SVG `viewBox="0 0 300 84" preserveAspectRatio="none"` with a `polygon` fill `rgba(65,216,180,.14)` and a `polyline` stroke `var(--mint-dark)` at 2.4
  - Series points: `0,64 50,58 100,55 150,47 200,42 250,33 300,26`
  - `.chart-labels`: `Apr` `May` `Jun` `Jul`

**Second hero element**, a floating `.hero-chip.hc2` positioned bottom-right of the visual (frosted white card, radius 16px):
- Line 1 (`.62rem/800` uppercase, muted): `EXPORTED`
- Line 2 (`.86rem/700`, ink): `Employee Report.csv`
- Line 3 (`.66rem`, mint-dark, with a leading check glyph): `4,820 rows · filters applied`

`aria-label` on the chip: `Export confirmation chip for an Employee Report CSV. Figures shown are illustrative.`

**Consistency rule the builder must hold:** `3,140 ÷ 4,820 = 65%`. If any of those three numbers change, all three change.

---

### 4.2 The console (the page-defining mock)

This is a new page-local component. It does not exist in `enterprise.css` and no sibling page has it.

#### 4.2.1 Frame and geometry

```css
.console {
  max-width: 1100px;
  margin: 40px auto 0;
  border: 1px solid var(--line);
  border-radius: 20px;
  background: var(--paper);
  box-shadow: 0 30px 76px rgba(41,41,76,.13);
  overflow: hidden;
}
.console-chrome {
  display: flex; align-items: center; gap: 8px;
  padding: 11px 16px;
  border-bottom: 1px solid var(--line);
  background: #fbfbfc;
}
.console-body { display: grid; grid-template-columns: 196px 1fr; }
.console-side { border-right: 1px solid var(--line); background: #fcfcfd; padding: 18px 12px; }
.console-main { padding: 20px 22px 24px; min-width: 0; }
```

Responsive: at `max-width: 900px` the sidebar is hidden (`display:none`) and `.console-body` becomes one column. At `max-width: 640px` the KPI row goes to `1fr 1fr`, the Employee Report table drops its `Country` column, and the Activity & health card row stacks to one column. The console must never cause horizontal page scroll; give `.console-main` `overflow-x: auto` on its table blocks only.

#### 4.2.2 Chrome bar

Three 8px dots (`#e4e4ea`, `#e4e4ea`, `#e4e4ea`) then a pill (`height:9px; border-radius:999px; background:#ececed; width:46%`) with the text `dashboard.vantagecircle.com` set at `.6rem`, muted, centered inside it.

#### 4.2.3 Sidebar (real product nav, `Insights Hub` deliberately absent)

Four group headers at `.6rem/800`, uppercase, `letter-spacing .12em`, `var(--muted)`. Rows at `.775rem/600`, `padding 7px 10px`, `border-radius 8px`. The active row gets `background: var(--soft); box-shadow: inset 2px 0 0 var(--coral); color: var(--ink);`

```
ANALYZE
  Overview                      <- active
  Workforce Health
    Health Insights
    Wellness Score      [NEW]
    Wellness Leagues
  Reports

CHALLENGES
  Create Challenge
  Manage Challenge
  Past Challenges

ENGAGE
  Announcements
  Publish Notifications

MANAGE
  Rewards Hub
  Configuration
```

The three items nested under `Workforce Health` are indented 12px and carry a small padlock glyph plus the `NEW` tag only on `Wellness Score` (that tag is real). The padlock is the honest gate signal; give it `aria-hidden="true"` and cover it in the pane note rather than a tooltip.

#### 4.2.4 Filter bar and freshness caption

Row above the tabs, `display:flex; flex-wrap:wrap; gap:8px; align-items:center;`

Five `.cf-chip` pills, each `padding 6px 11px; border:1px solid var(--line); border-radius:999px; background:#fff; font-size:.72rem; font-weight:600;` with a 8px chevron:

`Last Quarter` · `All Countries` · `All Departments` · `All Ages` · `All Genders`

Right-aligned in the same row, `.console-asof` at `.64rem`, `var(--muted)`:
`As of yesterday`

#### 4.2.5 The three-tab control

`role="tablist"` with `aria-label="Console views"`. Three buttons, each `flex:1`, `padding: 11px 8px`, `.82rem/700`, muted when unselected, ink when selected.

Tab labels and ids:

| Tab | Label | id | controls |
|---|---|---|---|
| 1 | `Participation` | `tab-participation` | `pane-participation` |
| 2 | `Challenges` | `tab-challenges` | `pane-challenges` |
| 3 | `Activity & health` + `Annual contract` chip | `tab-activity` | `pane-activity` |

A 2px coral thumb sits at `bottom:-1px`, `width: calc(100% / 3)`, and slides with a real translate. The shipped `.seg` handler in the chrome only supports two tabs; write a three-tab handler:

```css
.console-tabs { position: relative; display: flex; border-bottom: 1px solid var(--line); margin-top: 14px; }
.console-thumb { position: absolute; bottom: -1px; left: 0; height: 2px; width: calc(100% / 3);
  background: var(--coral); transition: transform .22s cubic-bezier(.22,.9,.24,1); }
.console-tabs.i1 .console-thumb { transform: translateX(100%); }
.console-tabs.i2 .console-thumb { transform: translateX(200%); }
@media (prefers-reduced-motion: reduce) { .console-thumb { transition: none; } }
.console-tabs button:focus-visible { outline: 3px solid var(--coral-dark); outline-offset: 2px; border-radius: 8px; }
```

JS: on click, set `aria-selected` on all three, toggle `hidden` on all three panes, and set `tabs.className = 'console-tabs i' + index`. Add left and right arrow key handling on the tablist (`ArrowRight` / `ArrowLeft` move selection and focus). Panes use the `hidden` attribute, not `display:none` alone.

The tab buttons themselves are real controls, so they sit **outside** any `role="img"` region. Each pane's data blocks carry their own `role="img"` wrappers with their own `aria-label`.

Tab 3's chip: `.tab-chip` at `.55rem/800` uppercase, `letter-spacing .08em`, amber tint `rgba(246,185,59,.18)` with `color:#8a5a06`, text `Annual contract`.

---

#### 4.2.6 Pane 1: Participation

`aria-label` for the pane's data region: `Participation view showing four key metrics, enrolled users 4,820, active users 3,140, incentivization 12,400 dollars, participation rate 65 percent, above an employee report table with five rows. Figures shown are illustrative.`

**Block A: KPI row.** Four cards, `repeat(4,1fr)`, gap 10px, each `padding 14px; border:1px solid var(--line); border-radius:15px;`

| Card title | `View more →` | Big value | Delta pill | Delta label | Sparkline | Extra line |
|---|---|---|---|---|---|---|
| `Enrolled Users` | yes | `4,820` | `+180` | `vs Prev Quarter` | rising area | |
| `Active Users` | yes | `3,140` | `+265` | `vs Prev Quarter` | rising area | |
| `Incentivization` | yes | `$12,400` | `+8%` | `vs Prev Quarter` | rising area | `Avg ~$2.57 per employee` |
| `Participation Rate` | yes | `65%` | `+4 pts` | `vs Prev Quarter` | rising area | |

Sparklines: inline SVG `viewBox="0 0 120 30" preserveAspectRatio="none"`, polyline stroke `var(--mint-dark)` at 1.8, polygon fill `rgba(65,216,180,.12)`. Four different point sets so they do not look copy-pasted.

**These four cards are the only elements on the entire page allowed to show a delta pill.** See section 1.9.

**Block B: Employee Report table.**

Header strip: `<b>Employee Report</b>` on the left, path string `Reports → Employee Report` at `.66rem` muted, and on the right a toolbar:
`Search by name or email...` (a disabled-looking input pill) · `All Departments` · `All Countries` · a coral `Export CSV` button.

Columns: `Employee` · `Department` · `Country` · `Enrollment status` · `Last active`

| Employee | Department | Country | Enrollment status | Last active |
|---|---|---|---|---|
| A. Rivera | Operations | United States | `Active` | Aug 10, 2026 |
| M. Okafor | Engineering | United Kingdom | `Active` | Aug 09, 2026 |
| S. Nakamura | Finance | Japan | `Inactive` | Jun 24, 2026 |
| L. Fernandes | Sales | India | `Dormant` | Apr 02, 2026 |
| K. Haddad | Operations | United Arab Emirates | `Active` | Aug 10, 2026 |

Status pills: `Active` mint tint `rgba(65,216,180,.16)` / `#128f72`; `Inactive` amber tint `rgba(246,185,59,.20)` / `#8a5a06`; `Dormant` neutral `rgba(41,41,76,.07)` / `rgba(41,41,76,.7)`.

Employee names must be initial-plus-surname. **Do not use any name from the design prototype's fake tenant.**

**Pane note** (`.console-note`, `.68rem`, muted, top hairline):
`Enrollment status runs Active, Inactive, Dormant. Cross-reference this report with the Transaction Report to find employees who enrolled and then went quiet.`

---

#### 4.2.7 Pane 2: Challenges

`aria-label`: `Challenges view showing an ended challenge at 71 percent participation, a score leaderboard, and one expanded row decomposed into per task and per week contributions. Figures shown are illustrative.`

**Block A: challenge header card.**

- 40px rounded challenge image placeholder (teal gradient `#26594e` to `#3ccaa6`, one white outlined circle, no photography)
- Title: `Mid-Year Reset 2026`
- Status pill: `Ended` · outlined type tag: `Custom`
- Right-aligned hero metric: `↗ 71% Participation`
- Meta row: `1,284 participants` · `06 Jul 2026 - 02 Aug 2026`

**Block B: leaderboard.**

Sub-tab row, real labels, first one active with `inset 0 -2px 0 var(--coral)`:
`Score Leaderboard` · `Steps Leaderboard` · `Team Leaderboard`

Legend pill to the right of the sub-tabs (`.board-pill`, `.62rem`, neutral tint):
`Team score = average of member scores`

Column header row: `Rank` · `Employee name` · `Score` · `Department`
Grid: `36px 1fr 76px 132px`

| Rank | Employee name | Score | Department |
|---|---|---|---|
| 1 | A. Rivera | 1,840 | Operations |
| 2 | M. Okafor | 1,795 | Engineering |
| **3** | **P. Alvarez** (expanded) | **1,742** | Finance |
| 4 | K. Haddad | 1,690 | Operations |

**Row 3 expanded panel** (this is the page's differentiating element). Background `var(--soft)`, radius 12px, inset, two sub-blocks side by side at `1fr 1fr`, gap 18px:

*Left sub-block header:* `Score breakdown by task`

| Task | Points | Status chip |
|---|---|---|
| `Steps` | `720` | `Completed` |
| `Water intake` | `480` | `Completed` |
| `Meditation` | `300` | `Partially completed` |
| `Sleep log` | `242` | `Partially completed` |
| **Total** | **`1,742`** | |

*Right sub-block header:* `Score breakdown by week`

| Week | Points |
|---|---|
| `Week 1` | `512` |
| `Week 2` | `468` |
| `Week 3` | `396` |
| `Week 4` | `366` |
| **Total** | **`1,742`** |

Render the week values as four small horizontal bars scaled to 512, so the decline is visible at a glance.

**Both totals must equal 1,742 and must equal the row's Score cell.** This arithmetic is the whole credibility argument of the section. Do not change one number without re-balancing the others.

Status chips: `Completed` mint tint; `Partially completed` amber tint; a `Missed` neutral-red tint exists in the product but is not used in these rows.

**Pane note:**
`Click any row to see per task and per week contribution. Export after the 3-day buffer so late-syncing activity is included.`

---

#### 4.2.8 Pane 3: Activity & health

`aria-label`: `Activity and health view showing average steps, active minutes, mindful minutes and sleep, an org wellness score of 74 out of 100 with its four components, wellness league tier distribution, and organization level health domain prevalence. Figures shown are illustrative.`

**Block A: At a Glance strip.** Header line: `<b>At a Glance</b>` with subheader `This Month`. Four mini cards, `repeat(4,1fr)`, gap 10px. Each: an icon chip (footprints, timer, brain, moon, all inline SVG at 15px), a label, a value with its unit suffix, and a full-width sparkline. **No delta pills on these cards.**

| Label | Value | Unit suffix |
|---|---|---|
| `Avg Steps` | `7,240` | `/day` |
| `Active Minutes` | `38` | `min/day` |
| `Mindful Minutes` | `9` | `min/day` |
| `Avg Sleep` | `6 hr 52 mins` | |

**Block B: three cards across**, `repeat(3,1fr)`, gap 12px. Each card carries a small `Annual contract` chip in its header.

**Card 1: `Org Wellness Score`**
- Big value `74` with a `/100` suffix at `1rem`, muted
- Section header `SCORE BREAKDOWN` at `.6rem/800`, uppercase, letter-spacing `.12em`
- Four rows, each a label, a track bar, and a `N` value against its cap. Use the production strings, in this order and with these colors:

| Row label | Value | Cap | Bar color |
|---|---|---|---|
| `Health Baselines (20%)` | `15` | 20 | `#9BAFC8` |
| `Participation (30%)` | `22` | 30 | `#21B8A6` |
| `Activity Levels (30%)` | `21` | 30 | `#7A56E4` |
| `Program Adherence (20%)` | `16` | 20 | `#F59E0B` |

`15 + 22 + 21 + 16 = 74`. Hold that.

**Card 2: `Wellness Leagues`**
- Subtitle: `On 10 Aug 2026`
- SVG donut, `viewBox="0 0 120 120"`, circle `r=42` (circumference `263.9`), `stroke-width 16`, `transform="rotate(-90 60 60)"`, no labels inside. Three arcs:

| Tier | Percent | dasharray segment | color |
|---|---|---|---|
| `Gold` | `18.4%` | `48.6 215.3` | `#F59E0B` |
| `Silver` | `46.2%` | `121.9 142.0` | `#94A3B8` |
| `Bronze` | `35.4%` | `93.4 170.5` | `#D4A574` |

Legend rows below, percentages to one decimal exactly as the product renders them: `● Gold 18.4%` · `● Silver 46.2%` · `● Bronze 35.4%`.
Threshold caption under the legend: `Based on avg daily steps over 30 days`
Footnote at `.62rem`: `Trends reflect only employees currently active in the system.`

Two clashing tier palettes exist in production. **Use the ramp above and only that ramp.**

**Card 3: `Health domain breakdown`**
- Two chips in the header: `Annual contract` and `Org level only`
- A quarter chip on its own line: `Jul - Sep, 2026`
- Three domain rows. Each: domain name, right-aligned `N% flagged`, a progress bar (amber `#F6B93B` fill on a `rgba(41,41,76,.10)` track), and a footer line `N% Normal`.

| Domain | Flagged | Normal |
|---|---|---|
| `Diabetes` | `14% flagged` | `86% Normal` |
| `Heart Health` | `11% flagged` | `89% Normal` |
| `Kidney Health` | `6% flagged` | `94% Normal` |

**Do not render a Compliance card, a Data Coverage tile, or a "Create Challenge" button inside this card.** The Compliance card carries a banned string; the coverage tile's values are demo-tenant data.

**Pane note, two sentences, both load-bearing:**
`Wellness figures are calculated daily and read as of yesterday. Health domain figures are organization level and reported by quarter, not sliced by department.`

**Second pane note, the disambiguation** (`.console-note` with a subtle amber left rule so it reads as a definition, not a disclaimer):
`Participation appears twice in this console and means two different things. On the Overview it is active users divided by enrolled users. Inside the wellness score it is daily engagement over the last seven days. They are not the same number and they are never reconciled.`

---

### 4.3 The count-only cohort mock (inside the privacy fairband)

A white panel, 380px, floating on the dark band, `box-shadow: 0 26px 60px rgba(0,0,0,.32)`, radius 18px, padding 18px 20px.

`aria-label`: `Challenge target audience step with a health risk code selected, showing a matching count of 214 employees and the product disclaimer that the list of users is not displayed. Figures shown are illustrative.`

Contents:

- Header row: `<b>Create challenge</b>` on the left, `Step 5 of 7 · Target Audience` on the right at `.66rem`, muted
- Field rows, each a label on the left and a value on the right:

| Label | Value |
|---|---|
| `Department` | `Any` |
| `Country` | `Any` |
| `Health Risk Code` | `At risk for diabetes` (rendered as a mint-tinted chip). This is the help docs' own worked example for risk targeting. Do not invent a risk-code string; no source lists the code vocabulary. |
| `Matching employees` | `214` (large, tabular, ink) |
| `Challenge privacy` | `Private` (rendered as a neutral chip, with a padlock glyph) |

- A tinted callout box under the fields, coral-tinted `rgba(241,81,98,.07)` with a `1px solid rgba(241,81,98,.3)` border and radius 12px, carrying the **literal product string in quotes**:
  `"The list of users is not displayed to protect individual privacy."`
- `.audit-caption` below: `Applying any audience filter marks the challenge private. Matching employees are enrolled automatically.`
- `<span class="mock-tag">Illustrative data</span>`

**The quoted string must be reproduced exactly, including the final period.** It is a real product string and it is the strongest sentence on this page.

---

### 4.4 The Recommended Actions mock (section S6, right column)

A white card, radius 18px, `border:1px solid var(--line)`, `box-shadow: 0 22px 54px rgba(41,41,76,.10)`, padding 20px 22px, max-width 460px.

`aria-label`: `Recommended actions panel listing three suggested next steps, including 312 employees inactive for 30 or more days. Figures shown are illustrative.`

- Header: `<b>Recommended Actions</b>` with the real subtitle beneath at `.68rem` muted: `System suggested next steps`
- Three rows, each a 32px tinted icon square plus a title and a one-line description:

| Icon tint | Title | Description | Chip |
|---|---|---|---|
| mint | `View Inactive Employees` | `312 employees inactive for 30+ days` | |
| coral | `Nudge Inactive Users` | `Pre-fills a custom email to that cohort` | |
| neutral | `Review Org Wellness Score` | `Component contributions for the last quarter` | `Annual contract` |

- `<span class="mock-tag">Illustrative data</span>`

Icons are inline SVG at 16px, drawn from `rgba(41,41,76,.34)` greys plus one mint and one coral accent. No icon font.

---

### 4.5 Glyphs for the three question cards (S2)

Three hand-drawn 74×44 SVG glyphs, in the house style: greys at `rgba(41,41,76,.14 / .16 / .24 / .34)` plus exactly one `#41d8b4` and one `#F15162` accent per glyph. Each diagrams its mechanic:

1. **Participation:** a stack of four horizontal bars of decreasing width, the top two filled mint, the bottom two grey, with one small coral dot at the end of the shortest bar. Reads as "some of the population is active".
2. **Challenges:** three ranked rows with a small expand chevron on the middle row and two short sub-rows fanning out beneath it. Reads as "a row that opens".
3. **Activity & health:** a rising line over four grid columns with a small padlock glyph at the top right in coral. Reads as "trend, gated".

---

### 4.6 Components to copy in from `design-system.md` §3.B before writing markup

`enterprise.css` does not contain any of these. Copy each block:

| Needed for | Classes | Source |
|---|---|---|
| S2 question cards | `.format-grid` (3-up variant: `repeat(3,1fr)`), `.format-card`, `.format-glyph`, `.best-for` | §3.B, `[STEPS]` |
| S5 privacy inset | `.fairband`, `.fair-fine` | §3.B, `[STEPS]` |
| S5 cohort mock | `.audit-board`, `.audit-caption` | §5.4 |
| S6 loop rows | `.employee-cols`, `.join-point`, `.join-icon` | §3.B |
| S8 proof | `.results-grid`, `.result-card`, `.stat`, `.segment`, `.proof-fine`, `.quote-band.text-only`, `.quote-who` | §3.B |
| S9 trust variant | `.solutions-trust` four overrides, `.mark-strip`, `.mark` | chrome.html, §3.B |
| S10 FAQ | `.faq-screen`, `.faq-list`, `.faq-item` | chrome.html F3 |
| S11 related | `.related-screen`, `.related-grid`, `.related-row`, `.related-icon` | chrome.html |
| Hero mock | `.dash`, `.dash-top`, `.dash-url`, `.metric-inline`, `.metric-card`, `.metric-value`, `.metric-delta`, `.chart-card`, `.chart`, `.target-line`, `.chart-labels` | shipped in `enterprise.css` |

New page-local components introduced by this page and by no sibling: `.console` and its whole family, `.ledger`, `.dim-row` / `.dim-chip`, `.seg-case`, `.report-list`, `.limit-row`, `.chain-row`.

The `.fairband` on this page overrides its columns to `1.15fr .85fr` so the two-column ledger fits. Declare that override next to the fairband block and comment why.

---

## 5. Claims table

Every factual assertion that appears on the page. Anything not on this list must not appear.

| # | Claim as it appears on the page | Section | Source | Status |
|---|---|---|---|---|
| 1 | Overview KPI labels: Enrolled Users, Active Users, Incentivization, Participation Rate | Hero, S3 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`; settled ruling `rewards.md` E1 | SHIPPED |
| 2 | Each KPI card carries a delta versus the previous period, default label "vs Prev Quarter", plus a weekly sparkline | Hero, S3 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`; `dash-design/.../2026-07-18-wellness-live-ground-truth.md §1d` | SHIPPED |
| 3 | Participation Rate is active users divided by enrolled users | S3 pane 3 note, FAQ | `research/insights-reports.md §2 Story A` citing the admin dashboard spec | SHIPPED |
| 4 | Incentivization prints an average per employee line | S3 pane 1 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 5 | Wellness reads snap to yesterday; the honest caption is "as of yesterday" | Hero, S3 | `dash-design/.../2026-07-18-wellness-live-ground-truth.md §4` | SHIPPED |
| 6 | Employee Report columns: name, email, Department, Country, Enrollment status, Last active date | S3 pane 1 | `astro/content/en/help/admin/reports/admin-how-do-i-view-employee-reports.md` | SHIPPED |
| 7 | Enrollment status values: Active, Inactive, Dormant | S3 pane 1 | same | SHIPPED |
| 8 | Employee Report filters: search by name or email, Department, Country; Export CSV | S3 pane 1 | same | SHIPPED |
| 9 | Cross-reference the Employee Report with the Transaction Report to find enrolled but inactive employees | S3 pane 1, S7 | `astro/content/en/help/admin/reports/admin-what-reports-are-available.md` | SHIPPED |
| 10 | Three challenge leaderboards: Score Leaderboard, Steps Leaderboard, Team Leaderboard | S3 pane 2 | `astro/content/en/help/admin/reports/admin-how-do-i-view-leaderboard.md` | SHIPPED |
| 11 | Score Leaderboard columns: Rank, Employee name, Score, Department | S3 pane 2 | same | SHIPPED |
| 12 | Clicking a row shows per-task and per-week breakdown with task completion status | S3 pane 2, S3 quote | same | SHIPPED |
| 13 | Team score is the average of member scores | S3 pane 2 legend | same; house rule | SHIPPED |
| 14 | Quote: "The score breakdown per user is one of the most useful tools in the dashboard. It shows exactly which tasks employees are completing and which they are skipping." | S3 | `astro/content/en/help/admin/reports/admin-what-reports-are-available.md` | SHIPPED, verbatim trimmed before the em-dash |
| 15 | Challenge cards render a participation hero, participant count and a date range | S3 pane 2 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 16 | At a Glance metrics: Avg Steps `/day`, Active Minutes `min/day`, Mindful Minutes `min/day`, Avg Sleep `hr`/`mins`, with the active date-preset as the subheader | S3 pane 3 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 17 | Org Wellness Score is a 0 to 100 composite, calculated daily | S3 pane 3, FAQ 3 | `astro/content/en/help/admin/workforce-health/admin-what-is-org-wellness-score.md`; settled ruling G3 | SHIPPED |
| 18 | Four components and weights, admin-card strings: Health Baselines 20%, Participation 30%, Activity Levels 30%, Program Adherence 20% | S3 pane 3 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`; ruling D3 | SHIPPED |
| 19 | Wellness score Participation is daily engagement over a 7-day window and is a different measure from the Participation Rate KPI | S3 pane 3 note | `dash-design/.../2026-07-18-wellness-live-ground-truth.md §4` | SHIPPED |
| 20 | Wellness Leagues are three tiers, Gold, Silver and Bronze, assigned from a rolling average daily step count over a configurable 7-day or 30-day window, recalculated daily, thresholds set per company | S3 pane 3 | `astro/content/en/help/admin/workforce-health/admin-how-do-leagues-work.md` | SHIPPED |
| 21 | League tier distribution renders as percentages to one decimal, with a threshold scale based on average daily steps over N days | S3 pane 3 | `dash-design/.../2026-07-18-wellness-live-ground-truth.md §2B` | SHIPPED UI labels |
| 22 | "Trends reflect only employees currently active in the system." | S3 pane 3 | same | SHIPPED, verbatim |
| 23 | Health domain prevalence is reported as "% flagged" per health area, by quarter | S3 pane 3 | `dash-design/docs/superpowers/refs/health-insights-2026-08-02/*.jpg`; `vfit-os/specs/product/03-health-wellness/workforce-health.md` | SHIPPED, gated |
| 24 | Health domain names include Diabetes, Heart Health, Kidney Health, Liver Health | S3 pane 3 | same screenshots | SHIPPED, gated |
| 25 | Health risk insights are organization level only, not sliced by department, team or location | S3 pane 3, S4 | `vfit-os/specs/product/03-health-wellness/workforce-health.md` | SHIPPED, code-verified spec wins over the help doc |
| 26 | Org Wellness Score, Wellness Leagues and Health Insights are entitlement-gated to annual contracts and provisioned by the account manager, not a toggle | S3, FAQ 3, S12 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED-GATED |
| 27 | Workforce Health needs 2 to 4 weeks of data collection for a reliable baseline | FAQ 3 | `astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md` | SHIPPED |
| 28 | Dashboard-wide filters: date range, Country, Department, Age group, Gender | S3, S4 | `astro/content/en/help/admin/workforce-health/admin-dashboard-overview.md`; `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 29 | Date-range presets include This Month, Last Quarter, Last 90 Days, This Year, Custom, Lifetime | S4 | `dash-design/.../2026-07-18-wellness-live-ground-truth.md §1d` | SHIPPED UI labels |
| 30 | Filter values come from the company's own employee data | S4 | `research/insights-reports.md §4.1` | SHIPPED |
| 31 | No business unit, tenure, job level, manager hierarchy or saved cohort dimension; filters are ad hoc | S4 | `research/insights-reports.md §4.4`; `dash-design/docs/filters.md` | SHIPPED, stated as an absence |
| 32 | Challenge and notification audiences add City, Language and Health Risk Code | S4, S5 | `astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md` | SHIPPED |
| 33 | A lagging department can be filtered on the leaderboard and sent a targeted message | S4 | `astro/content/en/help/admin/reports/admin-how-do-i-view-leaderboard.md` | SHIPPED |
| 34 | A department that is heavily Bronze may benefit from a department-specific challenge or walking group | S4 | `astro/content/en/help/admin/workforce-health/admin-how-do-leagues-work.md` | SHIPPED (documented guidance, not a customer result) |
| 35 | Admins CAN see aggregate metrics, challenge data and participation-oriented employee reports | S5 ledger, FAQ 2 | `astro/content/en/help/admin/settings/admin-data-privacy-security.md` | SHIPPED |
| 36 | Admins CANNOT see individual health data, HRA answers and risk categories, lab report values, mood logs, food diary or sleep patterns | S5 ledger, FAQ 2 | same | SHIPPED |
| 37 | Verbatim quote: "Your HR team sees whether you are participating and your challenge rankings, but we cannot see your weight, health assessment results, lab reports, or personal health data." | S5 | same | SHIPPED, verbatim |
| 38 | Where wellness scores are enabled, an admin sees a derived score, and the documentation states individual scores are for program design rather than decisions about specific employees | S5 note, FAQ 2 | `astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md` | SHIPPED |
| 39 | Health-risk audience selection returns a count only, with the string "The list of users is not displayed to protect individual privacy." | S5 mock | `vfit-os/specs/product/03-health-wellness/workforce-health.md` | SHIPPED, verbatim |
| 40 | Applying any audience filter marks a challenge Private | S5 mock, S6 | `astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md` | SHIPPED |
| 41 | Matching employees are enrolled automatically; employees do not browse and join | S5 mock, S6 | same | SHIPPED |
| 42 | Recommended Actions is a panel with the subtitle "System suggested next steps", with rows such as viewing inactive employees and nudging inactive users | S6 mock | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`; `dash-design/.../2026-07-18-wellness-live-ground-truth.md §5` | SHIPPED |
| 43 | Nudging pre-fills a custom email to that cohort | S6 mock | same | SHIPPED |
| 44 | A Streak challenge lifts Adherence, a Race lifts Activity, a content-led Custom challenge lifts Participation | S6 | `astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md` | SHIPPED, documented guidance |
| 45 | The six named reports and their exact locations | S7 | `astro/content/en/help/admin/reports/admin-what-reports-are-available.md` | SHIPPED, two gated |
| 46 | Every report has an Export CSV button and the file downloads to the browser; filters are applied before export | S7, FAQ 4 | `astro/content/en/help/admin/reports/admin-how-do-i-export-reports.md` | SHIPPED, kept generic on purpose |
| 47 | There is no scheduled report and no emailed delivery; the documented practice is a monthly reminder and archive | S7, FAQ 4 | same | SHIPPED, stated as an absence |
| 48 | There is no data warehouse connector | S7, FAQ 4 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md §08` | SHIPPED, stated as an absence |
| 49 | Export a Race challenge after the 3-day buffer so late-syncing data is included | S3 pane 2, S7 | `astro/content/en/help/admin/reports/admin-how-do-i-export-reports.md` | SHIPPED |
| 50 | Export is a role permission; admins without it see the control disabled | S7 | `dash-design/.../2026-07-18-wellness-live-ground-truth.md §2A` | SHIPPED UI behavior |
| 51 | Wipro: 3X participation increase, 163 to 550 active users, first challenge to third | S8 | `vfit-os/.claude/rules/data-accuracy.md:89-131`; `astro/content/en/casestudy/wipro-global-wellbeing.md` | APPROVED-CLAIM |
| 52 | Wipro: 46.53M cumulative steps | S8 | same | APPROVED-CLAIM |
| 53 | Wipro: 30+ countries with participants, labelled as this program's participant footprint | S8 | same | APPROVED-CLAIM, must carry the label |
| 54 | Avalon Consulting quote, attributed to Shubham Sanghavi, Consultant | S8 | `data-accuracy.md:193-240` | APPROVED-CLAIM, verbatim, title is Consultant |
| 55 | Trusted by 100+ organizations worldwide | Hero logo band | `data-accuracy.md:252-261` | APPROVED-CLAIM, the only aggregate |
| 56 | Logo names: Tata Motors, Wipro, IBS Software, Brazosport ISD, Landmark Group, POSOCO | Hero logo band | `data-accuracy.md:22` | APPROVED names |
| 57 | Vantage Fit operates under HIPAA guidelines | S9 | `vfit-os/sources/VFit-Marketing-Content-Compacted.md 2.15` | APPROVED phrasing, never "HIPAA compliant" |
| 58 | SOC 2 Type II | S9 | same | APPROVED |
| 59 | Four isolated regional instances: India, US, EU, UAE, chosen at signup, no cross-region sharing | S9 | `astro/content/en/help/admin/settings/admin-data-privacy-security.md`; `vfit-os/specs/product/00-platform/auth-login-signup.md` | SHIPPED |
| 60 | Leadership Insights sends no employee identifiers, only aggregated signal buckets | S9 | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 61 | Employees delete their own lab reports; employees self-delete their account with OTP; an admin cannot delete an account on their behalf | S9 | `astro/content/en/help/admin/settings/admin-data-privacy-security.md`; `vfit-os/specs/product/03-health-wellness/workforce-health.md` | SHIPPED |
| 62 | Steps count only from approved apps and devices; one primary device at a time; GPS pace validation and vehicle detection; source tracking; flagged activity does not reach rankings | FAQ 5 | `vfit-os/specs/product/10-integrations/device-integrations.md`; `astro/content/en/help/employee/health-tracking/how-do-i-track-a-gps-workout.md` | SHIPPED, no cap number quoted |
| 63 | Challenge results stay provisional for 3 days after the end date | FAQ 5, S7 | `astro/content/en/help/admin/challenges/admin-how-do-i-create-race-challenge.md` | SHIPPED |
| 64 | Admin dashboard is at `dashboard.vantagecircle.com` | S3 chrome bar | `astro/content/en/help/admin/settings/admin-how-do-i-sign-in.md` | SHIPPED |
| 65 | Sidebar section headers Analyze, Engage, Manage, Challenges, and the page names rendered | S3 sidebar | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`; `dash-design/.../2026-07-18-wellness-live-ground-truth.md §1a` | SHIPPED, Insights Hub deliberately omitted |

### 5.1 Claims considered and cut

| Considered | Why cut |
|---|---|
| Brazosport ISD 86% engagement plus 4/5 mood score | The mood score contradicts the page's own privacy claim. The 86% alone adds nothing this page needs. |
| Beroe 96% engagement | Contradicted by its own case study and flagged by the audit. |
| Industry Benchmark card on the Wellness Score page | The value is a hardcoded constant despite the card claiming anonymized industry data. |
| Workforce Health Snapshot 82% Normal / 18% Needs Attention and its deficiencies list | Production dummy fixtures served from a cache with no writer. |
| Data Coverage tile ("N of M employees with at least one lab report") | Screenshot values are a demo tenant, and coverage is a weak story given HRA completion reality. |
| "AI-powered wellness score insights" | The Wellness Score page's Insights panel is string templating mislabelled as AI. Only Leadership Insights is a real ML call, and that is claim 60. |
| n = 5 suppression, versioned consent, 30-day erasure SLA, minimum audience of 20 | Design intent, parked. |
| "Real-time analytics" | Wellness reads snap to yesterday. The page says daily and as of yesterday. |
| HRA completion rate as a named report | The spec mentions it, the help-doc report catalog does not list it. Not drawn, not named. |
| Any step cap number | Three sources, three answers. |
| Slack or Microsoft Teams | Zero spec coverage. |

---

## 6. Meta

**Meta title** (45 characters):
`Workforce Health Insights for HR | Vantage Fit`

**Meta description** (144 characters):
`See participation, challenge and activity analytics in one admin console. Aggregate by design, with CSV exports your board can read. Book a demo.`

**Optional SEO/AEO head layer** (harmless on a `noindex` mock, required on the shipped page):
- `<link rel="canonical" href="https://www.vantagefit.io/solutions/workforce-health-insights/">`
- `og:type` `website`
- `og:title` `Workforce Health Insights for HR | Vantage Fit`
- `og:description` `Participation, challenge and activity analytics in one admin console, aggregate by design.`
- `og:image` `https://www.vantagefit.io/og/workforce-health-insights.png`
- `twitter:card` `summary_large_image`
- JSON-LD: `FAQPage` carrying all five FAQ questions and answers **verbatim as rendered**, plus `SoftwareApplication` and `BreadcrumbList` (`Home → Solutions → Workforce health insights`).

The schema file on the live site is hand-maintained and drifts from visible copy on every page checked. If this mock ships schema, the strings must match the rendered copy character for character and must carry no banned stat.

**Head boilerplate:** exactly as `design-system.md` §8, including `<meta name="robots" content="noindex, nofollow">` and `<link rel="stylesheet" href="../styles/enterprise.css">` as the only stylesheet.

---

## 7. Menu fit

**Placement:** Solutions mega-menu, **Column ② "Workforce health & rewards, measure and motivate", row 2 of 3.**

| Property | Value |
|---|---|
| Menu label (exact, sentence case) | `Workforce health insights` |
| Description line (exact) | `Participation, challenge and activity analytics your board can read` |
| Badge | `Data out` |
| URL | `/solutions/workforce-health-insights/` |
| Gallery-card alternate description | `Participation + challenge + activity in one page` |
| Footer Solutions column | Row 8 of 9 |

**Nav self-location, mandatory on the built page:**
- Add `is-current` to the Solutions `.nav-trigger`
- Add `is-page` and `aria-current="page"` to the `Workforce health insights` `.mega-link`

**Its role in the data in, data out, action chain:**

The sign-off card states the chain verbatim: *"Data in → data out → action: HRA feeds insights, insights prove impact, rewards drive behavior."* This page is the **middle link and the only one that produces an artifact leadership sees.**

- **Backward, to page 2 (Health Risk Assessment, `Data in`):** the assessment is where the Baseline component of the wellness score comes from, and it is the source of the Health Risk Code used for count-only cohort targeting. The page links back from S6 row 1 of the chain row, and the S3 pane 3 wellness score breakdown names Health Baselines as a component.
- **Forward, to page 4 (Wellness rewards program, `Action`):** the Incentivization KPI on the Overview and the Transaction Report and Redemption Report are the rewards side of the same console. The page links forward from the chain row and from Related.
- **Sideways, to column ① (Wellness challenges):** every insight on this page resolves into launching or reshaping a challenge. That link is made twice, in S6 and in Related.

The page stands alone: a reader who arrives cold from search never needs the other two to understand it.

---

## 8. Cross-links

Two to three internal links per page is the convention. This page carries more because it is the hub of the chain, so keep the anchor text descriptive and never repeat the same anchor twice.

| From section | Anchor text | Target |
|---|---|---|
| S6 chain row | `Where the data comes from: Health Risk Assessment →` | `/solutions/health-risk-assessment/` |
| S6 chain row | `What you run against it: Wellness challenges →` | `/solutions/wellness-challenges/` |
| S6 chain row | `What keeps people coming back: Wellness rewards program →` | `/solutions/wellness-rewards-program/` |
| S8 proof fine | `Read the Wipro story →` | `https://www.vantagefit.io/casestudy/wipro-global-wellbeing/` |
| S9 trust actions | `Explore security & compliance →` | `https://www.vantagefit.io/features/security-and-compliance/` |
| S11 related | `Health Risk Assessment` | `/solutions/health-risk-assessment/` |
| S11 related | `Wellness rewards program` | `/solutions/wellness-rewards-program/` |
| S11 related | `Wellness challenges` | `/solutions/wellness-challenges/` |
| Hero, S9, S12 | `Book a demo` | `https://www.vantagefit.io/request-demo/` |
| Hero, S12 | `See pricing` | `https://www.vantagefit.io/pricing/` |

**Links this page should receive** (note for the set owner, not built here):
- From `/solutions/health-risk-assessment/`: forward link, "what HR sees back from it".
- From `/solutions/wellness-rewards-program/`: backward link, "how spend and participation reconcile".
- From `/solutions/wellness-platform/`: down-link into the measurement layer.
- From `/solutions/` hub: column ② card 2.
- From `/features/participation-analytics-and-insights/` if that Features page ships, since its menu description ("Trends, AI insights and board-ready exports in one console") is nearly this page's promise. **Flag the overlap:** the Features row and this Solutions page must not become duplicates. Recommendation: Features owns the capability list, Solutions owns the buying case.

**Do not link:** Insights Hub, `/slack-integration/`, `/health-fitness-analytics/` (retired into this page), or `/employee-wellness-software/` (currently the worst offender for fabricated ranges).

---

## 9. Assumptions and gaps

### 9.1 Assumptions I made

1. **The page sells both tiers, honestly.** Open question 1 in the insights dossier asks whether the page sells the premium tier or the base tier. My call: **sell the base tier as the promise and disclose the premium tier as an upgrade in the same breath.** Reason: participation and challenge analytics are what every buyer gets on day one, and a hero built on gated health-risk prevalence would misrepresent the purchase for most readers. The gate is disclosed in the tab chip, three card chips, a console note, an FAQ answer and the closer note.
2. **The Health Insights capability is described, not screenshotted.** Open question 2 asks whether mocks show the embedded analytics app as-is or the unshipped native replacement. My call: **neither.** The console renders a small, native-styled health domain card carrying only capability-true content (percent flagged, org level only, quarter based). This avoids both drawing an unshipped redesign and reproducing the embedded app's quirks and its banned Compliance string.
3. **The console's single global filter bar is a simplification.** In production, the Wellness Leagues page exposes date range only, and Health Insights uses a Quarter plus Tolerance selector with no country or department filters. I handled this by giving the health domain card its own quarter chip and a note. A reviewer should confirm this reads as honest rather than as a promise of unified filtering.
4. **Illustrative tenant scale is 4,820 enrolled.** Chosen because it is unremarkable, is not any customer's real headcount, and lets `3,140 / 4,820 = 65%` land on a clean integer. Every derived number in the console follows from it.
5. **Employee names in mocks are initial-plus-surname** and are not drawn from any repo. No name from the design prototype's fake tenant appears.
6. **Terminal periods on H1 and H2** across this page, matching `[TEAM]`, `[MULTI]` and `[MH]`. Hold it consistently.
7. **The Wipro proof strip earns its place.** A results section is optional per the prompt. Wipro is the only approved story that is itself a measurement-over-time story, which is this page's subject. If the built page runs long, this is the first section to cut.

### 9.2 Gaps a human must verify

1. **URL prefix conflict, unresolved.** `vfit-os/.claude/rules/seo-conventions.md:69,83` says solution pages are root-level with no `/solutions/` prefix and instructs not to propose URL changes. The signed-off menu and the shipping prompt both use `/solutions/…`. **This brief follows the menu.** Escalate before launch.
2. **Slug collision, flagged and not blocking this page.** `/solutions/wellness-challenges/` (the new library page) collides with the shipped consolidated page at `/solutions/wellness-challenge`, and there is also a live library at `vantagefit.io/wellness-challenges/`. This page links to the menu URL. Someone must decide whether the library replaces or sits above the live page.
3. **Features overlap.** The signed-off Features menu row `Participation analytics & insights` carries the description "Trends, AI insights and board-ready exports in one console", which is close to this page's promise. Decide the division of labor before both ship.
4. **`Participation Report`** appears in production nav and in the design-repo catalog but is absent from the help-doc report table. Not named on this page. Someone should confirm what it contains and whether it belongs in the six.
5. **The shipped Health Insights screen prints "HIPAA Compliant"** in a Compliance card, which is a live liability for a company whose approved phrasing is "operates under HIPAA guidelines". This page does not reproduce it. Flag to product.
6. **SOC 2 Type II** is approved by the claims gate but is flagged "not documented in KB" by the site audit. Expect a legal check.
7. **Wipro case-study URL** is assumed to be `https://www.vantagefit.io/casestudy/wipro-global-wellbeing/` from the content filename. Verify the rendered slug.
8. **Export mechanics conflict.** The help docs say exported CSVs respect applied filters; the production audit found the League Report export ignores inline filters and the Wellness Score export caps at 10,000 rows. This page keeps the claim generic ("filter first, then export") and makes no filters-always-carry claim and no uncapped-export claim. Product should reconcile the docs.
9. **The `NEW` tag on Wellness Score** in the sidebar is a real production string, but its lifetime is unknown. If it has been retired by build time, drop the tag rather than inventing a replacement.
10. **Recommended Actions row count** is 5 in the code-verified spec and 10 in the production audit. The mock shows three rows and makes no count claim.

### 9.3 If the built page runs long

Cut in this order, and only in this order:
1. S8 Proof (the Wipro strip and the Avalon quote). The page's credibility does not depend on it.
2. S4's two "what a segment view changes" cards, keeping the dimension chips and the honest-limits note.
3. FAQ items 5 then 4, never item 1 (the answer-first definition carries the AEO value) and never item 2 (the privacy answer).

**Never cut:** the console, the privacy ledger, the count-only cohort mock, the honest-limits note in S4, or the "two participations" note in pane 3. Those five are the page.
