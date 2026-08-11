# Wellness challenges (Library · flagship) brief

**URL:** `/solutions/wellness-challenges/`  
**Mock:** `vantage-fit-wellness-challenges-v1.html`  
**Role:** Flagship entry for the challenge library. Help HR **browse programs and pick a starting challenge type**. Showcase breadth (categories + formats + ready programs) without becoming a catalog dump. Link into single-format pages and platform/hub.

---

## 1. Research takeaways

### Product truth (what this page is about)

- Vantage Fit challenges are the **primary engagement engine**: HR creates from admin dashboard, employees join (manual or auto-enroll), track activity, climb leaderboards, earn points/badges/certificates.
- **Self-serve formats** (dashboard create): **Custom**, **Race**, **Journey**, **Streak**, **E-Marathon**.
- **Ops-only** (account manager): Level, GPS Marathon Event, Weight Burn, Training Plans. Mention lightly as available with AM; do not oversell as self-serve.
- **Library data** (`wellness-challenges.ts`): ~20 ready marketing programs across **physical, mental, nutrition, sleep, team, holistic**, each tagged with a format type (Race / Streak / Journey / E-Marathon / Custom) and individual/team/both.
- **Templates** in admin: pre-built configs (format, tasks, scoring, themes). HR still sets dates, audience, branding, teams, certificates.
- **Audience targeting:** all employees or filter by country, city, department, gender, age, language, health risk codes. Filtered challenges become Private.
- **Teams:** optional on Custom, Streak, Journey (average scoring). Race is individual-only for steps competition.
- **Integrity (nod only):** trusted sources, anomaly flags, buffers on rewards; full fairness deep-dive belongs on format pages (steps/team), not this library page.
- **Wearable not required** for many programs (phone steps, manual wellness logs for breathing, affirmations, mindful eating, etc.).

### Buyer job

US enterprise HR / Benefits / Wellbeing lead lands here when they search “corporate wellness challenges,” “employee wellness challenge ideas,” or browse Solutions. They need:

1. Proof there is **breadth** (not only steps).
2. A **path to pick** (category → format → program or deep-dive page).
3. Confidence they can **launch without a specialist** (self-serve + templates).
4. Clear next step: Book a demo, or drill into Steps / Multi-activity / Team / Virtual marathon.

### What this page is **not**

- Not a single-format product page (no full fraud leaderboard section, no average-scoring formula deep-dive).
- Not a dump of all ~20 challenge cards with long descriptions.
- Not a second homepage or platform page.

### Sources

| Source | Use |
|---|---|
| `vantagefit-astro/src/data/wellness-challenges.ts` | Program names, categories, formats, taglines |
| Help: `admin-what-challenge-formats.md`, `admin-how-do-i-create-a-challenge.md`, `admin-how-do-i-use-templates.md` | Self-serve vs ops, create flow, templates |
| OS: `specs/02-challenges-gamification/challenge-system-overview.md` | Lifecycle, 7 types, targeting, anti-cheat summary |
| Menu preview | Solutions IA: library flagship under Wellness challenges column |
| Shared research | Audience, CTAs, guardrails, sibling link targets |

---

## 2. Why this structure

Library archetype = **chooser with proof of breadth**, not problem→solution monologue.

| Section | Job |
|---|---|
| Hero | Frame as library + pick a starting type; primary CTA Book a demo; secondary Browse formats |
| Signal strip | Lean proof of breadth (formats, categories, ready programs). **Illustrative** counts from product data, not invented ROI |
| Browse by goal (categories) | Mental model: physical / mental / nutrition / sleep / team / holistic |
| Pick a format | Self-serve five formats with best-for lines + links to existing format pages |
| Ready programs (curated) | 6-8 real library programs, not full catalog; tag category + type |
| How HR launches | 4 steps: format/template → audience → optional teams/rewards → publish |
| Integrity (short) | One strip: fair competition, trusted tracking, no wearable required for many programs |
| FAQ | 4 rollout objections |
| Related + trust + final CTA | Sibling formats, rewards, platform, hub |

**Distinct from single-challenge pages:** no long “fairness formula” panel, no team-only formation grid, no single-metric leaderboard as the hero story. Hero is a **library browser mock** (admin challenge list + category filters + program cards).

---

## 3. Full copy deck

### Meta

- **Title:** Corporate Wellness Challenge Library for HR | Vantage Fit  
- **Description:** Browse ready wellness challenge programs across fitness, mental health, nutrition, sleep, and teams. Pick a format, launch from the dashboard, and track participation. Book a demo.

### Hero

- **Eyebrow:** Solutions · Wellness challenges library  
- **H1:** The challenge library HR uses to launch wellness people actually join.  
- **Lead:** Browse ready programs across fitness, mental health, nutrition, sleep, and teams. Pick a format, set the audience, and go live from the dashboard.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** Browse formats  
- **Micro:** Self-serve formats · Ready programs · Optional teams  

### Signal strip (illustrative product breadth)

Label: Built as a library, not a one-off race  

| Signal | Line |
|---|---|
| 5 | Self-serve formats Race, Streak, Journey, E-Marathon, Custom |
| 6 | Wellness categories Physical through holistic |
| 20+ | Ready program ideas Steps, sleep, sugar free, team yoga, and more |

*All three are product-structure counts from library data and help, not customer ROI.*

### Browse by goal

- **Eyebrow:** Start with the outcome  
- **H2:** Match the challenge to the habit you want.  
- **Lead:** Every ready program maps to a wellness category. Pick the goal first, then the format.

| Category | One line |
|---|---|
| Physical | Steps, cardio, cycle to work, strength |
| Mental | Breathing, affirmations, digital detox, work-life balance |
| Nutrition | Mindful eating, sugar free, plant-based |
| Sleep | Wind-down routines, 7-hour nights |
| Team | Department races, lunch walks, charity walk |
| Holistic | Multi-habit months when one metric is not enough |

### Pick a format

- **Eyebrow:** Self-serve formats  
- **H2:** Five formats you create from the dashboard.  
- **Lead:** Start simple or go multi-week. Your account manager can add specialized formats when you need them.

| Format | Best for | Link |
|---|---|---|
| Race | Quick competitions on one metric (often steps) | Steps Challenge page |
| Streak | Daily habit consistency | (anchor / multi-activity context) |
| Journey | Milestone map and multi-week adventure | Steps / multi-activity peers |
| E-Marathon | Virtual distance goals from steps | Virtual marathon page |
| Custom | Multi-week, multi-task programs | Multi-activity page |

Honest note: Level, GPS marathon events, Weight Burn, and Training Plans are configured with your account manager.

### Ready programs (curated sample)

- **Eyebrow:** Ready program ideas  
- **H2:** Programs employees recognize. Configurations you control.  
- **Lead:** Start from a proven theme. Adjust dates, audience, teams, and rewards before you publish.

Curated cards (from library data):

1. **Step it up** · Physical · Race · Log daily steps, race the leaderboard  
2. **Team step challenge** · Team · Race · Departments head-to-head on steps  
3. **Breathing exercise** · Mental · Streak · 10 minutes of breathwork daily  
4. **Mental health awareness** · Mental · Custom · Mood, mindfulness, check-ins  
5. **Sugar free** · Nutrition · Streak · Clean days for 30 days  
6. **Sleep challenge** · Sleep · Custom · 7 hours a night, logged  
7. **Charity walk** · Team · Race · Team kilometres toward a cause  
8. **Work life balance** · Mental · Custom · Boundaries and offline hours  

Footer: Explore format deep-dives for steps, multi-activity, teams, and virtual marathons.

### How HR launches

- **Eyebrow:** Admin workflow  
- **H2:** From idea to live challenge in one session.  

1. **Choose format or template.** Race for speed, Custom for multi-activity weeks, or a pre-built template.  
2. **Set tasks and targets.** Steps, hydration, mindfulness, content, and more depending on format.  
3. **Define who joins.** All employees or filter by department, location, or health risk codes. Optional teams.  
4. **Publish and measure.** Auto or manual join, leaderboards, points, badges, certificates, participation reports.

### Integrity strip

- **H3:** Competition people trust.  
- Trusted activity sources, anomaly checks, and a buffer before leaderboard bonuses credit. Many programs work with phone-only tracking or simple habit logs. No wearable required to participate in the library broadly.

### FAQ

1. **Is this only step challenges?**  
   No. Steps are popular, but the library covers mental health, nutrition, sleep, team social habits, and multi-activity Custom programs.

2. **Can HR create challenges without engineering help?**  
   Yes. Custom, Race, Journey, Streak, and E-Marathon are self-serve. Specialized formats are available with your account manager.

3. **Do employees need a wearable?**  
   No. Phone step sync covers many races and marathons. Streaks and Custom tasks often use in-app logs (breathing, meals, sleep check-ins).

4. **Can we run more than one challenge at once?**  
   Yes. Parallel challenges are supported so different teams or themes can run in the same period.

5. **How do we pick a first challenge?**  
   Many orgs start with a short Race (steps) or a simple Streak, then expand into Custom multi-week or team mode once habits stick.

### Related

- Step challenges  
- Multi-activity challenges  
- Team challenges  
- Virtual marathon  
- Wellness rewards program  
- Wellness platform  
- Solutions hub  

### Final CTA

- **H2:** Ready to build a challenge calendar people join?  
- **P:** See the library, formats, and admin create flow in a 30-minute walkthrough for your workforce.  
- **Checks:** Ready programs · Self-serve formats · Audience rules · Rewards tied to effort  

### Trust band

Standard enterprise line: HIPAA, SOC 2, GDPR, ISO 27001, ISO 27701.

---

## 4. Mega-menu fit

Under Solutions column **① Wellness challenges**:

- **Wellness challenges** (Library · flagship) ← this page, `aria-current`  
- Step challenges  
- Multi-activity challenges  
- Remote & hybrid team challenges  
- Virtual marathon  

Column **② Workforce health & rewards** links HRA, Insights, Rewards (sibling mocks as they ship). Featured: Platform + Hub in related/footer.

---

## 5. Stats / quotes policy

- **No fabricated customer ROI** on this page. Signal strip uses product-structure counts only.  
- Optional customer proof omitted (library page job is browse/pick; case metrics live better on format pages that already carry them).  
- Any UI numbers in mocks labeled illustrative.

---

## 6. Product gaps / notes

1. Marketing library (`wellness-challenges.ts`) is a **content catalog for the website**, not identical 1:1 to every admin template slug. Page presents programs as **ideas HR can configure**, not a guarantee every card is a one-click template ID.  
2. **E-Marathon** vs ops **GPS Marathon Event** can confuse buyers; copy keeps E-Marathon self-serve and GPS marathon as AM-only.  
3. **Holistic** category is used in IA language; library data mixes multi-habit programs under mental/custom more than a dedicated `holistic` key for every card. UI treats holistic as multi-habit intent.  
4. Journey deep-dive has no standalone Solutions mock yet; format card points to steps/multi-activity peers and demo.  

---

## 7. Design decisions (summary)

1. **Library browser hero** (admin list + category chips + program cards) instead of a single leaderboard phone.  
2. **Category → format → curated programs** funnel so breadth is scannable without 20 equal cards.  
3. **Format cards link out** to existing single-format pages; this page owns chooser narrative only.  
