# Page 5 brief: Wellness platform

**URL:** `/solutions/wellness-platform/`
**Mock file:** `claude-fable/vantage-fit-wellness-platform-v1.html`
**Archetype:** Platform / product-definition page
**Primary keyword:** employee wellness platform (850/mo, the biggest term in the six-page set)
**Placement:** Featured on the Solutions hub, first row of the footer Solutions column, and the `.mega-foot` line inside the Solutions mega-menu. **Not a mega-menu row.**
**Brief version:** 1.0, 2026-08-11

---

## 0. The one-line job of this page

Define what Vantage Fit **is**, as a system, in language a buyer can repeat to their CFO, and answer the one objection that kills a platform deal: *is this a real platform, or an app with a dashboard bolted on?*

The failure mode is a second homepage. The three guards written into this brief:

1. **No feature list.** Capability detail is routed to Features and to the five sibling Solutions pages, never explained inline.
2. **One diagram carries the argument.** Everything else hangs off the system map.
3. **The routing section replaces the usual related-programs row.** Routing is this page's job, so it gets a real section instead of a three-card afterthought.

---

## 1. Research takeaways that decided the structure

Each takeaway names the source path and the status. Statuses follow the dossier legend: SHIPPED / SHIPPED-GATED / ROADMAP / DESIGN-INTENT / UNVERIFIED.

### 1.1 The product genuinely is a loop, not a stack. That is the page.

The module map in `platform.md` §1.2 is not marketing structure, it is data flow: capture feeds programs, programs produce standing, standing produces points, all of it lands in the admin console, and the console's output goes back out as the next challenge audience and the next nudge. Two cited facts close the loop and make the diagram honest rather than decorative:

- **Insight to targeting.** Target Audience supports Country, City, Department, Gender, Age Range, Language and **Health Risk Code**, AND logic, with automatic enrollment. `[vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md]` SHIPPED
- **Insight to nudge.** The Overview's Recommended Actions panel surfaces rows like *"View Inactive Employees (92 users inactive for 30+ days)"* then *"Nudge Inactive Users"*, which pre-fills a custom email to that cohort. `[vfit-os/specs/product/09-admin-platform/admin-dashboard.md]` SHIPPED

**Structural consequence:** the system map is section 2, it is one inline SVG, and every later section is a zoom into one of its parts.

### 1.2 Configurability is the architecture, and it is under-told

Navigation itself is per-company. The Programs tab appears only if Library, Training Programs or Marketplace is enabled; the Community tab only if Social Feed, Events or Chat is enabled. `[vfit-os/specs/product/00-platform/navigation-ia.md]` SHIPPED
Full Mode vs Lite Mode is a company-wide packaging switch set by the account manager, and Lite Mode ships a genuinely different product. `[vantagefit-astro/content/en/help/admin/settings/admin-what-is-lite-mode.md]` SHIPPED

**Structural consequence:** Configuration sits in the **centre of the system map**, not as a footnote. A competitor that ships one fixed app cannot draw this diagram.

### 1.3 Three surfaces, with genuinely different capabilities. Being honest about this is the credibility play.

- **Employee mobile app (iOS and Android) is the full product.** Five-position bottom bar: Home, Challenges, Plus (+), Programs, Community. `[vfit-os/specs/product/00-platform/navigation-ia.md]` SHIPPED
- **Admin console is web only**, lives inside the Vantage Circle admin dashboard at `dashboard.vantagecircle.com`, requires the **HR Admin** role, and *"there's no admin functionality in the iOS app, Android app, or vc-fit web app."* `[vfit-os/specs/product/09-admin-platform/admin-dashboard.md]`, `[vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-sign-in.md]` SHIPPED
- **Employee web app is partial.** It does challenges, leaderboards, content and light logging. It does **not** do step tracking, device connection, GPS, wallet, profile or notifications. `[vantagefit-astro/content/en/help/employee/getting-started/using-vantage-fit-on-web.md]` SHIPPED

**Conflict followed:** the help doc says the web app has three tabs, the code-verified spec says four are now standard. `platform.md` §3.2 rules UNVERIFIED. **This page does not render a web tab bar and does not commit to a tab count.** It states the capability line only.

**Structural consequence:** the surfaces triptych is section 3, and the third panel is the **integration layer**, not the web app. The web app gets one honest trailing sentence.

### 1.4 The privacy architecture is a product mechanism, not a policy promise

When an admin targets a health-risk cohort, the system returns a **count only** plus the literal string *"The list of users is not displayed to protect individual privacy."* `[vfit-os/specs/product/03-health-wellness/workforce-health.md]` SHIPPED
Leadership Insights sends **no PII** to the ML service, only aggregated signal buckets. `[vfit-os/specs/product/09-admin-platform/admin-dashboard.md]` SHIPPED
The canonical admin CAN / CANNOT table is in `[vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md]` SHIPPED

**Structural consequence:** the page gets one `.fairband` dark inset whose proof asset is a **drawn audience-selector panel** carrying the real disclaimer string. That is the strongest single artefact available to this page and it directly answers "is the data model real".

### 1.5 Rollout is short, and the honest version of it sells

- Lite Mode plus admin CSV upload: **1 to 2 days** to live. `[vfit-os/specs/product/00-platform/auth-login-signup.md]` SHIPPED
- SSO: *"Once we have your IdP metadata, the Vantage Fit team usually takes around two weeks."* Any SAML 2.0 IdP; named: Microsoft Entra ID (formerly Azure Active Directory), Okta, OneLogin, Ping Identity. Configured by the Vantage Fit integration team, not from the console. **Provisioning is separate from SSO.** `[vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-enable-sso.md]` SHIPPED
- Four regional instances: India, US, EU, UAE. Chosen at onboarding, data stays in region. `[vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md]` SHIPPED
- One challenge can span countries. Start, daily reset and end all localize to each participant's local midnight. `[vantagefit-astro/content/en/help/admin/challenges/admin-can-i-run-challenges-across-time-zones.md]` SHIPPED
- A licence counts from an employee's **first login**, not from upload. `[vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-add-employees.md]` SHIPPED

**Structural consequence:** section 5 is a three-column **spec table**, not prose. It is the section an IT reviewer screenshots and pastes into a procurement thread. No sibling page in the set has one.

### 1.6 Sources that conflicted, and which one this page follows

| Point | Conflict | Ruling used here | Why |
|---|---|---|---|
| Wellness Score range | `leagues-wellness-score.md` says 0 to ~108; help doc and admin spec say 0-100 | **0 to 100.** In practice this page prints no range at all. | Settled ruling, `ia-claims-proof.md` G3 |
| Activity type count | 65 vs 47+ | **"65+ activity types"** | Settled ruling, `platform.md` A3, help-doc sourced |
| Insights Hub | Named as admin page 5 in the code-verified spec | **Not claimed, not drawn, not linked** | Settled ruling, `platform.md` A4. Nav commented out, all five sub-pages blank iframes |
| Languages | Help doc headline "13 languages"; the same table lists 14 locale rows; legacy page says "14+"; specs say "13+" | **"13 languages"**, help doc wins on precedence. Flagged to the claims reviewer, with a `VERIFY` comment in the HTML | `platform.md` §4.5 resolves it; `ia-claims-proof.md` §8.25 counsels printing no number. Precedence rule breaks the tie toward the help doc |
| Self-registration availability | Help doc says account-manager enabled; spec says on by default | **Omitted entirely from the page** | UNVERIFIED, `platform.md` §4.1 |
| Web app tab count | 3-tab help doc vs 4-tab spec | **No tab count printed** | UNVERIFIED, `platform.md` §3.2 |
| Employee account deletion | Help doc presents it as available; spec says per-company config, few companies | Page states only the unambiguous half: **an admin cannot delete an employee's account on their behalf** | Avoids a SHIPPED-GATED overclaim |
| SOC 2 Type II | Approved in the register; an internal audit says it is thinly documented | **Used**, and flagged to the claims reviewer in §9 | `platform.md` §5.1 |

### 1.7 What the research told me to leave out

`190+ countries` (reads as a footprint claim however it is framed, and `rewards.md` warns against both catalog and footprint readings) · app-store ratings and awards (UNVERIFIED for freshness) · the 19-admin-page count (would drag Insights Hub into view) · challenge-format counts (belongs to the challenge pages) · Slack and Microsoft Teams (zero spec coverage, banned) · ISO 27001, ISO 27701, GDPR (no cleared source) · any step-cap number · Training Plans, multi-wallet, manual step entry, monetary challenge rewards (all SHIPPED-GATED to single-digit or low-double-digit company counts) · the certification raster on the trust plaque (banned; typeset `.mark-strip` only).

---

## 2. Strategy

### 2.1 The buyer

Primary reader is the **HR buyer**, but this page is the one page in the set where the **IT / benefits admin and procurement** ride along and can veto. `[vfit-os/.claude/rules/hr-buyer-lens.md]`

| Persona | What they need from this page |
|---|---|
| HR Director (champion) | A sentence that defines the product and survives being repeated in a meeting they are not in |
| CHRO (decision maker) | Proof that the reporting layer is real and the participation claim is measured |
| CFO (financial buyer) | One vendor, not four. Licences counted from first login. Pricing route |
| IT / benefits admin (technical influencer) | The exact list of what IT has to do, plus SSO, provisioning, data region, and what the admin can see |
| Employee (end user) | Appears only through the app surface and the approved engagement figures |

### 2.2 The one thing this page must land

**Vantage Fit is one system with two surfaces and a configuration layer, and the reporting output feeds back into the program.** Everything else on the page is evidence for that sentence.

### 2.3 Why this section order

1. **Definition hero.** The search intent is "what is this and is it the category I want". The H1 is a definition, not a benefit. The hero visual is `.dash` **plus** `.phone`, deliberately showing two surfaces at once, so the definition is visible before it is read.
2. **System map.** The objection is answered second, not last, because a buyer who bounces at the fold never reaches a trust band. The loop closure (insight to targeting to nudge) is the specific thing an "app with a dashboard" cannot draw.
3. **Surfaces triptych.** Having asserted a system, show the same program from three seats. This is where the honest limits live (no admin on mobile, partial web app, one primary device), and the honesty is the proof.
4. **Participation, once.** The north star is stated in one section with four mechanics and three named customer numbers, then dropped. Stating it once and moving on is the discipline that keeps this from becoming a homepage.
5. **Rollout and IT.** Procurement's section. A spec table, not prose.
6. **Privacy architecture.** The dark inset. Product mechanism, not policy promise.
7. **Where to go deeper.** The routing grid. This is the anti-homepage device: nine Solutions and Features destinations with one-line reasons and no explanation.
8. **Trust band.** Infrastructure and process only, deliberately not repeating section 6's privacy argument.
9. **FAQ.** Five questions, four of them IT and procurement.
10. **Closer.**

### 2.4 What I deliberately left out, and why

| Left out | Why |
|---|---|
| The standard 3-card `.related-screen` | Section 7 already routes to nine pages with better reasons. A three-card outro after a twelve-link grid is padding. **This is a deliberate deviation from the house pattern; noted in §4.7.** |
| A full customer-result section | The approved proof for this page is three engagement figures. They belong attached to the participation claim they support, not floated in their own band. Folded into section 4 as a compact three-tile strip. |
| A formats explorer | Owned by `/solutions/step-challenges/` and `/solutions/wellness-challenges/`. Rebuilding it here is exactly the homepage failure. |
| A leaderboard integrity band | Owned by the challenge pages. This page's fairness beat is privacy, not anti-cheat. Anti-cheat gets one clause inside the integration surface. |
| A pricing table | Pricing is UNVERIFIED across sources. Route to `/pricing/` only. |
| A quote band with video | Two dark moments plus a fairband is already the maximum. The approved quotes for platform-level claims (Momentum Investments, Teva) both contain the banned word "seamless" in verbatim form, so quoting them would import a banned word into body copy. Skipped rather than paraphrased. |
| Competitor comparison | Belongs on `/compare/`. |

---

## 3. Section-by-section copy deck

Every string below is final copy. The builder writes zero new copy.
House rules in force: **no em-dashes**, sentence case headings, terminal periods on H1 and every H2, Oxford commas, US English, numerals for measurable quantities, verb-led CTAs.

---

### S1. Hero

`<header class="hero platform-hero" id="hero" aria-labelledby="hero-heading">`

| Element | Copy |
|---|---|
| `.eyebrow` | `Employee wellness platform` |
| `h1#hero-heading` | `An employee wellness platform: one app for employees, <em>one console for HR</em>.` |
| `.lead` | `Activity syncs from phones and wearables. Challenges run against it. Points turn into gift cards. HR gets participation and health trends back, in aggregate.` |
| `.btn-row` primary | `Book a demo` → `https://www.vantagefit.io/request-demo/` |
| `.btn-row` secondary (`.btn-outline`) | `See the system map` → `#system` |
| `.hero-note` (mint dot) | `No public signup. Employees are added by your HR team and sign in with single sign-on or their work email.` |

**Logo band** (last child of `<header class="hero">`, verbatim from `chrome.html`):

`Trusted by 100+ organizations worldwide` · TATA MOTORS · WIPRO · TEVA · GODREJ · TEXAS INSTRUMENTS · HEIDRICK & STRUGGLES · BRAZOSPORT ISD

Hero visual: `.dash` + `.phone`. Full spec in §4.1 and §4.2.

---

### S2. The system map (page-defining section)

`<section class="hub-section system-screen" id="system" aria-labelledby="system-heading">` · ground `var(--canvas)`

| Element | Copy |
|---|---|
| `.eyebrow` | `The system` |
| `h2#system-heading` | `Six modules, one loop.` |
| `.lead` | `Activity feeds programs. Programs produce standing and points. The console reads all of it, and what it learns goes back out as the next audience and the next nudge.` |

**Entry strip** (`.sysmap-entry`, sits above the diagram, dashed top-border card with a downward chevron):

- `.sysmap-entry-label`: `Before the loop starts`
- `.sysmap-entry-text`: `Employees are provisioned by CSV upload, SFTP sync or an HRIS integration, then sign in with SAML 2.0 single sign-on or their work email. Your company sits on one of four regional instances: India, US, EU or UAE.`

**The diagram.** Full SVG spec in §4.3. Node and flow copy:

| Node | Title | Line 1 | Line 2 | Line 3 |
|---|---|---|---|---|
| 1 (10 o'clock) | `Capture` | `Apple Health and Google Fit` | `Fitbit, Garmin, manual logging` | `Health Risk Assessment, where enabled` |
| 2 (12 o'clock) | `Programs` | `Challenges, teams, events` | `Content Library and mindfulness` | `Audience rules enroll people` |
| 3 (2 o'clock) | `Standing` | `Live challenge scoring` | `Individual and team leaderboards` | `Badges and Wellness Leagues` |
| 4 (4 o'clock) | `Rewards` | `Vantage Points` | `Gift card catalogue` | `SOLI purchasing power` |
| 5 (6 o'clock) | `Insight` | `Enrolled, Active, Participation Rate` | `Leadership Insights` | `CSV reports` |
| 6 (8 o'clock) | `Reach` | `Push notifications` | `System and custom emails` | `Announcements and surveys` |

| Centre hub | Copy |
|---|---|
| Title | `Configuration` |
| Line 1 | `Full Mode or Lite Mode` |
| Line 2 | `Per-company feature flags` |
| Line 3 | `Tabs appear only if you enable them` |

Flow labels, clockwise, sitting on their arrows:

| Arrow | Label |
|---|---|
| Capture → Programs | `activity` |
| Programs → Standing | `task completion` |
| Standing → Rewards | `points earned` |
| Rewards → Insight | `spend and redemption` |
| Insight → Reach | `who to reach` |
| Reach → Capture | `back into the app` |

**Trailing notes** (`.sysmap-note`, two lines, `.8rem`, muted):

1. `Capture covers 65+ activity types, from steps counted by the phone to manually logged yoga, swimming and strength training.`
2. `Wellness Leagues, the Org Wellness Score and workforce health analytics are annual-client features that your account manager sets up. Everything else in this map ships to every company.`

---

### S3. The three surfaces

`<section class="hub-section surfaces-screen" id="surfaces" aria-labelledby="surfaces-heading">` · ground `#fff`

| Element | Copy |
|---|---|
| `.eyebrow` | `Three surfaces` |
| `h2#surfaces-heading` | `The same program, from three seats.` |
| `.lead` | `Here is Step into Spring 2026 as an employee sees it, as HR runs it, and as your systems feed it.` |

**Card 1**

| Element | Copy |
|---|---|
| `.surface-tag` | `For employees` |
| `h3` | `Mobile app` |
| `.surface-sub` | `iOS and Android` |
| Mock | See §4.4 |
| `.surface-foot` | `Everything an employee needs lives here. There is no admin function in the iOS or Android app.` |

**Card 2**

| Element | Copy |
|---|---|
| `.surface-tag` | `For HR` |
| `h3` | `Admin console` |
| `.surface-sub` | `dashboard.vantagecircle.com` |
| Mock | See §4.5 |
| `.surface-foot` | `Web only, inside the Vantage Circle admin dashboard. It needs the HR Admin role.` |

**Card 3**

| Element | Copy |
|---|---|
| `.surface-tag` | `For IT` |
| `h3` | `Integration layer` |
| `.surface-sub` | `Wearables, single sign-on, HR systems` |
| Mock | See §4.6 |
| `.surface-foot` | `Single sign-on and HRIS sync are configured by our integration team, not from the console.` |

**Trailing note** (`.surfaces-note`, `.8rem`, muted):
`There is also a web app at app.vantagefit.io for challenges, leaderboards and light logging. Step tracking, device connection and the wallet stay in the mobile app.`

---

### S4. Why people take part

`<section class="hub-section why-screen" id="participation" aria-labelledby="participation-heading">` · ground `#f6f7f4`

| Element | Copy |
|---|---|
| `.eyebrow` | `The north star` |
| `h2#participation-heading` | `One number decides whether any of this worked.` |
| `.lead` | `Industry average sustained participation sits at 20 to 30 percent. Four design decisions are aimed squarely at that number.` |

`.why-grid`, four `.why-item` (glyph + `b` + `p`):

| # | Title (`b`) | Body (`p`) | Glyph |
|---|---|---|---|
| 1 | `No wearable required` | `Steps come from the phone itself: Apple Health on iPhone, Google Fit on Android.` | phone with a step arc |
| 2 | `Nobody has to go find it` | `Audience rules enroll every matching employee the moment a challenge goes live.` | funnel into a group |
| 3 | `Team score is an average` | `One strong walker cannot carry a team, and one quiet week cannot sink it.` | three bars with a level line |
| 4 | `Effort converts to something real` | `Vantage Points redeem for gift cards, priced by SOLI so the value holds across countries.` | card with a coin |

**Proof strip.** `.results-grid` overridden to three columns, three `.result-card`:

| `.stat` | `p` | `.segment` |
|---|---|---|
| `59%` | `engagement rate over a six-month program` | `Tata Motors · Step & Stride Challenge`<br>`1,248 active participants` |
| `88%` | `engagement rate over 28 days` | `IBS Software · March to Fitness`<br>`500+ active of 660 invited` |
| `86%` | `engagement rate over two weeks` | `Brazosport ISD · Fit Wars`<br>`132 active participants` |

`.proof-fine`:
- `small`: `Engagement rate is the share of the invited population that actively used the program. Results are from named customer programs and vary by workforce and program design.`
- `.text-link`: `Read customer stories` → `https://www.vantagefit.io/casestudy/`

> **Claims discipline for the builder:** do not append a causal clause to any of these three numbers. The sentence ends at the number and its definition.

---

### S5. Rollout and IT

`<section class="hub-section rollout-screen" id="rollout" aria-labelledby="rollout-heading">` · ground `#fff`

| Element | Copy |
|---|---|
| `.eyebrow` | `Rollout and IT` |
| `h2#rollout-heading` | `What your IT team actually has to do.` |
| `.lead` | `A file and a sign-in method. Single sign-on and HRIS sync are optional, and our integration team does that work.` |

`.spec-cols`, three `.spec-group`, each with an `h3` and four `.spec-row` (`dt` label, `dd` value):

**Group 1, `h3`: `Getting employees in`**

| Label | Value |
|---|---|
| `Provisioning` | `CSV upload by your HR admin from Configuration > Add Employees, SFTP sync, or an HRIS integration.` |
| `HRIS systems` | `Workday, DarwinBox, ADP, SAP SuccessFactors and other major HR systems, set up by our integration team.` |
| `Sign-in` | `Work email and password, a one-time code to work email, or SAML 2.0 single sign-on.` |
| `Time to live` | `1 to 2 days on Lite Mode with a CSV upload. Single sign-on adds about two weeks of our configuration once we have your identity provider metadata.` |

**Group 2, `h3`: `Running it globally`**

| Label | Value |
|---|---|
| `Data region` | `One of four regional instances: India, US, EU or UAE. Chosen at setup, and employee data stays there.` |
| `Languages` | `13 languages in the app and system emails, following each employee's own device setting. The admin console is English only.` |
| `Time zones` | `One challenge can span countries. Start, daily reset and end all follow each participant's local midnight.` |
| `Rewards by country` | `Configured in USD, shown to each employee in local currency, with a country-relevant gift card catalogue.` |

**Group 3, `h3`: `Access and security`**

| Label | Value |
|---|---|
| `Admin access` | `The HR Admin role, on the web only. There is no admin function in the mobile apps.` |
| `Single sign-on` | `Any SAML 2.0 identity provider. Named: Microsoft Entra ID (formerly Azure Active Directory), Okta, OneLogin and Ping Identity.` |
| `Devices` | `Apple Health and Google Fit by default, plus Fitbit, Garmin, Apple Watch and Samsung Watch. One primary source per employee.` |
| `Compliance` | `SOC 2 Type II. Operates under HIPAA guidelines. Security documentation is available during evaluation.` |

**Trailing note** (`.spec-note`, `.8rem`, muted):
`Provisioning is separate from single sign-on. Even with single sign-on switched on, employees still arrive by CSV, SFTP or HRIS.`

---

### S6. The privacy architecture (dark `.fairband` inset)

`<section class="hub-section privacy-screen" id="privacy" aria-labelledby="privacy-heading">` · ground `var(--canvas)`, with the dark `.fairband` inset inside it

Inside the `.fairband` left column:

| Element | Copy |
|---|---|
| `.eyebrow` (goes `--lime` on dark) | `Aggregate by architecture` |
| `h2#privacy-heading` | `HR can act on a health risk without seeing who has it.` |
| `.lead` | `This is enforced by the product, not by a policy page. Ask your privacy reviewer to check the screen on the right.` |

`.fair-list`, four `.fair-item`:

| # | Title (`b`) | Body (`p`) |
|---|---|---|
| 1 | `A count, never a list` | `Selecting a health-risk group returns a number and a privacy notice. The names are not shown to anyone.` |
| 2 | `Participation in, health out` | `Admins see enrollment, last active date, rankings and team scores. Not weight, assessment answers, lab values, mood or food logs.` |
| 3 | `AI runs on aggregates` | `Leadership Insights sends no personal data to the model, only aggregated signal buckets.` |
| 4 | `Employees hold their own switches` | `Leaderboard opt-out keeps someone in the challenge and out of the rankings. Wheelchair Mode changes how activity is tracked.` |

`.fair-fine` (top hairline, small, `rgba(255,255,255,.62)`), rendered as a quotation with attribution:

> `"Your HR team sees whether you are participating and your challenge rankings, but we cannot see your weight, health assessment results, lab reports, or personal health data."`
> `The sentence the Vantage Fit help centre gives HR to read out to employees.`

Right column: the audience-selector mock, spec in §4.7.

---

### S7. Where to go deeper

`<section class="hub-section explore-screen" id="explore" aria-labelledby="explore-heading">` · ground `#fff`

| Element | Copy |
|---|---|
| `.eyebrow` | `Go deeper` |
| `h2#explore-heading` | `Pick the part you need to evaluate.` |

No `.lead`. The grid is the content.

`.deep-grid`, three `.deep-col`. Each column: a `.deep-col-title` (uppercase micro-label) and a stack of `.deep-link` rows (`b` title with a trailing coral arrow, `span` one-line description).

**Column 1, title: `What you want to run`**

| Link | Description | href |
|---|---|---|
| `Wellness challenges` | `The full library of ready-to-run challenges.` | `/solutions/wellness-challenges/` |
| `Step challenges` | `Company-wide step goals that get everyone moving.` | `/solutions/step-challenges/` |
| `Multi-activity challenges` | `Any activity, solo or in teams, over themed weeks.` | `/solutions/multi-activity-challenges/` |
| `Remote & hybrid team challenges` | `Wellness that works away from the office.` | `/solutions/remote-team-wellness/` |
| `Virtual marathon` | `Distance events powered by steps.` | `/solutions/virtual-marathon/` |

**Column 2, title: `What you want to measure`**

| Link | Description | href |
|---|---|---|
| `Health Risk Assessment` | `Baseline health screening with aggregate insights.` | `/solutions/health-risk-assessment/` |
| `Workforce health insights` | `Participation, challenge and activity analytics your board can read.` | `/solutions/workforce-health-insights/` |
| `Wellness rewards program` | `Points and gift cards tied to real effort.` | `/solutions/wellness-rewards-program/` |

**Column 3, title: `Capability detail`**

| Link | Description | href |
|---|---|---|
| `Activity & health tracking` | `Steps, workouts, sleep and more, auto-synced.` | `/features/activity-tracking/` |
| `Integrations` | `Wearables, HRIS, SSO and more.` | `/features/integrations/` |
| `Security & compliance` | `Aggregate-only reporting, regional hosting, SOC 2 Type II.` | `/features/security-and-compliance/` |
| `Wellness leagues` | `Segment by activity level, lift every tier.` | `/features/wellness-leagues/` |

**Suite band** (`.suite-band`, a full-width tinted strip at the bottom of this section):

- `.suite-title`: `One vendor across wellness, recognition, surveys and perks`
- `.suite-body`: `Vantage Fit is one product within Vantage Circle's employee engagement platform, which also includes Vantage Recognition for recognition, Vantage Pulse for employee surveys, and Vantage Perks for discounts and benefits. Organizations that start with Vantage Fit can expand to the full suite without changing vendors.`
- `.suite-links`, three inline links, **same tab, no `rel="nofollow"`**:
  - `Vantage Recognition` → `https://www.vantagecircle.com/products/rewards-recognition/`
  - `Vantage Pulse` → `https://www.vantagecircle.com/products/employee-surveys/`
  - `Vantage Perks` → `https://www.vantagecircle.com/newperkspage/`

---

### S8. Trust band (dark, full bleed)

`<section class="screen trust-screen solutions-trust" id="security" aria-labelledby="security-heading">`

Structure is the chrome band. **Swap the copy to infrastructure only**, so it does not repeat S6.

| Element | Copy |
|---|---|
| `.eyebrow` | `Enterprise security` |
| `h2#security-heading` | `Four regions. One audited platform.` |
| `.lead` | `Where employee data lives, how it is protected, and what we can hand your security reviewers.` |
| `.trust-actions` primary | `Book a demo` → `/request-demo/` |
| `.trust-actions` text-link | `Explore security & compliance →` → `/features/security-and-compliance/` |

Four `.trust-card` (keep the entity glyphs from the chrome):

| Glyph | `h3` | `p` |
|---|---|---|
| `&#9673;` | `Data stays in your region` | `Four regional instances: India, US, EU and UAE. You choose one at setup and employee data stays there.` |
| `&#9737;` | `Encrypted in transit and at rest` | `Traffic runs over TLS, with SSL pinning in the mobile apps. Sensitive profile fields are encrypted at rest.` |
| `&#8644;` | `Audited and documented` | `SOC 2 Type II. Operates under HIPAA guidelines. Security documentation is available during evaluation.` |
| `&#10003;` | `Retention you can point to` | `Notifications are deleted after 14 days. Activity and health data are retained per your contract. An admin cannot delete an employee's account on their behalf.` |

`.trust-plaque`: the typeset `.mark-strip` from `chrome.html`, three marks only: **Follows HIPAA guidelines** · **SOC 2 Type II** · **Secured regional data hosting**. `.trust-support`: `Security documentation is available during evaluation.`

> **Hard rule:** do not restore the Cloudinary certification raster. Do not add ISO 27001, ISO 27701 or GDPR marks.

---

### S9. FAQ

`<section class="hub-section faq-screen" id="faq" aria-labelledby="faq-heading">` · ground `#fff`

| Element | Copy |
|---|---|
| `.eyebrow` | `Before you talk to procurement` |
| `h2#faq-heading` | `Questions IT asks first.` |

Five `<details class="faq-item">`. First one carries `open`.

**Q1** (answer-first definition, the AEO play, must also appear verbatim in the FAQPage schema)
`What is an employee wellness platform?`
> An employee wellness platform is software an employer provides so staff can track activity and health habits, take part in wellness programs, and earn rewards, while HR runs those programs and reports on them from one console. Vantage Fit does this with a mobile app for employees on iOS and Android, a web admin console for HR, and an integration layer that connects wearables, single sign-on and HR systems.

**Q2**
`What does our IT team have to do to launch?`
> At minimum, hand over an employee list. Your HR admin can upload a CSV from Configuration > Add Employees and be live in one to two days on Lite Mode. For automated provisioning we set up SFTP sync or an HRIS integration. For single sign-on, your IT team creates a SAML 2.0 application and exports the identity provider metadata to us. Once we have that metadata, configuration usually takes around two weeks.

**Q3**
`Do employees need a wearable?`
> No. Steps come from the phone itself, through Apple Health on iPhone and Google Fit on Android. If employees do have a device, Fitbit, Garmin, Apple Watch and Samsung Watch connect too. Each employee has one primary source at a time, so steps are never counted twice.

**Q4**
`How are we billed for employees who never sign in?`
> A licence is counted from an employee's first login, not from the moment they are uploaded. Upload 1,000 people, 600 sign in, and you are billed for 600. Bulk and lumpsum contracts are handled differently. Note that this billing count is not the same as the Active Users figure on the dashboard, which measures recent app usage.

**Q5**
`What can an HR admin see about one person?`
> Whether they are enrolled, when they were last active, their device type, their challenge rank and score, and the points they have earned and redeemed. Admins cannot see weight, BMI, Health Risk Assessment answers, lab report values, mood logs, food diaries or sleep detail. That split is enforced in the product: when an admin targets a health-risk group, the system returns a count and the message that the list of users is not displayed to protect individual privacy.

---

### S10. Closer

`<section class="final" id="demo" aria-labelledby="demo-heading">`

| Element | Copy |
|---|---|
| `h2#demo-heading` | `See the whole system on your own workforce.` |
| `p` | `In a 30-minute demo we will map your rollout, walk the employee app and the admin console, and show the reporting your leadership will read.` |
| `.btn-primary` | `Book a demo` → `/request-demo/` |
| `.btn-outline` | `See pricing` → `/pricing/` |
| `.final-checks` (3 lime-dotted) | `CSV to live in 1 to 2 days` · `No wearable required` · `Single sign-on optional` |
| `.final-note` | `One system, not four tools.` |

---

## 4. Product-real UI spec

Universal mock rules, from `design-system.md` §5:
1. Outer wrapper carries `role="img"` and an `aria-label` that describes what is shown and **ends with "Figures shown are illustrative."** (only where the mock contains numbers).
2. Every decorative child carries `aria-hidden="true"`.
3. `<span class="mock-tag">Illustrative data</span>` is visible on **every mock that shows a number**.
4. All digits get `font-variant-numeric: tabular-nums`.
5. Only real product nouns. No invented UI.

One illustrative program name runs through the whole page so the surfaces read as one system: **Step into Spring 2026**. Consistent illustrative figures across mocks: **4,820 enrolled · 3,140 active · 64% participation · 214 in the challenge · day 12 of 28 · 8,412 steps today**.

---

### 4.1 Hero `.dash`: the admin Overview

Reuses `.dash` / `.dash-top` / `.dash-body` / `.metric-inline` / `.metric-card.metric-main` / `.chart-card` from `enterprise.css`.

```
role="img"
aria-label="Admin console overview showing enrolled users, active users, incentivization spend
and a 64 percent participation rate, with an average daily steps trend.
Figures shown are illustrative."
```

- `.dash-top`: three grey dots plus `.dash-url`. **Render the URL pill with text**: `dashboard.vantagecircle.com`, `.55rem`, `rgba(41,41,76,.5)`, left-padded. That single detail is worth more than the blank pill.
- `.dash-title`: `small` = `Admin · Overview`, `strong` = `Company overview`, right-aligned `<span class="mock-tag">Illustrative data</span>`
- `.metric-inline`, three cells (`i` label uppercase, `b` value):
  - `ENROLLED USERS` / `4,820`
  - `ACTIVE USERS` / `3,140`
  - `INCENTIVIZATION` / `$6,410`
- `.metric-card.metric-main`:
  - `.metric-lab`: `Participation rate`
  - `.metric-value`: `64%`
  - `.metric-delta`: `+7 pts vs prev quarter`
- `.chart-card`:
  - `.chart-head`: `Avg steps · this month` with `.legend` `<i></i> Company`
  - `.chart` with `.target-line` label `Goal 8,000`
  - SVG `viewBox="0 0 300 84" preserveAspectRatio="none"`, polygon + polyline, points `0,66 50,58 100,52 150,44 200,38 250,26 300,18`
  - `.chart-labels`: `W1 W2 W3 W4`
  - Page-local stroke: `polyline { fill:none; stroke: var(--mint-dark); stroke-width:2.4; }` `polygon { fill: rgba(65,216,180,.14); }`

The four KPI labels are the exact code-verified set (Enrolled Users, Active Users, Incentivization, Participation Rate). Do not substitute.

---

### 4.2 Hero `.phone`: the employee Home screen

Reuses `.phone` / `.phone-screen` / `.phone-head` / `.avatar` / `.phone-stats` / `.phone-cta`, plus two page-local blocks.

```
role="img"
aria-label="Employee app home screen showing activity rings at 8,412 of 10,000 steps,
seven-day trends, and the Step into Spring 2026 challenge card.
Figures shown are illustrative."
```

- `.phone-head`: `Vantage Fit` + `.avatar`
- **NEW page-local `.rings-card`** (white, radius 14px, padding 12px): a 92×92 inline SVG with two concentric arcs.
  - Outer ring (steps): `stroke: var(--mint)`, track `rgba(41,41,76,.10)`, `stroke-dasharray` set to 84% of circumference, `stroke-linecap="round"`, rotated `-90deg`.
  - Inner ring (active calories): `stroke: var(--coral)`, same track, 100% filled.
  - Centre text: `8,412` (`.8rem/800`) over `steps` (`.52rem`, muted).
  - Right of the SVG, two `.ring-key` rows: mint dot + `Steps 8,412 / 10,000`; coral dot + `Active calories 268 / 250`.
  - Caption under: `Ring 2 shows active calories or active minutes, depending on your company setting.` (`.52rem`, muted)
- `.phone-stats`, three cells (`b` value, `span` label): `8,140` / `7d avg steps` · `7h 12m` / `Sleep` · `9 min` / `Mindful`
- **Challenge carousel strip** (reuse `.challenge` at reduced height, or a page-local `.pcard`): teal gradient art block 44px tall with the 🚶 emoji, then `small` `STEPS · RACE`, `b` `Step into Spring 2026`, `p` `Day 12 of 28`, `.progress` at `width:84%`
- **NEW page-local `.ptabs`** (the five-position bottom bar, this is the detail that proves it is a real app): five cells, each a 14px stroke glyph plus a `.5rem` label. Order and labels exactly: `Home` (active, coral) · `Challenges` · a 26px coral circle with a `+` · `Programs` · `Community`
- `<span class="mock-tag">Illustrative data</span>`

---

### 4.3 The system map SVG

This is the page's signature asset. Hand-built inline SVG. No library, no image.

**Wrapper**

```html
<figure class="sysmap" role="img" aria-label="Diagram of the Vantage Fit module loop. Capture
feeds Programs with activity. Programs feed Standing with task completion. Standing feeds Rewards
with points earned. Rewards feed Insight with spend and redemption. Insight feeds Reach with who
to reach. Reach feeds Capture by bringing employees back into the app. Configuration sits at the
centre of the loop and controls which modules a company runs.">
```

**Canvas:** `viewBox="0 0 1000 740"`, `width="100%"`, `height="auto"`, `preserveAspectRatio="xMidYMid meet"`.
Wrapper `.sysmap { overflow-x: auto; }` and, below 900px, `svg { min-width: 760px; }` so the diagram scrolls inside its own container rather than shrinking to illegibility. The page body must never scroll horizontally.

**Node geometry.** Six rounded rects, `width="220" height="112" rx="16"`.

| Node | rect x | rect y | centre |
|---|---|---|---|
| Capture | 90 | 216 | 200, 272 |
| Programs | 390 | 100 | 500, 156 |
| Standing | 690 | 216 | 800, 272 |
| Rewards | 690 | 472 | 800, 528 |
| Insight | 390 | 588 | 500, 644 |
| Reach | 90 | 472 | 200, 528 |

Centre hub: `rect x="370" y="390" width="260" height="110" rx="18"`, centre `500, 445`.

**Node styling**

- `.sm-node`: `fill: var(--paper)`, `stroke: rgba(41,41,76,.14)`, `stroke-width: 1.4`
- Each node gets a 4px coral or mint left accent bar: `rect width="4" height="112" rx="2"` at the node's left edge. Alternate `var(--mint)` for Capture, Standing, Insight and `var(--coral)` for Programs, Rewards, Reach, so the eye reads six distinct stops without hue carrying meaning (verify with `?gray`).
- `.sm-title`: `text-anchor="middle"`, `font-size="16"`, `font-weight="800"`, `fill: var(--ink)`, `letter-spacing="-.02em"`, baseline at rect `y + 34`
- `.sm-line`: `text-anchor="middle"`, `font-size="11.5"`, `fill: var(--muted)`, baselines at rect `y + 58`, `y + 78`, `y + 98`

**Hub styling**

- `.sm-hub`: `fill: #1D2228` (`var(--dark)`), no stroke
- Hub title: `Configuration`, `font-size="15"`, `font-weight="800"`, `fill:#fff`, baseline `418`
- Hub lines: `font-size="11"`, `fill: rgba(255,255,255,.66)`, baselines `442`, `460`, `478`

**Arrows.** One `<marker id="sm-arrow" ...>` definition, a 9×9 filled triangle, `fill: rgba(41,41,76,.42)`.
`.sm-flow { fill:none; stroke: rgba(41,41,76,.30); stroke-width: 2; marker-end: url(#sm-arrow); }`

| Arrow | Path `d` |
|---|---|
| Capture → Programs | `M 200 216 Q 240 130 384 150` |
| Programs → Standing | `M 610 156 Q 770 146 798 210` |
| Standing → Rewards | `M 800 328 L 800 466` |
| Rewards → Insight | `M 798 584 Q 770 656 616 646` |
| Insight → Reach | `M 390 644 Q 230 656 202 586` |
| Reach → Capture | `M 200 472 L 200 334` |

**Flow labels.** `<text class="sm-flow-label">` placed at the path midpoint, `text-anchor="middle"`, `font-size="11"`, `font-weight="700"`, `fill: rgba(41,41,76,.62)`, and **knocked out of the line behind them** with `paint-order="stroke"`, `stroke="#F8F8F9"` (the section ground), `stroke-width="7"`, `stroke-linejoin="round"`.

| Label | x, y |
|---|---|
| `activity` | 268, 160 |
| `task completion` | 716, 168 |
| `points earned` | 800, 400 |
| `spend and redemption` | 712, 636 |
| `who to reach` | 286, 636 |
| `back into the app` | 200, 402 |

**Do not** put numbers in this diagram. It carries no `.mock-tag` because it carries no figures.

**Reduced motion:** the diagram is static. If the builder animates the arrow dashes, it must be behind `@media (prefers-reduced-motion: no-preference)` and must not be the only way the flow reads.

---

### 4.4 Surface 1 mock: mobile app, Challenges tab

A narrower `.phone` (about 176px) inside `.surface-card`. Page-local class `.mini-phone`.

```
aria-label="Employee app challenges tab showing Step into Spring 2026 on day 12 of 28,
with the employee ranked 3rd of 214. Figures shown are illustrative."
```

- Screen header row: `Challenges` (`.7rem/800`) plus a bell glyph
- Sub-tab row (real product strings): `Ongoing` (selected, coral underline) · `Upcoming` · `Past`
- One challenge card: teal gradient art strip, `small` `STEPS · RACE`, `b` `Step into Spring 2026`, `p` `Day 12 of 28`, `.progress` at 84%, and a right-aligned `#3 of 214` chip
- `.ptabs` bottom bar, `Challenges` active
- `<span class="mock-tag">Illustrative data</span>`

### 4.5 Surface 2 mock: admin console, Overview

A compact `.dash` variant inside `.surface-card`. Page-local class `.mini-dash`.

```
aria-label="Admin console overview with four key figures and a recommended action to nudge
92 inactive employees. Figures shown are illustrative."
```

- `.dash-top` chrome bar with `.dash-url` reading `dashboard.vantagecircle.com`
- Two-column body: a 62px left rail plus the main panel
- **Left rail**, six items, product Title Case, `Overview` active with a coral inset bar:
  `Overview` · `Create Challenge` · `Manage Challenge` · `Employee Report` · `Rewards Hub` · `Configuration`
  (Render as 9px labels under 12px glyphs, or as truncated text rows. Do **not** invent a menu item. Do **not** render Insights Hub.)
- **Main panel**, a 2×2 grid of mini KPI tiles, exact labels:
  `Enrolled Users` `4,820` · `Active Users` `3,140` · `Incentivization` `$6,410` · `Participation Rate` `64%`
  Each tile: `.55rem` uppercase label, `1.05rem/800` value, and a 3-point sparkline.
- Below, a `Recommended actions` block with two rows, exact product strings:
  - `View Inactive Employees` with sub-line `92 users inactive for 30+ days`
  - `Nudge Inactive Users`
- `<span class="mock-tag">Illustrative data</span>`

### 4.6 Surface 3 mock: the integration layer

Deliberately not a browser and not a phone. A white panel, radius 18px, `1px solid var(--line)`, split into two labelled blocks by a hairline. Page-local class `.conn-panel`.

```
role="img"
aria-label="Connection panel showing Apple Health as the connected primary step source, with
Google Fit, Fitbit, Garmin and Health Connect available, plus employee sync options for CSV,
SFTP, HRIS and SAML single sign-on."
```

**Block A**, header `Device Connection` (real screen name). Five rows, each a 16px monochrome glyph, a name, and a right-aligned status chip:

| Row | Status chip |
|---|---|
| `Apple Health` | `Connected · primary` (mint chip, filled dot) |
| `Google Fit` | `Available` |
| `Fitbit` | `Available` |
| `Garmin` | `Available` |
| `Health Connect` | `Health imports` |

Caption under Block A (`.52rem`, muted): `One primary source at a time, so steps are never counted twice.`

> **Hard rule:** Health Connect must never be labelled a step source. Its chip reads `Health imports`.

**Block B**, header `Employee sync`. Four rows:

| Row | Right-hand value |
|---|---|
| `CSV upload` | `HR admin, self-serve` |
| `SFTP sync` | `Set up once` |
| `HRIS` | `Workday, DarwinBox, ADP, SAP` |
| `SAML 2.0 SSO` | `Entra ID, Okta, OneLogin, Ping` |

No numbers appear in this mock, so no `.mock-tag`.

---

### 4.7 The audience-selector mock (inside the `.fairband`)

Page-local class `.cohort-card`. Same shell as `.audit-board`: white panel, about 380px, `box-shadow: 0 26px 60px rgba(0,0,0,.32)`, radius 18px, floating on the dark band.

```
role="img"
aria-label="Create-challenge audience step. A health risk code is selected and the system
returns a count of 412 matching employees with a notice that the list of users is not displayed
to protect individual privacy. Figures shown are illustrative."
```

- `.cohort-head`: `b` `Create challenge`, `span` `Step 3 of 4 · Audience`
  - `Step 3 of 4` is the **Race** short path (Format, Basic Details, Audience, Review and Publish), which is the format the page's mocks run throughout (`STEPS · RACE`). `challenges.md` §4.2. The generic wizard is 7 steps with Target Audience at 5. Do not change one without the other.
- Three `.cohort-row` (label left, value right, hairline between):
  - `Country` / `All`
  - `Department` / `All`
  - `Health risk code` / a mint chip reading `1 selected`
- `.cohort-count` block, tinted `rgba(65,216,180,.10)`, radius 12px: `412` (`2.1rem/800`, tabular-nums) over `employees match`
- `.cohort-notice`, tinted `rgba(41,41,76,.05)`, radius 10px, with a small lock glyph and this **verbatim product string**:
  `The list of users is not displayed to protect individual privacy.`
- `.cohort-foot` (`.6rem`, muted): `Applying any audience filter marks the challenge Private.`
- `<span class="mock-tag">Illustrative data</span>`

> The `1 selected` value is deliberate. Health-risk code labels are not documented in any source, so the mock must not invent one.

---

### 4.8 Page-local CSS the builder must copy in

`chrome.html` supplies: nav state, `.hub-section`, `.hub-head`, `.reveal`, `.skip-link`, contrast lifts, focus ring, `.btn-primary` fix, forced-colors fallback, `.mock-tag`, `.solutions-trust` overrides, `.mark-strip`, FAQ, footer grid.

Copy from `design-system.md` §3.B before writing markup:

| Needed for | Classes | Source |
|---|---|---|
| S4 proof strip | `.results-grid` `.result-card` `.stat` `.segment` `.proof-fine` | §3.B |
| S6 dark inset | `.fairband` `.fair-list` `.fair-item` `.fair-fine` | §3.B, `[STEPS]` |

New page-local components to write (all named in this brief): `.sysmap` `.sysmap-entry` `.sysmap-note` `.sm-*` · `.surface-grid` `.surface-card` `.surface-tag` `.surface-sub` `.surface-foot` `.surfaces-note` · `.mini-phone` `.mini-dash` `.conn-panel` `.ptabs` `.rings-card` `.ring-key` · `.why-grid` `.why-item` · `.spec-cols` `.spec-group` `.spec-row` `.spec-note` · `.cohort-card` and children · `.deep-grid` `.deep-col` `.deep-col-title` `.deep-link` · `.suite-band` `.suite-title` `.suite-body` `.suite-links`

Overrides:
```css
.why-screen .results-grid { grid-template-columns: repeat(3, 1fr); }
.system-screen .eyebrow,
.why-screen .eyebrow,
.privacy-screen .eyebrow { color: var(--coral-deep); }
```

Grid columns: `.surface-grid` `repeat(3,1fr)` gap 14px · `.why-grid` `repeat(2,1fr)` gap 18px · `.spec-cols` `repeat(3,1fr)` gap 40px · `.deep-grid` `1.05fr .95fr .95fr` gap 40px.

Responsive floor: every multi-column grid ends at one column by 640px. `.surface-grid` goes to one column at **1100px** so each mock keeps its width: three up needs about 1160px of viewport before `.conn-panel` can hold `Apple Health` and the `Connected · primary` chip on one row, so 900px left the mocks squeezed under their own content width. `.sysmap` scrolls horizontally inside itself below 900px. `.conn-row` and `.md-body` use `minmax(0, 1fr)`, not `1fr`, so a name column wraps instead of forcing the panel wide.

### 4.9 Band alternation check

| # | Section | Ground |
|---|---|---|
| 1 | Hero + logo band | cream/white radial |
| 2 | System map | `var(--canvas)` |
| 3 | Surfaces | `#fff` |
| 4 | Participation + proof | `#f6f7f4` |
| 5 | Rollout and IT | `#fff` |
| 6 | Privacy (dark `.fairband` inset) | `var(--canvas)` |
| 7 | Where to go deeper | `#fff` |
| 8 | Trust band | dark gradient |
| 9 | FAQ | `#fff` |
| 10 | Closer | dark gradient |

No two identical grounds adjacent. `#f6f7f4` is used once, for the proof strip, as the house rule requires. Three dark moments (fairband inset, trust band, closer), and the fairband is separated from the trust band by section 7.

---

## 5. Claims table

Every factual claim rendered on the page, its source and its status. Anything not in this table does not go on the page.

### 5.1 Product architecture and modules

| # | Claim as rendered | Source | Status |
|---|---|---|---|
| 1 | Employees are added by HR and sign in with SSO or work email. No public signup | `vfit-os/specs/product/00-platform/auth-login-signup.md` | SHIPPED |
| 2 | Steps come from Apple Health on iPhone and Google Fit on Android, no wearable required | `vantagefit-astro/content/en/help/admin/settings/admin-what-is-vantage-fit.md` | SHIPPED |
| 3 | Fitbit, Garmin, Apple Watch and Samsung Watch connect as sources | `vfit-os/specs/product/10-integrations/device-integrations.md` | SHIPPED |
| 4 | Health Connect is for health imports, not steps | `vfit-os/specs/product/10-integrations/device-integrations.md` | SHIPPED |
| 5 | One primary device at a time, so steps are not double counted | `vfit-os/specs/product/01-core-tracking/activity-tracking.md` | SHIPPED |
| 6 | 65+ activity types | `vantagefit-astro/content/en/help/employee/health-tracking/what-activities-can-i-track.md` | SHIPPED (settled ruling `platform.md` A3) |
| 7 | Modules: challenges, teams, events, Content Library, mindfulness | `vfit-os/specs/product/02-…/challenges.md`, `06-content-education/content-library.md`, `03-health-wellness/mindfulness.md`, `05-social-community/community-social.md` | SHIPPED |
| 8 | Audience rules enroll matching employees automatically; employees do not browse and join | `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md` | SHIPPED |
| 9 | Live challenge scoring, individual and team leaderboards, badges | `vfit-os/specs/product/02-challenges-gamification/challenges.md` | SHIPPED |
| 10 | Team score is an average of member scores | `vantagefit-astro/content/en/help/admin/reports/admin-how-do-i-view-leaderboard.md` | SHIPPED |
| 11 | Vantage Points redeem for gift cards | `vantagefit-astro/content/en/help/employee/rewards/how-do-i-redeem-points.md` | SHIPPED |
| 12 | SOLI normalizes purchasing power across countries | `vfit-os/specs/product/08-rewards-marketplace/soli-currency.md` | SHIPPED |
| 13 | Admin KPI cards: Enrolled Users, Active Users, Incentivization, Participation Rate | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED (settled ruling, `rewards.md` E1) |
| 14 | Leadership Insights is AI generated | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 15 | Reports export to CSV | `vantagefit-astro/content/en/help/admin/reports/admin-how-do-i-export-reports.md` | SHIPPED |
| 16 | Push notifications, system emails, admin custom email, announcements, surveys | `vfit-os/specs/product/09-admin-platform/notifications.md`, `emails.md`, `surveys.md` | SHIPPED |
| 17 | Recommended Actions surfaces "View Inactive Employees (92 users inactive for 30+ days)" and "Nudge Inactive Users" | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED (label strings; the 92 is illustrative in the mock) |
| 18 | Full Mode or Lite Mode is a company-wide setting | `vantagefit-astro/content/en/help/admin/settings/admin-what-is-lite-mode.md` | SHIPPED |
| 19 | Tabs and menu items appear only if the feature is enabled | `vfit-os/specs/product/00-platform/navigation-ia.md` | SHIPPED |
| 20 | Wellness Leagues, Org Wellness Score and workforce health analytics are annual-client features set up by the account manager | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`, `03-health-wellness/workforce-health.md` | SHIPPED-GATED, rendered **with** the gate |

### 5.2 Surfaces

| # | Claim | Source | Status |
|---|---|---|---|
| 21 | Mobile app on iOS and Android with a five-position bottom bar: Home, Challenges, +, Programs, Community | `vfit-os/specs/product/00-platform/navigation-ia.md` | SHIPPED |
| 22 | Home screen shows two activity rings; ring 2 is active calories or active minutes per company config | `vfit-os/specs/product/00-platform/navigation-ia.md` | SHIPPED |
| 23 | Default targets when no challenge is running: 10,000 steps, 250 active calories | `vfit-os/specs/product/01-core-tracking/activity-tracking.md` | SHIPPED |
| 24 | Challenges tab sub-tabs: Ongoing, Upcoming, Past | `vfit-os/specs/product/00-platform/navigation-ia.md` | SHIPPED |
| 25 | Admin console is web only, at dashboard.vantagecircle.com, and needs the HR Admin role | `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-sign-in.md` | SHIPPED |
| 26 | No admin functionality in the iOS app, Android app or web app | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 27 | A web app at app.vantagefit.io does challenges, leaderboards and light logging; step tracking, device connection and the wallet stay in the mobile app | `vantagefit-astro/content/en/help/employee/getting-started/using-vantage-fit-on-web.md` | SHIPPED (no tab count claimed; layout is UNVERIFIED) |
| 28 | Admin nav destinations named in the mock: Overview, Create Challenge, Manage Challenge, Employee Report, Rewards Hub, Configuration | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |

### 5.3 Rollout, IT and security

| # | Claim | Source | Status |
|---|---|---|---|
| 29 | Provisioning by CSV upload (Configuration > Add Employees), SFTP sync or HRIS integration | `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-add-employees.md` | SHIPPED |
| 30 | HRIS: Workday, DarwinBox, ADP, SAP SuccessFactors and other major HR systems, set up by the integration team | same as 29 | SHIPPED (public help-doc list; **not** presented as a self-serve connector marketplace) |
| 31 | Sign-in: work email and password, one-time code to work email, or SAML 2.0 SSO | `vfit-os/specs/product/00-platform/auth-login-signup.md` | SHIPPED |
| 32 | SSO IdPs: Microsoft Entra ID (formerly Azure Active Directory), Okta, OneLogin, Ping Identity, and most other SAML 2.0 IdPs | `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-enable-sso.md` | SHIPPED |
| 33 | SSO takes about two weeks of Vantage Fit configuration once we have IdP metadata | same as 32 | SHIPPED |
| 34 | Provisioning is separate from SSO | same as 32 | SHIPPED |
| 35 | Lite Mode plus CSV: live in 1 to 2 days | `vfit-os/specs/product/00-platform/auth-login-signup.md` | SHIPPED |
| 36 | Four regional instances: India, US, EU, UAE. Chosen at setup, data stays in region | `vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md` | SHIPPED |
| 37 | 13 languages in the app and system emails, following the employee's device setting; admin console is English only | `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-change-language-settings.md` | SHIPPED, **flagged**, see §9.2 |
| 38 | One challenge spans countries; start, daily reset and end follow each participant's local midnight | `vantagefit-astro/content/en/help/admin/challenges/admin-can-i-run-challenges-across-time-zones.md` | SHIPPED |
| 39 | Rewards configured in USD, shown in local currency, with a country-relevant gift card catalogue | same as 38 | SHIPPED |
| 40 | A licence counts from an employee's first login, not from upload. Bulk and lumpsum contracts differ | `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-add-employees.md` | SHIPPED |
| 41 | Dashboard "Active Users" is not the billing count | same as 40, and `admin-dashboard-overview.md` | SHIPPED |
| 42 | SOC 2 Type II | `vfit-os/sources/VFit-Marketing-Content-Compacted.md` §2.15 | APPROVED, **flag to reviewer**, see §9.2 |
| 43 | Operates under HIPAA guidelines | same as 42 | APPROVED phrasing, never "HIPAA compliant" |
| 44 | Encryption: TLS in transit, SSL pinning in the mobile apps, AES at rest for sensitive profile fields | `vantagefit-astro/content/en/help/employee/getting-started/what-is-data-privacy.md`, `vfit-os/specs/product/00-platform/auth-login-signup.md` | SHIPPED |
| 45 | Notifications deleted after 14 days; activity and health data retained per contract | `vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md` | SHIPPED |
| 46 | An admin cannot delete an employee's account on their behalf | `vfit-os/specs/product/00-platform/auth-login-signup.md` | SHIPPED |
| 47 | Security documentation is available during evaluation | house line, already shipped on `[MULTI]` | Existing approved page copy |

### 5.4 Privacy architecture

| # | Claim | Source | Status |
|---|---|---|---|
| 48 | Health-risk cohort selection returns a count only, with the literal string "The list of users is not displayed to protect individual privacy." | `vfit-os/specs/product/03-health-wellness/workforce-health.md` | SHIPPED |
| 49 | Applying an audience filter marks the challenge Private | `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md` | SHIPPED |
| 50 | Admins CAN see enrollment, last active date, device type, rankings, team scores, points earned and redeemed | `vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md` | SHIPPED |
| 51 | Admins CANNOT see weight, BMI, HRA answers, lab values, mood logs, food diary, sleep detail | same as 50 | SHIPPED |
| 52 | Verbatim help-centre sentence: "Your HR team sees whether you are participating and your challenge rankings, but we cannot see your weight, health assessment results, lab reports, or personal health data." | same as 50 | SHIPPED, quoted verbatim |
| 53 | Leadership Insights sends no PII, only aggregated signal buckets | `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 54 | Leaderboard opt-out keeps an employee in the challenge and out of the rankings | `vfit-os/specs/product/00-platform/user-profile-settings.md` | SHIPPED |
| 55 | Wheelchair Mode | `vfit-os/specs/product/00-platform/user-profile-settings.md` | SHIPPED |

### 5.5 Proof and scale

| # | Claim as rendered | Source | Status |
|---|---|---|---|
| 56 | `Trusted by 100+ organizations worldwide` | `vfit-os/.claude/rules/data-accuracy.md` | APPROVED, the only aggregate scale claim |
| 57 | Logo words: Tata Motors, Wipro, Teva, Godrej, Texas Instruments, Heidrick & Struggles, Brazosport ISD | `vfit-os/.claude/rules/data-accuracy.md:22` | APPROVED names |
| 58 | Tata Motors, Step & Stride Challenge: 59% engagement rate over six months, 1,248 active participants | `data-accuracy.md:34-48`, `content/en/casestudy/tata-motors-case-study.md` | APPROVED-CLAIM |
| 59 | IBS Software, March to Fitness: 88% engagement rate over 28 days, 500+ active of 660 invited | `data-accuracy.md:72-85`, `content/en/casestudy/ibs-software-case-study.md` | APPROVED-CLAIM. **28 days, never 30** |
| 60 | Brazosport ISD, Fit Wars: 86% engagement rate over two weeks, 132 active participants | `data-accuracy.md:135-150` | APPROVED-CLAIM. **Engagement, not participation** |
| 61 | Industry average sustained participation is 20 to 30 percent | `data-accuracy.md:242-250` | APPROVED industry stat, labelled as an industry stat, never attributed to Vantage Fit |
| 62 | Ecosystem paragraph naming Vantage Recognition, Vantage Pulse, Vantage Perks | `vfit-os/.claude/rules/hr-buyer-lens.md:49-58`, `platform.md` §6.5 | APPROVED structure. Product name is **Vantage Recognition**, never "Vantage Rewards" |

### 5.6 Illustrative figures (mock-only, all carry `.mock-tag`)

`4,820` enrolled · `3,140` active · `$6,410` incentivization · `64%` participation rate · `+7 pts vs prev quarter` · `8,412 / 10,000` steps · `268 / 250` active calories · `8,140` 7-day average steps · `7h 12m` sleep · `9 min` mindful · `Day 12 of 28` · `#3 of 214` · `92 users inactive for 30+ days` · `412 employees match` · chart points `W1-W4` · `Goal 8,000`.

None of these is presented as a customer result. Each mock carries the visible `.mock-tag` and an `aria-label` ending "Figures shown are illustrative."

### 5.7 Explicitly excluded from this page

Slack · Microsoft Teams · ISO 27001 · ISO 27701 · GDPR compliance · "HIPAA compliant" · "HIPAA-Ready" · dedicated data center · 50+ countries · 190+ countries · 400+/200+/100+ companies · thousands/hundreds of organizations · 59-99% engagement · 81-94% · 60%+ avg engagement · 80%+ participation · 3X ROI · 12X platform cost · Accenture · Hershey · Cotiviti · any Beroe 96% · Landmark's 1B step ribbon · any completion rate · Insights Hub · the Wellness Score numeric range · the 25,000-step cap · Withings, Polar, Oura, Whoop · Apple, Facebook or personal-email sign-in · self-registration availability · a web app tab count · role-based admin permissions or an audit log · scheduled or emailed reports · department-level health-risk breakdowns · "Start Free Trial" · "Fit points" · any figure from `vc-dashboard-design/vc-data.js` · the Cloudinary certification raster · the product's own "HIPAA Compliant" compliance-card string.

---

## 6. Meta title and meta description

**URL:** `https://www.vantagefit.io/solutions/wellness-platform/`

**Meta title** (58 characters, no em-dash):
```
Employee Wellness Platform for Enterprise HR | Vantage Fit
```

**Meta description** (153 characters):
```
Vantage Fit is an employee wellness platform: one app for employees, one console for HR. Tracking, challenges, rewards, aggregate reporting. Book a demo.
```

**Alternate title if the shorter exact-match form is preferred** (39 characters): `Employee Wellness Platform | Vantage Fit`

**Optional head layer** (per the consolidated quality bar; harmless on a `noindex` mock, required on the shipped page):

- `<link rel="canonical" href="https://www.vantagefit.io/solutions/wellness-platform/">`
- `og:type` `website` · `og:title` same as the meta title · `og:description` `One app for employees, one console for HR, and an integration layer that connects wearables, SSO and HR systems.` · `og:image` `https://www.vantagefit.io/og/wellness-platform.png` · `twitter:card` `summary_large_image`
- Three `application/ld+json` blocks: `FAQPage` (all five questions and answers verbatim from §3 S9), `SoftwareApplication` (name Vantage Fit, applicationCategory Corporate Wellness, publisher Vantage Circle), `BreadcrumbList` (Home → Solutions → Wellness platform).

> Schema must match the rendered copy exactly and must carry no stat that is not in §5. `schema-data.js` drifts from visible copy on every page audited; do not repeat that.

**Adjacent keywords to weave into H2s and the FAQ, already placed:** employee wellness platform (H1, meta, FAQ Q1) · corporate wellness program software (FAQ Q1 body) · workplace wellness solution (suite band) · employee wellness app for companies (surfaces section) · wellness program for remote employees (routed to the sibling page).

---

## 7. Menu fit

### 7.1 Where this page sits

Wellness platform is **not** a Solutions mega-menu row. Per the signed-off preview it is:

1. **Featured on the Solutions hub** (`/solutions/`), as the hub's feature slot.
2. **Row 1 of the footer Solutions column**, above all nine program pages.
3. Reachable from the Solutions mega-menu's `.mega-foot` line: `The whole product on one page: Wellness platform` plus a `See the platform →` link.

**Menu label:** `Wellness platform`
**Recommended description line** (the preview does not fix one; this is `ia-claims-proof.md` §2's recommendation and I endorse it): `What Vantage Fit is, end to end`

### 7.2 Nav state on this page

- Put `is-current` on the **Solutions** `.nav-trigger`.
- There is no `.mega-link` for this page, so instead mark the `.mega-foot` `See the platform` link: change its `href` to `#top`, add `aria-current="page"`, and give it `.is-page`-equivalent treatment (`color: var(--ink); font-weight: 700;`).
- In the footer Solutions column, give `Wellness platform` `aria-current="page"` and `style="color:#fff;font-weight:700"`.
- **Do not** mark any Solutions row `is-page`, and do not add a new mega-menu row for this page.

### 7.3 Relationship to the data in → data out → action chain

This page is not in section ② and does not sit in the chain. It sits **above both sections**: it is the only page in the set allowed to describe the whole system, and it links **down** into both columns.

Its job relative to the chain is to make the chain legible before a buyer enters it. The system map draws `Capture → Programs → Standing → Rewards → Insight → Reach`, which is the same causal spine that section ② states as `Health Risk Assessment → Workforce health insights → Wellness rewards program`. Section 7 of the page then hands the reader off to each of those three pages by name, in that order, under the column header `What you want to measure`.

### 7.4 Open IA questions flagged, not resolved here

1. **URL prefix.** `vfit-os/.claude/rules/seo-conventions.md:69,83` says solution pages are root-level with no `/solutions/` prefix and instructs "do not propose URL changes". The signed-off menu and `REMAINING-SOLUTIONS-PROMPT.md` both use `/solutions/…`. **This brief follows the signed-off menu.** A human must reconcile the SEO convention.
2. **Slug collision.** `/solutions/wellness-challenges/` collides with the shipped `/solutions/wellness-challenge`, and it is not settled whether the new library page replaces or sits above the live `vantagefit.io/wellness-challenges/` (21 challenges, 21 child pages). This page links to `/solutions/wellness-challenges/` per the signed-off menu. Flagged for a human; not blocking.

---

## 8. Cross-links

Two to three internal links per page is the house rule; a platform page is the deliberate exception because routing is its job. Every link uses descriptive anchor text.

### 8.1 Outbound from this page

| From section | To | Anchor text | Why this link exists here |
|---|---|---|---|
| S7 col 1 | `/solutions/wellness-challenges/` | `Wellness challenges` | The Programs node of the map, expanded |
| S7 col 1 | `/solutions/step-challenges/` | `Step challenges` | Most common first program |
| S7 col 1 | `/solutions/multi-activity-challenges/` | `Multi-activity challenges` | Breadth beyond steps |
| S7 col 1 | `/solutions/remote-team-wellness/` | `Remote & hybrid team challenges` | Distributed workforce, the multi-country buyer |
| S7 col 1 | `/solutions/virtual-marathon/` | `Virtual marathon` | Event format |
| S7 col 2 | `/solutions/health-risk-assessment/` | `Health Risk Assessment` | The Capture node's third line, expanded |
| S7 col 2 | `/solutions/workforce-health-insights/` | `Workforce health insights` | The Insight node, expanded |
| S7 col 2 | `/solutions/wellness-rewards-program/` | `Wellness rewards program` | The Rewards node, expanded |
| S7 col 3 | `/features/activity-tracking/` | `Activity & health tracking` | Capture capability detail |
| S7 col 3 | `/features/integrations/` | `Integrations` | Surface 3, expanded |
| S7 col 3 | `/features/security-and-compliance/` | `Security & compliance` | S6 and S8, expanded |
| S7 col 3 | `/features/wellness-leagues/` | `Wellness leagues` | The gated Standing feature |
| S7 suite band | `vantagecircle.com/products/rewards-recognition/` | `Vantage Recognition` | Ecosystem, same tab, no nofollow |
| S7 suite band | `vantagecircle.com/products/employee-surveys/` | `Vantage Pulse` | Ecosystem |
| S7 suite band | `vantagecircle.com/newperkspage/` | `Vantage Perks` | Ecosystem |
| S4 `.proof-fine` | `/casestudy/` | `Read customer stories` | Stats hyperlink to their sources |
| S8 trust actions | `/features/security-and-compliance/` | `Explore security & compliance` | Second, deliberate |
| Hero, S8, S10 | `/request-demo/` | `Book a demo` | Primary CTA |
| S10 | `/pricing/` | `See pricing` | Procurement route |

**Deliberate omission:** the standard three-card `.related-screen` is **not** on this page. Section 7 supersedes it with twelve destinations and better reasons, and the five-column footer carries all nine Solutions links. Adding a three-card outro after a twelve-link grid would be padding, which this page set explicitly forbids. The builder should not add one back.

### 8.2 Inbound to this page (for the other five briefs)

| From | Where | Anchor |
|---|---|---|
| Solutions hub `/solutions/` | The feature slot at the top of the hub | `Wellness platform` |
| All six pages | Footer Solutions column, row 1 | `Wellness platform` |
| All six pages | Solutions mega-menu `.mega-foot` | `See the platform →` |
| `/solutions/workforce-health-insights/` | Its "how this fits the wider system" beat | `See the whole platform` |
| `/solutions/wellness-rewards-program/` | Its closing routing row | `See the whole platform` |

---

## 9. Assumptions and gaps

### 9.1 Assumptions I made

1. **The map's loop-closure arrow (`Insight → Reach → Capture`) is presented as a designed loop.** Each individual hop is cited SHIPPED (Recommended Actions pre-fills a nudge; audience rules take a Health Risk Code; push and email drive app opens). The framing "one loop" is editorial synthesis of cited hops, not a claim from a single source. It is defensible, and it is the page's whole argument, so a reviewer should read it as such.
2. **"Step into Spring 2026" is an invented program name**, chosen because `ia-claims-proof.md` §5.3 names it as an example of a correctly formatted formal challenge name. It appears only inside mocks, all of which carry `Illustrative data`.
3. **The `.dash-url` renders `dashboard.vantagecircle.com` as text.** The shipped component uses a blank pill. This is a small addition, justified because the real URL is a cited fact and it makes the surface credible.
4. **The suite paragraph is rendered in US English** ("Organizations"), against the approved source's British spelling, per the house rule that new copy is US English. If the claims reviewer requires the approved string verbatim, restore "Organisations".
5. **The `Health risk code` field renders `1 selected` rather than a named code.** Code labels are undocumented. Do not let a later edit substitute a plausible-sounding condition name.
6. **The trust band's four cards were rewritten to infrastructure** so they do not duplicate the S6 privacy argument. The chrome's default card 1 ("Private by design") was deliberately replaced.

### 9.2 A human must verify before publish

| # | Item | What is needed |
|---|---|---|
| 1 | **"13 languages"** | Two dossier files disagree on whether to print a number at all. `platform.md` §4.5 rules "13", `ia-claims-proof.md` §8.25 says print none. I followed the precedence rule to the help doc. **Add `<!-- VERIFY: 13 languages, sourced to admin-how-do-i-change-language-settings.md. The same article's table lists 14 locale rows and the legacy accessibility page says 14+. Confirm before publishing. -->` in the HTML next to the value.** If the reviewer refuses the number, the fallback copy is: `The app and system emails are localized and follow each employee's device setting. The admin console is English only.` |
| 2 | **SOC 2 Type II** | Approved in the register, but an internal audit records it as "not documented in the KB" beyond one line and asks for re-verification with security. Confirm before publish. It appears in the spec table, the trust card and the `.mark-strip`. |
| 3 | **HRIS list** | The public help-doc list is Workday, DarwinBox, ADP, SAP SuccessFactors "and other major HRIS systems". The wider spec list is client-specific work. Confirm the four named systems are still safe to name publicly. |
| 4 | **Tata / IBS / Brazosport usage caps** | `content-standards.md:25` requires checking the Usage Caps ledger in `content-marketing/plans/phase-1-blog-update-guide.md` before reusing a case study. Check the three programs in the proof strip and update the ledger. |
| 5 | **URL prefix conflict** | `/solutions/…` vs the root-level rule in `seo-conventions.md`. Unresolved; menu followed. |
| 6 | **Wellness challenges slug collision** | `/solutions/wellness-challenges/` vs shipped `/solutions/wellness-challenge`, and whether the new library page replaces or sits above `vantagefit.io/wellness-challenges/`. This page links to the signed-off URL. |
| 7 | **Feature URLs** | `/features/wellness-leagues/` and `/features/incentivization-and-rewards/` were corrected in `chrome.html` against `marketing-urls.js` `FEATURE_SLUGS`. Re-confirm the four Features links in S7 col 3 resolve. |

### 9.3 Genuine gaps in the source material

| Gap | How the page is designed around it |
|---|---|
| **No documented admin roles beyond "HR Admin"**, no permission matrix, no audit log (audit log is ROADMAP Backlog) | The spec table names only the HR Admin role. There is no roles-and-permissions module anywhere on the page, and the FAQ does not invite the question. |
| **No approved customer proof for a platform-level or ROI claim** | The proof strip carries three engagement figures attached to the participation claim only. There is no ROI number, no cost-saving number and no multiplier anywhere on the page. |
| **No approved figure for "time to first challenge" beyond the 1 to 2 day Lite Mode line** | The rollout section quotes only what is sourced, and marks SSO as an additive two weeks rather than a total. |
| **No sourced country coverage for the gift card catalogue** | Copy says "a country-relevant gift card catalogue" and "the value holds across countries". The 190+ figure is omitted on this page. |
| **HRA question count and time to complete are unsourced** | The HRA appears only as one line in the Capture node and one link in S7. No count, no duration, nothing depends on either. |
| **App-store ratings and awards are UNVERIFIED for freshness** | No ratings row and no awards row on this page. If the claims reviewer re-verifies them, the natural home is a strip under the logo band, not a new section. |
| **Insights Hub** | Excluded entirely. The admin console mock renders six nav items and Insights Hub is not one of them. |

### 9.4 Build checklist for the mock

- [ ] `<link rel="stylesheet" href="../styles/enterprise.css">` and nothing else external except the Noto Sans font link
- [ ] `<meta name="robots" content="noindex, nofollow">`
- [ ] Skip link is the first child of `<body>`
- [ ] Exactly one `h1`; every `<section>` has an `id` and `aria-labelledby`
- [ ] Sub-items inside lists are `<b>`, not `<h3>`
- [ ] Every mock: `role="img"`, full `aria-label`, `aria-hidden` on decorative children, visible `.mock-tag` wherever a number appears
- [ ] Tabular numerals on every digit column
- [ ] `.btn-primary` contrast override present
- [ ] Forced-colors fallback for `.stat` and `h1 em`
- [ ] Eyebrow contrast lift on `.system-screen`, `.why-screen`, `.privacy-screen`
- [ ] `.sysmap` scrolls horizontally inside itself below 900px; the page body never scrolls horizontally
- [ ] Grayscale `?gray` hook present, and the system map still reads with hue removed
- [ ] No em-dash anywhere in body copy (the only permitted one is inside the verbatim help-centre quotation, which contains none, so the page should contain zero)
- [ ] No `.related-screen`
- [ ] Trust plaque is the typeset `.mark-strip`, never a raster
- [ ] `VERIFY` HTML comment beside the 13-languages value
