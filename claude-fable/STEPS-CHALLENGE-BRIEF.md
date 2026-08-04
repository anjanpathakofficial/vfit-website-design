# Vantage Fit — Steps Challenge Solutions Page Brief (v1)

Model workspace: `claude-fable` · Deliverable pair: this brief + `vantage-fit-steps-challenge-v1.html`
Baseline: `../styled-homepage/` + `../styles/enterprise.css` · Companion mock: `vantage-fit-solutions-v1.html` (Solutions hub, prior pass; its brief now lives at `SOLUTIONS-HUB-BRIEF.md`)

---

## 1. Executive summary

The live `/steps-challenge/` page is the strongest use-case page on the site and it still sells
a fraction of the product. It lists four challenge formats as bare bullets (omitting the one
help docs call "the go-to format for most clients"), cites zero step statistics while sitting
on the richest approved proof pool in the company, answers step tracking with a Google-Fit-only
FAQ that erases the entire iPhone experience, and says nothing about the two things an
enterprise buyer actually probes: whether the numbers can be trusted, and what HR has to do to
run the thing.

This redesign rebuilds the page from product truth (help docs, admin dashboard designs, and
the vfit-os spec tree) around one spine: **a step challenge the whole company joins, with
numbers leadership can believe**. Eight sections: a product-forward hero, the five real
formats with their mechanics made visible, the inclusion story employees feel, the anti-cheat
story IT and Finance ask about, the HR control room, step-specific named proof, the trust
strip, and one demo CTA. Every claim traces to a source in §6.

---

## 2. Research takeaways

Audited: live page + `content/en/pages/use-cases/steps-challenge.yaml`, help docs
(`content/en/help/admin/challenges/`, `employee/challenges/`, `employee/getting-started/`),
dashboard designs (`vc-dashboard-design`), product specs + rules (`vfit-os`).

### 2.1 What the current page gets wrong

- **Formats are names, not mechanics.** "Race, Streak, E-marathon, Journey" as four bullets
  with zero explanation (`steps-challenge.yaml:22-29`). Custom multi-week is missing entirely,
  despite help docs calling it "almost always the right choice"
  (`admin-how-do-i-create-custom-challenge.md:15`).
- **The tracking FAQ is wrong for a US buyer.** "…logged in through Google Fit"
  (`steps-challenge.yaml:60`) — no Apple Health, no Fitbit/Garmin, no "no wearable required."
  The buyer reading this page is statistically on an iPhone.
- **Zero step stats on a step page.** The generic three-tile proof block (Tata 59% · IBS 88% ·
  BISD 86%) is shared across all ten use-case pages, and it uses the stale Tata figure — the
  newer step-specific result (70%, 43 teams) exists and is approved.
- **The #1 objection is unanswered.** Nothing about anti-cheat, device double-counting, or
  how winners are validated. Nothing about admin reporting or exports either.
- **Weakest possible testimonial** ("Coach Pyry", no company) on a page sitting one directory
  away from 30+ named-customer step case studies.

### 2.2 What the product actually has (under-sold or unsaid)

1. **Five self-serve step formats**, each a genuinely different game:
   Race (no target, pure live leaderboard) · Streak (daily target + days-completed scoring;
   miss a day, the streak resets) · Journey (cumulative milestones on a visual map; three
   ready templates: 7 Wonders of the World, Backpacking Europe, Everest Run) · E-Marathon
   (steps become distance at a configurable 1,000 steps = 1 km, km or miles) · Custom
   (multi-week themes, steps plus up to 27 task types). Formats run in parallel without limit,
   and a single walk credits every challenge it matches.
2. **A documented data-integrity subsystem**: steps accepted from recognized sources only,
   anomaly detection on implausible spikes, one primary device at a time (switching
   auto-disconnects the old one), GPS pace validation with vehicle detection, manual entry off
   by default, and a deliberate 3-day post-challenge buffer before winners are confirmed
   because wearables sync late. This is the single most credible thing the page can say and
   the live page says none of it.
3. **Inclusion mechanics that drive the participation number**: team scores are the average of
   members, not the sum ("a team of 5 where everyone scores 80 beats a team of 10 averaging
   70"); the badge ladder starts at 3,000 steps a day; leaderboard opt-out preserves points
   and team contribution; wheelchair mode exists; mood and health details are never public.
4. **A real HR workflow**: 5–10-minute creation wizard, pre-built templates, audience
   targeting on seven filters with a live match count and auto-enrollment (including
   new hires who become active mid-challenge), automated lifecycle emails, mid-flight editing
   plus force start/stop, per-participant time-zone localization (start, end, and the daily
   reset all hit at each person's midnight), and leaderboard CSV exports with per-task score
   breakdowns.
5. **Step-specific proof, approved and unused**: Tata Motors "Step Up & Elevate" (70%
   engagement, 43 teams, 7,600+ avg daily steps); POSOCO (97% participation, 11M+ steps in
   two weeks); IBS Software (88% engagement; 236 employees at 30,000+ steps/week by week 3);
   Wipro (participation 3X, 163 → 550 users, 30+ countries).

### 2.3 Claims corrections applied (vs the live page and even our own hub mock)

- "Trusted by 100+ organizations worldwide" — the only approved scale figure. The "in 50+
  countries" suffix used on the baseline homepage band is flagged for removal in the content
  refresh project, so this page drops it.
- Logo band uses approved client names only: Accenture and Hershey (present on the baseline
  band) are not on the approved-names list, so they are replaced with Godrej and
  Heidrick & Struggles.
- "Set up in under 10 minutes" (live subhead) is unsourced in specs; help docs say the wizard
  takes 5–10 minutes (`admin-how-do-i-create-a-challenge.md:13`). Copy says "minutes," and the
  one place a number appears it is "5–10 minutes," cited to help docs.
- Employees do not browse-and-join; enrollment is admin-added or audience-rule automatic.
  Copy never implies a join button.
- Engagement and participation are labeled as measured, never interchanged.
- No Slack/Teams claims (zero spec coverage), no ISO/GDPR claims in copy (SOC 2 Type II and
  "operates under HIPAA guidelines" only), Apple Health and Google Fit both named.
- No 25,000-step cap number in copy (help docs and specs disagree on its current state);
  the page says anomaly filtering exists without quoting a threshold.

---

## 3. Strategy: the story this page tells

**Buyer:** US enterprise HR / benefits / wellbeing leader, plus the program manager who will
actually run it. Search-intent research says this buyer is **mid-launch, not mid-research**
("give me the assets") — so the page never argues that step challenges matter. It answers, in
order, the five questions that decide the deal:

| # | Buyer question | Section |
|---|---|---|
| 1 | What exactly can I run? | S2 Five formats |
| 2 | Will my people actually join, and stick? | S3 Employee experience |
| 3 | Can I trust the numbers? | S4 Fair-numbers band |
| 4 | How much work is this for my team? | S5 HR control room |
| 5 | Who has done this and what happened? | S6 Proof |

Participation (the homepage north star) is the connective tissue: S3 is why people join, S4 is
why the number survives scrutiny, S5 is how HR reports it. Trust (S7) and one demo CTA (S8)
close. FAQ was considered and dropped per review; its four objections are folded into the
sections above (wearables → S3, time zones → S5, privacy → S7, launch speed → S1/S5).

**Design signature** (within the locked system): each format card in S2 carries a small
mechanic glyph — ranked bars for Race, seven day-dots for Streak, a milestone path for
Journey, a distance ring for E-Marathon, stacked week blocks for Custom — so the structure
itself teaches what the old page failed to explain. S4 makes the anti-cheat story visible: a
leaderboard snippet in which one implausible entry is flagged "source rejected." Everything
else reuses the baseline vocabulary unchanged.

---

## 4. Page architecture and wireframe notes

Eight sections. Every pattern from `enterprise.css` / the hub mock unless marked *(new)*.

### S1 — Hero (product-forward) + logo band
- Left: eyebrow `Solutions · Steps Challenge`, H1 with coral-gradient `em`, lead, CTA row
  (Book a demo · See pricing), three hero-note pills (no wearable · five formats ·
  aggregate-only reporting).
- Right: the baseline's `.dash` + `.phone` product composition, populated with step-challenge
  content: admin card showing a live challenge's participation and step trend; employee phone
  showing the challenge card, progress bar, and today's stats. Illustrative UI numbers, not
  claims.
- Logo band pinned to hero foot: "Trusted by 100+ organizations worldwide" + approved names.

### S2 — Five formats (canvas)
- H2 + lead, then a 3+2 `.format-card` grid *(new)*: mechanic glyph, name, mechanic sentence,
  `Best for` tag line. Foot note covers parallel challenges + one-walk-counts-everywhere.

### S3 — Employee experience (white)
- Split layout: left, six `.join-point` rows *(new — icon + bold + one-liner)*; right, the
  real employee-app screenshot (CDN asset from the baseline homepage).
- Covers: automatic enrollment, any-phone tracking (devices named), team-average scoring,
  badges from 3,000 steps, opt-out + wheelchair mode + private mood, local-currency rewards
  from the unified wallet.

### S4 — Fair numbers (dark band)
- H2 "Leaderboards your skeptics can audit." + lead, four `.trust-card`s (reused pattern):
  trusted sources · one device at a time · anomaly + GPS checks · 3-day results buffer.
- Right rail: `.audit-board` *(new)* — leaderboard snippet with one flagged row ("Source
  rejected") demonstrating the filter. Fine-print line: manual entry off by default.

### S5 — HR control room (canvas)
- Tour-tabs pattern (baseline): two tabs, "Launch & run" / "Prove it".
  - Tab 1 checks: 5–10-minute wizard + templates; audience rules with live match preview and
    auto-enrollment; automated lifecycle comms + mid-flight controls; time-zone-true global
    runs. Media: `.launch-mock` *(new)* — compact create-wizard card built from baseline
    admin-card language.
  - Tab 2 checks: participation rate vs target; department breakdown + step trends;
    leaderboard CSV with per-task breakdown; transaction/redemption/league reports. Media:
    real admin analytics screenshot (CDN asset). Measure-note repeats the participation-rate
    definition + aggregate-only line.

### S6 — Proof (proof-screen background)
- Four `.result-card`s (hub pattern) — Tata 70% · POSOCO 97% · IBS 88% · Wipro 3X — each
  tagged with client, program name, and segment; engagement/participation labeled correctly.
- Quote band (hub pattern): Rachel Arthur (photo asset + video modal) + a second text-only
  quote row from Momentum Investments (step-challenge-specific).
- Fine print + link to customer stories.

### S7 — Trust (dark, hub's 2×2 + plaque)
- Lead reframed for step data. Cards: private by design (admins see participation and
  rankings, never individual health details) · regional data residency (IN/US/EU/UAE) ·
  SSO & HRIS (SAML 2.0: Okta, Azure AD, OneLogin, Ping; Workday/ADP/DarwinBox, CSV, SFTP) ·
  independently audited (SOC 2 Type II; operates under HIPAA guidelines).
- Baseline certifications plaque reused for visual continuity (see §6 caveat).

### S8 — Related programs + final CTA
- Slim related row *(reuses hub's marathon-row)*: Team Challenge · Virtual Marathon ·
  Year-round Wellness Program (light links only, per the brief).
- Final CTA (baseline pattern): demo promise, Book a demo · See pricing, three final-checks.
- Footer: hub footer, Steps Challenge highlighted.

**Mobile:** format grid → single column; S3 split stacks (image below); audit-board stacks
under the trust cards; tabs keep the baseline's small-screen behavior; nav uses the baseline
accordion mega.

---

## 5. Copy deck (full)

> Final proposed strings. `<em>` marks the coral-gradient span. Written to the vfit-os voice
> guide: no em-dashes outside verbatim quotes and attributions, none of the banned buzzwords,
> restraint over hype.

**Meta title:** Corporate Step Challenge App for Teams | Vantage Fit
**Meta description:** Run a step challenge employees actually join: five formats, fair
leaderboards, automatic tracking, and reporting leadership can trust. Book a Vantage Fit demo.

### Nav
Solutions (current) · Features · Resources · Pricing · **Book a demo**
Mega: Steps Challenge marked as current page; banner links to the Solutions overview (hub).

### S1 Hero
- Eyebrow: `Solutions · Steps Challenge`
- H1: `A step challenge the <em>whole company</em> joins.`
- Lead: `Not just the athletes. Vantage Fit counts steps from any phone, scores teams by
  average so every member matters, and keeps leaderboards fair enough to survive your most
  competitive department. Create one from the dashboard in minutes.`
- Buttons: `Book a demo` (primary) · `See pricing` (outline)
- Hero pills: `No wearable required` · `Five challenge formats` · `Aggregate-only HR reporting`
- Hero visual labels (illustrative): admin card "Spring Steps Race — participation 82%, day 12
  of 28, steps trend"; phone "Spring Steps Race · 8,412 / 10,000 steps today · team rank #3".
- Logo band: `Trusted by 100+ organizations worldwide` — TATA MOTORS · WIPRO · TEVA · GODREJ ·
  TEXAS INSTRUMENTS · HEIDRICK & STRUGGLES · BRAZOSPORT ISD

### S2 Formats
- Eyebrow: `Five formats`
- H2: `One goal. Five ways to run it.`
- Lead: `Every workforce competes differently. Pick the format that fits yours, or run several
  at once: challenges stack without limit, and a single walk counts toward every challenge it
  matches.`
- Cards:
  1. **Race** — `No targets, no setup debates. Everyone climbs the same live leaderboard, and
     the most steps win.` · Best for: `your first challenge, 2 to 4 weeks`
  2. **Streak** — `A daily step goal, scored by days completed. Miss a day and the streak
     resets, so showing up beats sprinting.` · Best for: `habit building, e.g. 8,000 steps on
     4 days a week`
  3. **Journey** — `Walk a themed route together. Milestones unlock on a visual map, with
     three ready-made journeys: 7 Wonders, Backpacking Europe, Everest Run.` · Best for:
     `teams that want a story, 4 to 8 weeks`
  4. **E-Marathon** — `Steps become distance, 1,000 steps to the kilometer, in km or miles.
     A finish line your whole company can cross from anywhere.` · Best for: `one-day events
     and global offices`
  5. **Custom** — `Multi-week themes with steps at the core and 27 task types around them:
     hydration, mindfulness, sleep. The format most clients settle into.` · Best for:
     `month-long programs with variety`
- Foot note: `All five are self-serve from the admin dashboard. Team mode, points, and
  certificates work in every format.`

### S3 Employee experience
- Eyebrow: `For employees`
- H2: `Joining is automatic. Staying is the point.`
- Lead: `Most step challenges are won by the same five people while everyone else quietly
  stops opening the app. Vantage Fit is designed against that.`
- Points:
  1. `Enrollment without a signup drive` — `Audience rules add a department, a region, or the
     whole company automatically. New hires who match are enrolled when they become active.`
  2. `Any phone counts` — `Apple Health on iPhone, Google Fit on Android, and direct Fitbit
     and Garmin connections. Apple Watch, Samsung, and 70+ tracking apps sync through. No
     wearable required.`
  3. `Teams score by average, not total` — `A team of 5 that averages 80 beats a team of 10
     that averages 70. Small teams compete, and every member's effort moves the number.`
  4. `Progress from the first 3,000 steps` — `The badge ladder starts at 3,000 steps a day,
     with streak and milestone badges that reward consistency, not podiums.`
  5. `Private by choice` — `A leaderboard opt-out keeps points and team contribution while
     hiding the name. Wheelchair mode is built in. Mood and health logs are never public.`
  6. `Rewards that feel local` — `Points become gift cards in each employee's currency and
     market, from one wallet shared with Vantage Circle recognition.`
- Media: employee app screenshot (baseline CDN asset), alt text describes challenge journey,
  weekly tasks, team leaderboard.

### S4 Fair numbers
- Eyebrow: `Data integrity`
- H2: `Leaderboards your skeptics can audit.`
- Lead: `One impossible number at the top kills a challenge faster than low turnout. Vantage
  Fit filters the data before winners are ever named.`
- Cards:
  1. `Trusted sources only` — `Steps are accepted from recognized apps and devices. Anything
     from an unrecognized source is rejected.`
  2. `One device at a time` — `Each person has one primary step source. Connecting a new
     device disconnects the old one, so nothing double-counts.`
  3. `Anomaly and GPS checks` — `Implausible spikes are filtered. GPS workouts are validated
     for realistic pace, and vehicle movement stops the workout.`
  4. `A 3-day results buffer` — `Wearables sync late. Winners are confirmed only after a
     3-day post-challenge window, so final standings hold up.`
- Audit-board caption: `Live leaderboard, one entry flagged: 214,006 steps from an
  unrecognized source. Rejected.`
- Fine print: `Manual step entry stays off unless your company chooses to enable it.`

### S5 HR control room
- Eyebrow: `For HR teams`
- H2: `Launch in minutes. Run it without babysitting.`
- Lead: `The whole lifecycle lives in one dashboard: create, enroll, nudge, and report,
  without a spreadsheet in sight.`
- Tab: **Launch & run**
  1. `A wizard, not a project` — `Name it, set dates, pick the format. Help docs put the whole
     flow at 5 to 10 minutes, and templates ship with tasks and scoring preset.`
  2. `Audience rules with a live count` — `Target by country, city, department, gender, age,
     language, or health-risk band, and see how many employees match before you publish.`
  3. `Comms on autopilot` — `Enrollment, start, weekly progress, and completion emails send
     themselves. Push notifications go out from the challenge page when you want a nudge.`
  4. `Fair across every time zone` — `Start, end, and the daily reset land at each
     participant's local midnight. One challenge covers New York to Singapore.`
- Launch-mock labels: `Create challenge · Format: Race · Audience: All US offices ·
  1,284 employees match · Publish`
- Tab: **Prove it**
  1. `Participation, not vanity` — `A participation rate tracked against your target, with
     trends by week and the departments that need a different push.`
  2. `Step data leadership will read` — `Average daily steps, activity trends, and team
     standings, filterable by country, department, age, and gender.`
  3. `Exports that hold up` — `Leaderboard CSV with per-task score breakdowns, plus
     transaction, redemption, and league reports. Filters apply before export.`
- Measure note: `Participation rate = unique enrolled employees completing a qualifying
  wellness action in the previous 30 days ÷ enrolled employees. Employees see their own data.
  HR sees aggregate trends.`

### S6 Proof
- Eyebrow: `Named results`
- H2: `Step programs that actually got walked.`
- Lead: `Outcomes from named customers running step challenges on Vantage Fit, labeled the
  way they were measured.`
- Cards:
  1. `70%` — `engagement across 43 teams averaging 7,600+ daily steps, a 6% increase` —
     `Tata Motors · Step Up & Elevate · 6-month team challenge`
  2. `97%` — `participation in a two-week walkathon that logged 11M+ steps` —
     `POSOCO · Walking Miles, Losing Inches · Energy`
  3. `88%` — `engagement in 28 days; 236 employees passed 30,000 steps a week by week 3` —
     `IBS Software · March to Fitness · IT services`
  4. `3X` — `participation growth, 163 to 550 active users, across 30+ countries` —
     `Wipro · 2025 global challenges · IT services`
- Quote band 1 (video): `“Vantage Fit has helped our employees stay active, track their
  progress, and get rewarded — turning wellness into a daily habit that drives both health and
  happiness across BISD.”` — Rachel Arthur, Director of Benefits & Wellness, Brazosport ISD ·
  `Watch her story`
- Quote band 2 (text): `“We've seen a noticeable increase in engagement and participation in
  our step challenge.”` — Vurshayna Nadoo, Momentum Investments
- Fine print: `Results from named customer programs. Outcomes vary by workforce and program
  design.` · Link: `Read customer stories →`

### S7 Trust
- Eyebrow: `Enterprise security & compliance`
- H2: `Step data is personal data. Treat it that way.`
- Lead: `Vantage Fit reports participation and rankings to HR, and keeps everything else with
  the employee. Your privacy and security reviewers see the difference.`
- Cards:
  1. `Private by design` — `Admins see participation, steps, and rankings. Weight, health
     assessments, lab results, and mood stay with the employee, always.`
  2. `Regional data residency` — `Employee data stays in your assigned region: India, US, EU,
     or UAE instances.`
  3. `SSO & HRIS ready` — `SAML 2.0 single sign-on with Okta, Azure AD, OneLogin, and Ping,
     plus HRIS sync (Workday, ADP, DarwinBox), CSV, and SFTP.`
  4. `Independently audited` — `SOC 2 Type II audited; operates under HIPAA guidelines.
     Security documentation available during evaluation.`
- Plaque support line: `Security documentation is available during evaluation.`

### S8 Related + final CTA
- Related row heading: `Where teams go next`
  - `Team Challenge` — `Departments compete on averages, so every member counts.`
  - `Virtual Marathon` — `One day, one finish line, every office and time zone.`
  - `Year-round Wellness Program` — `String challenges into a twelve-month rhythm.`
- Final CTA:
  - H2: `See the challenge your workforce would actually walk.`
  - P: `In a 30-minute demo we'll pick a format for your workforce, walk the employee app,
    and show the participation reporting your leadership will see.`
  - Buttons: `Book a demo` · `See pricing`
  - Checks: `Create a challenge in minutes` · `No wearable required` · `No obligation`
- Footer: hub footer with Steps Challenge as the current Solutions item.

---

## 6. Sources: every stat and quote on the page

| Claim | Source |
|---|---|
| Five self-serve formats + mechanics (Race no-target; Streak daily target/reset + days-completed scoring; Journey milestones + 3 named templates; E-Marathon 1,000 steps = 1 km, km/miles; Custom multi-week, 27 task types) | `vantagefit-astro/content/en/help/admin/challenges/admin-what-challenge-formats.md`, `admin-how-do-i-create-race-challenge.md:24-26`, `admin-how-do-i-create-streak-challenge.md:23-29`, `admin-how-do-i-create-journey-challenge.md:32-38`, `admin-how-do-i-create-e-marathon.md:23-27`, `admin-what-tasks-can-i-include-in-a-custom-challenge.md:13` |
| Parallel challenges, one walk credits all matching | `admin-can-i-run-multiple-challenges-in-parallel.md:13,21` |
| Wizard 5–10 min; templates preset | `admin-how-do-i-create-a-challenge.md:13`, `admin-how-do-i-use-templates.md:17-23` |
| Audience rules: 7 filters, live match count, auto-enroll incl. late-activating hires | `admin-how-do-i-set-target-audience.md:19,27-35,49-65` |
| Lifecycle emails + push from challenge page; reminder off by default (not claimed on page) | `admin-what-emails-does-vfit-send.md:29-34`, `admin-how-do-i-manage-challenge.md:86-93` |
| Time zones: start/end/daily reset at participant-local midnight; localized rewards | `admin-can-i-run-challenges-across-time-zones.md:19-29` |
| Mid-flight edits, force start/stop, leaderboard CSV + per-task breakdown | `admin-how-do-i-manage-challenge.md:27-119`, `admin-how-do-i-view-leaderboard.md:95-102` |
| Reports list (employee, transaction, redemption, league) with pre-export filters | `admin-what-reports-are-available.md:17-24,129-142` |
| Devices: Apple Health hourly background, Google Fit, direct Fitbit/Garmin, Apple Watch/Samsung/70+ apps, no wearable required, web app cannot track | `how-does-step-syncing-work.md:17-45`, `do-i-need-a-wearable.md:13,40-58`, `vfit-os specs/product/10-integrations/device-integrations.md:32-40,170` |
| Anti-cheat: trusted sources, anomaly detection, GPS pace + vehicle detection | `vantagefit-astro/content/en/help/admin/settings/admin-data-privacy-security.md:68-75` |
| One primary device, auto-disconnect | `can-i-connect-multiple-devices.md:12,40-48` |
| 3-day results buffer (wearable late sync) | `admin-how-do-i-create-race-challenge.md:27-29,64-71` |
| Manual entry off by default | `admin-what-is-configurable.md:108` |
| Team score = average of members | `admin-how-do-i-manage-teams.md:19-23`; `vfit-os specs/product/02-challenges-gamification/challenges.md:99` |
| Badge ladder from 3,000 steps/day | `admin-how-do-badges-work.md:20-31` |
| Leaderboard opt-out preserves points/team contribution | `can-i-opt-out-of-leaderboard.md:24-29` |
| Wheelchair mode | `employee/getting-started/what-is-wheelchair-mode.md` |
| Mood/health never visible to admins | `admin-data-privacy-security.md:49-56`, `admin-what-tasks-can-i-include-in-a-custom-challenge.md:75` |
| Unified wallet with Vantage Circle recognition; local currency/vendors | `employee/rewards/how-do-i-earn-points.md:38-45`, `admin-can-i-run-challenges-across-time-zones.md:25-29` |
| Enrollment is admin/audience-rule (no browse-and-join claimed) | `vfit-os specs/product/02-challenges-gamification/challenges.md:42-47` |
| Tata Motors 70% / 43 teams / 7,600+ steps (+6%) — Step Up & Elevate only | `vfit-os .claude/rules/data-accuracy.md:50-66` |
| POSOCO 97% / 11M+ steps / 2 weeks | `data-accuracy.md:191`; `casestudy/posoco-walkathon-challenge.md` |
| IBS 88% engagement / 236 at 30k+/wk / 28 days | `data-accuracy.md:72-86` |
| Wipro 3X (163→550) / 30+ countries | `data-accuracy.md:93-101` |
| Rachel Arthur quote + video | `data-accuracy.md:147-150` (homepage carousel + YouTube LSX4pxSB6Qw) |
| Momentum Investments quote | `data-accuracy.md:217` (email testimonial, Oct 2025) |
| "100+ organizations" only; drop "50+ countries"; approved logo names | `data-accuracy.md:256-261,22`; `vfit-os projects/active/proj-002-vantagefit-io-content-refresh.md:77` |
| SSO (SAML 2.0, Okta/Azure AD/OneLogin/Ping), HRIS (Workday/ADP/DarwinBox), SFTP | `admin-how-do-i-enable-sso.md:19-57`, `admin-what-is-configurable.md:117-118`, `vfit-os specs/product/00-platform/auth-login-signup.md:38,219` |
| Data residency IN/US/EU/UAE | `admin-data-privacy-security.md:16-20`; `auth-login-signup.md:171` |
| SOC 2 Type II; "operates under HIPAA guidelines" phrasing | `vfit-os sources/VFit-Marketing-Content-Compacted.md:161-162` |
| Participation-rate definition | carried verbatim from the approved homepage/hub mocks |

**Caveats held over from the hub brief:** the certifications plaque image (HIPAA / ISO / GDPR
/ SOC 2) is reused for visual continuity with the approved baseline, but ISO 27001/27701 and
GDPR have no product-KB source; copy claims only SOC 2 + HIPAA guidelines. Verify the plaque
with the security team before production. HRIS vendor list carries the spec's own caveat
("confirm readiness before committing to a client") — fine for a mock, confirm for production.

---

## 7. Voice and mechanics notes

- Copy follows `vfit-os/messaging-audit/data/voice-and-tone-guide.md`: **no em-dashes**
  outside verbatim quotes and "— Name, Title" attributions; banned-word list respected (no
  "seamless", "comprehensive", "holistic", "empower", "all-in-one", etc.).
- Voice north star applied: "We help working people feel a little better today — without
  making it feel like work." The page's inclusion framing (S3) and modest verbs come from
  this; there is no "crush the competition" copy anywhere, which also matches the product
  mission's explicit warning against leaderboard-shark framing.
- SEO: meta title kept from the live page (it already targets "step challenge app", a
  documented low-difficulty wedge: KD 7). If a FAQ block is restored later, emit FAQPage
  JSON-LD (the site currently doesn't, flagged in the site inventory).

---

## 8. Component notes (patterns not in the baseline)

| Pattern | Purpose | Notes |
|---|---|---|
| `.format-card` + `.format-glyph` | S2 format cards with mechanic diagrams | Extends `.program-card` language; inline SVG glyphs in ink/mint; `Best for` tag reuses eyebrow typography. |
| `.join-point` | S3 employee experience rows | Icon tile + bold + one-liner, tour-checks rhythm in a two-column split. |
| `.audit-board` | S4 leaderboard snippet with a flagged row | White card on dark band; flagged row uses coral tint + "Source rejected" pill. Static (reveal only), honors reduced motion. |
| `.launch-mock` | S5 tab-1 media: create-wizard card | Built from baseline `.dash`/`.admin-card` language; illustrative labels only. |
| Related row | S8 | Reuses the hub's `.marathon-row` pattern, three-up grid. |

All other patterns (nav/mega, hero dash+phone, logo band, tour-tabs, result cards, quote band,
trust cards + plaque, final CTA, footer, video modal, reveal) are reused unchanged.

---

## 9. Assumptions stated

- The mock links sibling pages to live URLs (as the hub mock does) and the mega banner to the
  hub mock file for reviewer navigation.
- Illustrative product-UI numbers in the hero and launch mock (82% participation, 1,284
  match count, 8,412 steps) are clearly interface fiction, not outcome claims; all outcome
  claims live in S6 with named sources.
- Wellness Leagues are deliberately not sold on this page (annual-plan gated per
  `admin-dashboard.md:126-138`); the year-round story is delegated to the related-programs
  row, where the hub page handles it with the correct qualifier.
