# SOLUTIONS HUB BRIEF

**Page 6 of 6.** URL `/solutions/` · Archetype: hub / chooser / directory
**Mock to build:** `claude-fable/vantage-fit-solutions-hub-v1.html`
**Design system:** enterprise (Noto Sans). `<link rel="stylesheet" href="../styles/enterprise.css">` and nothing else external.
**Chrome:** paste nav, footer and closer from `scratchpad/research/chrome.html`. Use the **colon** form of the mega column headers (`Wellness challenges: what you want to run`) for consistency with the em-dash ban.
**Heading punctuation convention for this page:** terminal periods on H1 and every H2. Hold it everywhere.

---

## 1. Research takeaways that decided the structure

Each row is the fact, then the decision it forced, then the source.

| # | Fact | What it decided | Source |
|---|---|---|---|
| 1 | The signed-off Solutions IA has exactly two mega-menu columns plus a featured platform page plus the hub. Total set: "10 pages: hub + platform + 5 challenges + 3 health & rewards". | The hub gets exactly **9 destination cards**, in two named groups plus one featured card. No third category, no invented top-level item. | `vfit-website-design/menu/vantage-fit-solutions-menu-preview.html:343-367, :455-491`; `ia-claims-proof.md` §1.2 |
| 2 | The sign-off card states the section ② logic verbatim: *"Data in → data out → action: HRA feeds insights, insights prove impact, rewards drive behavior."* | This is not a marketing metaphor written for the page. It is the signed-off IA rationale. That is why it is safe to render as an actual drawn chain, and why the three card footers use those exact three verbs: **Feeds insights · Proves impact · Drives behavior**. | `menu/vantage-fit-solutions-menu-preview.html:483` |
| 3 | The chain is real in the product, link by link. Health profile / HRA / lab upload feed the Baseline component of the Wellness Score; scores roll up to Org Wellness Score and risk prevalence at org level only; challenge tasks carry point rewards which flow into the Vantage Points wallet; points come from challenge tasks, so the loop closes back into challenges. | The chain diagram may be drawn as a **closed loop**, with the return arm labelled by the points mechanic rather than by the risk-targeting mechanic. Risk-targeted challenges are a live capability but the roadmap says "used internally so far", so the loop-back is labelled with points, which is unambiguously shipped. | `health-hra.md` §7 items 5-12; `vfit-os/specs/product/03-health-wellness/workforce-health.md`; `vantagefit-astro/content/en/help/admin/challenges/admin-how-wellness-rewards-work.md` |
| 4 | Wellness platform owns 850/mo, the biggest term in the set, and is explicitly **"Featured on the hub"**, not a mega-menu row. It is also footer Solutions row 1. | The platform gets its own section with real weight, a dark `.fairband` inset, not a tenth card in a grid. | `menu/vantage-fit-solutions-menu-preview.html:478-481`; `ia-claims-proof.md` §1.2, §2 |
| 5 | The hub itself is 200/mo with **orientation** intent, and the proof-to-page map says explicitly: *"Solutions hub: one proof strip only: 100+ organizations, plus 2-3 labeled client outcomes. Do not use: a wall of stats. The hub is a chooser."* | No full customer-result section, no FAQ, no formats explorer, no dashboard deep dive. One three-tile proof strip and a compliance line. | `ia-claims-proof.md` §4.4, §6.2 |
| 6 | Employees do not browse and join. Enrollment is admin audience-rule auto-enrollment, with "Action Required? None, you're already in". | The single most useful one-line objection killer on a chooser page, because the buyer's first fear on every card is "nobody will sign up". It goes as the trailing note under section ①, not as a section. | `vfit-os/specs/product/02-challenges-gamification/challenges.md:42`; `HELP/employee/challenges/how-do-i-join-a-challenge.md:17-38` |
| 7 | Step tracking is automatic via Apple Health (iPhone) or Google Fit (Android), no wearable required. | The hero note. It is the second objection ("do we have to buy Fitbits?") answered in one line above the fold. Apple Health and Google Fit are always named together, per the house rule. | `HELP/admin/settings/admin-what-is-vantage-fit.md` |
| 8 | The Overview KPI cards are exactly four: **Enrolled Users · Active Users · Incentivization · Participation Rate**. | Both the hero `.dash` and the chain's "data out" mini-artifact render those four labels, exactly, and nothing else. This is the ruling in `ia-claims-proof.md` §G3 and `rewards.md` E1, over the five-card blend that appears in the help doc. | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md:55`; `ia-claims-proof.md` §G3 |
| 9 | Admins see aggregate participation, rankings and team scores. Admins cannot see individual weight, BMI, HRA answers, lab biomarkers, mood logs, food diary or sleep patterns. | One caption under the chain. It is the enterprise objection for the entire ② column, and on a chooser it is answered in a sentence and a link, not a section. | `HELP/admin/settings/admin-data-privacy-security.md`; `insights-reports.md` §3.1 |
| 10 | The certification raster is banned from the trust plaque. The approved typeset strings are exactly three: **Follows HIPAA guidelines · SOC 2 Type II · Secured regional data hosting**. | The hub drops the full dark `.trust-screen` band entirely and carries those three strings as a light pill row inside the proof strip. That removes one dark band and roughly 400px of page height, which is how the hub stays the shortest page in the set while still answering security. | `ia-claims-proof.md` §G3; `design-system.md` addendum F1; `claude-fable/vantage-fit-multi-activity-challenge-v1.html:1172-1190` |
| 11 | "100+ organizations" is the only approved aggregate scale claim. "50+ countries" is dead, use "worldwide". "190+ countries" is a rewards/SOLI capability only. | Logo band label is fixed. 190+ appears exactly once, inside the rewards chain card, attached to gift cards. | `vfit-os/.claude/rules/data-accuracy.md:252-261`; `vfit-os/specs/product/08-rewards-marketplace/soli-currency.md:105` |
| 12 | Signed-off menu labels and description lines exist verbatim for all eight column pages. | Every card title and every card description on this page is **lifted verbatim from the menu**. Zero new naming. That is the point of a hub: the nav and the hub must read identically or the user thinks they are in a different place. | `menu/vantage-fit-solutions-menu-preview.html:344-357` |

### Where sources conflicted, and which one I followed

| Conflict | Options | Followed | Why |
|---|---|---|---|
| URL shape | `seo-conventions.md:69,83` says solution pages are root-level with no `/solutions/` prefix. The signed-off menu and the shipping brief both use `/solutions/…`. | **`/solutions/…`** | Newer decision, and the shipping brief repeats it. Flagged in §9, not silently picked. |
| Overview KPI cards | Code-verified four (Enrolled Users, Active Users, Incentivization, Participation Rate) vs help-doc four (Active Users, Enrollment Rate, Completion Rate, Org Wellness Score) vs a five-card blend in `rewards.md` §6.2. | **Code-verified four** | Settled ruling, `ia-claims-proof.md` §G3 and `rewards.md` E1. |
| Wellness Score range | 0-100 (help doc + admin spec + shipped calculator) vs 0-~108 (`leagues-wellness-score.md`). | **0 to 100**, and in fact **not printed on this page at all** | Settled ruling `ia-claims-proof.md` §G3 / `platform.md` A1. The hub has no room for a score explainer, so the risk is designed out. |
| Activity type count | 65 vs 47+ vs "publish neither". | **"65+ activity types"** | Settled ruling `platform.md` A3, help-doc sourced. Used once, in the platform feature card. |
| Section ② item 2 description | Nav line "Participation, challenge and activity analytics your board can read" vs gallery line "Participation + challenge + activity in one page". | **Nav line, verbatim** | The nav line is what the user just read in the menu. The hub must echo it. |
| Insights Hub | Listed as a real admin page in `platform.md` §3.3 and `health-hra.md` §6.2; ruled unclaimable in `insights-reports.md` §7.3. | **Do not claim, draw or link** | Settled ruling `ia-claims-proof.md` §G3. Nav commented out in production, all five sub-pages blank iframes. Nothing on this page references it. |

---

## 2. Strategy

### The buyer
HR Director or Head of People, arriving from the Solutions mega-menu trigger, from organic search on "corporate wellness program software", or from a comparison shortlist. They have a budget line, a headcount, and usually a specific instruction from a CHRO or CFO. They are not reading. They are scanning for the row that matches their situation.

### The one thing this page must land
**"There is a page here for exactly my situation, and I can get to it in one click."**
Nothing else. Not what Vantage Fit is, not why wellness matters, not how the product works. The hub converts by handing off, and its success metric is next-click rate, not time on page.

### The defining objection, and how this page answers it
**"Which of these do I actually need?"**
Answered three ways, in escalating specificity, so a reader who bails at any point still routes correctly:

1. **By job** (sections ① and ②). Two groups with plain-language headers: what you want to run, and what you want to measure and motivate.
2. **By logic** (the drawn chain). Section ② is three pages that most buyers will assume are three separate products they have to price separately. Drawing HRA to insights to rewards as a closed loop, with the connection rendered rather than asserted, converts "three more things to buy" into "one loop, enter anywhere".
3. **By situation** (the decision helper). Four quoted HR sentences, each routed to one page. This catches the buyer who read both grids and still cannot self-select.

### Why this section order
Hero (promise + the two questions) → ① run it → ② measure it → featured platform → decision helper → proof → closer.

- ① before ② because the menu is ordered that way and because the overwhelming majority of buyers arrive wanting to run something, not wanting to measure something. Inverting it would make the page feel like an analytics product.
- The platform card sits **after** both grids, not first. It is the biggest search term, but on the hub it is the fallback for the buyer who did not self-select, plus the vendor-comparison destination. Leading with it would turn the hub into a second homepage, which the prompt and `platform.md` §7.3 both forbid.
- The decision helper sits **after** the platform card because by that point we know the reader has failed to self-select twice, and the helper is remedial routing. Putting it first would insult a buyer who already knows what they want.
- Proof is second to last and deliberately thin. Three tiles, then the compliance line, then the closer.

### What this page's signature is, structurally
Two things no sibling has:

1. **Section ② rendered as a literal chain**, with a rail, arrowheads between the cards, stage pills matching the nav badges (`Data in` / `Data out` / `Action`), each card carrying a mini product-real artifact of its stage, and a dashed **loop-back arm** returning under the three cards to section ①. The section logic is legible at a glance instead of being asserted in a paragraph.
2. **A decision helper that routes by goal**, written as four things HR actually says, in quotation marks.

### What I deliberately left out, and why

| Left out | Why |
|---|---|
| **FAQ** | Excluded by the prompt, and correct. A chooser that answers questions is a page that stopped routing. Every question a hub FAQ would ask is a card on the page. |
| **Full `.trust-screen` dark band** | Takes ~400px and repeats on five siblings. The security answer here is three approved strings plus a link, inside the proof strip. Also drops the page from three dark moments to two. |
| **`.related-screen` (3 related rows)** | Every sibling ends with it. On the hub the entire page is related rows, so a related section is a duplicate of itself. |
| **Formats explorer, task types, leaderboard mechanics, dashboards, redemption flow** | Each belongs to exactly one sibling. Explaining any of them here creates a page the buyer finishes instead of leaving. |
| **A full `.results-grid` of four with `.quote-duo` testimonials** | `[DEC-S]` cut the customer-result section from the signed-off Steps page; `ia-claims-proof.md` §4.4 caps the hub at one strip. Three tiles, no quotes. |
| **The wellness calendar, the 21-challenge catalogue, challenge formats** | These are the library page's assets. Naming them here steals its click. |
| **Wellness Score, Wellness Leagues, Workforce Health prevalence** | All annual-client or premium gated. A hub cannot carry a gating qualifier per card without becoming a pricing page. They are the insights page's job. |
| **Pricing figures** | `platform.md` §10 marks the $1/user/month tier UNVERIFIED against a live page showing three tiers. The secondary CTA links to pricing; the page never states a number. |
| **Slack, Microsoft Teams, ISO 27001, ISO 27701, GDPR, free trial** | Banned. |

### Copy density target
Measured against the siblings, which run 9 to 10 sections and 1,600 to 2,400 words of body copy. **This page: 7 sections, target 520 to 620 words of body copy, hard ceiling 700.** Every card description is one line. Every route is one line. The hero lede is one sentence. If a section needs a second paragraph, cut the paragraph, not the section.

---

## 3. Section-by-section copy deck

Everything below is final copy. The mock builder writes nothing new.
**No em-dashes anywhere.** Sentence case headings, terminal periods on H1/H2.

---

### S1. Hero
`<header class="hero hub-hero" id="hero" aria-labelledby="hero-heading">`
Ground: the standard `.hero` cream/white radial gradient.
**Page-local override, required:** `.hub-hero { min-height: auto; }` and `.hub-hero .hero-grid { padding: 40px 0 26px; }`. Rationale: the hub converts on next-click, so the first row of section ① must be reachable within one scroll flick on a 1366x768 laptop. This is the only page in the set that overrides `--hero-h`.

| Element | Copy |
|---|---|
| `.eyebrow` | `Solutions` |
| `h1` (id `hero-heading`) | `Pick the program you want to run. Then see what it moved.` <br>The `<em>` gradient span wraps **`see what it moved`**. |
| `.lead` | `Every program below runs on the same platform: automatic step tracking, audience-rule enrollment, and one participation number for leadership.` |
| `.btn-row` | Primary: `Book a demo` → `https://www.vantagefit.io/request-demo/` · Outline: `See pricing` → `https://www.vantagefit.io/pricing/` |
| `.hero-note` | `Steps sync from Apple Health and Google Fit. No wearable required.` |
| `.hero-visual` | Mock A (`.dash`) + Mock B (`.phone`). See §4. |

**`.logo-band`** (last child of `<header class="hero">`, verbatim from `chrome.html`):

- `.logos-label`: `Trusted by 100+ organizations worldwide`
- `.logo-word` items, in order: `TATA MOTORS` · `WIPRO` · `TEVA` · `GODREJ` · `TEXAS INSTRUMENTS` · `HEIDRICK & STRUGGLES` · `BRAZOSPORT ISD`

---

### S2. Section ①, the challenge grid
`<section class="hub-section run-screen" id="run" aria-labelledby="run-heading">` · Ground: `var(--canvas)` `#F8F8F9`

| Element | Copy |
|---|---|
| `.eyebrow` | `Wellness challenges` |
| `h2` (id `run-heading`) | `Five ways to run a challenge.` |
| `.lead` | `Start with the library if you would rather browse before you decide.` |

**`.format-grid`, five `.format-card`s.** Layout is the shipped 3+2: `repeat(6,1fr)`, gap 14px, cards `span 2`, children 4 and 5 `span 3`.

Card 1 carries a `Library` flag pill in its heading row, matching the nav badge (`.mtag.new` styling: white on `--coral`).

| # | `h3` (verbatim menu label) | `p` (verbatim menu description line) | `.best-for` footer | href |
|---|---|---|---|---|
| 1 | `Wellness challenges` + `Library` flag | `The full library of ready-to-run challenges` | **BEST FOR** `Browsing ready-to-run designs across physical, mental, nutrition, sleep and team.` | `/solutions/wellness-challenges/` |
| 2 | `Step challenges` | `Company-wide step goals that get everyone moving` | **BEST FOR** `The fastest launch and the widest audience you will get.` | `/solutions/step-challenges/` |
| 3 | `Multi-activity challenges` | `Any activity, solo or in teams, over themed weeks` | **BEST FOR** `Reaching employees who will never join a step race.` | `/solutions/multi-activity-challenges/` |
| 4 | `Remote & hybrid team challenges` | `Wellness that works away from the office` | **BEST FOR** `Teams split across offices, home and time zones.` | `/solutions/remote-team-wellness/` |
| 5 | `Virtual marathon` | `Distance events powered by steps` | **BEST FOR** `One flagship event the whole company can enter.` | `/solutions/virtual-marathon/` |

**Trailing note** (`.format-note`, `.8rem`, `--muted`, `margin-top: 22px`):
`Employees are enrolled by audience rules, so there is no sign-up step to chase.`

---

### S3. Section ②, the chain
`<section class="hub-section chain-screen" id="measure" aria-labelledby="measure-heading">` · Ground: `#fff`

| Element | Copy |
|---|---|
| `.eyebrow` | `Workforce health & rewards` |
| `h2` (id `measure-heading`) | `Three pages that run as one loop.` |
| `.lead` | `Health data in, aggregate insight out, rewards that pull people back into the next program.` |

**The chain.** Full build spec in §4, Mock C. Copy for the three links:

**Link 1**
| Element | Copy |
|---|---|
| Stage pill | `Data in` |
| `h3` | `Health Risk Assessment` (Title Case, product noun) |
| `p` | `Baseline health screening with aggregate insights` |
| Mini-artifact heading | `What goes in` |
| Mini-artifact rows | `Health profile` / `Height, weight, BMI` · `Health Risk Assessment` / `Self-reported factors` · `Lab report upload` / `Biomarkers extracted` + a `Premium` micro-chip on this row |
| Footer link line | `Feeds insights` + right arrow |
| href | `/solutions/health-risk-assessment/` |

**Link 2**
| Element | Copy |
|---|---|
| Stage pill | `Data out` |
| `h3` | `Workforce health insights` |
| `p` | `Participation, challenge and activity analytics your board can read` |
| Mini-artifact heading | `Admin · Overview` |
| Mini-artifact 2x2 KPI grid (exact shipped labels) | `Enrolled Users` `2,480` · `Active Users` `1,712` · `Incentivization` `$9,240` · `Participation Rate` `69%` |
| Mini-artifact fine line | `Aggregate only. No individual health data.` |
| Disclosure | `<span class="mock-tag">Illustrative data</span>` |
| Footer link line | `Proves impact` + right arrow |
| href | `/solutions/workforce-health-insights/` |

**Link 3**
| Element | Copy |
|---|---|
| Stage pill | `Action` |
| `h3` | `Wellness rewards program` |
| `p` | `Points and gift cards tied to real effort` |
| Mini-artifact heading | `Vantage Points` |
| Mini-artifact balance | `1,240` |
| Mini-artifact row | `Redeem points` |
| Mini-artifact chips | `Shopping` · `Food & dining` · `Travel` · `+ more` |
| Mini-artifact fine line | `Gift cards in 190+ countries, priced for local purchasing power.` |
| Disclosure | `<span class="mock-tag">Illustrative data</span>` |
| Footer link line | `Drives behavior` + loop arrow |
| href | `/solutions/wellness-rewards-program/` |

**Loop-back arm label** (a link, sits on the dashed return arc):
`Points send employees back into the next challenge` → `/solutions/wellness-challenges/`

**Caption under the chain** (`.chain-caption`, `.8rem`, `--muted`, `margin-top: 26px`):
`Admins see participation, rankings and team scores. They never see an individual's assessment answers, lab results or mood logs.`

---

### S4. Featured, the platform
`<section class="hub-section platform-screen" id="platform" aria-labelledby="platform-heading">` · Ground: `var(--canvas)` · contains one dark `.fairband` inset.

No `.hub-head`. The `.fairband` carries its own eyebrow, h2 and lead, exactly as the shipped pattern intends.

**Left column of the `.fairband`:**

| Element | Copy |
|---|---|
| `.eyebrow` (lime on dark) | `Featured` |
| `h2` (id `platform-heading`, `.fairband h2` compressed size) | `Wellness platform.` |
| `.lead` | `One platform under every program on this page. This is the page to send into a vendor comparison.` <br>**Corrected in claims review.** The earlier draft read "under all nine programs". Nine is the count of Solutions *pages*, one of which is the platform itself, so it cannot sit under nine; the page also links only eight programs. Worse, it collided with `Nine challenge formats` three lines below in the same card, where nine means something else entirely. No number is needed for this sentence to be true. |
| `.fair-list` item 1 | **`Tracking`** `Steps, workouts, sleep and 65+ activity types, synced or logged.` |
| `.fair-list` item 2 | **`Programs`** `Nine challenge formats. Five an admin can launch alone.` |
| `.fair-list` item 3 | **`Insight`** `Participation, challenge and activity analytics, aggregate only.` |
| `.fair-list` item 4 | **`Rewards`** `Vantage Points, real gift cards, priced for local purchasing power.` |
| `.fair-fine` | `People data arrives by CSV, SFTP or HRIS. Sign-in runs on SAML SSO.` |
| CTA | `<a class="text-link text-link-light" href="/solutions/wellness-platform/">See the platform</a>` |

**Right column:** Mock D, the `Connects to` card. See §4.

---

### S5. Decision helper
`<section class="hub-section route-screen" id="start" aria-labelledby="start-heading">` · Ground: `#fff`

| Element | Copy |
|---|---|
| `.eyebrow` | `Not sure where to start` |
| `h2` (id `start-heading`) | `Route by the goal you were given.` |
| `.lead` | `Four situations we hear most. Each one has a shortest path.` |

**`.route-list`, four `.route-row`s.** Each entire row is an `<a>`.

| # | Quoted situation (`b`) | One-line route (`p`) | `.route-dest` pill | href |
|---|---|---|---|---|
| 1 | `"This is our first wellness program."` | `Run a two-week step race. Steps track themselves, so nobody has to learn anything.` | `Step challenges` | `/solutions/step-challenges/` |
| 2 | `"Ours stalled after the first month."` | `Give people something to log besides steps: themed weeks, any activity, solo or in teams.` | `Multi-activity challenges` | `/solutions/multi-activity-challenges/` |
| 3 | `"Our people are not in one building."` | `Run one challenge across offices and time zones, with each day resetting at local midnight.` | `Remote & hybrid team challenges` | `/solutions/remote-team-wellness/` |
| 4 | `"Leadership wants a number, not a story."` | `Start at the reporting and work backwards to the program that produces it.` | `Workforce health insights` | `/solutions/workforce-health-insights/` |

**Trailing note** (`.route-note`, `.85rem`, `--muted`, `margin-top: 22px`, both page names are inline `.text-link`-style links):
`Need a health baseline before you design anything? Start with the ` **`Health Risk Assessment`** ` (`/solutions/health-risk-assessment/`). ` `Want one flagship event instead of a program? Run a ` **`virtual marathon`** ` (`/solutions/virtual-marathon/`).`

---

### S6. Proof strip
`<section class="hub-section proof-hub" id="proof" aria-labelledby="proof-heading">` · Ground: `#f6f7f4`

| Element | Copy |
|---|---|
| `.eyebrow` | `Proof` |
| `h2` (id `proof-heading`) | `What these programs have produced.` |

No lede. The tiles are the lede.

**`.results-grid`, three `.result-card`s.** Page-local override: `grid-template-columns: repeat(3,1fr)`.

| # | `.stat` | `p` (what it measured) | `.segment` |
|---|---|---|---|
| 1 | `59%` | `engagement rate across plant locations over six months` | `TATA MOTORS · STEP & STRIDE CHALLENGE`<br>`1,248 active participants` |
| 2 | `88%` | `engagement rate over 28 days` | `IBS SOFTWARE · MARCH TO FITNESS`<br>`500+ active participants of 660 invited` |
| 3 | `3X` | `participation increase, 163 to 550 active users` | `WIPRO · THREE 2025 CHALLENGES`<br>`Participants in 30+ countries` |

**`.proof-fine`** (flex row directly under the grid):
- left `small`: `Results from named customer programs. Outcomes vary by workforce and program design.`
- right `.text-link`: `Read customer stories` → `https://www.vantagefit.io/casestudy/`

**`.assure-row`** (new page-local block, sits below `.proof-fine` with a `margin-top: 34px` and a `1px solid var(--line)` top rule):
- `b`: `Employees see their own data. HR sees aggregate trends.`
- Three light pills (`.mark-strip-light`), each with a small check glyph: `Follows HIPAA guidelines` · `SOC 2 Type II` · `Secured regional data hosting`
- Right-aligned `.text-link`: `See security & compliance` → `https://www.vantagefit.io/features/security-and-compliance/`

---

### S7. Closer
`<section class="final" id="demo" aria-labelledby="demo-heading">` · Ground: dark gradient. Structure verbatim from `chrome.html`.

| Element | Copy |
|---|---|
| `h2` (id `demo-heading`) | `Bring us your headcount. We will shape the program.` |
| `p` | `In a 30-minute demo we will pick the format for your workforce, walk the employee app, and show the participation reporting your leadership will see.` |
| `.btn-row` | Primary `Book a demo` → `https://www.vantagefit.io/request-demo/` · Outline `See pricing` → `https://www.vantagefit.io/pricing/` |
| `.final-checks` | `Launch in minutes` · `No wearable required` · `No obligation` |
| `.final-note` | `Turn participation into progress.` |

---

## 4. The product-real UI spec

Universal rules apply to all four mocks: `role="img"` on the outer container with a full `aria-label` that **ends with "Figures shown are illustrative."**, `aria-hidden="true"` on every decorative child, a visible `<span class="mock-tag">Illustrative data</span>` wherever a number appears, and `font-variant-numeric: tabular-nums` on every digit run.

---

### Mock A. Hero `.dash`, the admin Overview
Shipped `.dash` component. Position: absolute inside `.hero-visual`, `top:6px; left:0; width:min(100%,430px)`, rotate `1.1deg`, shadow `0 30px 74px rgba(41,41,76,.18)`.

- `.dash-top`: three 8px grey dots + a 42%-wide 9px `.dash-url` pill.
- `.dash-title`: `small` = `Admin · Overview`, `strong` = `All employees · Last 30 days`. `.mock-tag` on the right.
- `.metric-inline`, three cells, exact shipped KPI labels:
  `ENROLLED USERS` **`2,480`** · `ACTIVE USERS` **`1,712`** · `INCENTIVIZATION` **`$9,240`**
- `.metric-card.metric-main` (mint `#e8f7f1` tint):
  `.metric-lab` = `Participation Rate · last 30 days`, `.metric-value` = **`69%`**, `.metric-delta` = `+7 pts vs previous 30 days`
- `.chart-card`: `.chart-head` = `Avg steps` with `.legend` = `This quarter`. `.chart` box 84px with the CSS `repeating-linear-gradient` gridlines, a `.target-line` labelled `Goal 8,000`, and the polygon/polyline SVG at `viewBox="0 0 300 84" preserveAspectRatio="none"`. Points: polyline `0,68 50,60 100,54 150,45 200,39 250,27 300,19`. `.chart-labels`: `W1 W2 W3 W4`.
- Page-local chart paint: `polyline { fill:none; stroke: var(--mint-dark); stroke-width:2.4; stroke-linecap:round; stroke-linejoin:round; }` and `polygon { fill: rgba(65,216,180,.14); }`
- `aria-label`: *"Admin Overview showing 2,480 enrolled users, 1,712 active users, a 69 percent participation rate and a rising average step trend. Figures shown are illustrative."*

**Why these labels:** all four are the code-verified Overview KPI cards, and `Avg steps` is a real At a Glance metric. Nothing invented.

---

### Mock B. Hero `.phone`, the employee Challenges tab
Shipped `.phone` component. Position: absolute, `right:-16px; bottom:2px; width:194px`, rotate `-3deg`, `z-index:2`, shadow `0 28px 60px rgba(0,0,0,.36)`.

- `.phone-head`: `Vantage Fit` + `.avatar`.
- **Sub-tab row** (page-local `.pseg`, reuse the `[TEAM]` segmented pattern): `Ongoing` (selected) · `Upcoming` · `Past`. These are the real Challenges tab sub-tabs.
- **Three challenge rows** (page-local `.prows` / `.prow`, 26px gradient art tile + two-line label + right meta):
  1. art tile mint gradient, `Spring Steps Race` / `Race · steps`, right meta `Day 12 of 28`. Below it a `.progress` bar at `width:84%` with `.progress-label` `Today` / `8,412 / 10,000`.
  2. art tile coral gradient, `Move, Nourish, Reset` / `Custom · themed weeks`, right meta `Week 2 of 4`
  3. art tile slate gradient, `Everest Run` / `Journey · milestones`, right meta `3 of 7`
- `.phone-cta`: `View leaderboard`
- `.mock-tag`
- `aria-label`: *"Employee app Challenges tab showing three ongoing challenges and today's step progress. Figures shown are illustrative."*

**Why these names:** `Ongoing / Upcoming / Past` are the shipped sub-tabs. `Everest Run` is one of the three built-in Journey templates. `Move, Nourish, Reset` traces to the help doc's own Custom-challenge weekly-theme example. `Race`, `Custom`, `Journey` are shipped format names. Nothing invented.

---

### Mock C. The chain (the page's signature). Build this exactly.

**Markup skeleton**

```html
<div class="chain" role="group" aria-label="How the three workforce health and rewards pages connect: data in, then data out, then action, looping back into challenges.">
  <a class="chain-link reveal" href="/solutions/health-risk-assessment/"> … </a>
  <span class="chain-arm" aria-hidden="true"><svg viewBox="0 0 34 12">…</svg></span>
  <a class="chain-link reveal" href="/solutions/workforce-health-insights/"> … </a>
  <span class="chain-arm" aria-hidden="true"><svg viewBox="0 0 34 12">…</svg></span>
  <a class="chain-link reveal" href="/solutions/wellness-rewards-program/"> … </a>
  <div class="chain-loop">
    <a class="chain-loop-label" href="/solutions/wellness-challenges/">Points send employees back into the next challenge</a>
  </div>
</div>
```

**Grid**

```css
.chain { position: relative; display: grid; grid-template-columns: 1fr 34px 1fr 34px 1fr;
         gap: 0; margin-top: 40px; padding-bottom: 58px; }
```

**`.chain-link`**
`background: var(--paper); border:1px solid var(--line); border-radius:18px; padding:20px 22px 20px; display:flex; flex-direction:column;`
Hover: `translateY(-3px)`, border to `rgba(41,41,76,.22)`, `box-shadow: var(--shadow-soft)`.

Card internal order:
1. `.chain-head`: a **9px node dot** (`border-radius:50%`) then the **stage pill**. This row sits at a fixed offset so the node dots line up across all three cards: give `.chain-head { height: 22px; display:flex; align-items:center; gap:10px; }` and the card `padding-top: 20px`, so every node dot centre is at **31px from the top of the card**.
2. `h3` (`1.08rem`, `letter-spacing:-.02em`, `margin-top:16px`)
3. `p` (`.84rem`, `--muted`, `line-height:1.45`, `margin-top:7px`)
4. `.chain-mini`: the artifact panel. `margin-top:18px; background: var(--canvas); border:1px solid var(--line); border-radius:12px; padding:12px 13px;`
5. `.chain-hand`: `margin-top:auto; padding-top:14px; border-top:1px solid var(--line); font-size:.78rem; font-weight:800; letter-spacing:-.01em;` with a 13px arrow SVG. Card 1 and 2 use a right arrow; card 3 uses a loop arrow (`↺` drawn as SVG).

**Stage pills** (`.chain-stage`, `.58rem/800`, uppercase, `letter-spacing:.1em`, `padding:3px 9px`, `border-radius:999px`). Never rely on hue alone: the word is always present, so the `?gray` grayscale review passes.

| Stage | Text | Background | Text colour | Node dot |
|---|---|---|---|---|
| 1 | `Data in` | `rgba(65,216,180,.14)` | `#128f72` | `--mint` |
| 2 | `Data out` | `rgba(41,41,76,.07)` | `var(--ink)` | `rgba(41,41,76,.45)` |
| 3 | `Action` | `rgba(241,81,98,.10)` | `var(--coral-deep)` | `--coral` |

**`.chain-arm`** (the drawn connection, this is the whole point of the section)
`align-self: start; margin-top: 31px; display:flex; align-items:center; justify-content:center;` so the arm's vertical centre lands exactly on the node-dot centre line, making the rail read as continuous across card gutters.
SVG, `width:34; height:12; viewBox="0 0 34 12"`:
- a 2px horizontal line from `x=0` to `x=25` at `y=6`
- an arrowhead: `polyline points="24,2 30,6 24,10"` , `fill:none`, `stroke-width:2`, `stroke-linecap:round`, `stroke-linejoin:round`
- Arm 1 stroke: `url(#armA)` a left-to-right gradient from `#41d8b4` to `rgba(41,41,76,.42)`
- Arm 2 stroke: `url(#armB)` from `rgba(41,41,76,.42)` to `#F15162`
Define both `<linearGradient>`s once in a zero-size `<svg aria-hidden="true">` at the top of the section, or inline per arm. Either is fine.

**`.chain-loop`** (the return arc, drawn not labelled)
`position:absolute; left:14%; right:14%; bottom:0; height:44px;`
`border:2px dashed rgba(241,81,98,.32); border-top:0; border-radius:0 0 18px 18px;`
An arrowhead SVG absolutely positioned at the **left** end of the arc, pointing **up** (back toward section ①): `left:-7px; top:-1px;` `polyline points="2,8 7,2 12,8"` stroked `rgba(241,81,98,.55)`, 2px.
`.chain-loop-label`: absolutely centred on the bottom edge of the arc, `transform: translate(-50%, 50%)`, `background: var(--paper); border:1px solid rgba(241,81,98,.3); border-radius:999px; padding:6px 15px; font-size:.74rem; font-weight:700; color: var(--coral-deep); white-space:nowrap;` Hover: background `rgba(241,81,98,.06)`.

**Mini-artifact specs**

*Card 1, `What goes in`.* Heading `.62rem/800 uppercase, letter-spacing .1em, --muted`. Three rows, each `grid-template-columns: 1fr auto`, `padding:7px 0`, hairline between:
| Row label (`b`, `.78rem`) | Sub (`span`, `.7rem`, `--muted`) | Right |
|---|---|---|
| `Health profile` | `Height, weight, BMI` | mint check glyph `✓` |
| `Health Risk Assessment` | `Self-reported factors` | mint check glyph `✓` |
| `Lab report upload` | `Biomarkers extracted` | `Premium` micro-chip, `.55rem/800`, `rgba(255,157,87,.16)` bg, `#a05a1e` text |
No numbers in this artifact, so no `.mock-tag` needed. **Do not invent an HRA question count or a time-to-complete. Neither is sourced.**

*Card 2, `Admin · Overview`.* Heading row = `Admin · Overview` on the left, `.mock-tag` on the right. Then a 2x2 grid, `gap:8px`, each cell `background: var(--paper); border:1px solid var(--line); border-radius:9px; padding:8px 9px`:
| Label (`.6rem/700 uppercase, --muted`) | Value (`.95rem/800, --ink, tabular-nums`) |
|---|---|
| `Enrolled Users` | `2,480` |
| `Active Users` | `1,712` |
| `Incentivization` | `$9,240` |
| `Participation Rate` | `69%` |
Fine line under the grid, `.66rem`, `--muted`: `Aggregate only. No individual health data.`

*Card 3, `Vantage Points`.* Heading row = `Vantage Points` left, `.mock-tag` right. Then:
- a balance line: `1,240` at `1.4rem/800` `--ink` tabular-nums, with `pts` at `.7rem` `--muted`
- one action row styled as a small coral pill button: `Redeem points`
- a chip row, four `.62rem` pills with `1px solid var(--line)`: `Shopping` `Food & dining` `Travel` `+ more`
- fine line, `.66rem`, `--muted`: `Gift cards in 190+ countries, priced for local purchasing power.`

**Do not render retailer logos or a brand wall.** No source enumerates catalogue brands. The sourced axis is category.

**Responsive**
- `<= 1100px`: `.chain { grid-template-columns: 1fr; gap: 0; padding-bottom: 0; }`. Arms become vertical: `.chain-arm { margin: 10px auto; transform: rotate(90deg); }`. `.chain-loop` switches from an absolute arc to a static full-width row: `position:static; height:auto; border:0; border-top:2px dashed rgba(241,81,98,.32); margin-top:18px; padding-top:18px; display:flex; justify-content:center;` and `.chain-loop-label { position:static; transform:none; }`.
- `<= 640px`: `.chain-mini` keeps its 2x2 KPI grid (it fits at 320px at `.6rem` labels). Nothing hides.

**Reduced motion:** `.chain-link` uses `.reveal`, which already has its kill switch. The arms and loop are static, no animation. Do not animate the chain.

**Forced colors:** the arms and loop are strokes, not gradient-clipped text, so they survive. The `.result-card .stat` gradient text in S6 still needs the standard `@media (forced-colors: active)` fallback.

---

### Mock D. The `Connects to` card (right column of the `.fairband`)
White panel on the dark band. Reuse the `.audit-board` shell: `background:#fff; border-radius:18px; padding:20px 22px; box-shadow: 0 26px 60px rgba(0,0,0,.32); width:100%; max-width:380px;`

- Head: `b` = `Connects to`
- Chip grid, `flex-wrap`, `gap:7px`, each chip `.72rem/700`, `padding:6px 11px`, `border-radius:999px`, `1px solid var(--line)`, `--ink` text:
  `Apple Health` · `Google Fit` · `Fitbit` · `Garmin` · `Apple Watch` · `SAML SSO` · `HRIS sync` · `CSV & SFTP`
- Hairline, then two rows (`grid-template-columns: 1fr auto`, `.78rem`, `padding:8px 0`):
  | Left | Right |
  |---|---|
  | `Languages` | `13` |
  | `Data regions` | `India, US, EU, UAE` |
- Caption, `.66rem`, `--muted`: `HRIS and SSO are set up with our integration team.`
- No `.mock-tag`: every figure here is a sourced product fact, not illustrative. That distinction is deliberate and correct.
- `aria-label` on the container: *"Card listing the device, sign-in and people-data integrations Vantage Fit connects to, plus 13 languages and four data regions."* (No "illustrative" clause, because nothing here is illustrative.)

**Hard constraints on this card:** Apple Health and Google Fit always appear together. Never label Android step sync "Health Connect steps", so Health Connect is omitted entirely. Do not list Withings, Polar, Oura or Whoop. Do not present HRIS as a self-serve connector marketplace, which is why the caption is there. No Slack, no Microsoft Teams.

---

## 5. Claims table

Every factual statement rendered on the page. Anything not in this table does not go on the page.

| # | Claim as it appears | Section | Status | Source |
|---|---|---|---|---|
| 1 | `Steps sync from Apple Health and Google Fit. No wearable required.` | Hero note | SHIPPED | `vantagefit-astro/content/en/help/admin/settings/admin-what-is-vantage-fit.md` |
| 2 | `automatic step tracking, audience-rule enrollment, and one participation number for leadership` | Hero lede | SHIPPED | as above; `vfit-os/specs/product/02-challenges-gamification/challenges.md:42`; `vfit-os/specs/product/09-admin-platform/admin-dashboard.md:55` |
| 3 | `Trusted by 100+ organizations worldwide` | Logo band | APPROVED-CLAIM | `vc-os/vfit-os/.claude/rules/data-accuracy.md:252-261` |
| 4 | Logo words: Tata Motors, Wipro, Teva, Godrej, Texas Instruments, Heidrick & Struggles, Brazosport ISD | Logo band | APPROVED-CLAIM (all seven on the approved client list) | `data-accuracy.md:22` |
| 5 | Five section ① card titles and description lines, verbatim | S2 | SIGNED-OFF IA | `menu/vantage-fit-solutions-menu-preview.html:344-349` |
| 6 | `Browsing ready-to-run designs across physical, mental, nutrition, sleep and team.` | S2 card 1 | SHIPPED (MARKETING-ASSET) | `vantagefit-astro/src/data/wellness-challenges.ts`; live library renders 5 categories, `challenges.md` §2 |
| 7 | `Employees are enrolled by audience rules, so there is no sign-up step to chase.` | S2 note | SHIPPED | `vfit-os/specs/product/02-challenges-gamification/challenges.md:42`; `HELP/employee/challenges/how-do-i-join-a-challenge.md:17-38` |
| 8 | Three section ② card titles and description lines, verbatim, plus the `Data in` / `Data out` / `Action` badges | S3 | SIGNED-OFF IA | `menu/vantage-fit-solutions-menu-preview.html:354-357, :469-474` |
| 9 | The chain sequence itself: HRA feeds insights, insights prove impact, rewards drive behavior | S3 | SIGNED-OFF IA + SHIPPED mechanics | `menu/…preview.html:483`; `health-hra.md` §7 items 5-12 |
| 10 | `Health profile / Height, weight, BMI` | S3 card 1 | SHIPPED | `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` |
| 11 | `Health Risk Assessment / Self-reported factors` | S3 card 1 | SHIPPED | `vantagefit-astro/content/en/help/…/what-is-hra.md` |
| 12 | `Lab report upload / Biomarkers extracted` + `Premium` chip | S3 card 1 | SHIPPED-GATED (premium, whitelist-gated) | `vfit-os/specs/product/03-health-wellness/workforce-health.md` |
| 13 | `Enrolled Users · Active Users · Incentivization · Participation Rate` | S3 card 2 and Mock A | SHIPPED (exact card set) | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md:55`; ruling `ia-claims-proof.md` §G3 |
| 14 | Values `2,480 / 1,712 / $9,240 / 69% / +7 pts / 8,412 / 10,000 / Goal 8,000 / 1,240 pts / Day 12 of 28 / Week 2 of 4 / 3 of 7` | Mocks A, B, C | **ILLUSTRATIVE.** Visibly tagged `Illustrative data` and named in every `aria-label`. | design-system rule §5 universal rule 3; `content-standards.md:14-25` item 5 |
| 15 | `Aggregate only. No individual health data.` and the chain caption | S3 | SHIPPED | `HELP/admin/settings/admin-data-privacy-security.md`; `insights-reports.md` §3.1 |
| 16 | `Vantage Points`, `Redeem points`, `Shopping / Food & dining / Travel` categories, real gift cards | S3 card 3 | SHIPPED | `rewards.md` §10; `vfit-os/specs/product/08-rewards-marketplace/rewards-wallet.md`. Category axis sourced as 20+ categories; brand names deliberately omitted per `rewards.md` E2 |
| 17 | `Gift cards in 190+ countries, priced for local purchasing power.` | S3 card 3 | SHIPPED, **rewards capability only, never a customer footprint** | `vfit-os/specs/product/08-rewards-marketplace/soli-currency.md:105` |
| 18 | `Steps, workouts, sleep and 65+ activity types, synced or logged.` | S4 | SHIPPED | `HELP/employee/health-tracking/what-activities-can-i-track.md:3,:13`; ruling `platform.md` A3 |
| 19 | `Nine challenge formats. Five an admin can launch alone.` | S4 | SHIPPED | `vfit-os/specs/product/02-challenges-gamification/challenges.md:230`; `challenges.md` §1.1 |
| 20 | `Participation, challenge and activity analytics, aggregate only.` | S4 | SHIPPED | `insights-reports.md` §1.1, §3.1 |
| 21 | `People data arrives by CSV, SFTP or HRIS. Sign-in runs on SAML SSO.` | S4 | SHIPPED (HRIS is integration-team, hence the Mock D caption) | `HELP/admin/settings/admin-how-do-i-add-employees.md`; `HELP/admin/settings/admin-how-do-i-enable-sso.md` |
| 22 | Integration chips: Apple Health, Google Fit, Fitbit, Garmin, Apple Watch, SAML SSO, HRIS sync, CSV & SFTP | Mock D | SHIPPED | `vfit-os/specs/product/10-integrations/device-integrations.md`; `platform.md` §2.3 |
| 23 | `Languages 13` | Mock D | SHIPPED | `HELP/admin/settings/admin-how-do-i-change-language-settings.md` (article's own headline count) |
| 24 | `Data regions India, US, EU, UAE` | Mock D | SHIPPED | `vfit-os/specs/product/00-platform/auth-login-signup.md`; `HELP/admin/settings/admin-data-privacy-security.md` |
| 25 | `HRIS and SSO are set up with our integration team.` | Mock D | SHIPPED, and a required honesty qualifier | `platform.md` §2.3 do-not-claim 14 |
| 26 | Route 1: `Run a two-week step race. Steps track themselves…` | S5 | SHIPPED | `HELP/admin/challenges/admin-how-do-i-create-race-challenge.md:13,:24-27,:59`; step auto-sync per claim 1 |
| 27 | Route 2: `themed weeks, any activity, solo or in teams` | S5 | SHIPPED | `HELP/admin/challenges/admin-how-do-i-create-custom-challenge.md`; 27 task types per `challenges.md` §3 |
| 28 | Route 3: `one challenge across offices and time zones, with each day resetting at local midnight` | S5 | SHIPPED | `HELP/admin/challenges/admin-can-i-run-challenges-across-time-zones.md:17-29` |
| 29 | Route 4: `Start at the reporting and work backwards` | S5 | SHIPPED | `insights-reports.md` §1.1 six named reports |
| 30 | `59% engagement rate across plant locations over six months` / Tata Motors · Step & Stride Challenge / 1,248 active participants | S6 | APPROVED-CLAIM | `data-accuracy.md:34-48`; `content/en/casestudy/tata-motors-case-study.md` |
| 31 | `88% engagement rate over 28 days` / IBS Software · March to Fitness / 500+ active participants of 660 invited | S6 | APPROVED-CLAIM | `data-accuracy.md:72-85`; `content/en/casestudy/ibs-software-case-study.md` |
| 32 | `3X participation increase, 163 to 550 active users` / Wipro · three 2025 challenges / participants in 30+ countries | S6 | APPROVED-CLAIM | `data-accuracy.md:89-131`; `content/en/casestudy/wipro-global-wellbeing.md` |
| 33 | `Results from named customer programs. Outcomes vary by workforce and program design.` | S6 | House disclaimer | `design-system.md` §10 anti-pattern 5 |
| 34 | `Employees see their own data. HR sees aggregate trends.` | S6 | SHIPPED | `HELP/admin/settings/admin-data-privacy-security.md` |
| 35 | `Follows HIPAA guidelines` · `SOC 2 Type II` · `Secured regional data hosting` | S6 | APPROVED phrasing. **SOC 2 Type II is thinly sourced; flag to the claims reviewer before publishing.** | `vfit-os/sources/VFit-Marketing-Content-Compacted.md` §2.15; ruling `design-system.md` F1; strings verbatim from `claude-fable/vantage-fit-multi-activity-challenge-v1.html:1172-1190` |
| 36 | `Book a demo` / `See pricing` | Hero, S7 | House CTA rule | `ia-claims-proof.md` §5.5 |

### Claims considered and cut, not softened

| Cut | Why |
|---|---|
| HRA question count, time to complete | Genuinely unsourced. The Mock C card 1 artifact is designed so it does not need either number. |
| HRA completion rate (~20% of employees) | Real but off-message and unhelpful on a chooser. Belongs in the HRA page's honest-uptake section if anywhere. |
| Wellness Score, Wellness Leagues, Org Wellness Score, Health Insights | All annual-client or premium gated. Cannot carry a gate qualifier per card on a hub. |
| Insights Hub | Ruled unclaimable. Not drawn, not named, not linked. |
| Any completion rate | None exists in the approved register. |
| "Creating a challenge takes 5-10 minutes" | True and sourced, but it is the challenge pages' proof point. Using it here would make the hub explain rather than route. The closer's `Launch in minutes` check carries the same reassurance without a figure. |
| $1/user/month | UNVERIFIED against a live three-tier pricing page. |
| Slack, Microsoft Teams | Zero spec coverage, banned. |
| ISO 27001, ISO 27701, GDPR, "HIPAA compliant", "Start Free Trial", "50+ countries", "Fit points" | All banned. |
| Certification raster image | Banned from the plaque and from this page. |
| Any figure from `vc-dashboard-design/vc-data.js` (Acme, Priya Sharma, 68% participation) | Seeded fiction. The illustrative values in §5 row 14 are original to this mock and are not lifted from that file. |

---

## 6. Meta

```html
<title>Employee Wellness Solutions for HR Teams | Vantage Fit</title>
<meta name="description" content="Choose a corporate wellness program by what you want to run or what you need to measure: challenges, health assessment, insights and rewards. Book a demo.">
<meta name="robots" content="noindex, nofollow">
```

- **Title:** 53 characters. No em-dash (the `seo-conventions.md` template's own em-dash is overridden by the house ban).
- **Description:** 152 characters. Capability phrase + the two-question frame + CTA, matching the observed pattern in `ia-claims-proof.md` §6.1.
- **Primary keyword:** corporate wellness program software / employee wellness solutions. Volume 200/mo, orientation intent (`ia-claims-proof.md` §6.2).
- **`noindex, nofollow` is required.** This is an unshipped mock on a preview host.
- **Schema:** none. The consolidated quality bar adds `FAQPage`, `SoftwareApplication` and `BreadcrumbList`, but this page has no FAQ, and `schema-data.js` is documented as drifting from visible copy on every page checked (`prior-audits.md` P14). If a `BreadcrumbList` is added later it must list only `Home > Solutions` and nothing beneath it.

---

## 7. Menu fit

**Where this page sits.** `/solutions/` is the index behind the **Solutions** top-level trigger. It is not a row inside the mega-menu, and it is **not** listed in the footer Solutions column (`ia-claims-proof.md` §1.3 confirms the footer column starts at Wellness platform). It is reached by clicking the trigger rather than hovering it.

**Nav self-location, required page-local state:**
- `.nav-trigger.is-current` on the **Solutions** trigger: `background: var(--soft); color: var(--ink); box-shadow: inset 0 -2px 0 var(--coral); border-radius: 9px 9px 0 0;`
- **No** `.mega-link.is-page` inside the Solutions panel, because no row in the panel is this page. This is the only page in the set where the trigger is lit and no row is. Leave it that way rather than inventing a "Solutions overview" row.
- In the footer Solutions column, no link gets `aria-current="page"` either, for the same reason.

**Menu label and description line.** The hub has no menu row, so it has no description line. If one is ever needed (for a mobile accordion header, for example), use `All solutions` / `Pick by what you want to run, or what you want to measure`. Flag this to the IA owner as a new string rather than shipping it silently.

**How this page plays in the data in → data out → action chain.** The hub is the only page in the set that renders the whole chain at once. Its job is to make the chain legible *before* the reader commits to any one of the three pages, so that when they land on `/solutions/health-risk-assessment/` they already know it is stage one of three and not a standalone product. The stage pills on the three cards use the exact badge strings from the mega-menu (`Data in`, `Data out`, `Action`), so the hub and the nav teach the same model. Card footers carry the sign-off verbs verbatim: **Feeds insights → Proves impact → Drives behavior**, with the loop-back arm closing to section ①.

**Mega-menu markup for this page.** Paste the Solutions and Features panels from `chrome.html` unchanged, except the two column headers, which use the colon form:
- Column 1: `Wellness challenges: what you want to run`
- Column 2: `Workforce health & rewards: measure and motivate`
Remove the preview's "open Solutions by default on load" line. Keep `chrome.html`'s Escape / `esc-closed` / `aria-expanded` handling on all three paths.

---

## 8. Cross-links

**Outbound, and the section each link lives in.** Every one of the nine Solutions pages is linked at least once. Four are linked twice, from the grid and again from the decision helper, which is intentional: a hub should give a high-intent page two chances to be clicked.

| Destination | Linked from |
|---|---|
| `/solutions/wellness-challenges/` | S2 card 1 · S3 chain loop-back label |
| `/solutions/step-challenges/` | S2 card 2 · S5 route 1 |
| `/solutions/multi-activity-challenges/` | S2 card 3 · S5 route 2 |
| `/solutions/remote-team-wellness/` | S2 card 4 · S5 route 3 |
| `/solutions/virtual-marathon/` | S2 card 5 · S5 trailing note |
| `/solutions/health-risk-assessment/` | S3 chain link 1 · S5 trailing note |
| `/solutions/workforce-health-insights/` | S3 chain link 2 · S5 route 4 |
| `/solutions/wellness-rewards-program/` | S3 chain link 3 |
| `/solutions/wellness-platform/` | S4 `See the platform` |
| `https://www.vantagefit.io/casestudy/` | S6 `.proof-fine` |
| `https://www.vantagefit.io/features/security-and-compliance/` | S6 `.assure-row` |
| `https://www.vantagefit.io/request-demo/` | Hero, S7, nav CTA |
| `https://www.vantagefit.io/pricing/` | Hero, S7, nav |

**Inbound, expected.** The Solutions mega-menu trigger (click). Organic search on the hub keyword. The five challenge pages and the three health-and-rewards pages should each carry a "see all solutions" style link back here, but that is those pages' business, not this one's.

**Links deliberately not made.**
- No link to `/wellness-challenges/` (the live root-level library). Section ① routes to `/solutions/wellness-challenges/` per the signed-off menu. The relationship between the two is an open IA question, see §9.
- No link to `/employee-wellness-software/`, currently the worst offender for fabricated engagement ranges.
- No link to `/slack-integration/`. True orphan, zero spec coverage, banned.
- No link to `/health-fitness-analytics/` or `/mental-health-and-wellbeing-challenges/`. Both retired from Solutions.
- No parent-suite links (Vantage Recognition, Vantage Pulse, Vantage Perks). The ecosystem paragraph is the Wellness platform page's asset. Duplicating it here would pull the reader out of the Solutions funnel at the exact moment they are choosing.

---

## 9. Assumptions and gaps

### Flagged for a human, not blocking

1. **Slug collision.** The signed-off menu specifies `/solutions/wellness-challenges/`, while a shipped consolidated page targets `/solutions/wellness-challenge` (singular). Section ① card 1 follows the menu. **A human must resolve which slug ships.**
2. **Library relationship.** It is unresolved whether `/solutions/wellness-challenges/` replaces the live `vantagefit.io/wellness-challenges/` (21 challenges, 21 child pages) or sits above it as the Solutions-level entry. This page assumes **above**, and does not link the live library directly. If the decision flips to "replaces", nothing on this page changes except that the live URL should 301.
3. **URL prefix.** `seo-conventions.md:69,83` mandates root-level solution URLs with no `/solutions/` prefix and says not to propose URL changes. The signed-off menu and the shipping brief both use the prefix. This page uses the prefix. Unresolved at the SEO level.
4. **SOC 2 Type II sourcing.** Approved in `VFit-Marketing-Content-Compacted.md` §2.15, but an internal audit records it as "not documented in the KB" beyond that line. It appears once on this page, in the `.assure-row`. **Flag to the claims reviewer before publishing.**
5. **Hub menu label.** The hub has no signed-off menu label or description line because it has no menu row. If one is needed, `All solutions` is proposed above and needs IA sign-off.
6. **`/casestudy/` index URL.** Used as the `.proof-fine` destination. Confirm the canonical customer-stories URL after the Resources mega-menu merge (Client Success Stories + Case Studies + Testimonials consolidate into "Customer stories").

### Assumptions I made, stated so they can be overturned

1. **The hero is not full-fold.** I override `--hero-h` on this page alone. If a reviewer wants system consistency over hub conversion, revert `.hub-hero { min-height: auto; }` and accept that section ① drops below the fold.
2. **No `.trust-screen` band.** Security is answered by three approved strings and one link inside the proof strip. If the enterprise reviewer wants the full band back, it goes between S6 and S7 and the `.assure-row` is deleted so the strings are not duplicated.
3. **No `.related-screen`.** Redundant on a hub. If house consistency wins, it would have to point at Features or Resources, not at Solutions, or it duplicates the page.
4. **Four routes, not five.** The decision helper covers step challenges, multi-activity, remote/hybrid and insights. HRA and virtual marathon are caught in the trailing note, and rewards is caught by the chain. If a fifth route is wanted, use `"We are still comparing vendors."` → `Read the platform overview first.` → Wellness platform.
5. **Illustrative figures are original.** `2,480 / 1,712 / $9,240 / 69% / +7 pts / 8,412 / 1,240 pts` are invented for this mock, tagged `Illustrative data`, and are deliberately **not** the `vc-data.js` seeded numbers (Acme, 68% participation) which are banned.
6. **The `Premium` chip on the lab-report row.** Lab report analytics is premium and whitelist-gated. Marking it inside the artifact is more honest than omitting the row, and cheaper than a paragraph. If legal prefers no gating language on a hub, delete the row entirely rather than dropping the chip.
7. **Section ② card descriptions use the nav line, not the gallery line.** The gallery alternate for insights ("Participation + challenge + activity in one page") is shorter and would fit better, but the hub must echo what the reader just saw in the menu.

### Build checklist for the mock author

- [ ] `<link rel="stylesheet" href="../styles/enterprise.css">` and nothing else external. Noto Sans 400;500;600;700;800 from Google Fonts.
- [ ] `noindex, nofollow`. `theme-color #18262b`.
- [ ] Skip link as the first child of `<body>`.
- [ ] Copy in page-locally: `.hub-section`, `.hub-head`, `.reveal`, `.skip-link`, contrast lifts, focus visibility, the `.btn-primary` gradient contrast fix (`--coral-dark` to `--coral-deep`), forced-colors fallback, `.mock-tag`, `.format-grid` / `.format-card` / `.format-glyph` / `.best-for`, `.fairband` / `.fair-list` / `.fair-item` / `.fair-fine`, `.results-grid` / `.result-card` / `.proof-fine`. Then the new blocks: `.hub-hero`, `.chain*`, `.route*`, `.assure-row`, `.mark-strip-light`.
- [ ] Five `.format-glyph` SVGs at 74x44, drawn from `rgba(41,41,76,.14/.16/.24/.34)` greys plus one `#41d8b4` and one `#F15162` accent. Each diagrams its mechanic: (1) a stacked card deck for the library, (2) a rising step bar row, (3) four themed week blocks, (4) three separated location nodes joined by a dotted line, (5) a distance arc with a finish marker.
- [ ] Band order and grounds: hero gradient → `--canvas` → `#fff` → `--canvas` (dark `.fairband` inset) → `#fff` → `#f6f7f4` → dark `.final`. Never two identical adjacent. Exactly two dark moments, separated by two light sections.
- [ ] Every section has an `id` and `aria-labelledby`. Exactly one `h1`.
- [ ] Sub-items inside lists are `<b>`, not `<h3>`. No h3 inflation.
- [ ] Every mock: `role="img"`, full `aria-label` ending "Figures shown are illustrative." (except Mock D, which has no illustrative figures), `aria-hidden="true"` on decorative children, visible `.mock-tag` wherever a number appears, `tabular-nums` on digits.
- [ ] Scripts, in order: mobile nav toggle, mega-menu (hover, focus, Escape with `esc-closed` and focus return, mobile accordion), nav `.lit` scroll toggle, `.reveal` IntersectionObserver with the reduced-motion branch, grayscale `?gray` hook. **Omit the segmented-control handler and the video modal.** This page has neither.
- [ ] Grayscale check: open with `?gray` and confirm the three chain stages are still distinguishable. They are, because each pill carries its word.
- [ ] Word count of body copy under 700. If over, cut supporting prose, never a heading or a card description.
