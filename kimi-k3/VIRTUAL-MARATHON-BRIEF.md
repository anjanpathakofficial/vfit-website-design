# Virtual Marathon page — brief & copy deck

Deliverable: `vantage-fit-virtual-marathon-v1.html` (same folder).

- **Page type:** individual solutions / use-case page under "Run a Challenge," child of the Solutions hub.
- **Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary: program managers; tertiary gate: IT/security.
- **Positioning spine:** extends the homepage north star (employee participation) to a page-level promise: *a company marathon event every employee can enter, with finish-line numbers HR can share.*
- **Primary CTA:** Book a demo · **Secondary:** See pricing.
- **Visual system:** `../styles/enterprise.css` + patterns from `../styled-homepage/` and my prior `vantage-fit-steps-challenge-v1.html` (nav, mega menus, hero dash/phone composition, stat cards, FAQ, trust band, final CTA, footer). The Virtual Marathon mega-menu item carries the `aria-current="page"` "You're here" marker.

---

## 1. Research takeaways (product truth, not the old page)

Sources at latest `main`: `vantagefit-astro` (help docs, legacy use-case YAML, case studies), `vc-os/vfit-os` (challenge specs, data-accuracy rules), `vc-dashboard-design` (via Steps research; reports/console behavior).

### What the live page gets wrong or misses

The current `/virtual-marathon/` page (`content/en/pages/use-cases/virtual-marathon.yaml`) is a thin event brochure: hero, three race levels (5/10/21 km), global participation, live leaderboard, badges. Against help docs and specs, it misses or mis-weights:

1. **The mechanic itself.** Nowhere does the old page say distance comes from *everyday steps, not GPS* — the single biggest inclusivity fact (`admin-how-do-i-create-e-marathon.md`: "Distance is calculated from step count, not GPS… their regular daily steps are automatically counted"). Default 1,000 steps = 1 km, configurable ratio, km or miles.
2. **Two durations, one format.** The old page sells only a one-day event. Product truth: the E-Marathon runs one-day *or* multi-week (2–4 weeks recommended for meaningful distance) (`admin-how-do-i-create-e-marathon.md`, `admin-when-to-use-a-one-day-virtual-marathon.md`).
3. **Tiered rewards.** Multi-target single-day marathon with auto-scaled rewards (higher distance tier, higher reward) is in the product spec (`vfit-os/specs/02-challenges-gamification/challenge-marathon.md`) and hinted by the old page's "unique rewards" line but never explained as a fairness/inclusion mechanic.
4. **A real "when to run it" playbook.** The help docs contain a genuinely strategic answer: program kickoff, observance days (World Health Day, World Heart Day), office anniversaries, re-engaging dormant employees, regional head-to-heads, midpoint energizer or finale of a longer program — plus when *not* to use a one-day format (`admin-when-to-use-a-one-day-virtual-marathon.md`). The old page has none of this.
5. **GPS race-day events exist** as a managed format: "Marathon Event — real GPS-tracked marathon with live distance tracking, used for physical running events" (`admin-what-challenge-formats.md`, ops-only). The old page never bridges virtual to physical race culture.
6. **Simplest setup in the catalog.** "E-Marathons are intentionally simple… That is all the configuration needed" (name, dates, ratio, audience, publish). A strong HR-time-to-value proof the old page omits.
7. **Global operation depth.** Time-zone-localized start/end, USD rewards shown in local currency, country-relevant gift-card catalogues (`admin-can-i-run-challenges-across-time-zones.md`) — the old page says "adjusts for time zones" without substance.
8. **Recognition & reporting.** Distance-milestone badges (up to marathon-distance), branded completion certificates, day-of push notifications, live admin dashboard, leaderboard CSV / participation report / points ledger (challenges + reports help docs). Old page: one badges bullet, zero reporting.
9. **Inclusion detail:** marathon distance tasks support run, cycle, and *wheel* tags (`challenge-marathon.md` config), and cumulative scoring means no streak pressure (`what-is-an-e-marathon.md`). Both serve the participation thesis; neither is marketed.
10. **Proof.** The old page has zero stats. The case-study library has real marathon/walkathon results, three of them US companies (see §4).

### Positioning constraints honored

- North star = participation; tone = inclusive event, not elite-runner culture (`MISSION.md`).
- Banned vocabulary avoided ("best-in-class," "revolutionize," etc.).
- Only approved aggregate claim: "100+ organizations" (`vfit-os/.claude/rules/data-accuracy.md`).
- GPS "Marathon Event" presented as managed/account-manager-configured, never self-serve (ops-only per `admin-what-challenge-formats.md` and consolidated guardrails).
- No team-leaderboard claim for E-Marathon (help docs show individual distance rankings only; team mechanics are documented for Streak/Journey/Custom).
- The one-day doc's internal participation ranges (25–60%) treated as internal guidance, not marketing stats. Not used on the page.
- No cash prizes, no self-serve employee enrollment implied.

---

## 2. Page structure & rationale

Ten sections, deliberately leaner than my Steps page (per consolidated boss feedback: short one-line card copy, no redundant ledes, proof only because real stories exist):

| # | Section | Job |
|---|---------|-----|
| 1 | Hero + logo band | Promise ("a marathon your whole company can enter"), dash + phone product visual of a live event day, two real proof chips, trust strip |
| 2 | Problem | Name why physical race events exclude most of a workforce (runners only, one city, logistics cost, over by 9 a.m.) and reframe: keep the event energy, drop the barriers |
| 3 | How it works | The mechanic the old page never explains: steps become distance, no GPS, cumulative, km or miles. Plus the distance-tier strip (5K/10K/half/full) with auto-scaled rewards — the inclusion mechanic |
| 4 | Ways to run it | Buyer self-selects: one-day event vs multi-week E-Marathon vs managed GPS race day. Light links to sibling programs |
| 5 | Event playbook | The strategic "when to run one" content from the help docs, packaged as five occasion cards. This is the page's unique value vs the Steps page |
| 6 | For HR | Simplest setup in the catalog + promotion tools + time zones + leave-with-numbers reporting (event-recap mock) |
| 7 | Proof | Four real, sourced results; three US companies plus one global-scale event |
| 8 | Trust | Compact dark band for the IT gate (global event touches every employee's phone) |
| 9 | FAQ | Six rollout objections, all answers sourced from help docs |
| 10 | Final CTA + footer | Demo framed as "pick a date, we'll build your marathon" |

Why this order: a marathon page is bought as an *event*, not a habit program, so the story is occasion-led. Problem (physical races exclude) → mechanic (steps become distance, everyone can enter) → durations (pick your format) → occasions (when to put one on the calendar) → run/report (HR effort and proof) → results → trust → objections. The playbook section sits before For HR because "when would I use this?" is the buyer's first question after "what is it?"; the old page's failure to answer either is its core weakness.

Deliberately excluded: pricing detail (links out), a formats-explorer of all five challenge types (that belongs to the Steps page; here it would dilute), team-challenge mechanics (not documented for E-Marathon), the help docs' internal participation-range table (internal guidance, not marketing proof), video testimonials (no licensed assets).

---

## 3. Full copy deck

### S1 Hero
- Eyebrow: Solutions · Virtual Marathon
- H1: **A marathon your whole company can enter.**
- Lead: Vantage Fit turns everyday steps into marathon distance. No GPS routes, no wearables to buy, no running required. Employees pick a distance that fits them, and HR gets a finish-line report worth sharing.
- CTAs: Book a demo · See pricing
- Note chips: No wearable or GPS required · Distances from 5K to a full marathon · Trusted by 100+ organizations
- Hero visual: admin dash mock ("World Heart Day Marathon," sample metrics: 2,140 enrolled / 1,904 checked in / 18,442 km together, distance leaderboard in km) + employee phone mock (12.4 km of 21 km, rank, points, "Counted from steps, no GPS") + proof chips (94% Embrace Pet Insurance, 42 km avg Carter Myers). Dashboard figures are illustrative sample data; the two chip figures are real case-study results.
- Logo band: Trusted by 100+ organizations in 50+ countries — TATA MOTORS · WIPRO · ACCENTURE · TEVA · TEXAS INSTRUMENTS · HERSHEY · BRAZOSPORT ISD (mirrors sibling pages)

### S2 Problem — "A parking-lot 5K was never going to include everyone."
Lead: skipped (lean rule; heading carries it).
Pain cards:
1. **Only the runners show up** — A traditional race draws the same athletic few, and everyone else watches from the sidelines.
2. **One city, one morning** — Remote and global teams can't join an event that happens in one parking lot at 7 a.m.
3. **Logistics eat the budget** — Permits, route marshals, insurance, and t-shirts, all before anyone takes a step.
4. **Over by 9 a.m.** — A nice photo, a sweaty email, and no numbers leadership can use.

Pivot: A virtual marathon keeps the shared-start-line energy and drops every barrier. Same event, every office, every fitness level.

### S3 How it works — "Every step becomes distance."
Three steps:
1. **Move as you normally do** — Steps sync from the phone or wearable employees already have. Distance is calculated from step count, not GPS, so no routes and no workouts to start.
2. **Watch the distance add up** — 1,000 steps becomes a kilometer by default, on a ratio and in units (km or miles) you choose. A lunch walk counts as much as a morning run.
3. **Cross your finish line** — The leaderboard ranks total distance over the event. Progress is cumulative, so a rest day never resets anyone.

Tier strip: **5K** first finish line · **10K** the classic · **Half** 21.1 km · **Full** 42.2 km · or set a custom distance.
Support line: Everyone picks the distance that motivates them. Bigger targets earn bigger rewards, scaled automatically. Run, cycle, or wheel.

### S4 Ways to run it — "One format, three event styles."
| Style | Tag | Copy | Best for |
|---|---|---|---|
| One-day virtual marathon | 24 hours | A single shared moment: everyone competes on the same day across distance tiers, and results land within 24 hours. | program launches and observance days |
| Multi-week E-Marathon | 2–4 weeks | Distance accumulates over weeks, so "Walk Across America" style campaigns have room to breathe. The simplest setup in our challenge catalog. | health months and themed campaigns |
| GPS race day | Managed format | A real GPS-tracked marathon with live distance tracking for physical running events, configured with your account manager. | companies with an established running culture |

Related links: Step challenges → · Team challenges → · Year-round wellness program →

### S5 Event playbook — "When to put one on the calendar."
1. **Program kickoff** — Launch or relaunch your wellness program with a shared moment; the energy carries into the challenges that follow.
2. **Observance days** — World Health Day, World Heart Day, a company anniversary. The event maps to the date, and participation becomes a quotable metric.
3. **Re-engagement spark** — One day feels manageable in a way a 30-day program doesn't. A low-barrier event pulls dormant employees back into the app.
4. **Regional head-to-head** — Which office or region logs the most kilometers? Clean, fast, unambiguous bragging rights.
5. **Energizer or finale** — Punctuate a longer program when engagement dips, or close a quarter with a finish line.

Support line: Building a daily habit instead? A one-day event is a punctuation moment, not a program. Pair it with a Streak or Custom challenge for the weeks that follow.

### S6 For HR — "Launch in an afternoon. Recap it the next morning."
- **The simplest setup we make** — Name, dates, distance ratio, audience, publish. No weekly themes, no task lists, no scoring rules to configure.
- **Promotion built in** — Announce by email and in-app banner ahead of the event, then send a day-of push notification when the start line opens.
- **One event, every time zone** — Start and end times localize to each participant's midnight, so a one-day marathon is one true day everywhere. Rewards set in USD display in local currency.
- **Leave with numbers** — Watch check-ins and distance live, then share the recap: who joined, how far the company went, who crossed each finish line.

Recap mock: Participation Report · Challenge Leaderboard (CSV) · Transaction Report — footer: "World Heart Day Marathon · 1,904 checked in · 18,442 km together · recap ready next morning" (illustrative).

### S7 Proof — "Finish-line numbers from real events."
- **94%** — Embrace Pet Insurance (Insurance · Ohio): engagement across an 8-week company marathon — 19.3M+ steps logged together.
- **42 km** — Carter Myers Automotive (Automotive · Virginia): average distance per employee in a 4-week walkathon. A full marathon each, from everyday steps.
- **89%** — Cotiviti (IT services · Utah): engagement in a week-long virtual walkathon — 19,400+ km covered by 540+ employees.
- **24 countries** — Global Corporate Walkathon (hosted on Vantage Fit): 3,700+ participants and 74 teams in one month-long event.

Disclaimer: Results from published Vantage Fit customer case studies. Engagement and distance figures are as reported by each program.

### S8 Trust — "Global event. Local data."
- **Compliance** — HIPAA-aligned and GDPR compliant, with SOC 2 Type II and ISO 27001/27701 documentation available during evaluation.
- **Regional data residency** — Employee data stays in its assigned region: US, EU, India, or UAE.
- **SSO & HRIS ready** — SAML 2.0 with Okta, Azure AD, OneLogin, or Ping; HRIS and SFTP provisioning keep rosters in sync.
- **Private by design** — Admins see aggregate metrics, never individual health profiles. Leaderboard opt-out is built in.

### S9 FAQ — "Questions HR teams ask."
1. **Do employees have to run, or use GPS?** No — everyday steps convert to distance automatically; no routes, no GPS workouts, no running required.
2. **Do employees need a fitness tracker?** No — phones count steps on their own; Fitbit and Garmin connect directly; Apple Watch and most bands sync via Apple Health; one primary device, no double-counting.
3. **One day or multi-week: which should we pick?** One-day for a shared moment tied to a date; 2–4 weeks for distance campaigns and habit support. Many teams pair them: a one-day kickoff, then a multi-week main event.
4. **Can our global offices join the same event?** Yes — start and end times localize per time zone, and rewards display in local currency across 190+ countries.
5. **How do the distance tiers work?** Employees choose 5K, 10K, half, or full marathon (or a custom distance you set). Rewards scale with the target automatically, so effort is recognized at every level.
6. **What can we report afterward?** Live check-in and distance dashboards during the event; leaderboard CSV, participation report, and a points transaction ledger after it.

### S10 Final CTA — "Pick a date. We'll build your marathon."
Book a 30-minute walkthrough and we'll mock up a virtual marathon for your workforce: tiers, theme, and the reporting behind it.
Checks: Live in days · No wearables or GPS required · One event across every time zone · Rewards in local currency.
Note: Give every employee a finish line worth crossing.

---

## 4. Stat & claim sources

| Claim on page | Source |
|---|---|
| Embrace Pet Insurance 94% engagement, 8-week marathon, 19,355,000+ steps, 71+ participants | `vantagefit-astro/content/en/casestudy/embrace-pet-insurance-marathon.md` |
| Carter Myers Automotive 42+ km avg distance, 732+ participants, 4-week walkathon | `content/en/casestudy/carter-myers-automotive-virtual-walkathon.md` |
| Cotiviti 89% engagement (per case-study title), 540+ participants, 19,461+ km total, week-long walkathon | `content/en/casestudy/cotiviti-virtual-walkathon.md` |
| Global Corporate Walkathon: 3,700+ participants, 74 teams, 24 countries, 30 days | `content/en/casestudy/global-corporate-virtualwalkathon.md` (hosted on Vantage Fit; labeled as such) |
| Steps→distance, no GPS, default 1,000 steps = 1 km, configurable ratio, km or miles, cumulative not daily, 2–4 week guidance, simplest setup (5 fields) | `content/en/help/admin/challenges/admin-how-do-i-create-e-marathon.md` |
| Employee-facing mechanic: no streak pressure, consistency over bursts, distance leaderboard | `content/en/help/employee/challenges/what-is-an-e-marathon.md` |
| One-day marathon occasions (kickoff, observance days, anniversaries, re-engagement, head-to-head, energizer/finale), when not to use, distance tiers 5K/10K/half/full, promote 1 week ahead, day-of push, same-day results | `content/en/help/admin/challenges/admin-when-to-use-a-one-day-virtual-marathon.md` |
| Tiered auto-scaled rewards; distance types run/cycle/wheel; single-day validation | `vfit-os/specs/02-challenges-gamification/challenge-marathon.md` |
| GPS "Marathon Event" as ops-only managed format | `content/en/help/admin/challenges/admin-what-challenge-formats.md` |
| Time-zone localization; USD→local currency rewards | `content/en/help/admin/challenges/admin-can-i-run-challenges-across-time-zones.md` |
| No wearable required; device mix; one primary device | `content/en/help/employee/getting-started/do-i-need-a-wearable.md`, `can-i-connect-multiple-devices.md` |
| Distance-milestone badges; branded certificates | `content/en/help/admin/challenges/admin-how-do-badges-work.md`, `admin-how-do-i-configure-certificates.md` |
| Reports: Participation, Leaderboard CSV, Transaction | `content/en/help/admin/reports/admin-what-reports-are-available.md` |
| 190+ countries rewards | `vfit-os` `audit/site-refresh-2026-07/product-code-specs.md` §SOLI |
| SSO providers; data residency regions; aggregate-only admin views | `vfit-os` `product-code-specs.md` |
| "100+ organizations in 50+ countries" logo band | Approved aggregate per `vfit-os/.claude/rules/data-accuracy.md`; wordmarks mirror sibling pages |

No stats, customers, or capabilities were invented. Dashboard/recap figures inside mocks are labeled-style illustrative sample data; real numbers appear only in proof chips and the proof section.

---

## 5. Meta drafts

- **Title (57 chars):** `Corporate Virtual Marathon for Global Teams | Vantage Fit`
- **Alt title (59 chars):** `Virtual Marathon for Employees — No GPS Needed | Vantage Fit`
- **Description (159 chars):** `Run a virtual marathon your whole company can enter. Everyday steps convert to distance automatically, tiered courses from 5K to 42K, and reporting HR can share.`
- **URL:** keep `/virtual-marathon/` (existing SEO equity).
- Suggested schema for production: FAQPage for S9; BreadcrumbList (Solutions → Virtual Marathon).

## 6. Assumptions & gaps

1. **Compliance claims need verification.** Same flag as the Steps brief: HIPAA/GDPR/SOC 2/ISO phrasing mirrors sibling mocks; vfit-os data-accuracy rules treat live-site compliance claims as unapproved sources. Verify with the security team before production.
2. **GPS Marathon Event** is presented strictly as a managed, account-manager-configured format (ops-only per help docs and consolidated guardrails).
3. **Cotiviti's 89% engagement** comes from the published case-study title (the body lists participant/step/distance totals but not the rate). Sourced, but worth a re-check against the customer's approved numbers before production.
4. **Global Corporate Walkathon proof** is Vantage Fit's own hosted event, not a customer; labeled "hosted on Vantage Fit" on the card to stay honest.
5. **"Run, cycle, or wheel"** is grounded in the spec's distance-type config (run/cycle/wheel tags); phrased as inclusion, not as a separate product feature. Worth a PM confirmation that wheel mode ships in the marathon UI.
6. **No team-leaderboard claims** for E-Marathon (documented only for other formats). If team scoring ships for marathons later, S3/S4 can gain a line.
7. **US-market framing:** three of four proof cards are US companies; global scale is carried by the time-zone/currency story and the 24-country event card.
8. Dashboard and recap figures are illustrative sample data, consistent with sibling mocks; real figures appear only in labeled proof elements.
