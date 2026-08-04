# Steps Challenge page — brief & copy deck

Deliverable: `vantage-fit-steps-challenge-v1.html` (same folder).
Named `STEPS-CHALLENGE-BRIEF.md` rather than `SOLUTIONS-BRIEF.md` so it doesn't overwrite the existing Solutions-hub brief in this folder.

- **Page type:** individual solutions / use-case page (child of the Solutions hub), not a hub and not a homepage.
- **Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; secondary: program managers; tertiary gate: IT/security.
- **Positioning spine:** extends the homepage north star — employee participation — to one page-level promise: *a step challenge employees join and finish, with numbers HR can report.*
- **Primary CTA:** Book a demo · **Secondary:** See pricing.
- **Visual system:** `../styles/enterprise.css` + patterns from `../styled-homepage/` (nav, mega menus, hero dash/phone composition, `.steps` cards, trust band, final CTA, footer). Nav and footer mirror `vantage-fit-solutions-v1.html` for consistency; the Steps Challenge mega-menu item carries an `aria-current="page"` "You're here" marker.

---

## 1. Research takeaways (product truth, not the old page)

Sources pulled at latest `main`: `vantagefit-astro` (help docs + case studies), `vc-dashboard-design` (admin prototypes/specs), `vc-os/vfit-os` (product specs, positioning, data-accuracy rules).

### Capabilities the live page under-sells or misses

The current `/steps-challenge/` page (`content/en/pages/use-cases/steps-challenge.yaml`) is a thin brochure: hero, four one-word format bullets, leaderboards, rewards bullet, one coach testimonial, three thin FAQs. Against the help docs and product specs, it misses:

1. **Custom multi-week challenges entirely** — the format help docs call the go-to for most clients: weekly themes, 27 task types (`admin-how-do-i-create-custom-challenge.md`, `admin-what-tasks-can-i-include-in-a-custom-challenge.md`).
2. **Team mechanics** — team score = *average of member effort* (fairness), admin/CSV/employee-created teams, separate team leaderboard (`admin-how-do-i-manage-teams.md`, `how-do-teams-work.md`).
3. **Global operation** — start/end/daily reset localized to each participant's midnight; USD-configured rewards shown in local currency with country-relevant gift-card catalogues (`admin-can-i-run-challenges-across-time-zones.md`).
4. **Parallel challenges** — unlimited concurrent challenges; one walk counts toward all of them (`admin-can-i-run-multiple-challenges-in-parallel.md`).
5. **Fairness & anti-cheat** — daily step caps, trusted step sources, suspicious-activity inspection, leaderboard opt-out, 3-day post-end sync buffer before winners are picked (`how-does-the-leaderboard-work.md`, `can-i-opt-out-of-leaderboard.md`, `admin-how-do-i-create-race-challenge.md`; vfit-os `specs/02-challenges-gamification/challenge-system-overview.md`).
6. **Device reassurance** — no wearable required (Apple Health / Google Fit on phones), direct Fitbit + Garmin, Apple Watch and most bands via Apple Health, one primary device to prevent double-counting (`do-i-need-a-wearable.md`, `can-i-connect-multiple-devices.md`).
7. **Rewards depth** — real-time point crediting, gift-card wallet shared with Vantage Circle recognition, OTP-secured bulk uploads (`admin-how-wellness-rewards-work.md`, `how-do-i-redeem-points.md`).
8. **Recognition layer** — automatic badges (7 categories, 25+ levels, 3,000→40,000 steps) and branded auto-generated completion certificates (`admin-how-do-badges-work.md`, `admin-how-do-i-configure-certificates.md`).
9. **Admin story** — pre-built templates, audience targeting (department/country/age/language), CSV enrollment, live participation dashboard, Participation Report / leaderboard CSV / Transaction Report (`admin-how-do-i-use-templates.md`, `admin-how-do-i-set-target-audience.md`, `admin-what-reports-are-available.md`; vc-dashboard-design `vc-data.js`, `docs/modules/wellness.md`).
10. **Named proof** — the old page has zero stats; the case-study library has a deep bench of US step-challenge results (see §4).

### Positioning constraints honored (from vfit-os)

- North star = participation/adoption; tone = inclusive habit product, not gym-bro leaderboard culture (`MISSION.md`).
- Banned vocabulary avoided: "synergy," "leverage," "best-in-class," "leading provider," "revolutionize," "behavior change," "wellness compliance," "health monitoring" (`.claude/CLAUDE.md`, `audit-standard.md`).
- Only approved aggregate claim used: **"100+ organizations"** (`.claude/rules/data-accuracy.md`).
- Wellness Leagues / Wellness Score deliberately **not marketed** (annual-contract gated per `product-code-specs.md`).
- No self-serve employee joining implied (enrollment is admin-driven); no cash/monetary prizes marketed; no Health Connect claims for Android; backlog wearables (Withings/Polar/Oura/Whoop) not listed.

---

## 2. Page structure & rationale

Nine sections, ~4,000px of scroll — a focused conversion page:

| # | Section | Job |
|---|---------|-----|
| 1 | Hero + logo band | Promise ("join — and finish"), dual admin/employee product visual, two named proof chips, trust strip |
| 2 | Problem | Name the buyer's lived experience (week-one spike, week-three silence) and reframe it as a design problem, not a motivation problem |
| 3 | Formats | Five self-serve formats + parallel running as a 6th card; buyer self-selects; light links to sibling programs |
| 4 | Participation engine | The four mechanics that answer the problem section: zero-effort tracking, fair competition, real rewards, recognition beyond the podium |
| 5 | For HR | Launch (templates, targeting, time zones) + measure (report mock) — the "numbers leadership will believe" story |
| 6 | Proof | Four named US customer stat cards, all traceable to published case studies |
| 7 | Trust | Dark band for the IT gate: compliance, residency, SSO/HRIS, privacy-by-design |
| 8 | FAQ | Six questions that double as objection handling; all answers sourced from help docs |
| 9 | Final CTA + footer | Demo ask framed as "see *your* company's challenge" |

Why this order: problem → solution mechanics → admin control → proof → trust mirrors how an HR buyer evaluates ("will people use it?" → "can I run it?" → "did it work for others?" → "will IT sign off?"). Formats come early because format choice is the page's namesake intent and supports SEO; the engine section is where differentiation lives, so it gets the most visual weight.

Deliberately excluded: pricing detail (links out), video testimonials (no licensed assets for this page), Wellness Leagues/Wellness Score (gated), industry variants (not warranted for a single-program page).

---

## 3. Full copy deck

### S1 Hero
- Eyebrow: Solutions · Steps Challenge
- H1: **The step challenge employees join — and finish.**
- Lead: Vantage Fit turns daily steps into friendly competition with real rewards. Steps sync automatically from the phones and wearables your people already carry — and every walk shows up in reporting HR can stand behind.
- CTAs: Book a demo · See pricing
- Note chips: No wearable required · Live in days, not months · Trusted by 100+ organizations
- Hero visual: admin dash mock ("Global Step Challenge", sample metrics 2,140 enrolled / 1,862 active / 46 teams / 87% participation, team leaderboard) + employee phone mock (steps, streak, points, "Synced from Apple Health") + proof chips (91% SRS Medical, 87% DLA). All dashboard figures are illustrative sample data; the two chip figures are real case-study results.
- Logo band: Trusted by 100+ organizations in 50+ countries — TATA MOTORS · WIPRO · ACCENTURE · TEVA · TEXAS INSTRUMENTS · HERSHEY · BRAZOSPORT ISD (mirrors the Solutions hub mock for consistency)

### S2 Problem — "Most step challenges peak in week one."
Lead: A launch-day spike, a quiet leaderboard by week two, and a participation number you'd rather not present. It isn't motivation that's missing — it's mechanics.
Pain cards:
1. **Manual tracking kills momentum** — If joining means installing a pedometer app and typing in totals, most of the company opts out by day three.
2. **The same ten people win** — When only raw step totals count, your marathoners dominate and everyone else stops checking the leaderboard.
3. **Nothing to come back for** — One bad day shouldn't end someone's challenge. Without streaks, milestones, and rewards, it does.
4. **No proof it worked** — A screenshot of a spreadsheet isn't a result. Leadership asks who participated and what changed — and the answer is usually a shrug.

Pivot: Every one of these is a design problem. Vantage Fit's step challenges are built around the fixes: automatic tracking, fair scoring, real rewards, and reporting that holds up in a leadership review.

### S3 Formats — "Run the challenge your culture will finish."
Lead: Start from a ready-made template — format, targets, and scoring pre-set — or configure your own. Every format syncs steps automatically, scores in real time, and supports teams.

| Format | Tag | Copy | Best for |
|---|---|---|---|
| Race | 1–2 weeks | The classic: a straight step-count showdown on a live leaderboard. No targets, no tasks — just total steps. The fastest way to get a whole company moving. | a first challenge or company-wide energizer |
| Streak | 2–4 weeks | Everyone chases the same daily step target and fights to keep their streak alive. Miss a day and the streak resets — rankings count total days completed, so a slip never ends the game. | building a daily walking habit |
| Journey | 3 templates included | Steps move individuals or teams along a virtual map — the 7 Wonders of the World, Backpacking Europe, or an Everest climb — earning points at every milestone. | storytelling and themed campaigns |
| E-Marathon | Custom distance | Steps convert to distance on the leaderboard — 1,000 steps to a kilometer by default, your ratio, your units. A marathon everyone in the company can enter. | event-style pushes with a finish line |
| Custom multi-week | Most flexible | Weekly themes with any mix of 27 task types — steps, distance, active minutes, water, sleep, meditation, and more. The format most long-running programs grow into. | keeping engagement past week two |
| Run them in parallel | No extra setup | No limit on concurrent challenges, and one walk counts toward every challenge an employee joins — each with its own leaderboard, points, and audience. | regions, departments, and squads at once |

Related links: Team challenges → · Virtual marathon → · Year-round wellness program →

### S4 Participation engine — "Built so week three feels like week one."
1. **Zero-effort tracking** — Steps sync themselves. No manual entry, no extra hardware to buy or distribute. (iPhone/Android out of the box; Fitbit & Garmin direct; Apple Watch and most bands via Apple Health; one primary device, no double-counting.)
2. **Competition that stays fair** — Team scores average members' effort; daily step caps and anti-cheat checks; leaderboard opt-out that still counts participation; 3-day post-end sync buffer.
3. **Rewards worth walking for** — Real-time point crediting; gift cards from a country-relevant catalogue in local currency across 190+ countries; one wallet shared with Vantage Circle recognition.
4. **Recognition beyond the win** — Automatic badges across 25+ levels (3,000-step day to marathon-distance runs); branded completion certificates with logo, seal, signature; automatic weekly summaries and reminders.

### S5 For HR — "Launch in minutes. Report like you meant it."
Lead: You shouldn't need a wellness coordinator to run a wellness challenge. Templates carry the configuration; the dashboard carries the proof.
- **Templates, not blank pages** — Pre-built challenges ship with format, targets, scoring, and weekly themes set. Choose dates and audience, and go live — a steps-only race can launch in 1–2 days.
- **Aim it at the right people** — Target by department, country, age group, or language. Enroll automatically or bulk-upload a CSV. Run separate challenges for regions or business units at the same time.
- **One challenge, every time zone** — Starts, ends, and daily resets localize to each participant's midnight — a 30-day challenge is 30 true days everywhere. Rewards set in USD display in local currency.
- **Managed without busywork** — Edit dates, themes, and tasks mid-challenge; send push notifications to participants; export the leaderboard to CSV any time.

Report mock: Participation Report · Challenge Leaderboard (CSV) · Transaction Report — "Figures as of yesterday · filterable by date, department, and country."

### S6 Proof — "Participation you can put in a board deck."
- **97%** — MindPoint Group (Cybersecurity · Virginia): participation in a 14-day walkathon — 51,000+ steps per employee on average.
- **91%** — SRS Medical (Medical devices · Massachusetts): engagement in the "Step It Up!" walkathon — average step counts rose 19% in the final two weeks.
- **87%** — DLA (Architecture · Pennsylvania): engagement across a 3-week step challenge — 1.49M steps and 1,500+ km logged.
- **63M+** — Intrado (Technology · Nebraska): steps logged by 1,100+ employees in the 5-week "Healthy Me" campaign.

Disclaimer line: Results from published Vantage Fit customer case studies. Engagement and participation figures are as reported by each customer's program.

### S7 Trust — "IT signs off. Employees opt in."
- **Security & compliance** — SOC 2 Type II compliant, with GDPR, ISO 27001, and ISO 27701 practices. Documentation available during evaluation.
- **Regional data residency** — Employee data stays in its assigned region — US, EU, India, or UAE. Nothing moves across borders.
- **SSO & HRIS ready** — SAML 2.0 single sign-on with Okta, Azure AD, OneLogin, or Ping. HRIS and SFTP provisioning keep rosters in sync.
- **Privacy by design** — Admins see aggregate metrics — never individual health profiles. Leaderboard opt-out is built in, and employee data is never sold or shared for advertising.

### S8 FAQ — "Questions HR teams ask."
1. **Do employees need a fitness tracker?** No — Apple Health/Google Fit on phones; Fitbit/Garmin direct; Apple Watch and most bands via Apple Health; one primary device, no double-counting.
2. **Can we run one challenge across countries and time zones?** Yes — localized start/end/daily reset; local-currency rewards with country-relevant catalogues.
3. **How do teams work?** Teams on Streak/Journey/Custom; average-not-sum scoring; dashboard, CSV, or employee-created teams; separate team leaderboard.
4. **How long does it take to launch?** Templates carry configuration; most teams launch in days; steps-only race with CSV enrollment in 1–2 days.
5. **What can we report when it's over?** Live participation/active-user/team-rankings dashboard; leaderboard CSV (weekly/overall, by department); participation report; points transaction ledger.
6. **What stops people from cheating?** Trusted step sources only; daily/hourly caps flag inhuman totals; admin inspection; 3-day sync buffer before winners are finalized.

### S9 Final CTA — "See your company's challenge before you launch it."
Book a 30-minute walkthrough — we'll configure a sample step challenge for your workforce and show you the live reporting behind it.
Checks: Go live in days · No wearable required · Unlimited parallel challenges · Works across 190+ countries.
Note: Turn daily steps into a habit your whole company shares.

---

## 4. Stat & claim sources

| Claim on page | Source |
|---|---|
| MindPoint Group 97% participation, 14-day walkathon, 51,719+ avg steps | `vantagefit-astro/content/en/casestudy/mindpoint-group-virtual-walkathon.md` |
| SRS Medical 91% engagement, +19.37% avg steps final two weeks | `content/en/casestudy/srs-medical-step-it-up-walkathon.md` |
| DLA 87% engagement, 1.49M+ steps, 1,500+ km, 3 weeks | `content/en/casestudy/dla-winter-step-challenge.md` |
| Intrado 1,100+ employees, 63M+ steps, 5 weeks | `content/en/casestudy/intrado-healthy-me-campaign.md` |
| 5 self-serve formats; Race 1–2 wks, Streak 2–4 wks; Journey templates (7 Wonders, Backpacking Europe, Everest Run); E-Marathon 1,000 steps = 1 km default | `content/en/help/admin/challenges/admin-what-challenge-formats.md`, `admin-how-do-i-create-{race,streak,journey-challenge,e-marathon}.md` |
| 27 task types in Custom challenges | `content/en/help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md` |
| Team score = average; CSV team upload; team leaderboard | `content/en/help/admin/challenges/admin-how-do-i-manage-teams.md`, `content/en/help/employee/challenges/how-do-teams-work.md` |
| Unlimited parallel challenges; one walk counts for all | `content/en/help/admin/challenges/admin-can-i-run-multiple-challenges-in-parallel.md` |
| Time-zone localization; USD→local-currency rewards display | `content/en/help/admin/challenges/admin-can-i-run-challenges-across-time-zones.md` |
| No wearable required; Fitbit/Garmin direct; Apple Health ecosystem; one primary device | `content/en/help/employee/getting-started/do-i-need-a-wearable.md`, `can-i-connect-multiple-devices.md` |
| Real-time point crediting; gift-card wallet shared with Vantage Circle R&R | `content/en/help/admin/challenges/admin-how-wellness-rewards-work.md`, `content/en/help/employee/rewards/how-do-i-redeem-points.md` |
| 190+ countries (SOLI purchasing-power equalized rewards) | `vfit-os/audit/site-refresh-2026-07/product-code-specs.md` §SOLI |
| Badges 7 categories / 25+ levels / 3,000→40,000 steps; branded certificates | `content/en/help/admin/challenges/admin-how-do-badges-work.md`, `admin-how-do-i-configure-certificates.md` |
| 3-day post-end sync buffer; admin-selected winners | `content/en/help/admin/challenges/admin-how-do-i-create-race-challenge.md` |
| Step caps / anti-cheat (10k steps/hr, 50k/day flags, trusted sources) | `vfit-os/specs/02-challenges-gamification/challenge-system-overview.md` |
| Leaderboard opt-out | `content/en/help/employee/challenges/can-i-opt-out-of-leaderboard.md` |
| Templates; audience filters (dept/country/age/language); CSV enrollment; 1–2 day steps-only launch | `content/en/help/admin/challenges/admin-how-do-i-use-templates.md`, `admin-how-do-i-set-target-audience.md`; `vfit-os` `product-code-specs.md` §Lite Mode |
| Reports: Participation, Leaderboard CSV, Transaction; "as of yesterday"; filters | `content/en/help/admin/reports/admin-what-reports-are-available.md`; `vc-dashboard-design/docs/modules/wellness.md` |
| SAML SSO (Okta, Azure AD, OneLogin, Ping); data residency US/EU/India/UAE; aggregate-only admin views; never sold/shared | `vfit-os/audit/site-refresh-2026-07/product-code-specs.md` §1, §privacy |
| SOC 2 Type II; GDPR; ISO 27001/27701 | SOC 2: `vfit-os/sources/VFit-Marketing-Content-Compacted.md`. GDPR/ISO: live security page + existing hub mock — **verify with the security team before production** (vfit-os data-accuracy rules flag live-site claims as unapproved sources). Footer compliance strip mirrors the hub mock. |
| "100+ organizations in 50+ countries" logo band | Approved aggregate per `vfit-os/.claude/rules/data-accuracy.md`; wordmark list mirrors `vantage-fit-solutions-v1.html` |

No stats, customers, or capabilities were invented. Dashboard figures inside the hero/report mocks are labeled-style sample data (challenge name, counts), consistent with the hub mock's approach.

---

## 5. Meta drafts

- **Title (58 chars):** `Corporate Step Challenges Employees Finish | Vantage Fit`
- **Alt title (60 chars):** `Step Challenge App for Work — HR-Ready Reporting | Vantage Fit`
- **Description (157 chars):** `Run a corporate step challenge employees actually finish. Five formats, automatic step sync from phones and wearables, real rewards, and participation reporting HR can trust.`
- **URL:** keep `/steps-challenge/` (existing SEO equity).
- Suggested schema for production: FAQPage for S8; BreadcrumbList (Solutions → Steps Challenge).

## 6. Mega-menu note

The mock's Solutions menu matches the hub mock's grouping (By program / By need). The only addition for this page state: the current page's item (`/steps-challenge/`) gets `aria-current="page"` and a "You're here" pill — worth keeping in production for wayfinding from the mega-menu.

## 7. Assumptions made

1. Kept the existing `/steps-challenge/` URL and the hub mock's nav/footer/compliance strip for consistency, even though GDPR/ISO claims need security-team verification (flagged above).
2. Hero/report dashboard numbers are illustrative sample data, matching the hub mock's convention; real customer numbers appear only in labeled proof chips and the proof section.
3. Sibling programs appear only as light text links (per prompt scope) — no cross-promo cards.
4. US-market framing: all four proof customers are US companies; time-zone/local-currency story leads the global angle rather than non-US case studies.
5. "14+ languages" was used on the hub but not repeated here (not needed for this page's story; left to the hub).
