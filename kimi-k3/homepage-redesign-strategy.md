# Vantage Fit Homepage Redesign — Strategy & Copy Deck

**Prepared for:** Vantage Fit (vantagefit.io) homepage redesign
**Audience:** Senior HR leaders, CHROs, Benefits & Wellbeing leaders — US enterprise market
**North star metric:** Employee participation
**Companion artifact:** `vantage-fit-homepage-v2.html` (working hi-fi implementation of this strategy)

---

## 1. Homepage Audit & Recommendations

Audit of the current homepage (`vantagefit-astro`: `src/components/marketing/HomePage.astro` + `content/en/pages/home.yaml`).

### 1.1 Current structure (10 stacked sections)

1. Hero — "The wellness platform employees actually use — launched in days, not months."
2. Logo strip + "How Corporate Wellness programs help?" + 3 stat cards (59% / 88% / $250)
3. "A platform based on Cue > Action > Reward" (3 images)
4. Feature tabs — "Everything your workforce needs to stay healthy and active" (5 tabs)
5. Testimonials — "Real people, real results" (3 videos, far down the page)
6. "Why Vantage Fit?" — 3 benefit cards + product video + security pill strip
7. Blog — "Our Wellness Blogs"
8. Final CTA — "See why 100+ organizations trust Vantage Fit…"

### 1.2 Messaging weaknesses

- **Split-brain hero.** "Employees actually use" (participation) + "launched in days, not months" (vendor convenience) compete in one H1. Implementation speed is a proof point, not the promise — it belongs in micro-copy, not the headline.
- **No single metric owns the page.** Participation stats appear mid-page as decorative cards. For an HR buyer whose #1 failure mode is "nobody uses the benefit," the page never names the enemy (post-launch drop-off) or the north star (sustained participation).
- **Jargon-first frameworks.** "Cue > Action > Reward" asks the buyer to learn our behavioral-science model before understanding the value. Buyers buy outcomes, not frameworks.
- **Generic, SEO-flavored headings.** "How Corporate Wellness programs help?" (also grammatically broken) and "Everything your workforce needs to stay healthy and active" could appear on any competitor's site.
- **Feature-led, not outcome-led.** Five capability tabs describe what the product *has*, not what the buyer *gets* (a defensible participation number, a program that runs itself).
- **Credibility gaps an enterprise buyer will catch:**
  - Tata Motors engagement cited as **59%** (homepage) vs **70%** (team-challenges page) — inconsistent.
  - G2 rating cited as **4.6** (about) vs **4.5** (EWS page); Capterra **4.3** vs **4.5** — inconsistent.
  - "$250 healthcare savings per employee per year" — unsourced. Enterprise buyers (and their legal teams) will discount or challenge it.
  - Testimonial video `4h9eRm4hNe0` is credited to **"Shyam Surendran"** (homepage YAML, partnership pages) and **"Tarun Rangwani"** (client-testimonials page) — must be resolved before relaunch.
- **Trust is underweighted for the actual buying situation.** An India-headquartered vendor selling health-adjacent software to US enterprises faces a trust deficit. Today security is one pill-shaped strip ("Your data is safe with us") buried in section 6 of 8. SOC 2 / ISO 27001 / ISO 27701 / GDPR / HIPAA credentials deserve a first-class section.
- **AI story is absent from the homepage.** The product now has AI-powered insights (health data upload analysis, "what to launch next" recommendations, leadership insights). The schema/SEO copy even calls Vantage Fit an "AI-powered corporate wellness platform" — but the homepage never says it. For an "AI-first" refresh this is the single biggest messaging gap.

### 1.3 UX / UI issues

- **Length:** 8+ major sections with redundant beats (stats appear twice; CTAs 6+ times). Narrative momentum dies before the testimonials.
- **Buried proof:** the strongest conversion assets (customer videos, named customer stats) sit below the fold in sections 5–6 of 8.
- **Logo strip is a CSS sprite animation** — inaccessible (no alt text per logo), un-clickable, and it mixes small Indian brands with US enterprise names with no hierarchy.
- **Mixed audiences without a primary:** employee-app imagery and HR-buyer copy interleave without signaling "this page is for the HR buyer; the employee experience is the *evidence*."
- **Blog section on the homepage** is low-intent content that dilutes the conversion path; it belongs in Resources.
- **No persistent conversion element** — the demo CTA disappears on scroll.

### 1.4 Conversion opportunities

1. Make **participation** the hero promise *and* show it being measured (product UI as proof) — already the strength of the v1 sample; retain it.
2. Move **proof** (named-customer stats + video testimonials) into the middle of the page, immediately after the product story.
3. Add an **Enterprise Security & Compliance** section to neutralize the offshore-vendor objection before the final CTA.
4. One primary CTA ("Book a demo") repeated at each story beat + a sticky nav CTA; secondary CTA = pricing (pre-qualifies enterprise buyers).
5. Preempt the ROI question with honest, sourced, time-bounded stats ("who, what program, what period") instead of unsourced savings claims.

### 1.5 Retain / Remove / Consolidate

| Verdict | Content |
|---|---|
| **Retain** | 3 customer video testimonials (YouTube); named stats 59% Tata Motors / 88% IBS / 86% Brazosport ISD; "100+ organizations"; security certifications (SOC 2, ISO 27001, ISO 27701, GDPR, HIPAA); "launched in days" (as micro-copy); feature depth (challenges, rewards, analytics); final CTA. |
| **Remove** | Homepage blog section; "How Corporate Wellness programs help?" heading; unsourced "$250 savings" claim; decorative Cue>Action>Reward image row; brand watermark flourishes. |
| **Consolidate** | 5 feature tabs → one "two experiences" story (employee app + HR admin); stats cards + testimonials → one Proof section; security pill + Why-Vantage-Fit → one Trust section; 10 sections → 5. |

---

## 2. Information Architecture — New Homepage

Five full-screen sections + footer. One story: **Promise → Engine → Proof → Trust → Action.**

```
NAV (sticky)  Solutions ▾ · Features ▾ · Resources ▾ · Pricing · [Book a demo]

S1  HERO (100vh)
    Promise: participation as the outcome + product UI proving it (HR dashboard + employee app)
    Micro-trust bar (SOC 2 · launch speed · 100+ orgs) + customer logo strip

S2  THE PARTICIPATION ENGINE (product story, ~1.3 screens)
    Problem framing (post-launch drop-off) → 4-step loop: Invite → Participate → Reward → Improve
    Two-experience tabs: For employees / For HR teams (measurement story lives in HR panel)

S3  PROOF (100vh)
    3 named-customer result stats + 3 customer testimonial videos + case-study CTA

S4  ENTERPRISE TRUST (100vh)
    "Your data is safe with us" — 5 compliance credentials + 4 trust pillars + security CTA

S5  CLOSE (compact)
    Final CTA band: demo promise + pricing link + plan micro-copy + compliance chips

FOOTER  Product · Solutions · Resources · Company + certifications
```

**Design principles applied**

- **One idea per screen.** Each section answers exactly one buyer question, in the order enterprise buyers ask them: *What is it? → How does it work? → Does it work for companies like mine? → Can I trust you with my data? → What do I do next?*
- **Employee experience is evidence, not audience.** The page speaks to the HR buyer throughout; the employee app appears only as proof that participation will happen.
- **Show the metric, then show the proof.** The hero *displays* participation being measured; S3 *proves* it with customers; S4 *de-risks* it.
- **Progressive disclosure.** Deep feature detail moves to nav dropdowns and sub-pages; the homepage carries the narrative, not the catalog.

---

## 3. Navigation & Submenu Structure

Top level (unchanged per brief): **Solutions ▾ · Features ▾ · Resources ▾ · Pricing** + persistent **Book a demo** CTA. Links below map to existing site pages — no new page builds required.

### Solutions ▾ (organized by *how buyers buy*: challenge types + strategic needs)

| Group | Item | Target URL |
|---|---|---|
| **Challenges** | Step Challenges — "Launch a company-wide step challenge in minutes" | `/steps-challenge/` |
| | Team Challenges — "Build camaraderie with team-based competition" | `/team-challenges/` |
| | Multi-Activity Challenges — "65+ activities, one inclusive challenge" | `/multi-activity-challenges/` |
| | Virtual Marathon — "Unite a global workforce in a one-day event" | `/virtual-marathon/` |
| **By need** | Remote & Hybrid Team Wellness | `/remote-team-wellness/` |
| | Global Employee Engagement | `/global-employee-engagement/` |
| | Mental Health & Wellbeing | `/mental-health-and-wellbeing-challenges/` |
| | Holistic Wellness Program | `/holistic-wellness-program/` |
| | Wellness Rewards Program | `/wellness-rewards-program/` |
| | Workforce Health Analytics | `/health-fitness-analytics/` |
| *Featured* | Wellness Challenges Library → "23+ ready-to-run programs" | `/wellness-challenges/` |
| *Footer link* | All-in-one Employee Wellness Software → | `/employee-wellness-software/` |

### Features ▾ (organized by *user*: employee experience vs HR command center)

| Group | Item | Target URL |
|---|---|---|
| **Employee experience** | Activity Tracking | `/features/activity-tracking/` |
| | Personalized Programs | `/features/personalized-programs/` |
| | Mental Wellbeing | `/features/mental-health-and-mindfulness/` |
| | Incentives & Rewards | `/features/incentivization-and-rewards/` |
| | Wellness Leagues | `/features/wellness-leagues/` |
| **HR & admin** | Admin Dashboard | `/features/admin-dashboard/` |
| | Workforce Health Analytics | `/health-fitness-analytics/` |
| | Health Data Upload (AI insights) | `/features/health-data-upload/` |
| | Engagement Tools | `/features/engagement-tools/` |
| | Integrations | `/features/integrations/` |
| | Security & Compliance | `/features/security-and-compliance/` |

### Resources ▾

Blog · Client Success Stories (`/casestudy/`) · Guides · Tools & Templates · 2026 Industry Report · Podcasts · Help Center
*Featured:* ROI Calculator (`/tools-and-templates/`) · Competitor Comparisons (`/compare/`)

### Pricing — direct link (`/pricing/`), no dropdown.

**IA rationale:** Solutions = buyer problems (why they're here), Features = product capabilities (what we ship), Resources = self-education (how they justify internally). This mirrors how enterprise HR buyers navigate and scales cleanly as new challenges/features ship — new items slot into existing groups without restructuring.

---

## 4. Wireframe — Five Full-Screen Sections

### S1 — HERO (100vh, dark)

```
┌────────────────────────────────────────────────────────────────┐
│ TOPLINE: Employee wellness built around the metric that        │
│ matters first: participation.                                  │
├────────────────────────────────────────────────────────────────┤
│ NAV (sticky): ◆ Vantage Fit   Solutions▾ Features▾ Resources▾  │
│               Pricing                        [Book a demo]     │
├──────────────────────────────┬─────────────────────────────────┤
│ ● Built for sustained        │  ┌─ HR DASHBOARD (tilted) ────┐ │
│   participation              │  │ Participation rate  68% ↑7 │ │
│                              │  │ 1,455 of 2,140 · target 75%│ │
│ H1: More employees           │  │ [participation trend chart]│ │
│ participating. Better        │  └────────────────────────────┘ │
│ workforce wellbeing.         │   ┌─ PHONE: employee app ───┐  │
│                              │   │ Move Together challenge │  │
│ Lead paragraph (2 lines)     │   │ 72% to goal · 850 pts   │  │
│                              │   └──────────────────────────┘  │
│ [Book a demo] [See how       │   caption: Illustrative data    │
│  participation grows ↓]      │                                 │
│                              │                                 │
│ ● SOC 2 & ISO 27001 · Launch │                                 │
│   in days · 100+ orgs        │                                 │
├──────────────────────────────┴─────────────────────────────────┤
│ LOGO STRIP: Trusted by 100+ organizations across 50+ countries │
│ TATA MOTORS · WIPRO · HERSHEY · IBS SOFTWARE · BRAZOSPORT ISD  │
└────────────────────────────────────────────────────────────────┘
```

### S2 — THE PARTICIPATION ENGINE (~1.3 screens, light)

```
┌────────────────────────────────────────────────────────────────┐
│ EYEBROW: The participation engine                              │
│ H2: Most wellness programs flatline after launch week.         │
│     This one is built for day 90.                              │
│ Lead: problem framing (post-launch silence)                    │
│ ┌──────────┬──────────┬──────────┬──────────┐                  │
│ │ 01 Invite│02 Particip│03 Reward│04 Improve│  4-step loop    │
│ └──────────┴──────────┴──────────┴──────────┘                  │
│ TABS: [ For employees ] [ For HR teams ]                       │
│ ┌─ benefits (3, stacked) ────┬─ product screen ─────────────┐  │
│ │ employee: inclusion,       │ phone app  OR  admin console │  │
│ │ progress, rewards          │ (admin shows 68% gauge, dept │  │
│ │ HR: launch, measure, prove │ bars, Wellness Score 72)     │  │
│ └────────────────────────────┴──────────────────────────────┘  │
└────────────────────────────────────────────────────────────────┘
```

### S3 — PROOF (100vh, gray)

```
┌────────────────────────────────────────────────────────────────┐
│ EYEBROW: Proof, not promises                                   │
│ H2: Real programs. Real participation. On camera.              │
│ ┌─────────────┬─────────────┬─────────────┐                    │
│ │ TATA MOTORS │ IBS SOFTWARE│ BRAZOSPORT  │  big-number stats │
│ │    59%      │    88%      │    86%      │  + program names │
│ └─────────────┴─────────────┴─────────────┘  + variance note │
│ ┌─────────────┬─────────────┬─────────────┐                    │
│ │ ▶ VIDEO     │ ▶ VIDEO     │ ▶ VIDEO     │  click-to-play   │
│ │ Rachel A.   │ Shyam S.    │ Matt W.     │  YouTube thumbs  │
│ │ BISD        │ Landmark    │ BWC         │  + 1-line quote  │
│ └─────────────┴─────────────┴─────────────┘                    │
│ [ Explore all customer stories → ]                             │
└────────────────────────────────────────────────────────────────┘
```

### S4 — ENTERPRISE TRUST (100vh, dark)

```
┌────────────────────────────────────────────────────────────────┐
│ EYEBROW: Enterprise security & compliance                      │
│ H2: Your data is safe with us.                                 │
│ Lead: certified, audited, privacy-first from day one           │
│ ┌──────┬───────────┬───────────┬──────┬───────┐                │
│ │SOC 2 │ ISO 27001 │ ISO 27701 │ GDPR │ HIPAA │  cert badges  │
│ └──────┴───────────┴───────────┴──────┴───────┘                │
│ ┌─────────────┬─────────────┬─────────────┬─────────────┐      │
│ │ Certified & │ Regional    │ No external │ Enterprise  │      │
│ │ audited     │ data hosting│ PII sharing │ controls    │      │
│ └─────────────┴─────────────┴─────────────┴─────────────┘      │
│ [ Explore security & compliance → ]  Top-rated on G2 & Capterra│
└────────────────────────────────────────────────────────────────┘
```

### S5 — CLOSE (compact, coral)

```
┌────────────────────────────────────────────────────────────────┐
│ H2: Make participation the beginning of your wellness story —  │
│     not the missing chapter.                                   │
│ Demo promise (one line: tour, build a challenge, see the metric)│
│ [Book your Vantage Fit demo]  [Explore pricing]                │
│ No obligation · 50–50,000 employees · Single challenge or      │
│ year-round                              SOC 2 · ISO · GDPR · HIPAA │
└────────────────────────────────────────────────────────────────┘
FOOTER: brand + 4 link columns + certifications + © line
```

---

## 5. Complete Homepage Copy

> Status notes: product-UI numbers (68%, 1,455/2,140, etc.) are labeled "illustrative" on-page. Customer stats are verbatim from current case-study claims. Items flagged **[VERIFY]** need a fact-check before launch (see §1.2).

**Meta title:** Vantage Fit — Employee Wellness Platform Built for Participation
**Meta description:** Vantage Fit helps enterprises grow and sustain employee wellness participation — inclusive challenges, rewards people want, and AI-powered analytics that prove ROI. SOC 2, ISO 27001, GDPR & HIPAA ready.

### S1 — Hero

- **Kicker:** ● Built for sustained participation
- **H1:** More employees participating. Better workforce wellbeing.
- **Lead:** Vantage Fit turns one-time wellness launches into year-round habits — inclusive challenges every employee can join, rewards worth earning, and AI-powered analytics that prove it's working.
- **Primary CTA:** Book a demo → `/request-demo/`
- **Secondary CTA:** See how participation grows ↓ (anchor to S2)
- **Micro-trust (3 bullets):** SOC 2 & ISO 27001 certified · Launch in days, not months · 100+ organizations worldwide
- **Dashboard visual (illustrative):** Participation rate 68% (↑ 7 pts this quarter) · 1,455 participating / 2,140 enrolled · target 75% · 6-month participation trend · caption "Illustrative product data"
- **Phone visual:** "Move Together" challenge, 72% to goal, 6 active days, team rank #12, 850 points
- **Logo strip label:** Trusted by 100+ organizations across 50+ countries
- **Logos:** TATA MOTORS · WIPRO · HERSHEY · IBS SOFTWARE · BRAZOSPORT ISD · LANDMARK GROUP

### S2 — The Participation Engine

- **Eyebrow:** The participation engine
- **H2:** Most wellness programs flatline after launch week. This one is built for day 90.
- **Lead:** Wellness benefits rarely fail loudly — a launch email, a spike of sign-ups, then silence. Vantage Fit closes the loop that keeps employees joining, coming back, and progressing.

**The loop (4 steps):**
1. **Invite** — Launch a company-wide challenge in under 10 minutes, targeted by team, location, or the whole workforce. No IT project required.
2. **Participate** — 65+ activities and seven challenge formats — steps, mindfulness, sleep, nutrition, virtual marathons — so wellness is bigger than a fitness contest.
3. **Reward** — Points, badges, leagues, and gift cards from 100+ brands employees actually want — Amazon, Starbucks, Nike.
4. **Improve** — See participation by department and location in real time, and let AI recommend the program to run next.

**Tabs — For employees** *(subhead: A wellness app people open on purpose.)*
- **A way in for everyone** — Physical, mental, and everyday wellbeing — in 14+ languages, on any device, with or without a wearable.
- **Progress you can feel** — Personal goals, streaks, and team challenges turn a distant health outcome into today's next step.
- **Rewards worth earning** — Real effort converts to points employees redeem in a global catalog of 100+ brands.

**Tabs — For HR teams** *(subhead: A command center, not another dashboard.)*
- **Launch without a project** — Start from proven templates — step challenges, virtual marathons, habit streaks — and adapt goals, audience, and rewards.
- **One number to lead with** — A rolling 30-day participation rate with trends and department breakdowns — plus a Wellness Score for supporting context.
- **Proof for the CFO** — Exportable participation, rewards, and outcomes reports. No black-box promises.
- **Admin visual (illustrative):** 68% gauge · participation by department bars vs 75% target · Wellness Score 72/100 (supporting) · footnote: "Participation rate = unique enrolled employees completing a qualifying wellness action in the previous 30 days ÷ enrolled employees."

### S3 — Proof

- **Eyebrow:** Proof, not promises
- **H2:** Real programs. Real participation. On camera.
- **Lead:** The strongest proof is specific: who participated, in what program, over what period — and what HR leaders say when you ask them directly.

**Stats row:**
- **Tata Motors — 59%** workforce engagement in the "Step Up & Elevate" program across 43 teams. **[VERIFY: cited as 70% elsewhere on site]**
- **IBS Software — 88%** participation in a 28-day "March to Fitness" challenge — 17 points above the industry benchmark.
- **Brazosport ISD — 86%** engagement in a two-week "Fit Wars" challenge across district staff.
- **Disclaimer:** Customer program results; outcomes vary by workforce, program design, and measurement window.

**Video testimonials (click-to-play, YouTube):**
1. **Rachel Arthur** — Director of Benefits & Wellness, BISD (`LSX4pxSB6Qw`)
   "Vantage Fit has helped our employees stay active, track their progress, and get rewarded — turning wellness into a daily habit that drives both health and happiness across BISD."
2. **Shyam Surendran** — Sr. Manager Training, Landmark Leisure (`4h9eRm4hNe0`) **[VERIFY: also credited as "Tarun Rangwani" on client-testimonials page]**
   "Vantage Fit gave our team the first momentum toward healthier habits, turning 'something is better than nothing' into a culture of wellness and daily progress."
3. **Matt Whitmore** — Managing Partner, BWC Real Estate (`L_39IykL-O4`)
   "In just four months, Vantage Fit has seamlessly integrated into our growing business, boosted workplace wellbeing, and delivered incredible results for our employees."

- **CTA:** Explore all customer stories → `/casestudy/`

### S4 — Enterprise Trust

- **Eyebrow:** Enterprise security & compliance
- **H2:** Your data is safe with us.
- **Lead:** Wellness data is personal. Vantage Fit is certified, audited, and privacy-first from day one — so US enterprises can launch with confidence, wherever their teams are.
- **Certification badges:** SOC 2 · ISO 27001 · ISO 27701 · GDPR · HIPAA

**Trust pillars:**
1. **Certified & independently audited** — SOC 2 attestation and ISO 27001/27701 certification, with GDPR compliance and HIPAA-aligned safeguards for employee health information.
2. **Regional data hosting** — Dedicated data centers within your region keep employee data where your policies require it.
3. **No external sharing of PII** — Employee personal data is never sold or shared with third parties. Reports are aggregated so no individual can be identified. **[VERIFY: minimum-cohort threshold claim with product]**
4. **Enterprise-grade controls** — SSO, role-based access, consent management, and a dedicated health-data admin role come standard.

- **CTA:** Explore security & compliance → `/features/security-and-compliance/`
- **Micro-line:** Top-rated by HR teams on G2 and Capterra

### S5 — Close

- **H2:** Make participation the beginning of your wellness story — not the missing chapter.
- **Body:** In one 30-minute demo: tour the employee experience, build a sample challenge for your workforce, and see exactly how participation is measured.
- **Primary CTA:** Book your Vantage Fit demo → `/request-demo/`
- **Secondary CTA:** Explore pricing → `/pricing/`
- **Micro-copy:** No obligation · Plans for teams of 50 to 50,000 · Single challenge or year-round
- **Compliance chips (repeat):** SOC 2 · ISO 27001 · GDPR · HIPAA

### Footer

- **Brand line:** The employee wellness platform built to grow participation through inclusive programs, meaningful rewards, and measurable outcomes.
- **Product:** Employee Wellness Software · Pricing · Security & Compliance · Integrations
- **Solutions:** Step Challenges · Team Challenges · Virtual Marathon · Wellness Rewards
- **Resources:** Blog · Client Success Stories · Guides · Help Center
- **Company:** About Us · Partnerships · Contact · Download the App
- **Legal line:** © 2026 Vantage Circle. Homepage redesign prototype. · *Participation is the proof. Wellbeing is the promise.*

---

## 6. UX / UI Rationale — Why Each Section Exists

| Section | Buyer question it answers | Why it converts (enterprise HR lens) |
|---|---|---|
| **S1 Hero** | "What is it, and is it for me?" | Leads with the buyer's #1 anxiety — participation, not features. The product UI *in the hero* does two jobs: proves the north star is measurable, and shows the two interfaces HR must believe in (admin console + employee app). Micro-trust bar + logos neutralize the "unknown vendor" reflex within 5 seconds. Dark, data-forward aesthetic signals enterprise gravity, not consumer wellness fluff. |
| **S2 Engine** | "How does it actually work?" | Names the enemy (post-launch drop-off) before presenting the mechanism — problem-agitate-solve. The 4-step loop translates the old internal "Cue>Action>Reward" framework into buyer language. Employee/HR tabs let two stakeholders self-select without doubling page length; the HR panel carries the *measurement* story (rolling participation rate, department breakdowns, Wellness Score positioned as supporting context, not a black-box promise) — which is exactly how the admin product is designed (dashboard: participation north star, target lines, league/tier analytics). "AI recommends what to launch next" plants the AI-first flag using a real capability. |
| **S3 Proof** | "Does it work for companies like mine?" | Moves the strongest conversion assets to mid-page. Stats are specific and time-bounded (who, what program, what window) because enterprise buyers distrust round numbers; the variance disclaimer *builds* credibility. Video testimonials are the highest-trust asset on the site — a US benefits director (BISD) speaking to camera is worth more than any copy we write — and click-to-play keeps the section at one screen (no autoplay, no modals, privacy-enhanced youtube-nocookie embeds). |
| **S4 Trust** | "Can I put employee health data in your hands?" | Directly attacks the India→US trust deficit at the moment evaluation turns into procurement. Five credentials are shown as a badge row (scannable in 3 seconds), then four pillars answer the exact due-diligence questions infosec/legal will ask (audits, data residency, PII handling, access controls). Dark background gives the section institutional weight; linking to the full security page supports procurement self-service. |
| **S5 Close** | "What happens if I say yes?" | A single, low-friction ask with the demo *scoped* ("tour, build a challenge, see the metric") so the buyer knows the 30 minutes won't be a generic pitch. Pricing link pre-qualifies enterprise budget expectations. Repeating compliance chips next to the CTA is deliberate: the last thing seen before converting is a trust signal. |

**Cross-cutting UI decisions**

- **Full-screen rhythm, no scroll-jacking.** Sections use `min-height: 100svh` with content vertically centered, giving the "five screens" feel without scroll-snapping (which breaks accessibility and fights long content on short viewports; mobile relaxes to natural height).
- **Sticky nav with dropdowns** keeps "Book a demo" reachable at every scroll depth and carries the full IA without lengthening the page.
- **One CTA hierarchy everywhere:** coral primary (demo) + quiet secondary (pricing/anchor). No competing third action.
- **Honest data labeling.** Illustrative dashboard numbers are captioned as such; customer numbers carry program names and windows. This is a deliberate enterprise-credibility choice, not legal boilerplate.
- **Accessibility:** semantic landmarks, `aria`-correct tabs and dropdowns, keyboard-focusable menus, `prefers-reduced-motion` support, alt text on testimonial thumbnails.
- **Performance:** single self-contained HTML file, system font stack, zero JS libraries; videos load zero YouTube JS until clicked (facade pattern).

**What changed vs the v1 sample:** 11 sections → 5; added testimonial videos (S3) and full security section (S4); replaced v1's text-only nav with the production IA dropdowns; folded v1's standalone "measurement" section into the HR tab of S2 and its "responsible participation" ideas into S2/S4; dropped the FAQ and blog sections to Resources/pricing pages (documented in §1.5).

---

## Appendix — Pre-launch verification checklist

1. Resolve "Shyam Surendran" vs "Tarun Rangwani" credit on video `4h9eRm4hNe0`.
2. Reconcile Tata Motors engagement: 59% vs 70% across pages.
3. Reconcile review ratings (G2 4.5 vs 4.6; Capterra 4.3 vs 4.5) — homepage deliberately uses "top-rated on G2 and Capterra" until fixed.
4. Confirm "aggregated so no individual can be identified" (minimum-cohort reporting) with product before publishing S4 pillar 3.
5. Replace text wordmark logos with approved customer logo assets and confirm logo permissions (Hershey, Landmark Group).
6. Confirm SOC 2 report availability for procurement (link or "available under NDA" note on security page).
