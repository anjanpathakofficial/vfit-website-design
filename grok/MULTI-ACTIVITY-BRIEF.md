# Multi-activity Challenge — Solutions Page Brief

**Page:** Multi-activity Challenge (individual Solutions / use-case page)  
**Live URL (context only):** https://www.vantagefit.io/multi-activity-challenges/  
**Audience:** US enterprise HR / CHRO / Benefits / Wellbeing leaders; program managers who run challenges  
**North star:** **Employee participation** — why multi-activity (custom tasks beyond steps) includes more people and sustains programs  
**Visual baseline:** `styled-homepage/` + `styles/enterprise.css` + `vantage-fit-steps-challenge-v1.html`  
**Primary CTA:** Book a demo · **Secondary:** See pricing  

---

## 1. Research takeaways (product truth)

Sources prioritized: help docs (`vantagefit-astro/content/en/help/admin/challenges/`), employee challenge help, `vfit-os/specs/02-challenges-gamification/`, named case studies. Live marketing page was **not** treated as source of truth.

### 1.1 What “Multi-activity Challenge” actually is in product

In product, this maps to the **Custom Challenge** format (`vfit_campaign` / multiweek):

| Product name | Marketing page name | What it is |
|--------------|---------------------|------------|
| **Custom Challenge** | Multi-activity Challenge | Multi-week program with **weekly themes**, **multiple tasks per week**, per-task points, optional teams |

Help title: *“How do I create a custom (Multi-Week Multi-Activity) challenge?”*

**When to use (from help):**
- Multi-week wellness programs (e.g. 4-week “Wellness Month”)
- Multiple task types in one challenge (steps + water + meditation + content)
- Distinct theme, logo, and color per week
- Full control over scoring, targets, and team configuration

**Sibling formats (related links only, not this page’s hero):** Race, Streak, Journey, E-Marathon (steps-primary). Ops-only: Level, Marathon Event, Weight Burn, Training Plans.

### 1.2 Task inventory — count carefully (27)

Help article *“What tasks can I include in a Custom Challenge?”* (updated 2026-05-19) documents **27 task types** in Full Mode. Lite Mode is **Step Count only**.

| Category | Tasks (count) | Tracking style |
|----------|---------------|----------------|
| **Movement & Fitness** | Step Count, Distance, Calorie Count, Active Minutes **(4)** | Auto-tracked (phone/wearable) |
| **Workouts & Strength** | Strength Log, Aerobics / HIIT, Yoga **(3)** | Manual log |
| **Mind & Body** | Meditation, Mindfulness, Squat Tracker, Book Reading **(4)** | Manual (squat = in-app camera) |
| **Nutrition & Hydration** | Water Log, Meal Log **(2)** | Manual log |
| **Health Tracking & Vitals** | Sleep Tracker, Heart Rate, Weight, Health Vitals (HRA), Lab Report Upload **(5)** | Mix of manual / sync / upload |
| **Mental & Emotional** | Mood Log **(1)** | Manual; **private to employee** (not on leaderboards) |
| **Content & Learning** | Video Workout, Content Reading, Bite-Size Content **(3)** | Event-based (complete content) |
| **Habits & Specialized** | Smoking Cessation Log, Custom Loggable Activity, Adherence (Custom Habit), Doctor Visit, Manual Steps **(5)** | Manual / check-in |

**4 + 3 + 4 + 2 + 5 + 1 + 3 + 5 = 27**

**Beyond the 27:** Admins can create company-branded **custom loggable activities** and **adherence (habit) activities** at Configuration → Activities (e.g. “Office Yoga”, “Avoided Sugar”) and assign them as challenge tasks.

**Tracking behaviors (buyer-relevant):**
| Behaviour | Examples | Participation implication |
|-----------|----------|---------------------------|
| Auto-tracked | Steps, distance, calories, active minutes | Lowest friction |
| Manual log | Water, yoga, meditation, meals, sleep, custom activities | Requires habit; good for non-runners |
| Event-based | Content read/watch, lab upload, HRA | Education & compliance tasks |

**VFit OS note:** Spec `challenge-custom.md` says “20+ task types” (older/draft). Marketing uses **27** from the current help reference.

### 1.3 Capabilities the old marketing page under-sells

| Capability | Why it matters to HR | Source |
|------------|----------------------|--------|
| **Weekly themes** (name, logo, color per week) | Feels like a curated program, not a points dump | Custom challenge help |
| **Any mix of tasks per week** | Steps + mindfulness + hydration in one program | Custom challenge help |
| **Daily vs weekly mode** per task | “Hit target 4 days” vs “accumulate total” | Custom challenge help |
| **Per-task points + balanced scoring** | No single task dominates; score breakdown per task/week | Custom challenge help |
| **Score caps** | Non-step tasks: points up to 100% of target; steps default 25k/day (customizable via AM) | Custom challenge help |
| **Custom loggable + adherence activities** | Company-specific habits (Walking Meetings, vitamins) | Activities help |
| **Templates** (e.g. holistic multi-week) | Launch without blank-canvas design | Templates help |
| **Teams** (avg of individual scores) | Peer accountability for multi-task programs | Teams help |
| **Audience filters** + private/public | Pilot a dept or company-wide | Target audience help |
| **Certificates** with branding | Recognition beyond top-3 | Certificates help |
| **Full Mode vs Lite Mode** | Multi-activity requires Full Mode | Tasks help |
| **Parallel challenges** | Layer multi-activity over always-on streak | Parallel challenges help |
| **Timezone localization** | Global multi-week programs | Time zones help |

### 1.4 Proof we can cite (named, multi-activity-relevant)

| Outcome | Org | Why it fits multi-activity | Source |
|---------|-----|----------------------------|--------|
| **86%** engagement · 132 participants · 6,000+ avg steps/day | Brazosport ISD (“Fit Wars”) | Steps + 1-mile walks + mindfulness + water (multi-task campaign) | `brazosport-case-study.md` |
| Quote: activities, points, recognition, prizes | Rachel Arthur, Director of Benefits & Wellness, BISD | Named, approved | Same |
| **1,100+** participants · 63M+ steps | Intrado (“Healthy Me”, 5 weeks) | Steps + meal log + yoga + meditation; Custom Challenge builder cited | `intrado-healthy-me-campaign.md` |
| **3X** participation (163 → 550) across series | Wipro Global Wellbeing | Wellbeing Fest mixed steps, water, squats, mindfulness | `wipro-global-wellbeing.md` |
| Near-equal gender participation (49.3% women / 45.1% men) | William Grant & Sons | Multi-activity over months: steps, sleep, hydration, nutrition, mindfulness | `william-grant-sons-vantage-fit-case-study.md` |

**Rule:** Pair metric with org + program context. Add: *Customer experiences vary by workforce and program design.* Do not invent metrics.

### 1.5 Assumptions (stated)

- Buyers land here when step-only programs exclude desk workers, non-runners, or people who want mental/nutrition habits.
- Page positions **Custom Challenge** as the multi-activity product — not a separate SKU.
- Primary conversion is **Book a demo**.
- Security trust strip reuses homepage claims (HIPAA, SOC 2, GDPR, ISO 27001/27701).
- Mood Log privacy (employee-only) is a trust feature if mental health tasks are mentioned — not a hero claim.

---

## 2. Page strategy

### Job of this page

Help an enterprise HR buyer answer:
1. Will people who **don’t walk 10k steps** still participate?
2. Can we run **holistic** (move + mind + nourish) without five separate tools?
3. Can HR **build and score** multi-task programs without ops engineering?
→ Book a demo.

### Positioning line

> Multi-activity challenges include more of your workforce — weekly themes, 27 task types, and custom habits so wellness is not only a race for high steppers.

### Narrative arc (decided)

| # | Section | Intent |
|---|---------|--------|
| 1 | **Hero** | Inclusion + program depth + dual CTAs |
| 2 | **Proof strip** | Early credibility (multi-activity named results) |
| 3 | **Task-type explorer** | Signature: what employees can do (categories, not feature dump) |
| 4 | **Why multi-activity wins** | Participation outcomes: inclusion, variety, habit, education |
| 5 | **Built for HR** | Wizard: weeks → tasks → scoring → teams → publish |
| 6 | **Customer outcomes** | Brazosport feature + support cards |
| 7 | **FAQ** | Rollout objections (Lite Mode, complexity, scoring, desk workers) |
| 8 | **Trust + final CTA** | Security + Book a demo / pricing |

### Signature element

**Task-type explorer** (category cards + tracking legend) — product truth steps page cannot own. Formats explorer is for Steps Challenge; multi-activity owns **breadth of tasks + weekly builder**.

### What we deliberately de-emphasize

- Full 27-item catalog on-page (group by category; one-line each).
- Ops-only formats.
- Clinical BMI/ROI claims from case studies unless carefully framed (Brazosport BMI: optional, easy to overclaim — **omit from hero proof**).
- Spec’s “3X Wipro” without series context — use with program naming.

---

## 3. Full copy deck

### Meta

- **Title:** Multi-activity Wellness Challenges for Teams | Vantage Fit  
- **Description:** Run multi-week custom challenges with 27 task types — steps, hydration, mindfulness, content, and company habits. Include more employees. Book a demo.

### Nav (aligned with styled-homepage / steps page)

Solutions · Features · Resources · Pricing · **Book a demo**  
Solutions mega: Multi-activity challenges **current** under By program.

### S1 — Hero

- **Eyebrow:** Solutions · Multi-activity Challenge  
- **H1:** A wellness challenge that includes more than steppers.  
- **Lead:** Build multi-week programs with weekly themes and mixed tasks — movement, hydration, mindfulness, content, and company-specific habits — so desk workers and high performers can all earn points.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** See pricing  
- **Micro line:** 27 task types · Weekly themes · Custom habits  

**Hero visual (product-real):** Weekly program preview card  
- Week 1: Move — Steps + Active Minutes  
- Week 2: Nourish — Water + Meal Log + Content  
- Week 3: Rest — Sleep + Meditation  
- Week 4: Thrive — Steps + Water + Adherence  

### S2 — Proof strip

- **Kicker:** Multi-activity programs with named results  
- **Chips:**  
  - **86%** engagement · Brazosport ISD · Fit Wars (steps + mindfulness + water)  
  - **1,100+** participants · Intrado · 5-week Healthy Me  
  - **3X** participation · Wipro · multi-challenge series with holistic weeks  
- **Disclaimer:** Customer experiences vary by workforce and program design.

### S3 — Task-type explorer

- **Eyebrow:** What’s in a multi-activity challenge  
- **H2:** 27 task types. Mix what your workforce will actually do.  
- **Lead:** Auto-tracked movement for low friction. Manual logs for habits. Content and custom activities for culture-fit programs.

**Category cards (short one-liners):**

| Category | One-line | Example tasks |
|----------|----------|---------------|
| Movement & fitness | Phone or wearable sync | Steps, distance, calories, active minutes |
| Workouts & strength | Log sessions in the app | Strength, HIIT, yoga |
| Mind & body | Minutes that count for points | Meditation, mindfulness, squats, reading |
| Nutrition & hydration | Daily habits, not only miles | Water, meal log |
| Health vitals | Screenings and baselines | Sleep, heart rate, weight, HRA, lab upload |
| Content & learning | Finish to complete | Videos, articles, bite-size lessons |
| Habits & custom | Your company’s language | Adherence check-ins, custom loggable activities, doctor visit |

**Legend strip:** Auto-tracked · Manual log · Event-based  
**Foot:** Full Mode unlocks all task types. Lite Mode is steps-only — ask about upgrading for multi-activity.

### S4 — Why multi-activity wins (participation)

- **Eyebrow:** Built for participation  
- **H2:** Give every employee a way to score.  
- **Cards (short):**  
  1. **Include non-runners** — Hydration, mindfulness, content, and desk-friendly tasks so step totals are not the only path to points.  
  2. **Weekly themes keep novelty** — Move, Nourish, Rest, Thrive — each week feels new without relaunching the whole program.  
  3. **Balance the leaderboard** — Set points per task so one marathon week does not erase consistent habit-keepers.  
  4. **Company-specific activities** — Create “Walking Meeting” or “Avoided Sugar” and assign them as challenge tasks.  
  5. **Teams optional** — Team score averages individuals so quiet contributors still matter.  
  6. **Templates to launch faster** — Start from a pre-built multi-week template, then tune targets and branding.

### S5 — Built for HR

- **Eyebrow:** For HR & program managers  
- **H2:** Design the program in the dashboard wizard.  
- **Steps:**  
  1. **Create** — Select Custom Challenge; set name, dates, image, privacy.  
  2. **Theme weeks** — Name each week; set theme logo and color.  
  3. **Add tasks** — Pick types, targets, daily or weekly mode, and points; drag to reorder.  
  4. **Score fairly** — Cap over-target abuse; review score breakdown design so no single task dominates.  
  5. **Audience, teams, certificates** — Filter who joins; optional teams and branded certificates.  
  6. **Publish & run** — Invite, notify, watch multi-task leaderboards and enrollment health.  
- **Measure note:** Enrollment status, challenge leaderboards with per-task score breakdown, points and redemptions — program health, not clinical surveillance.  
- **Global note:** Time zones localize challenge windows for multi-country teams.

### S6 — Customer outcomes

- **Eyebrow:** Customer outcomes  
- **H2:** Multi-activity programs with published results.  
- **Feature story:** Brazosport ISD — **86%** engagement on “Fit Wars” (2 weeks): steps targets, walks, mindfulness sessions, water logging. Quote: *“It's a great way to log activities. Employees are also rewarded with points, recognition and prizes.”* — Rachel Arthur, Director of Benefits & Wellness.  
- **Secondary:**  
  - Intrado — **1,100+** participants · Healthy Me · steps + meals + yoga + meditation  
  - Wipro — **3X** participation across a 2025 challenge series including holistic Wellbeing Fest  
  - William Grant & Sons — multi-activity wellness; near-equal gender participation (**illustrative of inclusion**, cite carefully: 49.3% women / 45.1% men of participants)  
- **Links:** Read customer stories · View testimonials  
- **Disclaimer:** Customer experiences vary…

### S7 — FAQ (rollout objections)

1. **How is this different from a step challenge?**  
   Step challenges (Race, Streak, Journey, E-Marathon) center on steps or step-derived distance. Multi-activity uses the **Custom Challenge** format: multiple task types per week, weekly themes, and balanced multi-task scoring.

2. **Will desk workers and non-runners participate?**  
   Yes — that is the design intent. Pair auto-tracked steps with water, mindfulness, content, adherence, and custom activities so people who are not high steppers still complete tasks and earn points.

3. **Is multi-activity available on every plan?**  
   **Full Mode** includes all 27 task types. **Lite Mode** is Step Count only. Your account manager can confirm mode and upgrade path.

4. **How does scoring work across different tasks?**  
   Each task has its own point value. Employees earn toward the task target (non-step tasks do not pay extra past 100% of target; steps use a daily cap, default 25,000). Total score sums points across tasks and weeks. Employees can open a score breakdown per task and week from the leaderboard.

5. **Can we invent company-specific tasks?**  
   Yes. Create custom loggable activities or adherence habits under Configuration → Activities, then add them as tasks in a Custom Challenge (e.g. Office Yoga, Walking Meetings, Took Vitamins).

6. **Do we have to build from scratch?**  
   No. Use pre-built challenge templates with recommended tasks, targets, and weekly structure, then adjust dates, audience, branding, and difficulty.

### S8 — Trust + final CTA

- **Eyebrow:** Enterprise security  
- **H2:** Participation data your security team can review.  
- **Certs:** HIPAA · SOC 2 · GDPR · ISO 27001 · ISO 27701  
- **Final H2:** Ready to run a multi-activity challenge?  
- **Lead:** See the Custom Challenge builder, employee task experience, and HR reporting in a 30-minute walkthrough.  
- **Primary:** Book a demo · **Secondary:** See pricing  
- **Checks:** 27 task types · Weekly themes · Custom habits · Templates · Full Mode  

### Related (light)

Steps Challenge · Team challenges · Virtual marathon · Wellness rewards · Year-round wellness program  

### Footer

Product / Solutions / Company; Solutions lists Multi-activity (current) + siblings.

---

## 4. Wireframe notes

```
[Nav — Solutions current → Multi-activity]
[Hero — H1 + lead + CTAs | week-by-week program preview]
[Proof strip — 3 multi-activity chips]
[Task explorer — category grid + tracking legend]
[Participation pillars — 2×3 short cards]
[HR ops — numbered rail + admin/product visual]
[Outcomes — Brazosport feature + 2–3 support cards + quote]
[FAQ — accordion ~5–6]
[Related pills]
[Trust band + Final CTA]
[Footer]
```

**Visual system:** Noto Sans, coral/mint/charcoal, pill CTAs, 22px radii, sticky nav + mega from homepage. Prefer product-real UI (weekly themes, task list, admin wizard). CDN dashboard image where available.

---

## 5. Stats & quote source log

| Claim | Source path |
|-------|-------------|
| 27 task types + categories + Lite/Full Mode | `help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md` |
| Custom challenge wizard, weekly themes, daily/weekly mode, scoring caps, teams | `help/admin/challenges/admin-how-do-i-create-custom-challenge.md` |
| Custom loggable activities | `help/admin/challenges/admin-how-do-i-create-custom-activities.md` |
| Adherence activities | `help/admin/challenges/admin-how-do-i-create-adherence-activities.md` |
| Formats map (Custom = multi-activity) | `help/admin/challenges/admin-what-challenge-formats.md` |
| Templates | `help/admin/challenges/admin-how-do-i-use-templates.md` |
| Employee complete tasks (auto/manual/event) | `help/employee/challenges/how-do-i-complete-challenge-tasks.md` |
| Team average scoring | `help/admin/challenges/admin-how-do-i-manage-teams.md` |
| Rewards / points | `help/admin/challenges/admin-how-wellness-rewards-work.md` |
| Custom = multiweek product behavior | `vc-os/vfit-os/specs/02-challenges-gamification/challenge-custom.md` |
| Brazosport 86%, Fit Wars multi-task, Rachel Arthur quote | `casestudy/brazosport-case-study.md` |
| Intrado 1,100+, Healthy Me multi-activity | `casestudy/intrado-healthy-me-campaign.md` |
| Wipro 3X participation series | `casestudy/wipro-global-wellbeing.md` |
| William Grant multi-activity / gender split | `casestudy/william-grant-sons-vantage-fit-case-study.md` |
| Security certs | Styled homepage / security feature page claims |

---

## 6. Deliverables

| File | Purpose |
|------|---------|
| `MULTI-ACTIVITY-BRIEF.md` | This document |
| `vantage-fit-multi-activity-challenge-v1.html` | High-fidelity mock |

---

## 7. Open items (non-blocking)

1. Exact public template names in the library (help examples: “4-Week Holistic Wellness”, “Mindful March”) — confirm production list before hardcoding template product names beyond generic language.  
2. Active Minutes may require feature flag / account manager enablement — do not claim always-on for every tenant.  
3. VFit OS “20+” vs help “27” — prefer help for customer-facing count; keep engineering aligned later.  
4. Ship in Astro as refreshed `/multi-activity-challenges/` when ready to replace legacy page.
