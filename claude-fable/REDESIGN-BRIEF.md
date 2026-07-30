# Vantage Fit Homepage Redesign — Strategy Brief

**Prepared for:** Vantage Fit marketing website redesign
**Audience:** Senior HR leaders, CHROs, Benefits & Wellbeing leaders — US enterprise market
**North-star metric:** Employee participation
**Companion file:** `vantage-fit-homepage-v2.html` (the built homepage — 5 full-screen sections)
**Sources:** `vantagefit-astro` repo (live site source), `vc-dashboard-design` (HR admin product prototype), `vantage-fit-homepage-v1.html` (shortlisted design direction), live vantagefit.io

---

## 0. Executive summary

1. **The story compresses to five screens:** Promise → Product → Proof-you-can-measure → Proof-from-customers → Trust-then-act. Each screen answers one buyer question, in the order an enterprise HR leader actually asks them.
2. **Participation stays the spine.** The v1 sample's participation-first hero is retained and made *more* authentic: every number on the page now matches the real admin-dashboard prototype (68% rate, 1,455 of 2,140 enrolled, 75% target, 58→61→64→68 quarterly climb, department breakdowns).
3. **Two missing trust layers are added:** a customer-video section built from the three real testimonial videos already on vantagefit.io, and a full "Your data is safe with us" enterprise security section — elevated from the current site's single badge-pill into a section with substance (aggregated-only HR visibility, n<5 cohort suppression, consent & erasure SLAs, regional hosting).
4. **The India-HQ objection is answered with specifics, not logos.** US enterprise buyers de-risk vendors through compliance artifacts. The page now leads its close with HIPAA · SOC 2 Type II · GDPR · ISO 27001 · ISO 27701 plus privacy-by-design mechanics that a security reviewer can verify.
5. **Everything that doesn't serve an enterprise buying decision is cut:** the blog feed, the "Cue > Action > Reward" internal framework, the announcement bar, the FAQ (migrated to demo/pricing pages), and the unattributed "$250 savings" stat.
6. **Navigation is restructured** from a 24-link sprawl (10 Solutions + 14 Features) into three balanced, scannable menus organized around buyer intent, with every item mapped to an existing URL — no new pages required on day one.

---

## 1. Audit of the current homepage (vantagefit.io)

### 1.1 What's working — keep the momentum

Recent messaging commits (`fix(messaging): hero copy rewrites`, `fix(truth-sweep): remove fabricated proof points`) already moved the site in the right direction. Credit where due:

- **Hero headline is outcome-oriented:** "The wellness platform employees actually use — launched in days, not months." This is a genuine differentiator claim, not category wallpaper.
- **Proof points are now sourced:** 59% Tata Motors and 88% IBS Software both link to real case studies.
- **Testimonials are real and filmed:** three named customers with titles, companies, and YouTube videos — rare and valuable; most competitors have stock-photo quotes.
- **Performance discipline exists** (YouTube facades, inline critical CSS, content-visibility) — the redesign shouldn't regress it.

### 1.2 Messaging weaknesses

| # | Weakness | Evidence | Consequence |
|---|----------|----------|-------------|
| M1 | **Three conflicting positioning lines ship simultaneously.** | `<title>`: "Employee Wellness Platform Employees Love" · H1: "the wellness platform employees actually use" · JSON-LD: "AI-powered corporate wellness platform" | Brand memory never compounds; "AI-powered" exists only where buyers can't see it. |
| M2 | **The north-star metric is absent from the homepage.** | No participation number appears anywhere on the page; the hero has zero stats. Meanwhile the product's entire admin experience headlines a participation gauge vs. target. | The site sells "a platform"; the product sells "a number going up." The strongest, most differentiated claim goes unused. |
| M3 | **"Cue > Action > Reward" is internal jargon shipped as a section.** | H2 "A platform based on Cue > Action > Reward" + three image cards with *zero body copy* | Buyers don't buy behavioral-science frameworks; they buy outcomes. A full screen spent explaining nothing. |
| M4 | **"How Corporate Wellness programs help?"** is a weak, ungrammatical frame for the strongest content on the page (the stats). | `home.yaml:17` | Proof presented apologetically. |
| M5 | **The "$250 healthcare savings" stat is unattributed** — its `source_url` is an empty string (renders a self-linking `<a href="">`). | `home.yaml:27-30` | One unverifiable claim contaminates two verifiable ones next to it. Enterprise buyers notice. |
| M6 | **Security is a pill, not a section.** "Your data is safe with us" is a single heading + one composite badge image inside the "Why Vantage Fit?" section. No body copy at all. | `HomePage.astro:458-471` | For an India-based vendor selling health data handling to US enterprises, this is the single biggest messaging under-investment on the page. |
| M7 | **Testimonial videos carry no numbers.** The three video cards sit two sections away from the stats that would substantiate them (BISD's own case study: 86% engagement). | Sections 2 vs 4 | Faces without evidence; evidence without faces. |
| M8 | **SEO blog listicles occupy the conversion path.** "61 Unique Step Challenge Team Names," "Top 15 Self Care Ideas… in 2024" (stale year) render above the final CTA. | `home.yaml:130-156` | Undermines enterprise seriousness; leaks exit paths right before the close. |
| M9 | **Readability is poor for scanning:** 956 words, Flesch 38.2 ("hard"). | in-repo crawl audit | Executives scan; they don't read. |

### 1.3 UX/UI issues

| # | Issue | Evidence |
|---|-------|----------|
| U1 | **Desktop feature tabs dead-end** — the five feature panels have no links at all on desktop (the "Learn more →" only renders on mobile). Five product stories, zero paths forward. | `HomePage.astro:224-241` vs `:264` |
| U2 | **Client logos are invisible to everyone but sighted mouse users** — the logo strip is a single CSS `background-image` on an empty `<div>`: no DOM text, no alt, no SEO value, grayscale at 120s marquee speed. | `main.css:165-201` |
| U3 | **The announcement bar competes with the hero** — "Reserve My Spot" (HR Challenge League) is the first CTA on the page and steals 56px plus first-glance attention from "Book a Demo." | `AnnouncementBar.astro` |
| U4 | **G2/Capterra/Gartner proof is a static image** with inconsistent alt text; the ratings numbers (4.5 / 4.5 / 4.7) exist nowhere in on-page text. A rich JSON-LD trove (Google Play 4.5★ from ~37,800 ratings) is never surfaced to humans. | `HomePage.astro:69-75`, `schema-data.js` |
| U5 | **Mega-menu overload:** Features panel = 14 links; Solutions = 10; Solutions and Features overlap ("Wellness Rewards Program" vs "Incentivization & Rewards"; "Health & Fitness Analytics" vs "Admin Dashboard"). Mobile flattens all groups into undifferentiated lists and reorders items vs desktop. | `header-data.js` |
| U6 | **Section rhythm is monotone dark→dark→gray→white→dark→gray→dark** with no narrative signposting (no eyebrows/kickers); every section restarts the story. | `HomePage.astro` |
| U7 | Footer near-duplicates confuse: "Client Success Stories" vs "Client Testimonials," "Partners" vs "Partnership." | `Footer.astro` |

### 1.4 Conversion opportunities

1. **Put the north-star number above the fold.** A live-feeling participation dashboard in the hero converts the abstract promise ("employees actually use it") into an artifact the buyer can imagine presenting internally. This is the v1 sample's biggest idea — keep it.
2. **One primary CTA, everywhere: "Book a demo."** Remove the announcement bar's competing ask. Secondary CTAs should only *advance the story* (watch stories, view pricing), never fork it.
3. **Pair every testimonial with its case-study metric.** BISD videos + "86% engagement" beats either alone.
4. **Use the security section as a closer.** In enterprise deals, security review is where timelines die. Answering it pre-emptively on the homepage ("HR sees aggregated trends only," "n<5 suppression," "30-day erasure SLA") signals procurement-readiness and shortens the demo-to-security-review gap.
5. **Surface the ratings as text** (G2 4.5 · Capterra 4.5 · Gartner 4.7 · Google Play 4.5/37K+) — crawlable, quotable, screenshot-able.
6. **Cut homepage word count ~40%** and let numbers carry the argument. Target: every section scannable in <10 seconds.

### 1.5 Keep / consolidate / cut

| Current content | Decision | Where it goes in v2 |
|---|---|---|
| Hero differentiator claim ("launched in days, not months") | **Keep** | Hero trust-note row |
| G2/Capterra/Gartner badges | **Keep, as text** | §4 ratings row |
| Client logo strip | **Keep, rebuilt as real text/DOM** | Hero bottom band |
| 59% Tata / 88% IBS stats | **Keep, expanded** | §4 results band (+ Beroe 96%, Wipro 3X) |
| "$250 healthcare savings" | **Cut** (unattributed; truth-sweep leftover) | Restore only with a source |
| Cue > Action > Reward section | **Cut** (jargon) | Logic absorbed into §2 engine strip |
| 5 feature tabs | **Consolidate** | §2 tabbed employee/HR panels + nav Features menu |
| Testimonial videos (3) | **Keep, elevated** | §4 — with per-customer metrics |
| "Why Vantage Fit?" claims | **Consolidate** | §2 benefits + §3 board-proof framing |
| "Your data is safe with us" pill | **Keep, expanded to a full section** | §5 |
| Blog feed | **Cut from homepage** | Resources menu (Blog, Guides, Podcasts) |
| Announcement bar (HR Challenge League) | **Cut from homepage** | Resources menu featured slot (optional) |
| FAQ (v1 sample) | **Cut from homepage** | Demo + Pricing pages; definitions inlined where they matter (§3) |
| Final CTA | **Keep, merged into §5** | Trust → act on one screen |

---

## 2. New homepage information architecture

### 2.1 The narrative arc — five screens, five buyer questions

An enterprise wellbeing buyer's internal monologue, in order:

| Screen | Buyer question | Answer | Section |
|---|---|---|---|
| 1 | "What is this, and why should I care?" | *A wellness platform judged on the only metric that matters: participation.* | **Hero** + trusted-by band |
| 2 | "How would it actually work for my people — and for my team?" | *An engine that makes joining easy and returning rewarding; one console for HR.* | **Platform** (engine + employee/HR tabs) |
| 3 | "Can I defend this program to my CHRO/CFO/board?" | *A daily participation rate vs. target, broken down by department — exportable, explainable.* | **Measurement** |
| 4 | "Who like us has done this, and what happened?" | *Filmed customers + case-study numbers: 96%, 88%, 59% at 10K+ scale, 3X across 30+ countries.* | **Customer proof** (videos + results) |
| 5 | "Will this survive security review — and what do I do next?" | *HIPAA · SOC 2 II · GDPR · ISO 27001/27701, privacy-by-design mechanics → Book a demo.* | **Trust + CTA** |

The page reads as one argument: **participation is the promise → here's the machine that produces it → here's how you'll measure it → here's who already did it → here's why it's safe → book the demo.**

### 2.2 What changed vs. the v1 sample (11 sections → 5)

| v1 sample section | v2 disposition |
|---|---|
| Topline banner | Cut (banner blindness; competes with nav) |
| Hero | **Screen 1** (tightened; trust notes now include compliance) |
| Logo strip | Merged into **Screen 1** bottom |
| "Participation problem" | Merged into **Screen 2** intro copy |
| "Participation engine" (4 big cards) | Compressed into **Screen 2** horizontal step strip |
| Employee/HR experience tabs | **Screen 2** main body |
| Measurement | **Screen 3** (numbers corrected to dashboard ground truth) |
| Proof (3 stat cards) | Merged into **Screen 4** results band |
| *(missing)* Testimonial videos | **Screen 4** — new |
| "Responsible wellness" 4 cards | Absorbed: privacy cards → **Screen 5**; measurement card → **Screen 3** |
| Buying/pricing band | Absorbed into **Screen 5** CTA (+ Pricing in nav) |
| FAQ | Cut from homepage (migrate to demo/pricing pages) |
| *(missing)* Security & compliance | **Screen 5** — new |
| Final CTA | Merged into **Screen 5** |

### 2.3 Authenticity rule

Every product number shown on the page is the same number the admin-dashboard prototype ships: participation 68% vs 75% target, 1,455 of 2,140 enrolled, quarterly trail 58→61→64→68 (+4 pts vs. prior quarter), department bars 82/76/71/66/58/49, activities per quarter 48,200, Wellness Score 72/100, 88% of activity logged automatically (63% app + 25% wearables). When a prospect moves from homepage → demo, the demo confirms the homepage. Marketing that previews the real product is the cheapest trust you can buy.

---

## 3. Navigation & submenu proposal

### 3.1 Principles

1. **Four top-level items + one CTA.** Solutions · Features · Resources · Pricing · [Book a demo]. Nothing else.
2. **Solutions = buyer intent ("I want to…"), Features = product capability ("It has…").** The current overlap (rewards/analytics in both) is resolved by this rule.
3. **Max ~10 links per panel, in named groups of ≤6.** Every link maps to an existing URL — zero new pages required to ship.
4. **Groups survive on mobile.** Accordions preserve group headers instead of flattening.
5. Language switcher moves to the footer (it currently spends prime header space on a minority need).

### 3.2 Solutions menu — organized by intent

**BY PROGRAM** *(what you want to run)*
| Label | Existing URL |
|---|---|
| Step challenges | `/steps-challenge/` |
| Multi-activity challenges | `/multi-activity-challenges/` |
| Team challenges | `/team-challenges/` |
| Virtual marathons | `/virtual-marathon/` |
| Mental health & wellbeing | `/mental-health-and-wellbeing-challenges/` |
| Year-round wellness program | `/holistic-wellness-program/` |

**BY NEED** *(what you're solving)*
| Label | Existing URL |
|---|---|
| Engage a global workforce | `/global-employee-engagement/` |
| Support remote & hybrid teams | `/remote-team-wellness/` |
| Reward healthy habits | `/wellness-rewards-program/` |
| Measure program impact | `/health-fitness-analytics/` |

**Panel footer:** "See Vantage Fit as your all-in-one employee wellness platform →" → `/employee-wellness-software/`

### 3.3 Features menu — three groups of four

**FOR EMPLOYEES**
| Label | Existing URL |
|---|---|
| Activity & health tracking | `/features/activity-tracking/` |
| Nutrition & hydration | `/features/nutrition-and-hydration/` |
| Mental wellbeing & mindfulness | `/features/mental-health-and-mindfulness/` |
| Personalized programs | `/features/personalized-programs/` |

**FOR HR TEAMS**
| Label | Existing URL |
|---|---|
| Admin dashboard & analytics | `/features/admin-dashboard/` |
| Incentives & rewards | `/features/incentivization-and-rewards/` |
| Engagement tools & community | `/features/engagement-tools/` |
| Wellness leagues | `/features/wellness-leagues/` |

**PLATFORM**
| Label | Existing URL |
|---|---|
| Integrations — wearables, HRIS, SSO | `/features/integrations/` |
| Security & compliance | `/features/security-and-compliance/` |
| Accessibility | `/features/accessibility/` |
| Health data upload | `/features/health-data-upload/` |

*Demoted from top nav (reachable from feature pages): Fitness & Exercise, Health Metrics — both are facets of "Activity & health tracking." 14 links → 12, in scannable groups. Security & compliance earns a top-nav seat because enterprise buyers look for it there.*

### 3.4 Resources menu — learn vs. evaluate

**LEARN**
| Label | Existing URL |
|---|---|
| Blog | `/en/blog/` |
| Guides & eBooks | `/guides/` |
| Podcasts | `/en/blog/podcasts/` |
| 2026 Well-Being Industry Report | `/2026-global-workplace-well-being-industry-report/` |

**EVALUATE**
| Label | Existing URL |
|---|---|
| Customer stories | `/casestudy/` |
| ROI calculator | `/tools-and-templates/employee-wellness-roi-calculator/` |
| Compare platforms | `/compare/` |
| Help Center | `/en/help/` |

**Featured card:** Wellness Challenges Library — "Browse ready-to-run challenges" → `/wellness-challenges/`
*(The HR Challenge League promo can rotate through this featured slot instead of owning a site-wide announcement bar.)*

### 3.5 Pricing
Direct link → `/pricing/`. No dropdown.

### 3.6 Footer
Five columns: **Solutions** (6 program links) · **Features** (4: dashboard, rewards, integrations, security) · **Resources** (customer stories, ROI calculator, guides, blog, help center, pricing) · **Company** (about, partners, careers, contact, download app) · brand column (mission line + compliance chips + "Powered by Vantage Circle" + language links). Merge the current duplicate links (testimonials/success-stories → one "Customer stories").

---

## 4. Wireframe — five full-screen sections

Each section is designed to `min-height: 100svh − nav` on desktop, with proximity scroll-snap and a right-edge progress rail (5 dots). Annotations → rationale in §6.

```
┌─────────────────────────────────────────────────────────────┐
│ NAV  ♥ Vantage Fit   Solutions▾ Features▾ Resources▾ Pricing │ sticky, 68px
│                                            [Book a demo]    │
╞═════════════════════════════════════════════════════════════╡
│ ①  HERO ······································· dark teal   │
│  ● Built for sustained participation                        │
│  MORE EMPLOYEES PARTICIPATING.          ┌─ dashboard card ─┐│
│  BETTER WORKFORCE WELLBEING.            │ Participation 68%││
│  lead: platform employees choose to     │ ↑4pts · 1455/2140││
│  join… participation you can measure    │ target 75% ───── ││
│  [Book a demo] [Watch customer stories] │ trend chart ↗    ││
│  ✓launch in days ✓100+ orgs·50+ countries│  ┌phone: challenge│
│  ✓HIPAA·SOC 2·GDPR·ISO 27001            └──┤ app mockup   │││
│  ───────────────────────────────────────────┴──────────────┘│
│  TRUSTED BY: TATA MOTORS · WIPRO · ACCENTURE · TEVA ·       │
│  TEXAS INSTRUMENTS · HERSHEY · BRAZOSPORT ISD               │
╞═════════════════════════════════════════════════════════════╡
│ ②  PLATFORM ···································· light      │
│  ● The participation engine                                 │
│  H2: Built for the day after launch.    lead: programs peak │
│  at announcement and fade by week six — Vantage Fit keeps   │
│  the loop running.                                          │
│  ┌01 Invite┐→┌02 Participate┐→┌03 Reward┐→┌04 Improve┐     │
│  [ For employees | For HR teams ]  ← tabs                   │
│  ┌ 3 benefits ────────┐ ┌ product mockup ────────────────┐  │
│  │ every kind of      │ │ employee app / admin console   │  │
│  │ participant·streaks│ │ (switches with tab)            │  │
│  │ ·real rewards      │ └────────────────────────────────┘  │
╞═════════════════════════════════════════════════════════════╡
│ ③  MEASUREMENT ································· soft green │
│  ● Analytics for HR leaders                                 │
│  H2: Lead with participation.        ┌ measurement card ──┐ │
│      Prove it to the board.          │ ◔ 68% gauge · live │ │
│  ✓ daily rate vs target, defined     │ 58→61→64→68 trend  │ │
│  ✓ dept/country/age/gender breakdown │ dept bars vs 75%   │ │
│  ✓ board-ready, audit-logged exports │ 48,200 activities  │ │
│  ✓ Wellness Score as context, not    │ 88% auto-logged    │ │
│    a black box                       │ Score 72/100 supp. │ │
│                                      └ definition footnote┘ │
╞═════════════════════════════════════════════════════════════╡
│ ④  CUSTOMER PROOF ······························ dark teal  │
│  ● Customer stories                                         │
│  H2: Hear it from the teams who run it.                     │
│  ┌▶ Rachel Arthur ┐ ┌▶ Shyam Surendran┐ ┌▶ Matt Whitmore ┐  │
│  │ Brazosport ISD │ │ Landmark Leisure│ │ BWC Real Estate│  │
│  │ "daily habit…" │ │ "culture of     │ │ "in just four  │  │
│  │ 86% · 2-week   │ │  progress"      │ │  months…"      │  │
│  └────────────────┘ └─────────────────┘ └────────────────┘  │
│   96% Beroe · 88% IBS · 59% Tata(10K+) · 3X Wipro(30+ ctry) │
│   ★4.5 G2  ★4.5 Capterra  ★4.7 Gartner   All stories →     │
╞═════════════════════════════════════════════════════════════╡
│ ⑤  TRUST + CTA ································· light→coral│
│  ● Enterprise security & compliance                         │
│  H2: Your data is safe with us.                             │
│  [HIPAA] [SOC 2 Type II] [GDPR] [ISO 27001] [ISO 27701]     │
│  ✓ HR sees aggregated trends only   ✓ n<5 cohorts hidden    │
│  ✓ consent versioning·30-day erasure ✓ regional hosting     │
│  ✓ role-based access·audit-logged   ✓ SSO·HRIS·wearables    │
│  ┌─ coral band ────────────────────────────────────────────┐│
│  │ Make participation the start of your wellness story.    ││
│  │ [Book a demo]  [View pricing]   no-obligation walkthrough││
│  └─────────────────────────────────────────────────────────┘│
╞═════════════════════════════════════════════════════════════╡
│ FOOTER: Solutions·Features·Resources·Company·mission+badges │
└─────────────────────────────────────────────────────────────┘
```

Interaction model: sticky nav with hover/click mega-menus (groups preserved on mobile as accordions) · §2 tabs switch employee/HR panels · §4 video cards open a native `<dialog>` modal with the real YouTube embed (plus "Watch on YouTube" fallback link) · right-edge dot rail tracks the five sections · scroll-snap is `proximity` (never fights the user) and disabled on mobile/reduced-motion.

---

## 5. Homepage copy deck (complete)

### Nav
Brand: **Vantage Fit** · Items: Solutions · Features · Resources · Pricing · CTA: **Book a demo**
(Submenu labels + descriptions: see §3 tables; each mega-menu item carries its one-line description.)

### Screen 1 — Hero
- **Kicker:** `● Built for sustained participation`
- **H1:** `More employees participating. Better workforce wellbeing.` *(em: "participating")*
- **Lead:** `Vantage Fit is the wellness platform enterprise HR teams use to make wellbeing measurable — inclusive challenges employees choose to join, rewards worth returning for, and one participation number your board can trust.`
- **Primary CTA:** `Book a demo` → /request-demo/
- **Secondary CTA:** `Watch customer stories` → #stories
- **Trust notes:** `Launch in days, not months` · `100+ organizations · 50+ countries` · `HIPAA · SOC 2 · GDPR · ISO 27001`
- **Dashboard mockup:** Program overview / Workforce participation · Last 30 days · **Participation rate 68%** · `↑ 4 pts vs last quarter` · Participating **1,455** · Enrolled **2,140** · Target **75%** · chart "Participation over time" with 75% target line
- **Phone mockup:** Good morning, Mia · ACTIVE CHALLENGE **Move Together** · "Any activity counts. 8 days left." · Your goal 72% · 6 active days · #12 team rank · 850 points · [Continue challenge]
- **Caption:** `Illustrative product data`
- **Logo band:** `TRUSTED BY 100+ ORGANIZATIONS IN 50+ COUNTRIES` — TATA MOTORS · WIPRO · ACCENTURE · TEVA PHARMACEUTICALS · TEXAS INSTRUMENTS · HERSHEY · BRAZOSPORT ISD

### Screen 2 — Platform
- **Eyebrow:** `The participation engine`
- **H2:** `Built for the day after launch.`
- **Lead:** `Most wellness programs peak on announcement day and fade by week six. Vantage Fit keeps the loop running — a reason to join, a reason to return, and a next program that learns from the last.`
- **Engine steps:**
  1. **Invite** — `Launch targeted programs for teams, regions or the whole workforce in days — from proven templates.`
  2. **Participate** — `17 activity types — steps, workouts, mindfulness, sleep, nutrition — so it's never just a step contest.`
  3. **Reward** — `Points, badges and gift cards employees actually want, earned for effort and consistency, not just rank.`
  4. **Improve** — `See which teams need a different approach, then relaunch in clicks — not another project.`
- **Tabs:** `For employees` / `For HR teams`
- **Employee benefits:**
  - **Every kind of participant** — `Physical, mental and everyday wellbeing across varied interests, abilities and time zones.`
  - **Progress people can feel** — `Daily goals, streaks and team challenges turn a distant outcome into a visible next step.`
  - **Rewards worth earning** — `Meaningful participation converts to points and a global gift-card catalogue.`
  - *Footnote:* `Employees rate the app 4.5★ across 37,000+ Google Play ratings.`
- **HR benefits:**
  - **Launch without a project** — `Start from proven formats — Race, Streak, E-Marathon, Journey — and adapt goal, audience, timing, reward.`
  - **See participation clearly** — `The live rate vs your target, trending over time, by department, country and challenge.`
  - **Run one connected program** — `Challenges, rewards, communications and reporting in one console — not five tools.`
- **Employee panel mockup:** Your wellness · This week: "Three ways to move closer to your goal" · Move Together (Team challenge · Day 12) · Mindful minutes (4-day streak) · 1,250 points (ready to redeem)
- **Admin panel mockup:** sidebar Overview/Analytics/Challenges/Reports · Participation overview · Last 30 days · 68% / 1,455 participating / 2 active challenges · "Participation by department" bars vs Target 75%

### Screen 3 — Measurement
- **Eyebrow:** `Analytics for HR leaders`
- **H2:** `Lead with participation. Prove it to the board.`
- **Lead:** `Every wellbeing budget gets asked the same question: is anyone actually using it? Vantage Fit headlines the answer — one defensible participation rate — then explains what drives it.`
- **Checklist:**
  - `A rolling participation rate against your target — updated daily, defined transparently.`
  - `Breakdowns by department, country, age and gender show exactly where the program needs help.`
  - `Board-ready reports — scheduled, exportable, and audit-logged.`
  - `A Wellness Score (0–100) as supporting context — an explainable composite, never a black box.`
- **Measurement card:** WORKFORCE PARTICIPATION · `● Updated daily` · Gauge **68%** (30-day participation) · `1,455 of 2,140 enrolled active` · Trend: `Four quarters, one direction` / `58 → 61 → 64 → 68` · Department bars: Engineering 82 · Product 76 · Marketing 71 · Operations 66 · Support 58 · Sales 49 vs `Target 75%` · Stats: Activities this quarter **48,200** · Logged automatically **88%** *(app + wearables)* · Wellness Score **72/100** *(supporting)*
- **Definition footnote:** `Example view. Participation = enrolled employees with at least one logged activity or challenge in the rolling 30-day window.`

### Screen 4 — Customer proof
- **Eyebrow:** `Customer stories`
- **H2:** `Hear it from the teams who run it.`
- **Lead:** `HR and business leaders on what changed when wellness became something employees actually do.`
- **Video card 1:** ▶ **Rachel Arthur** — Director of Benefits & Wellness, Brazosport ISD — `"Turning wellness into a daily habit that drives both health and happiness across BISD."` — chip: `86% engagement · 2-week challenge`
- **Video card 2:** ▶ **Shyam Surendran** — Sr. Manager Training, Landmark Leisure — `"'Something is better than nothing' became a culture of wellness and daily progress."` — chip: `Landmark Group · 5,000+ participants`
- **Video card 3:** ▶ **Matt Whitmore** — Managing Partner, BWC Real Estate — `"In just four months, Vantage Fit has seamlessly integrated into our growing business."` — chip: `Measurable results in 4 months`
- **Results band:** `96%` engagement · Beroe, 850 employees | `88%` engagement · IBS Software, 28-day challenge | `59%` engagement · Tata Motors, 10,000+ workforce | `3X` participation growth · Wipro, 30+ countries
- **Ratings row:** `★ 4.5 G2` · `★ 4.5 Capterra` · `★ 4.7 Gartner Peer Insights` · Link: `See all customer stories →` → /casestudy/
- **Footnote:** `Results are customer-reported program outcomes; they vary by workforce, program design and measurement window.`

### Screen 5 — Trust + CTA
- **Eyebrow:** `Enterprise security & compliance`
- **H2:** `Your data is safe with us.`
- **Lead:** `Employee health data demands a higher bar. Vantage Fit is audited against the standards your security team will ask about — and designed so individual health data stays private to the employee.`
- **Compliance cards:**
  - **HIPAA** — `Health information handled to HIPAA guidelines.`
  - **SOC 2 Type II** — `Enterprise controls, audited annually.`
  - **GDPR** — `Compliant, with EU data-residency options.`
  - **ISO 27001** — `Certified information security management.`
  - **ISO 27701** — `Certified privacy information management.`
- **Privacy-by-design checklist:**
  - `HR and admins see aggregated, population-level trends — never individual health records.`
  - `Small cohorts are suppressed: groups under 5 are never shown.`
  - `Versioned consent with re-consent on change, and a 30-day data-erasure SLA.`
  - `Regional data hosting; PII is never shared with third parties.`
  - `Role-based access, with every report export logged — who, what, when.`
  - `SSO, HRIS and wearable integrations without data sprawl.`
- **Link:** `Read the full security overview →` → /features/security-and-compliance/
- **CTA band (coral):**
  - **H2:** `Make participation the start of your wellness story — not the missing chapter.`
  - **Body:** `A focused 30-minute walkthrough: the employee experience, a sample challenge for your workforce, and exactly how participation is measured.`
  - **CTAs:** `Book a demo` · `View pricing`
  - **Note:** `No obligation · Tailored to your workforce and program goals`

### Footer
Mission line: `The employee wellness platform built to grow participation — inclusive programs, meaningful rewards, measurable results.` · Columns per §3.6 · Compliance chips: HIPAA · SOC 2 · GDPR · ISO 27001 · ISO 27701 · `Powered by Vantage Circle` · `© 2026 Vantage Circle. All rights reserved.` · Terms · Privacy · Cookie Policy

---

## 6. UX/UI rationale, section by section

**Screen 1 — Hero.** Enterprise HR buyers arrive skeptical of wellness vendors ("we bought one; nobody used it"). The hero concedes that history and stakes the brand on the fix: a participation number, shown *inside the actual product artifact* they'd use to defend the program. The dashboard mockup is the promise made tangible; the phone mockup answers "will my employees tolerate this?" in the same glance. Compliance chips appear here — not because buyers decide on them in second one, but because their *absence* above the fold is what US enterprise visitors notice from an unfamiliar vendor. The logo band closes the screen so the first scroll begins from borrowed credibility. One primary CTA; the secondary CTA fast-forwards skeptics straight to filmed proof.

**Screen 2 — Platform.** One screen must do what the current site spreads across three (Cue/Action/Reward + feature tabs + Why Vantage Fit): explain the machine. The four-step engine strip gives the mental model (why participation compounds); the employee/HR tabs give the two proofs of it (an app people enjoy; a console HR controls). The tab pattern also performs segmentation: a CHRO self-identifies with "For HR teams" and immediately sees the admin console — the thing most wellness marketing hides. Real template names (Race, Streak, E-Marathon, Journey) and the "17 activity types" figure replace generic feature adjectives with verifiable specifics.

**Screen 3 — Measurement.** This is the section that converts *senior* buyers, because it arms their internal pitch. The left column speaks in the buyer's ceremony language (targets, breakdowns, board reports, no black boxes); the right column is a faithful miniature of the real analytics spine — headline rate vs. target, then trend, then department breakdown — the exact "spine rule" the product enforces. Including the metric's definition in fine print is deliberate: transparency about measurement is itself a differentiator in a category notorious for vanity metrics.

**Screen 4 — Customer proof.** Video testimonials are the highest-trust format the brand owns, and they currently sit unnumbered mid-page. Here they arrive *after* the buyer knows what the product does (so the stories land as confirmation, not decoration) and each face is paired with its program's metric — faces + numbers in one card. The results band deliberately mixes proof types: intensity (Beroe 96%), a famous enterprise at scale (Tata Motors, 10,000+), duration (IBS 28-day), and global growth (Wipro 3X, 30+ countries) — one for each flavor of buyer doubt. Ratings render as text for credibility, crawlability and quotability.

**Screen 5 — Trust + CTA.** Ending on security is a sequencing decision: it's the last objection before a demo request, and for an India-headquartered vendor selling to US enterprises it's the objection. The section upgrades "badge wallpaper" into mechanics a security reviewer can verify (aggregation-only visibility, n<5 suppression, consent versioning, erasure SLA, audit-logged exports) — signaling that procurement will be fast, which is itself a selling point. The coral CTA band sits on the same screen so trust resolves directly into action, and the demo promise is concrete (30 minutes, sample challenge, measurement walkthrough) rather than "talk to sales."

**Global decisions.** Five `100svh` sections with proximity snap and a dot rail make the story's length legible ("five screens, then you're done") and give internal stakeholders a shared vocabulary for reviewing it. Dark→light alternation (dark promise/proof, light explanation) creates rhythm the current monotone page lacks. All mockups are code-drawn (no screenshots): they load instantly, never go stale in a way a CMS can't fix, and match the real dashboard's numbers. Scroll-snap is `proximity` not `mandatory` — it suggests, never hijacks — and is disabled on mobile and for reduced-motion users.

---

## 7. Data provenance & open items

### Verified sources used
- **Product numbers:** `vc-dashboard-design` prototype (matches production Vantage Fit vocabulary; participation definition verbatim from its ground-truth spec).
- **Case-study metrics:** `vantagefit-astro/content/en/casestudy/*` — Beroe 96% · IBS Software 88% · Tata Motors 59% (10,001+ employees) · Wipro 3X, 30+ countries · Brazosport ISD 86% · Landmark Group 5,000+ participants.
- **Videos:** YouTube IDs from `home.yaml` — Rachel Arthur `LSX4pxSB6Qw`, Shyam Surendran `4h9eRm4hNe0`, Matt Whitmore `L_39IykL-O4`.
- **Compliance set:** HIPAA · ISO 27001 · ISO 27701 · GDPR · SOC 2 (homepage badge alt + security feature page + EWS page FAQ: "SOC 2 Type II certified… EU data residency options"). CCPA is *not* claimed anywhere — so v2 doesn't claim it.
- **Privacy mechanics:** aggregation-only admin visibility & n≥5 suppression & consent/erasure SLAs from the dashboard prototype's settings/governance and the EWS FAQ.

### Open items to resolve before production
1. **Name conflict:** video `4h9eRm4hNe0` is attributed to *Shyam Surendran* everywhere except `/client-testimonials/`, which says *Tarun Rangwani*. v2 uses Shyam Surendran (canonical majority) — confirm with the CS team.
2. **Ratings conflict:** hero badge alt says G2 4.5 / Capterra 4.5 / Gartner 4.7; `about-us.yaml` says G2 4.6 / Capterra 4.3. v2 uses 4.5/4.5/4.7 — pick one source of truth.
3. **"$250 savings" claim** dropped pending a citable source.
4. **"Step & Stride"** program name (v1 sample) not found in any case study — v2 says "10,000+ workforce" instead. Tata's documented programs: original (59%) and "Step Up & Elevate" (70%, 43 teams).
5. **Encryption specifics** (at rest/in transit) are not claimed anywhere in the repo, so v2 doesn't invent them — worth adding to the security page with InfoSec sign-off.
6. **Landmark chip** pairs Shyam (Landmark Leisure) with the Landmark Group case-study scale (5,000+ participants) — confirm the relationship is fine to imply.

### Implementation notes (for the Astro port)
- `HomePage.astro` renders four locales from per-locale YAML — plan the five-section content model in `home.yaml` first, then the markup once.
- Rebuild the logo strip as real DOM text/images (SEO + a11y), not a CSS background.
- Reuse the existing YouTube facade/modal pattern (`#video-modal`) for the §4 cards; thumbnails can use `img.youtube.com/vi/{id}/hqdefault.jpg` as today.
- Individual client/cert logo assets are inventoried in the research (Cloudinary paths) — the v2 prototype draws them as styled text to stay self-contained; swap in real logo files during the port.
- Keep the perf conventions (facades, inline critical CSS, `content-visibility`) — the v2 prototype follows them in spirit (zero external requests, JS-free above the fold).
