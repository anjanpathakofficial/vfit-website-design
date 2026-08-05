# Mental Health & Wellbeing Challenge — Solutions Page Brief

**Page:** Mental Health & Wellbeing (individual Solutions / use-case page)  
**Live URL (context only):** https://www.vantagefit.io/mental-health-and-wellbeing-challenges/  
**Audience:** US enterprise HR / Benefits / Wellbeing leaders; program managers who run challenges  
**North star:** Participation in wellbeing programs people will actually join — not stigma-heavy clinical framing  
**Visual baseline:** `styled-homepage/` + `styles/enterprise.css` + Steps quality bar in `grok/`  
**Primary CTA:** Book a demo · **Secondary:** See pricing  

---

## 1. Research takeaways (product truth)

Sources prioritized: help docs (`vantagefit-astro/content/en/help/`), `vfit-os` specs (mindfulness, leaderboards, challenges, content), named case studies. Live marketing page is **not** source of truth.

### 1.1 What “Mental Health & Wellbeing” is in product

There is **no separate clinical product** and **no therapy / EAP substitute**. In product, this program is:

| Building block | What it is | Why it maps to this page |
|----------------|------------|--------------------------|
| **Custom Challenge** | Multi-week, multi-activity program with weekly themes, per-task points, optional teams | Primary vehicle for “wellbeing month” style campaigns |
| **Mind & body task types** | Meditation (minutes), Mindfulness (sessions / breathing), Yoga | Core mind-body challenge tasks |
| **Sleep Tracker** | Manual bedtime/wake or device sync (Apple Watch / Fitbit) | Rest / recovery themes |
| **Mood Log** | 1–5 scale + reason categories | Personal check-in; **private to employee** |
| **Guided mindfulness library** | 30+ audio sessions across 7 categories (meditation, sleep, relaxation, white noise, yoga, self-awareness, top picks) | In-app practice without a second meditation app |
| **Adherence (habit) activities** | Yes/no daily check-ins HR configures (e.g. sleep-before-11, gratitude journal if admin creates the habit) | Consistency without athleticism |
| **Custom loggable activities** | Company-named activities (e.g. Office Yoga, Meditation Sessions) | Brand workplace rituals into challenges |
| **Content / bite-size content tasks** | Read articles or short wellness content for points | Education without lectures |
| **Water / hydration** | Built-in water log as low-friction habit task | Easy “everyone can join” pillar |
| **Streak Challenge** | Daily **step** target only; ranks by days completed | Adjacent habit format — not mind-body multi-task |
| **Leaderboard opt-out** | Employee toggle; still participates, earns points; team score still counts | Critical for wellbeing stigma reduction |
| **Admin privacy boundary** | Admins see participation/rankings; **not** individual mood, sleep patterns, food diary, weight, HRA answers | Trust messaging for HR + legal |

**Primary format for this page:** Custom Challenge (not Race / E-Marathon as hero).  
**Secondary formats (light):** Streak for daily consistency when movement is the habit; parallel challenges allowed.

**Mode constraint:** Lite Mode = steps only. Mindfulness, mood, sleep, multi-activity require **Full Mode**. Be honest in FAQ.

### 1.2 Capabilities the page should sell (HR jobs)

| Capability | HR job | Source |
|------------|--------|--------|
| Weekly themed multi-activity challenges | Run a coherent wellbeing campaign (Move / Rest / Thrive), not a one-off quiz | Custom challenge help |
| Meditation + mindfulness + yoga as tasks | Include mind-body without a second vendor | Task types + mindfulness spec |
| Habit adherence + custom activities | Track consistency (yes/no and duration logs) | Adherence / custom activities help |
| Score caps on non-step tasks (100% of target) | Fair points for habits; no over-grind | Custom challenge scoring |
| Recognition: certificates, badges, Vantage Points → gift cards | Reward consistency, not podium athleticism | Certificates / badges / rewards help |
| Audience filters + public/private | Pilot a department or roll company-wide | Target audience help |
| Teams (optional; average of individuals) | Peer support without pure individual ranking | Custom challenge teams |
| Leaderboard opt-out | Participate privately | Employee opt-out help |
| Mood never on leaderboards / never to admins | Personal insight only | Task types note + mood help + privacy help |
| Regional data residency (IN / US / EU / UAE) | Enterprise security conversation | Admin data privacy help |
| Parallel challenges | Always-on habit + themed multi-week campaign | Parallel challenges help |

### 1.3 Clinical / claim boundaries (non-negotiable)

**Do claim**
- Wellbeing **engagement programs** HR can launch and measure
- Habit tasks: mindfulness minutes, meditation logs, sleep logging, hydration, content, custom habits
- Privacy-aware competition (opt-out; private mood)
- Participation analytics leadership can read

**Do not claim**
- Therapy, counseling, diagnosis, treatment, or clinical outcomes
- EAP / telehealth replacement (partnerships may exist elsewhere; not product core for this page)
- “Reduce anxiety / depression by X%” without approved clinical study
- Admin access to individual mood or sleep details
- That Streak format tracks meditation streaks natively (Streak = steps only)
- Unlimited or clinical-grade content library (catalog is curated ~30+ sessions, 7 categories)

**Tone rule:** No stigma-heavy “mental illness” framing. Sentence-case. No em-dashes. Verb-led CTAs. HR is the reader.

### 1.4 Proof we can cite (named, published)

| Outcome | Org | Context | Source |
|---------|-----|---------|--------|
| **86%** engagement | BISD (Brazosport ISD) | 2-week multi-activity “Fit Wars”; mindfulness 10–15 min ≥4×/week; hydration; steps | `casestudy/brazosport-case-study.md` |
| **59%** engagement · 1,248 active · **~7 min/day** mindfulness · **7h 39m** avg sleep logged | Tata Motors | 6-month digital wellness pilot (steps + yoga + sleep + mindfulness) | `casestudy/tata-motors-case-study.md` |
| Rachel Arthur quote (logging, points, recognition) | BISD | Benefits & Wellness director | Same case study |

**Rule:** Pair metric with org + program context. Add: *Customer experiences vary by workforce and program design.*  
**Optional only:** Use named results; do not invent wellbeing-only ROI or clinical deltas. BMI / mood score claims from case studies may be **sensitive** — prefer engagement + participation-style metrics on this page; if mood average is used, attribute carefully and avoid clinical interpretation.

### 1.5 Gaps / assumptions

| Item | Status |
|------|--------|
| No single SKU named “Mental Health Challenge” | True — Custom + mindfulness module + habits |
| “Gratitude” as built-in task | Not a named built-in type; admin can create adherence/custom activity |
| Guided sessions clinical quality | Lifestyle audio library, not clinical intervention |
| Sleep auto-sync | Documented for Apple Watch / Fitbit; manual also supported |
| Mood as challenge task | Documented as task type; scoring is completion-oriented; **values never on LB / never admin-visible** |
| Security certs (HIPAA, SOC 2, etc.) | Reuse homepage / security page claims; no new cert invented |
| Live URL content | Ignored as blueprint; rebuilt from product truth |

---

## 2. Page strategy

### Job of this page

Help an enterprise HR buyer answer:
1. Will people **join** a wellbeing program (not only the already-fit)?
2. Can we run **mind-body + habit** programs without buying a second meditation app?
3. Can we measure **participation** without becoming a surveillance tool or clinical system?
→ Book a demo.

### Positioning line

> Run wellbeing challenges employees will actually join — multi-activity habits, in-app mindfulness, privacy-aware leaderboards, and HR reporting on participation (not private health details).

### Narrative arc (decided — differs from Steps)

| # | Section | Intent |
|---|---------|--------|
| 1 | **Hero** | Wellbeing programs people join; dual CTAs; privacy micro-trust |
| 2 | **Proof strip** | Named engagement from multi-activity / wellness programs |
| 3 | **Program model** | Custom multi-week themes + mind-body task mix (signature element) |
| 4 | **Privacy-first participation** | Opt-out, private mood, what HR can / cannot see |
| 5 | **Why people join** | Low-barrier tasks, consistency rewards, no wearable mandate for mind-body logs |
| 6 | **Built for HR** | Launch → incentivize → measure participation |
| 7 | **Customer outcomes** | Optional named stories (BISD, Tata) |
| 8 | **FAQ** | Clinical boundary, privacy, Full Mode, formats |
| 9 | **Trust + final CTA** | Security + Book a demo / pricing |

**Signature element:** Themed multi-activity wellbeing program (task mix cards + example week themes), **not** four step formats.

### What we deliberately de-emphasize

- Pure step Race / E-Marathon as heroes (link as related).
- Clinical language, therapy, diagnostics.
- HRA / lab reports as centerpiece (available in product; not this page’s job).
- Gym-bro aesthetics and “win the leaderboard or fail.”

---

## 3. Full copy deck

### Meta

- **Title:** Mental Health & Wellbeing Challenges for Work | Vantage Fit  
- **Description:** Launch multi-activity wellbeing challenges with mindfulness, habits, sleep logging, private mood check-ins, and privacy-aware leaderboards. Measure participation. Book a demo.

### Nav (aligned with styled-homepage / Steps)

Solutions · Features · Resources · Pricing · **Book a demo**  
Solutions mega: By program includes Mental Health & Wellbeing (current).

### S1 — Hero

- **Eyebrow:** Solutions · Mental Health & Wellbeing  
- **H1:** Wellbeing challenges people will actually join.  
- **Lead:** Run multi-week programs that mix mindfulness, rest, hydration, and light movement. Low-barrier habits, private-by-choice rankings, and participation reports for HR — not a therapy product.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** See pricing  
- **Micro line:** Multi-activity Custom challenges · Guided mindfulness in-app · Leaderboard opt-out  

### S2 — Proof strip

- **Kicker:** Teams already running multi-activity wellbeing programs  
- **Chips:**  
  - **86%** engagement · BISD · 2-week campaign with mindfulness + hydration  
  - **~7 min/day** mindfulness · Tata Motors · 6-month wellness pilot  
  - **1,248** active participants · Tata Motors · plant-scale program  
- **Disclaimer:** Customer experiences vary by workforce and program design.

### S3 — Program model (signature)

- **Eyebrow:** How the program works  
- **H2:** One Custom Challenge. Many wellbeing tasks.  
- **Lead:** Build a multi-week campaign with a theme each week. Assign mind-body, habit, and education tasks with points — so the program feels curated, not like a pure steps race.

**Example themes (illustrative program design, grounded in product task types):**

| Week theme | Example tasks (product-real) |
|------------|------------------------------|
| Move gently | Steps or Active Minutes · Yoga log |
| Steady mind | Meditation minutes · Mindfulness session |
| Rest & recover | Sleep log · Guided sleep session |
| Daily habits | Water log · Adherence check-in · Content read |

**Task capability cards:**

1. **Meditation & mindfulness** — Log minutes or complete guided sessions from a 30+ library across seven categories (meditation, sleep, relaxation, and more).  
2. **Sleep tracking** — Log bedtime and wake time, or sync from supported devices.  
3. **Habit adherence** — Create yes/no daily habits employees check off (and can use beyond the challenge).  
4. **Hydration & light movement** — Water and steps keep the program inclusive for every fitness level.  
5. **Mood check-in (private)** — Optional 1–5 self log with reasons; never shown to admins or on leaderboards.  
6. **Content tasks** — Earn points for reading articles or short-form wellness content.

**Foot note:** Full Mode unlocks multi-activity and mind-body tasks. Lite Mode is steps-only.

**Foot CTA:** Want a sample 4-week wellbeing calendar for your workforce? Book a demo.

### S4 — Privacy-first

- **Eyebrow:** Built for trust  
- **H2:** Participation you can measure. Details employees keep.  
- **Lead:** Wellbeing programs die when people fear surveillance. Vantage Fit separates program metrics from private personal logs.

**Three pillars:**

1. **Leaderboard opt-out** — Employees hide from individual rankings and still complete tasks, earn points, and contribute to team averages.  
2. **Mood stays personal** — Mood entries are private to the employee — not visible to HR, managers, or colleagues.  
3. **What admins see** — Enrollment, challenge rankings, and team scores. Not individual weight, mood logs, food diary, sleep patterns, or HRA answers.

### S5 — Why people join

- **Eyebrow:** Built for participation  
- **H2:** Lower the stigma. Raise the join rate.  
- **Cards:**  
  1. **Low-barrier tasks** — Five-minute meditation and habit check-ins beat marathon-only culture.  
  2. **Consistency over athleticism** — Daily targets and score caps reward showing up, not over-grinding.  
  3. **Optional teams** — Peer accountability without forcing public individual ranking.  
  4. **Recognition that lands** — Certificates, badges, and Vantage Points redeemable for gift cards.  
  5. **One app for mind and body** — Guided sessions live next to challenges — no second meditation login.  
  6. **Private when needed** — Opt out of leaderboards without leaving the program.

### S6 — Built for HR

- **Eyebrow:** For HR & wellbeing program managers  
- **H2:** Launch a wellbeing campaign from the dashboard.  
- **Steps:**  
  1. **Create** — Choose Custom Challenge; set name, dates, privacy.  
  2. **Theme weeks** — Name weeks (e.g. Steady Mind, Rest) with logos and colors.  
  3. **Add tasks** — Meditation, mindfulness, sleep, water, content, adherence, custom activities; set daily or weekly mode and points.  
  4. **Target & incentivize** — Audience filters; points; optional certificates.  
  5. **Run & report** — Invite, nudge, watch leaderboards; export participation and reward activity.  
- **Measure note:** Report who joined and stayed active. Do not promise clinical outcome dashboards you do not have.

### S7 — Customer outcomes (optional, approved stories only)

- **Eyebrow:** Customer outcomes  
- **H2:** Wellbeing programs with named results.  
- **Feature:** BISD — **86%** engagement on a 2-week multi-activity campaign that included mindfulness sessions and hydration logging.  
- **Secondary:** Tata Motors — **59%** engagement, **1,248** active participants; average **~7 minutes** daily mindfulness and **7h 39m** sleep logged during a 6-month pilot.  
- **Quote (BISD):** “It's a great way to log activities. Employees are also rewarded with points, recognition and prizes.” — Rachel Arthur, Director of Benefits & Wellness  
- **Disclaimer:** Customer experiences vary…

### S8 — FAQ (4–5)

1. **Is this a therapy or EAP product?**  
   No. Vantage Fit is a wellbeing engagement platform for challenges, habits, and guided mindfulness content. It is not therapy, diagnosis, or a clinical treatment program. Pair with your EAP as needed.

2. **Can employees stay off the leaderboard?**  
   Yes. A Settings toggle hides them from individual rankings. They still participate, complete tasks, earn points, and can contribute to team scores.

3. **What personal wellbeing data can HR see?**  
   Participation and challenge standings. Admins cannot see individual mood logs, sleep patterns, food diary, weight, or Health Risk Assessment answers.

4. **Do we need a separate meditation app?**  
   No. Guided mindfulness audio (30+ sessions across seven categories) ships in Vantage Fit and can count toward challenge tasks.

5. **What challenge format should we use?**  
   Custom Challenge for multi-activity wellbeing themes. Use Streak when you want a simple daily step habit. Race and distance formats fit movement sprints — link them as related programs.

### S9 — Trust + final CTA

- **Eyebrow:** Enterprise security  
- **H2:** Wellbeing data handled with clear boundaries.  
- **Certs:** HIPAA · SOC 2 · GDPR · ISO 27001 · ISO 27701  
- **Final H2:** Ready to launch a wellbeing challenge people will join?  
- **Lead:** See a sample multi-week Custom Challenge, employee privacy controls, and HR reporting in a 30-minute walkthrough.  
- **Primary:** Book a demo · **Secondary:** See pricing  
- **Checks:** Multi-activity Custom challenges · In-app mindfulness · Leaderboard opt-out · Participation reporting  

### Related (light)

Steps Challenge · Multi-activity challenges · Team challenges · Holistic / year-round wellness · Remote team wellness  

### Footer

Product / Solutions / Company; Solutions lists Mental Health & Wellbeing (current) + Steps + related.

---

## 4. Wireframe notes

```
[Nav — Solutions current]
[Hero — H1 + lead + CTAs | task-mix preview visual]
[Proof strip — 3 chips]
[Program model — theme example + 6 capability cards]
[Privacy-first — 3 pillars]
[Participation — 6 cards]
[HR ops — numbered rail + dashboard image]
[Outcomes — 1 feature + support cards + optional quote]
[FAQ — accordion ~5]
[Related chips]
[Trust band + Final CTA]
[Footer]
```

**Visual system:** Noto Sans, coral/mint/charcoal, pill CTAs, 22px radii, sticky nav. Prefer product-real UI: admin analytics CDN image used on Steps; illustrative week themes as UI cards (label illustrative where needed).

**Accessibility:** Semantic headings, details/summary FAQ, focus-visible, reduced-motion respect, alt text on media.

---

## 5. Stats & source log

| Claim | Source path |
|-------|-------------|
| Custom multi-week multi-activity; weekly themes; task points; score caps | `help/admin/challenges/admin-how-do-i-create-custom-challenge.md` |
| 27 task types incl. Meditation, Mindfulness, Yoga, Sleep, Mood (private), Water, Content, Adherence | `help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md` |
| Adherence vs loggable custom activities | `admin-how-do-i-create-adherence-activities.md`, `admin-how-do-i-create-custom-activities.md` |
| Formats overview; Streak = daily steps habit; parallel challenges | `admin-what-challenge-formats.md` |
| Mindfulness 7 categories, 30+ sessions, challenge integration | `vfit-os/specs/03-health-wellness/mindfulness-meditation.md` |
| Plus menu: Mindfulness, Mood, Sleep | `help/employee/health-tracking/how-do-i-use-the-plus-menu.md` |
| Mood 1–5 private | `help/employee/health-tracking/how-do-i-track-my-mood.md` |
| Leaderboard opt-out (still earn points; team still counts) | `help/employee/challenges/can-i-opt-out-of-leaderboard.md` + `specs/02-challenges-gamification/leaderboards.md` |
| Admin cannot see mood, sleep patterns, food, weight, HRA; can see participation | `help/admin/settings/admin-data-privacy-security.md` |
| Certificates | `admin-how-do-i-configure-certificates.md` |
| Badges / consistency | `admin-how-do-badges-work.md` |
| Vantage Points / gift cards | `admin-how-wellness-rewards-work.md` |
| Lite Mode = steps only | `admin-what-is-lite-mode.md` / task types mode table |
| BISD 86%, mindfulness, Rachel Arthur | `casestudy/brazosport-case-study.md` |
| Tata 59%, 1248, 7 min mindfulness, 7h39m sleep | `casestudy/tata-motors-case-study.md` |
| Mission: habit product, not clinical | `vfit-os/MISSION.md` |
| Security certs strip | Styled homepage / security feature page (reuse) |

---

## 6. Deliverables

| File | Purpose |
|------|---------|
| `grok/MENTAL-HEALTH-BRIEF.md` | This document |
| `grok/vantage-fit-mental-health-wellbeing-v1.html` | High-fidelity mock (`../styles/enterprise.css`) |

---

## 7. Open items (non-blocking)

1. Confirm preferred hero case study for US buyers (BISD is US education; Tata is India manufacturing) — both used, BISD featured.  
2. Whether marketing may show aggregate organizational mood (BISD case study) without clinical reading — **omitted from hero metrics** to stay safe.  
3. Ship path in Astro for `/mental-health-and-wellbeing-challenges/` when replacing legacy page.  
4. Product marketing may later add EAP partner modules; do not hardcode partner claims until approved.
