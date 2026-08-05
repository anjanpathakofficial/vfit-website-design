# Vantage Fit — Mental Health & Wellbeing Solutions Page Brief (v1)

Model workspace: `claude-fable` · Deliverable pair: this brief + `vantage-fit-mental-health-wellbeing-v1.html`
Baseline: `../styled-homepage/` + `../styles/enterprise.css` · Siblings in the same system:
`vantage-fit-steps-challenge-v1.html`, `vantage-fit-team-challenge-v1.html`,
`vantage-fit-multi-activity-challenge-v1.html`, `vantage-fit-virtual-marathon-v1.html`,
`../solutions-page/vantage-fit-solutions-v1.html` (hub)
Live URL this replaces: `/mental-health-and-wellbeing-challenges/` (URL preserved, not changed)

> This brief documents the page **as shipped**, not as planned. Where the built page diverges from
> the blueprint it was written against, the divergence is called out in §3.7 and the copy deck in §5
> is transcribed from the HTML.

---

## 1. What this page is

This is the single Solutions page a buyer opens when their leadership has asked what the company is
doing about stress and burnout. The program it sells is not a format the product ships: **there is no
"mental health challenge" in Vantage Fit.** A wellbeing program is a Custom multi-week challenge
carrying wellbeing tasks (mindfulness, meditation, yoga, sleep, mood check-in, content, custom
habits) drawn from the same 27-task library that powers every other challenge. The reader is a US
enterprise HR director, CHRO or benefits leader, with privacy counsel sitting beside them as a
co-buyer rather than an afterthought. The CFO is deliberately not a reader here, because no approved
wellbeing ROI figure exists.

The page does exactly one job: **make the case that mental wellbeing can go on the scoreboard
employees are already on, and that HR still never sees a single person's mood.** Everything else on
the page exists to make one of those two halves believable. Primary CTA is Book a demo, secondary is
See pricing, and there is no third conversion path.

---

## 2. Research takeaways

Audited: 22 help docs under `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/`, five
code-verified specs under `/Users/anjanpathak/work/vc-os/vfit-os/specs/product/`, the admin dashboard
prototype and its ground-truth sweep in `/Users/anjanpathak/work/gitcode/vc-dashboard-design/`, the
live page source `content/en/pages/use-cases/mental-health-and-wellbeing-challenges.yaml`, and the
approved-proof gate.

### 2.1 The structural fact that shaped the whole page

**There is no mental-health format.** The five self-serve formats are Custom, Race, Journey, Streak
and E-Marathon (`help/admin/challenges/admin-how-do-i-create-a-challenge.md:15-25`;
`specs/product/02-challenges-gamification/challenges.md:44-56`). Streak is steps-only and cannot
carry a mindfulness habit ("Only steps count in a Streak Challenge. There are no other task types
like water, sleep, or meditation" — `help/employee/challenges/what-is-a-streak-challenge.md:26`).
Race has no task configuration at all. A wellbeing program is therefore **a Custom multi-week
challenge whose tasks come from the Mind & Body, Mental & Emotional Health, Health Tracking and
Content categories** (`help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md:45-83`).

Consequence: the five-format explorer that anchors the sibling Steps page **cannot appear here**. It
would be the page's only outright falsehood. S3 replaces it with a wellbeing-task strip.

### 2.2 What the product actually has, under-sold or unsaid on the live page

1. **Wellbeing is a scored task, not a shelf.** Mindfulness, Meditation, Yoga, Sleep Tracker, Mood
   Log, Content Reading, Bite-Size Content and Adherence habits are all configurable tasks with
   targets and point values inside a Custom challenge
   (`admin-what-tasks-can-i-include-in-a-custom-challenge.md:43-91`). Completing a guided session
   "is logged as a mindfulness activity" and "contributes to challenges and wellness scoring"
   (`specs/product/03-health-wellness/mindfulness.md:32`), so **playing the session is the logging
   step**. The live page presents the same library as passive content and never says this.
2. **The 100%-of-target cap is the fairness mechanic nobody else can copy.** Non-step tasks are
   "Capped at 100% of the target. Going over the target does not earn extra points", with the doc's
   own example: log 5 yoga sessions against a target of 3 and you still earn points for 3
   (`help/employee/getting-started/ts-leaderboard-score-wrong.md:59-64`, corroborated
   `admin-how-do-i-create-custom-challenge.md:94` and
   `help/employee/challenges/how-does-the-leaderboard-work.md:45-47`). On a wellbeing challenge,
   nobody can out-meditate the leaderboard. This is the mathematical reason a modest logger stays in
   contention to the last day, and it is entirely absent from the live page.
3. **The published CAN / CANNOT visibility table.** `help/admin/settings/admin-data-privacy-security.md:43-54`
   lists, in public documentation an employee can read, exactly what an admin can and cannot see.
   **Mood logs are in the CANNOT column.** The same file ships HR the script verbatim at `:56`. Most
   vendors bury this in a security whitepaper behind a form; here it is a help article. The live page
   answers the privacy question with a weak line about not requiring employee details for session
   access, discarding the strongest asset on the account.
4. **Leaderboard opt-out that preserves participation.** Verbatim from
   `help/employee/challenges/can-i-opt-out-of-leaderboard.md:26-29`: hidden from rankings, "You still
   participate in challenges", "You still earn points", "Your scores still count for your team."
   Reversible "as many times as you like" (`:33-37`). The doc even names "Reducing pressure" as a
   legitimate reason. This is the direct answer to the stigma objection and it is a shipped mechanic,
   not a policy.
5. **Nobody signs up.** Two enrollment paths, both admin-driven, with "None — you're already in" in
   the doc's own Action Required column (`help/employee/challenges/how-do-i-join-a-challenge.md:17-38`);
   code-verified as "There is no browse-and-join flow"
   (`specs/product/02-challenges-gamification/challenges.md:42-44`). Any audience filter marks the
   challenge Private and invisible to non-matching employees
   (`admin-how-do-i-set-target-audience.md:41-45`).
6. **The Plus (+) menu groups the wellbeing actions in one place** — Mindfulness, Mood Tracker, Sleep
   Log (`help/employee/health-tracking/how-do-i-use-the-plus-menu.md:31-37`). Neither the live page
   nor the foundation research names it. It is the best product-real hero asset available and the
   page uses it.
7. **A daily mood reminder the employee sets themselves.** Mood is one of six local reminder types,
   with the time and repeat days chosen by the employee and fired by the phone
   (`help/employee/getting-started/how-do-i-set-reminders.md:26-45`). Employee-owned, not HR-pushed:
   the precise opposite of surveillance framing.
8. **What HR actually gets.** Per-task and per-week score breakdown per employee with
   completed / partially completed / missed status
   (`help/admin/reports/admin-how-do-i-view-leaderboard.md:72-83`), CSV export with per-task scores
   and filters applied before export (`:95-102`; `admin-what-reports-are-available.md:129-142`), two
   org-level trends in the Overview At a Glance card, Mindful Minutes per day and average sleep per
   day (`specs/product/09-admin-platform/admin-dashboard.md:56`, corroborated in the live-code ground
   truth at `vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md:74`),
   and one anonymous post-challenge survey (`specs/product/09-admin-platform/surveys.md:31-40`).
9. **What HR does not get, and this is load-bearing.** **No mood report exists in either repo** —
   "mood tracking has no model in either repo"
   (`vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md:122`). No
   scheduled report delivery, no exec digest. Health-risk reporting is organisation-level only. The
   page states this rather than hiding it.

### 2.3 What the live page claims that sources do not support

| Live claim (`mental-health-and-wellbeing-challenges.yaml`) | Verdict |
|---|---|
| "Link employees to professional counselors or helplines as needed"; "connect employees with professional help" | **Does not ship.** There is no counselling, therapist network, helpline or clinical triage capability. The only adjacent thing is a Wellness Marketplace category of third-party listings, where "Admins cannot add or remove offerings", the docs call it "Not a benefits platform", and it hedges with "**If** your company's EAP is listed" (`help/admin/programs/admin-how-does-marketplace-work.md:93-99,119`). The page removes the claim and states the boundary instead. |
| FAQ "Does Vantage Fit provide partner services for mental health & wellbeing?" → "Yes." | Implies a first-party service. Retired; replaced by FAQ 4. |
| "curated articles, webinars, and expert talks" | Webinars and expert talks are **not verified content types**. Verified types are articles, videos, podcasts and bite-size micro-lessons (`admin-what-is-configurable.md:36`). Cut. |
| Hero "86% challenge participation" (Brazosport) | **Mislabel.** The gate file records it as an **engagement** rate, and it measures a physical challenge. Cut from this page entirely. |
| Testimonial block closing with IBS 88% and "5,000+ steps a day" | Accurate but topically wrong: a step statistic closing a mental-health page. The on-topic IBS figures (130 / 95) existed and were unused. Now used. |
| "30+ MP3 sessions" style session counts | Draft-spec only. Page prints "7 categories" and nothing else about library size. |

### 2.4 Constraints the page had to respect or disclose

- **Lite Mode kills this program.** No water/sleep/mood logging, no Mindful Minutes, Plus menu shows
  only Sync (`help/admin/settings/admin-what-is-lite-mode.md:26-49`). Full Mode is an
  account-manager setting and **"Downgrading from Full to Lite is not supported"** (`:61-67`).
- **Missed daily check-ins cannot be back-filled** (`how-do-i-complete-challenge-tasks.md:104`).
- **Content tasks require reaching the end** — "Skipping through a video won't register as done" (`:60`).
- **Challenge reminder emails are off by default** and enabling them requires the account manager
  (`admin-what-emails-does-vfit-send.md:34,94`).
- **HRA and Workforce Health are gated** — health-risk targeting needs the HRA (AM-enabled) and
  Workforce Health is "premium, limited-availability… whitelist-gated in code today"
  (`specs/product/03-health-wellness/workforce-health.md:24,105`).
- **Mindfulness, meditation, yoga, sleep and mood are self-logged with no verification mechanism
  described anywhere.** The word "verified" never appears near a wellbeing log on this page.

---

## 3. Why this structure

Eleven sections. The order is engineered so that each section manufactures the objection the next one
answers. The single most important ordering decision on the page: **privacy comes before reporting.**
If reporting ran first, the privacy band would read as a retraction of the numbers just promised.
Running privacy first makes the reporting section read as the reader's own next thought, which is
exactly what its headline says.

| # | Section | The belief it has to create |
|---|---|---|
| S1 | Hero | "Mindfulness sits in the same task list, with the same tick, as steps, and the mood row is locked." |
| S2 | Why programs stall + scope strip | "They understand why my last wellbeing spend died, and they are not pretending to be my EAP." |
| S3 | Wellbeing tasks | "This is not a library. These are tasks with targets and a completion status." |
| S4 | Join and stay | "People will actually be in it, and a modest logger will still be in contention in week four." |
| S5 | Privacy and stigma | "Counsel can verify the boundary before we ever take a call, and it is a product mechanic, not a policy paragraph." |
| S6 | What you report | "I still walk into the CHRO review holding a number, and I know exactly which number." |
| S7 | Proof | "Real employers ran this, and the figures are on-topic rather than borrowed from a step challenge." |
| S8 | FAQ | "My five rollout questions are answered in writing, on the page, before I ask them." |
| S9 | Trust | "Where the data lives and who can delete it is answered, and it does not repeat S5." |
| S10 | Related | "This slots into the programs I already run." |
| S11 | Closer | "The demo is about my task mix and my privacy review, not a generic tour." |

### 3.1 S1 Hero — the whole argument in one frame
A drawn phone in week 2 of a mindfulness week, with four task rows: a mindfulness session marked
Done, a sleep log with a Log button, auto-tracked steps, and a mood check-in marked Done with a lock
glyph reading "Private to you". A second frame layers at the lower right showing the Plus menu open
on Mindfulness, Mood Tracker and Sleep Log. The composition makes the page's argument without a
caption: mindfulness sits in the same list, with the same target and the same tick, as steps, and the
mood row is the one that is locked. The phone is moved off the shared absolute placement and sits
centre-left specifically so the plus-menu frame never overlaps the mood row.

### 3.2 S2 — the failure, then the concession
Three struck-through failure lines, written in **neutral third person about the category**. This was a
hard rule: a named human at the buying company bought the meditation licence and the EAP, and that
human is often the benefits leader who can kill the deal. There is no "you" and no "your last
program" anywhere in the three lines. Immediately underneath, a two-column scope strip states what
this is and what it is not. Drawing the EAP boundary as a concession, near the top, before any
selling, is the conversion event with a benefits buyer scanning for overclaim. This section carries
no image on purpose.

### 3.3 S3 — a task strip, not a format explorer
Six cards on a six-column grid, each spanning two, each with a "How it logs" chip naming the real
behaviour class: manual log, manual or device-synced, event-based, daily check-in. The chip is the
section's honesty device. It tells a skeptical buyer, in the same breath as the pitch, which tasks
are self-reported and which cannot be. One text link goes down to
`/features/mental-health-and-mindfulness/` and the page never re-describes the library again: this
page owns program and BOFU intent, the feature page owns capability depth.

### 3.4 S5 — the objection band, repointed
The blueprint specified the count-only audience screen as the panel here. **The built page overrules
that.** That screen is HRA-gated and Workforce Health is whitelist-gated in code, so making a
limited-availability screen the page's central privacy artifact over-represents it to every buyer who
will never get it. The panel is instead the **published CAN / CANNOT table**, reproduced without
addition, reorder or paraphrase, with the Mood logs row typographically emphasized. It is ungated,
already public, independently checkable by counsel before a call, and its mood row is the page's
thesis in one line. The count-only screen survives as the fourth item in the dark band, with its gate
stated in the fine print underneath.

The panel is **not** `role="img"`. Every row is published documentation, so the two columns are real
`<ul>` lists named by their Can see / Cannot see labels, and the verbatim caption is read out. It
carries a green "From the privacy doc" tag rather than an Illustrative data tag, because nothing in
it is invented.

### 3.5 S6 — the reader's own next thought
Headline is written as the question the privacy band just provoked. Two tabs only. The Prove-it tab's
report mock carries **one** annotation, pointing at the Mood check-in row: *"The score shows the
check-in happened. The value is never shown."* That single callout is the page's thesis rendered as a
product frame, and it is the reason the mock exists at all. Build rule enforced throughout: **no mood
value, mood score, mood average or mood trend renders in any mock on this page.**

### 3.6 Beats deliberately cut

| Cut | Why |
|---|---|
| Five-format explorer | There is no mental-health format. It would be the page's only outright falsehood. |
| Three-big-numbers stat band (`.results-grid`) | Every large approved percentage on this account (88, 86, 70, 59) measures a **physical** challenge. A stat band here is dishonest by construction and a burned buyer smells it instantly. |
| Standalone scoring / data-integrity section | The 100%-of-target cap is real and strong, but it is the Multi-activity page's centre of gravity. Here it is one row of copy in S4, not a section and not a visual. |
| Timeline or "five weeks to launch" rail | Nav furniture that spends words without advancing an argument. |
| Absorbing the trust block into the privacy band | They answer different questions (who can see what / where it lives and who can delete it) and the page needs both dark moments for rhythm. A content rule forbids S9 from restating anything in S5. |
| Video quote and `#video-modal` | Quote duo is text-only, so the modal markup and its script block were both removed. |
| Wellness Marketplace, in any form | Admins cannot curate it, it is AM-gated, the docs call it "not a benefits platform". Topic stays off the page rather than being described carefully. |
| ROI, absenteeism, claims-cost framing | No approved wellbeing ROI figure exists. Every ROI question redirects to participation. |
| Brazosport's organisational mood score of 4/5 | See §7. |

### 3.7 Where the built page diverges from the blueprint it was written against

Recorded so a reviewer comparing the two does not think something was lost by accident.

1. **S5 panel repointed** from the count-only audience screen to the CAN / CANNOT table. Reasoning in §3.4.
2. **S6 honesty block reduced.** The blueprint required three disclosures in `.measure-note`: no mood
   report, manual CSV only with no scheduled delivery or exec digest, and reminder emails off by
   default. The shipped line is **"There is no mood report of any kind, and no aggregate mood
   score."** The other two were cut in the leanness pass, with FAQ 2 absorbing the reporting-limits
   half. **This is the one cut in the build that reduces disclosed honesty, and it is flagged in §9
   for a decision** rather than presented as settled.
3. **S4 row 3 collapsed.** "No wearable, no desk" became "No wearable needed", the
   Fitbit/Garmin/Samsung override clause was removed as an overstatement, and web logging plus
   offline playback moved into FAQ 5.
4. **S3 lead says "Vantage Points"** rather than "points". Sourced, with a caveat in §9.
5. **S3 card 1 absorbed the 7-category fact** ("a 7-category library") and the second format note was
   rewritten to "with their own targets, points and completion status" instead of "scored the same
   way", because steps have no ceiling and non-step tasks cap at 100%, so "the same way" was a false
   equivalence that contradicted S4 row 4.
6. **FAQ 4 rewritten** from an existence claim to a provision claim: "Vantage Fit does not provide
   counseling, a therapist network, a helpline, or clinical screening." The corpus does document
   third-party EAP listings inside the Marketplace, so the stronger negative would have been false.
7. **FAQ 2 gained** the organisation-level-only qualifier for workforce health reporting;
   **FAQ 3 gained** the late-add scoring rule.
8. **S7 verb change:** IBS's figure reads "logged their daily mood", not "monitored". The gate file's
   own wording used "monitored"; it was changed to keep the page's banned-word grep clean, since
   surveillance vocabulary is graded fatal here. Figure, client and program are untouched.
9. **Eyebrows added** to S2, S3 and S8, which the blueprint did not specify.
10. **The word "actually" was de-ticked** from six uses to one. It survives only in the S6 headline,
    where the contrast is earned.
11. **Sibling links are same-directory** (`vantage-fit-steps-challenge-v1.html`,
    `vantage-fit-team-challenge-v1.html`) because the file landed in `claude-fable/`, not
    `solutions-page/`. Both targets exist on disk.

### 3.8 Design signature within the locked system
Two full-bleed dark moments only (S9 trust, S11 closer) with light S10 between them; the mid-page dark
moment is the **contained** `.fairband` card in S5, so the privacy argument gets visual weight without
breaking the light/dark rhythm. New page-scoped patterns: the wellbeing task list and plus-menu frame
in the hero, `.stall-grid` and `.scope-strip` in S2, `.can-cannot` in S5, `.report-mock` with its
`.tk-row` per-task sub-table and `.rm-callout` annotation in S6, `.proof-list` narrative cards in S7,
and a native `<details>` `.faq-list` in S8. Everything else is reused unchanged.

---

## 4. The objection this program raises

**"We cannot be seen collecting mental health data."**

It is the objection native to this program and the number one deal-killer. In the buyer's words: *our
privacy counsel will not sign off on an app that logs how our employees feel; if a manager ever sees
one mood entry, that is the story.* Its twin, arriving from the employee side, is: *in our culture, if
you sign up for the wellbeing challenge, people assume you are struggling, so the ones who need it
most will not click.*

The page answers both with the same band (S5), because they are the same objection seen from two
ends: **participation visible, feelings invisible.**

The proof is four shipped mechanics plus one published document, not a policy paragraph:

1. **Mood is private to the employee**, quoted from the public help doc:
   "Your mood data is private to you. It is not visible to your HR admin, manager, or colleagues."
   (`help/employee/health-tracking/how-do-i-track-my-mood.md:43`, restated admin-side at
   `admin-what-tasks-can-i-include-in-a-custom-challenge.md:75`.)
2. **Leaderboard opt-out preserves participation, points and team contribution**, reversible any time
   (`can-i-opt-out-of-leaderboard.md:17-37`). A competitor either has a public leaderboard or no
   leaderboard. Having both is the whole anti-stigma argument.
3. **Any audience filter makes the challenge private**, so it is not even visible to non-matching
   employees (`admin-how-do-i-set-target-audience.md:41-45`).
4. **Cohort selection returns a count, not a list**, with the disclaimer printed in the product:
   "The list of users is not displayed to protect individual privacy."
   (`specs/product/03-health-wellness/workforce-health.md:76`), gated honestly in the fine print.
5. **The published CAN / CANNOT table** as the panel, with Mood logs in the CANNOT column
   (`admin-data-privacy-security.md:43-54`) and the verbatim HR script at `:56` as the caption.

And the stigma half is answered structurally before S5 even arrives: **nobody signs up**, because
there is no browse-and-join flow anywhere in the product. Joining the wellbeing challenge is
indistinguishable from joining the step challenge, because in both cases you were enrolled.

**The objection this answer creates** is *"if HR cannot see the data, what exactly do I report?"* — and
that is precisely why S6 follows immediately, headlined as the reader's own question, and why its
honest answer is narrow: participation, completion, per-task detail, two org-level trends, one
anonymous survey, and never a person's mood.

---

## 5. Full copy deck (as shipped)

> Transcribed from the HTML. `<em>` marks the single gradient span on the page. Two em-dashes exist,
> both `&mdash;`, both inside the Rachel Arthur verbatim quote and its attribution.

### Head
- **Title:** `Employee Mental Health & Wellbeing Challenges | Vantage Fit`
- **Description:** `Run employee mental health and wellbeing challenges with private mood tracking, guided mindfulness and habits your people score. Book a Vantage Fit demo.`
- **Canonical:** `https://www.vantagefit.io/mental-health-and-wellbeing-challenges/`; hreflang en/fr/es/de retained unchanged
- **OG title:** `Employee mental health and wellbeing challenges`
- **OG description:** `Mindfulness, sleep and mood check-ins run inside a challenge everyone is already enrolled in. HR sees participation. Admins never see a mood entry.`
- **Robots:** `noindex, nofollow` (mock only, remove for production)
- **JSON-LD:** `FAQPage`, built from the five S8 questions, byte-identical to the visible copy

### Nav
Solutions (current section) · Features · Resources · Pricing · **Book a demo**
Run a challenge column: Steps Challenge · Team Challenge · Multi-activity Challenge ·
**Mental Health & Wellbeing** (current page) · Virtual Marathon.
Mega banner: `See every program on one page: the Solutions overview`

### S1 Hero (`#hero`)
- Eyebrow: `Solutions · Mental health & wellbeing`
- H1: `Mental health and wellbeing challenges people join without <em>declaring anything</em>.`
- Lead: `Put mental wellbeing on the scoreboard your employees are already on, and still never see one person's mood. Mindfulness, sleep and mood check-ins run as scored tasks nobody signs up for.`
- Buttons: `Book a demo` · `See pricing`
- Hero notes: `Nobody signs up. You enroll by audience rule.` · `Mindfulness, sleep and mood log as scored tasks.` · `Admins never see a mood entry.`
- Phone strings: `Vantage Fit` / `Custom challenge` / `Mindful March` / `Week 2 of 4` / `Week 2 · Mindfulness week` / `Overall progress 64%` / `Today's progress` / `Mindfulness session · 1/1 · Done` / `Sleep log · 0/1 · Log` / `Step count · 6,240 / 8,000 · Auto-tracked` / `Mood check-in · Private to you · Done` / `Illustrative data`
- Plus-menu frame: `Plus menu · Mindfulness` / `Mindfulness` / `Mood Tracker` / `Sleep Log`
- Logo band: `Trusted by 100+ organizations worldwide` — TATA MOTORS · WIPRO · IBS SOFTWARE · BRAZOSPORT ISD · HEIDRICK & STRUGGLES

### S2 Why programs stall (`#why-stall`)
- Eyebrow: `Why programs stall`
- H2: `Wellbeing programs rarely fail on content.`
- Lead: `They fail on three things that have nothing to do with the library.`
- Item 1: ~~`The content waits to be opened.`~~ `A library only produces usage when someone decides to open it.`
- Item 2: ~~`Joining is a disclosure.`~~ `Anything labeled mental health asks the people who need it most to be seen.`
- Item 3: ~~`The only number is utilization.`~~ `Leadership asks what moved, and the answer is a license count.`
- Scope strip, left: `What this is` — `A habit and participation layer, run as a scored challenge, at whole-workforce scale.`
- Scope strip, right: `What this is not` — `An EAP, counseling, a therapist network, a helpline, or a clinical screening tool. This sits under them in your benefits stack.`
- Handoff: `The fix for all three is the same: put wellbeing in the task list everyone is already enrolled in.`

### S3 Wellbeing tasks (`#tasks`)
- Eyebrow: `Wellbeing tasks`
- H2: `What a wellbeing challenge is made of.`
- Lead: `Not a library. Tasks with targets, Vantage Points and a completion status.`
- Cards (title / description / How it logs):
  1. `Mindfulness and meditation` — `Employees finish a guided session from a 7-category library, and finishing it is the log.` — `Manual log · guided session`
  2. `Yoga` — `Employees log a session, or use the 7-minute routine.` — `Manual log`
  3. `Sleep tracker` — `Logged by hand, or synced from Apple Watch or Fitbit.` — `Manual or device-synced`
  4. `Mood check-in` — `A 5-point scale with optional reasons, private to the employee.` — `Manual log`
  5. `Content and bite-size lessons` — `Counts only when the employee reaches the end of the content.` — `Event-based, cannot be self-logged`
  6. `Custom habit` — `One daily tap, for example sleep before 11 PM.` — `Daily check-in`
- Note 1: `Available task types depend on your configuration. The full set runs in Full Mode.`
- Note 2: `These sit in the same challenge as step and activity tasks, with their own targets, points and completion status.`
- Text link: `See how mindfulness and mood tracking work →` → `/features/mental-health-and-mindfulness/`

### S4 Join and stay (`#followthrough`)
- Eyebrow: `For employees`
- H2: `Nobody signs up, and nobody quietly drops out.`
- Lead: `Three mechanics get people in without a sign-up. Three more keep a modest logger within reach of the top until the last day.`
- Rows:
  1. `Enrolled, not invited` — `An audience rule enrolls everyone who matches, or you add people by search or CSV upload. There is no browse-and-join flow.`
  2. `Nothing to disclose to take part` — `Health-profile onboarding is skippable past the health connection, so weight and BMI are optional.`
  3. `No wearable needed` — `Steps come from Apple Health on iOS and Google Fit on Android, with no wearable required.`
  4. `The keenest meditator cannot run away with the leaderboard` — `Wellbeing tasks earn points up to 100% of the target and no further, so five yoga sessions against a target of three still score three.`
  5. `A bad week is not permanent` — `The weekly leaderboard resets each Monday, while the overall view stays cumulative.`
  6. `A reminder the employee sets, not one HR pushes` — `Mood is one of six reminder types. The employee picks the time and the repeat days.`
- Media alt: `Vantage Fit mobile app showing a challenge with weekly tasks and a leaderboard`
- Note 1: `Missed daily check-ins cannot be back-filled, so set targets people can hit.`
- Note 2: `Custom habits stay in the employee's Plus menu whether or not a challenge is running.`

### S5 Privacy (`#privacy`)
- Eyebrow: `Privacy and stigma`
- H2: `Participation visible. Feelings invisible.`
- Lead: `The reason people take part in this one is that taking part reveals nothing.`
- Item 1: `Mood is private to the employee` — `From the published help doc: "Your mood data is private to you. It is not visible to your HR admin, manager, or colleagues."`
- Item 2: `Hide from the leaderboard, stay in the program` — `Opt-out hides an employee from rankings, but they still participate, still earn points, and still count toward their team's average.`
- Item 3: `Any filter makes the challenge private` — `Applying an audience filter makes the challenge visible only to employees who match it.`
- Item 4: `Cohorts come back as a count, not a list` — `The audience screen returns a number and the line "The list of users is not displayed to protect individual privacy."`
- Fine print: `Health-risk targeting requires the health risk assessment and a premium module, enabled by your account manager.`
- Panel head: `What an admin can see` · tag `From the privacy doc`
- **Can see:** Aggregate metrics · Challenge participation status · Leaderboard rankings · Team scores · Registration status · Last active date · Device type
- **Cannot see:** Weight, BMI and body measurements · Health assessment answers and risk categories · Lab biomarker values · **Mood logs** · Food diary · Sleep patterns
- Panel caption (verbatim): `"Your HR team sees whether you are participating and your challenge rankings, but we cannot see your weight, health assessment results, lab reports, or personal health data."`

### S6 What you report (`#hr`)
- Eyebrow: `For HR teams`
- H2: `So what do you actually report?`
- Lead: `Participation, completion and per-task detail. Never a person's mood.`
- Tabs: `Launch and run` · `Prove it`
- **Launch and run:**
  1. `Built in the wizard, with real fields` — `Challenge name, dates, privacy, week theme, task type, target value, daily or weekly, points, audience.`
  2. `Creating a challenge takes 5 to 10 minutes from the admin dashboard.`
  3. `Enroll immediately, or enroll when active` — `People who install the app mid-challenge get picked up.`
  4. `Push mid-flight` — `Send a notification to all participants, or add a theme for an upcoming week.`
  - Launch mock: `Create challenge` / `Step 9 of 9 · Review` / `Format: Custom Challenge · multi-week` / `Name: Mindful March` / `Week 2: Mindfulness week` / `Task type: Mindfulness · target 4 · weekly · 40 pts` / `Privacy: Private` / `Audience: US offices · 412 match` / `Publish challenge` / `Participants are enrolled automatically when it goes live.` / `Illustrative data`
- **Prove it:**
  1. `Per-task and per-week breakdown, per employee` — `Completed, partially completed, or missed.`
  2. `Export CSV` — `Per-task scores, name, department, rank and team. Filters apply before export.`
  3. `Two organization-level trends` — `Mindful Minutes per day and average sleep per day, each with a sparkline and trend direction. Full Mode only.`
  4. `One anonymous post-challenge survey` — `A 1 to 5 rating with an optional comment, fired at completion.`
  - Measure note: `There is no mood report of any kind, and no aggregate mood score.`
  - Report mock: `Mindful March · Leaderboard` / `Challenges → Manage → Leaderboard` / tabs `Score` `Steps` `Team` / `All departments` `Search by name` `Export CSV` / columns `Rank` `Employee` `Department` `Score` / `1 Dana Whitfield · People Ops · 412` / `2 Marcus Ellery · Field Service · 398` (expanded) / `Per-task breakdown · Week 2` / `Step count 120 pts Completed` / `Mindfulness 40 pts Completed` / `Sleep log 15 pts Partially completed` / `Mood check-in 20 pts Completed` / **callout** `The score shows the check-in happened. The value is never shown.` / `Content reading 0 pts Missed` / week toggle `Week 1–4` / `Illustrative data`

### S7 Proof (`#proof`)
- Eyebrow: `Named results`
- H2: `Wellbeing programs that ran.`
- `Brazosport ISD, "Fit Wars"` — `A 2-week campaign at a Texas school district, May 6–19, 2024, in which employees engaged in 10 to 15-minute mindfulness sessions at least four times a week.`
- `IBS Software, "March to Fitness"` — `Inside a 28-day challenge with 500+ active participants, 130 employees logged their daily mood and 95 engaged in mental wellness activities.`
- `Wipro, "Inbox to Inner Peace"` — `A challenge whose stated purpose was mental wellbeing, Jun 11–24, 2025, logging 163 yoga sessions and 1,279 mindfulness minutes.`
- `Tata Motors` — `Daily mindfulness averaged 9 minutes on the Step Up & Elevate Challenge and 7 minutes on the Step & Stride Challenge, where average sleep was 7h 39m.`
- Quote 1 (with photo): `"Vantage Fit has helped our employees stay active, track their progress, and get rewarded — turning wellness into a daily habit that drives both health and happiness across BISD."` — `— Rachel Arthur, Director of Benefits & Wellness, Brazosport Independent School District`
- Quote 2 (text only): `"One of the features I loved the most is the Yoga Nidra session, which helped us relax in the stress-induced environment."` — `Celegence, email testimonial`
- Fine print: `Results from named customer programs. Outcomes vary by workforce and program design.` · `Read customer stories →`

### S8 FAQ (`#faq`)
- Eyebrow: `Privacy, reporting and rollout` · H2: `Questions before rollout.`
1. **`Can HR see an employee's mood entries?`** — `No. Mood data is private to the employee and never appears on a leaderboard. A mood check-in can be scored, so the score shows only that it happened.`
2. **`What does HR get to report on?`** — `Participation, completion and a per-task breakdown for each employee. Not a mood report, not a mood trend, and not a health breakdown by department: workforce health reporting is organization-level only.`
3. **`Do employees have to sign up?`** — `No. An audience rule enrolls everyone who matches, or you add people by search or CSV upload. Someone added after the start scores from that date forward, so a late add gives nobody an advantage.`
4. **`Does this replace our EAP?`** — `No. Vantage Fit does not provide counseling, a therapist network, a helpline, or clinical screening. Run it alongside the EAP contract you already hold, as the daily habit layer underneath it.`
5. **`Will this work for employees without a wearable or a desk?`** — `Yes. Mood, sleep and water log from the web as well as the app, and guided sessions play offline and sync later. Steps need no wearable.`

### S9 Trust (`#security`)
- Eyebrow: `Enterprise security & compliance`
- H2: `Where the data lives, and who can delete it.`
- Lead: `Counsel can check the boundary before the first call. This is the rest of the security questionnaire.`
- Actions: `Book a demo` · `Explore security & compliance →`
- Card 1: `Secured regional data hosting` — `India, the US, the EU and the UAE, chosen at signup, permanent, with no cross-region sharing.`
- Card 2: `Follows HIPAA guidelines` — `SOC 2 Type II, with audit documentation shared under NDA during evaluation.`
- Card 3: `Deletion stays with the employee` — `Account deletion is employee-initiated and OTP-verified. An admin cannot do it on their behalf.`
- Card 4: `Consent language your legal team writes` — `Custom terms can be added to employee onboarding, set up by your account manager.`
- Plaque alt: `Vantage Fit security and compliance badges` · support line: `Employees see their own data. HR sees aggregate trends.`

### S10 Related (`#related`)
- Eyebrow: `Keep exploring` · H2: `Where wellbeing programs go next.`
- `Multi-activity Challenge` — `27 task types and a new theme each week.` → live URL
- `Steps Challenge` — `The program most teams already run.` → `vantage-fit-steps-challenge-v1.html`
- `Team Challenge` — `Teams score on the average, so the least active member matters most.` → `vantage-fit-team-challenge-v1.html`

### S11 Closer (`#demo`)
- H2: `See the wellbeing program your people would take part in.`
- P: `A 30-minute demo, built around your task mix and your privacy review.`
- Buttons: `Book a demo` · `See pricing`
- Checks: `See the mood check-in and what an admin sees instead` · `Review the privacy boundary with your IT team` · `No obligation`
- Note: `Participation visible. Feelings invisible.`

### Footer
Product: Wellbeing tasks · HR analytics · Security · Pricing.
Solutions: **Mental health challenges** (current) · Step challenges · Team challenges · Wellness
program · Remote teams · Global engagement · Analytics.
Company: About · Customer results · Case studies · Contact sales.
Bottom: `© 2026 Vantage Circle. All rights reserved.` · `HIPAA guidelines · SOC 2 Type II` ·
`Wellness built for participation.`

---

## 6. Claims ledger

Confidence key: **A** = current public help doc · **B** = code-verified spec · **C** = approved proof
gate (`04-proof-map.md` / `data-accuracy.md`) · **D** = published documentation quoted verbatim ·
**ILL** = illustrative, visibly labeled · **CONV** = design-system convention carried from approved
sibling pages.

Paths are relative to `vantagefit-astro/content/en/` for help docs and `vfit-os/` for specs unless
stated.

| # | Claim / figure on the page | Section | Source | Conf |
|---|---|---|---|---|
| 1 | Mindfulness, sleep and mood run as scored tasks with targets and points | S1, S3 | `help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md:43-91` | A |
| 2 | Nobody signs up; audience rule or admin add; no browse-and-join flow | S1, S2, S4, S6, S8 | `help/employee/challenges/how-do-i-join-a-challenge.md:17-38`; `specs/product/02-challenges-gamification/challenges.md:42-44` | A + B |
| 3 | Admins never see a mood entry | S1, S5, S6, S8 | `help/employee/health-tracking/how-do-i-track-my-mood.md:43`; `admin-what-tasks-can-i-include-in-a-custom-challenge.md:75` | A |
| 4 | Plus menu groups Mindfulness, Mood Tracker, Sleep Log | S1 (visual) | `help/employee/health-tracking/how-do-i-use-the-plus-menu.md:31-37` | A |
| 5 | "Mindful March" is a real shipped template name | S1, S6 (mock) | `help/admin/challenges/admin-how-do-i-use-templates.md:42` | A |
| 6 | Points are labelled Vantage Points | S3 | `help/admin/challenges/admin-how-wellness-rewards-work.md:13,59` (label is configurable, see §9) | A |
| 7 | Finishing a guided session is itself the log and counts toward the challenge | S3 | `specs/product/03-health-wellness/mindfulness.md:32,74` | B |
| 8 | Mindfulness library spans 7 categories | S3 | `specs/product/03-health-wellness/mindfulness.md:30-34` | B |
| 9 | Yoga logs manually or via the 7-minute routine | S3 | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:50` | A |
| 10 | Sleep logs manually or syncs from Apple Watch or Fitbit | S3 | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:65` | A |
| 11 | Mood log is a 5-point scale with optional reasons | S3 | `help/employee/health-tracking/how-do-i-track-my-mood.md:17-27` | A |
| 12 | Content tasks count only on reaching the end; cannot be self-logged | S3 | `help/employee/challenges/how-do-i-complete-challenge-tasks.md:60`; task doc `:110` | A |
| 13 | Adherence habit is one daily tap, e.g. sleep before 11 PM | S3 | `help/admin/challenges/admin-how-do-i-create-adherence-activities.md:31-41` | A |
| 14 | Task availability depends on configuration; full set in Full Mode | S3 | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:97-102` | A |
| 15 | Health-profile onboarding is skippable past the health connection | S4 | `help/employee/getting-started/how-do-i-complete-onboarding.md:19-76` | A |
| 16 | Steps from Apple Health (iOS) and Google Fit (Android); no wearable required | S4, S8 | `specs/product/10-integrations/device-integrations.md:22,170` | B |
| 17 | Non-step tasks cap at 100% of target; 5 sessions against a target of 3 score 3 | S4 | `help/employee/getting-started/ts-leaderboard-score-wrong.md:59-64` | A |
| 18 | Weekly leaderboard resets each Monday; overall stays cumulative | S4 | `help/employee/challenges/how-does-the-leaderboard-work.md:32-33` | A |
| 19 | Mood is one of six employee-set reminder types, employee picks time and repeat days | S4 | `help/employee/getting-started/how-do-i-set-reminders.md:26-45` | A |
| 20 | Missed daily check-ins cannot be back-filled | S4 | `how-do-i-complete-challenge-tasks.md:104` | A |
| 21 | Custom habits stay in the Plus menu with or without an active challenge | S4 | `admin-how-do-i-create-adherence-activities.md:43-67` | A |
| 22 | Mood-privacy sentence, quoted verbatim | S5 | `help/employee/health-tracking/how-do-i-track-my-mood.md:43` | D |
| 23 | Leaderboard opt-out: still participates, still earns points, still counts for team | S5 | `help/employee/challenges/can-i-opt-out-of-leaderboard.md:17-37` | A |
| 24 | Any audience filter marks the challenge private | S5 | `help/admin/challenges/admin-how-do-i-set-target-audience.md:41-45` | A |
| 25 | Cohort selection returns a count plus the privacy disclaimer string, quoted | S5 | `specs/product/03-health-wellness/workforce-health.md:76` | B |
| 26 | HRA and Workforce Health are AM-enabled / premium (stated as a gate) | S5 | `admin-how-do-i-set-target-audience.md:78`; `workforce-health.md:24,105` | A + B |
| 27 | CAN / CANNOT table, 13 rows, no addition, reorder or paraphrase | S5 | `help/admin/settings/admin-data-privacy-security.md:43-54` | D |
| 28 | Privacy caption, quoted verbatim | S5 | `admin-data-privacy-security.md:56` | D |
| 29 | Wizard field names (name, dates, privacy, week theme, task type, target, mode, points, audience) | S6 | `help/admin/challenges/admin-how-do-i-create-custom-challenge.md:34-120` | A |
| 30 | Creating a challenge takes 5 to 10 minutes from the admin dashboard | S6 | `admin-how-do-i-create-a-challenge.md:13` | A |
| 31 | Enroll Immediately / Enroll When Active | S6 | `admin-how-do-i-set-target-audience.md:53-65` | A |
| 32 | Notification to all participants; add a theme for an upcoming week | S6 | `help/admin/challenges/admin-how-do-i-manage-challenge.md:42-48,86-94` | A |
| 33 | Per-task and per-week breakdown with completed / partially completed / missed | S6, S8 | `help/admin/reports/admin-how-do-i-view-leaderboard.md:72-83` | A |
| 34 | CSV export contents; filters applied before export | S6 | `admin-what-reports-are-available.md:129-142`; `admin-how-do-i-view-leaderboard.md:95-102` | A |
| 35 | Score / Steps / Team leaderboard views; department filter and name search | S6 (mock) | `admin-what-reports-are-available.md:80-86` | A |
| 36 | At a Glance shows Mindful Minutes/day and Avg Sleep/day with sparkline and trend; Full Mode only | S6 | `specs/product/09-admin-platform/admin-dashboard.md:56`; `help/employee/health-tracking/what-are-trends.md:35,41` | B + A |
| 37 | One anonymous survey at challenge completion, 1 to 5 rating plus optional comment | S6 | `specs/product/09-admin-platform/surveys.md:31-40` | B |
| 38 | No mood report and no aggregate mood score exists | S6, S8 | `vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md:122` | B |
| 39 | Workforce health reporting is organisation-level only | S8 | `specs/product/03-health-wellness/workforce-health.md` (organisation-level only; no department, team or location breakdown exists) | B |
| 40 | A late-added participant scores from the join date forward | S8 | `help/admin/challenges/admin-how-do-i-add-remove-participants.md:61-69` | A |
| 41 | Mood, sleep and water log on the web as well as the app | S8 | `help/employee/health-tracking/how-do-i-use-the-plus-menu.md:73` | A |
| 42 | Guided sessions play offline and sync later | S8 | `specs/product/03-health-wellness/mindfulness.md:33,52` | B |
| 43 | No counseling, therapist network, helpline or clinical screening is **provided** | S2, S8 | Stated as a boundary. Nothing in either repo ships such a capability; the only adjacent object is a third-party Marketplace directory that admins cannot curate (`help/admin/programs/admin-how-does-marketplace-work.md:93-99,119`) | A (negative) |
| 44 | Brazosport ISD "Fit Wars": 2 weeks, May 6–19 2024, 10 to 15-min mindfulness at least 4x/week, Texas school district | S7 | `04-proof-map.md:247-260` | C |
| 45 | IBS Software "March to Fitness": 28 days, 500+ active participants, 130 logged daily mood, 95 mental wellness activities | S7 | `04-proof-map.md:237-244` | C |
| 46 | Wipro "Inbox to Inner Peace": Jun 11–24 2025, 163 yoga sessions, 1,279 mindfulness minutes | S7 | `04-proof-map.md:225-235` | C |
| 47 | Tata Motors: 9 min mindfulness on Step Up & Elevate, 7 min on Step & Stride, 7h 39m average sleep on Step & Stride | S7 | `04-proof-map.md:262-266` | C |
| 48 | Rachel Arthur quote and attribution, character-for-character | S7 | `04-proof-map.md:368-408` | C |
| 49 | Celegence Yoga Nidra quote, organisation-only attribution | S7 | `04-proof-map.md:368-408` | C |
| 50 | "Trusted by 100+ organizations worldwide" | S1 | `data-accuracy.md:252-261` | C |
| 51 | Logo band names (Tata Motors, Wipro, IBS Software, Brazosport ISD, Heidrick & Struggles) | S1 | approved-names list, `data-accuracy.md`. Accenture and Hershey stripped from the baseline band | C |
| 52 | Four regions, chosen at signup, permanent, no cross-region sharing | S9 | `admin-data-privacy-security.md:16-21` | A |
| 53 | Follows HIPAA guidelines; SOC 2 Type II | S9, footer | `vfit-os/sources/VFit-Marketing-Content-Compacted.md:161-162` | C |
| 54 | Employee-initiated, OTP-verified deletion; admin cannot delete on their behalf | S9 | `admin-data-privacy-security.md:58-66` | A |
| 55 | Custom onboarding terms, AM-configured | S9 | `admin-data-privacy-security.md:86-88` | A |
| 56 | "audit documentation shared under NDA during evaluation" | S9 | **Not product-sourced.** Sales-process convention; sibling pages say "Security documentation available during evaluation" | CONV |
| 57 | "Employees see their own data. HR sees aggregate trends." | S9 plaque | Carried verbatim from the approved homepage and hub mocks | CONV |
| 58 | Multi-activity row: 27 task types, a new theme each week | S10 | `admin-what-tasks-can-i-include-in-a-custom-challenge.md:13,100` | A |
| 59 | Team row: teams score on the average | S10 | `admin-how-do-i-create-custom-challenge.md:108` | A |
| 60 | Hero phone figures: 64% overall, 6,240 / 8,000 steps, 1/1 and 0/1 counters | S1 | invented | **ILL** |
| 61 | Launch mock figures: `target 4 · weekly · 40 pts`, `US offices · 412 match` | S6 | invented | **ILL** |
| 62 | Report mock: roster names Dana Whitfield / Marcus Ellery, scores 412 / 398, per-task points 120 / 40 / 15 / 20 / 0 | S6 | invented | **ILL** |

**Every mock carrying an invented figure ships a visible `Illustrative data` tag and repeats
"Illustrative data" in its `aria-label`.** Three mocks, three tags, three labels. The CAN / CANNOT
panel carries a green `From the privacy doc` tag instead, because it invents nothing.

**Deliberately absent from the ledger because they are absent from the page:** any engagement or
participation percentage, any step cap number, any anti-cheat threshold, any tie-break rule, any ROI
or healthcare-savings figure, GDPR / ISO 27001 / ISO 27701 in copy, headings, meta or alt text, any
Slack or Teams claim, any named session title outside the verbatim Celegence quote, and any mood
value, score, average or trend in any mock.

---

## 7. Proof decision

**The page carries a customer-result section, reduced, with no stat band.** Approved on-topic proof
exists for this program, so it is not padding, but the shape is deliberately different from the Steps
page.

**No `.results-grid`, no three-big-numbers tiles.** Every large approved percentage on this account
(IBS 88%, Brazosport 86%, Tata 70%, 59%) is an **engagement** rate measuring a **physical** challenge.
A big-number band here would either mislabel those figures or borrow a step result to close a mental
health page, which is exactly what the live page does today. Instead, four narrative cards set every
figure inline at body size, with the client and the program named in the same sentence as the number.

**What is cited and why:**

- **Brazosport ISD, "Fit Wars"** — a named **US** employer with a largely non-desk workforce, a
  citable program design (2 weeks, 10 to 15-minute mindfulness sessions at least four times a week),
  and the strongest named-person quote in the pool.
- **IBS Software, "March to Fitness"** — the only two hard mental-health **counts** in the approved
  set (130 logged daily mood, 95 engaged in mental wellness activities), with the 500+ participant
  context in the same sentence so the counts are not inflated by omission.
- **Wipro, "Inbox to Inner Peace"** — the only approved program whose **stated purpose** was mental
  wellbeing. Its 57-active-users figure is deliberately not shown, anywhere.
- **Tata Motors** — the only approved figures that describe sustained daily wellbeing behaviour
  (mindfulness minutes per day, average sleep), labelled per named program as the gate requires.

**Quotes: two, never three.** Rachel Arthur (Brazosport, named person and title, with photo) carries
the named-US-buyer voice. Celegence's Yoga Nidra line, organisation-only attribution, is the one
place a named session title is permitted, because it is inside a verbatim quote. Elsa Robertson
(Heidrick & Struggles) is the approved substitute if the Celegence slot is ever dropped.

**The one figure held back: Brazosport's organisational mood score of 4/5.** It is gate-approved and
on-topic, and it is still omitted from v1. The page tells the reader twice that no mood rollup reaches
an admin and that mood is never visible. Printing an organisational mood figure, however carefully
framed, hands a skeptical buyer the single contradiction that unravels the page's entire argument, and
creates a demo expectation the product cannot meet, since no mood model exists in either repo. See §9
for the open item this creates for the data owner.

---

## 8. Meta title and description

| Field | String | Chars |
|---|---|---|
| **Title** | `Employee Mental Health & Wellbeing Challenges \| Vantage Fit` | **59** |
| **Meta description** | `Run employee mental health and wellbeing challenges with private mood tracking, guided mindfulness and habits your people score. Book a Vantage Fit demo.` | **153** |
| **OG title** | `Employee mental health and wellbeing challenges` | 47 |
| **OG description** | `Mindfulness, sleep and mood check-ins run inside a challenge everyone is already enrolled in. HR sees participation. Admins never see a mood entry.` | 147 |

**Title reasoning: keep the live title unchanged.** It sits in the 50–60 range, carries the head term
"mental health", ends `| Vantage Fit`, uses no em-dash, and already holds ranking equity on a URL the
brief requires us to preserve. Changing it buys nothing and risks the one asset we were told to
protect. Tested alternates, not shipped: `Mental Wellbeing Challenges: Private by Design | Vantage Fit`
(60, right at the ceiling) and `Employee Mental Wellbeing Challenges | Vantage Fit` (50). Both drop
"Health", the higher-volume term.

**Description reasoning:** the live description duplicates the feature page's in substance. This one
differentiates toward **program and privacy**, carries the primary keyword in the first six words,
names the three mechanics, and ends on the verb-led CTA. No stat, because every stat strong enough to
lift CTR on this account measures a physical challenge.

**URL unchanged:** `/mental-health-and-wellbeing-challenges/`, with all four hreflang alternates
retained. **Cannibalization ruling:** this Solutions page owns program, outcome and BOFU intent;
`/features/mental-health-and-mindfulness/` owns capability depth. The page links down to it exactly
once, in S3, and never re-describes the library.

**FAQPage JSON-LD is emitted** from the five S8 questions, verified byte-identical to the visible
copy. The live page emits none, so this is a free structured-data win and it targets the objection
query cluster (`can my employer see my mental health app data`, `employee wellness data privacy`,
`wellbeing platform vs EAP`) that nobody is currently answering.

---

## 9. Assumptions and open questions

**Needs a human decision**

1. **Brazosport's organisational mood score of 4/5 is held out of v1.** It is approved in the gate
   file, but it implies a mood rollup that the same page says does not reach an admin, and no mood
   model exists in either code repo. **Data owner: reconcile the figure's provenance against the
   mood-privacy guarantee.** If it clears, it may be added to the Brazosport line in S7 as an outcome
   the district reported, and nowhere else. It must never appear in a mock or near the privacy band.
2. **S6's honesty block was reduced during the leanness pass.** The blueprint required three
   disclosures; the shipped `.measure-note` carries one. The two dropped facts are both true and both
   things a buyer would be annoyed to find later: exports are a manual CSV click with no scheduled
   delivery and no executive digest (`admin-what-reports-are-available.md:151`), and challenge
   reminder emails are off by default (`admin-what-emails-does-vfit-send.md:34,94`). **Recommend
   restoring both**, either to the measure note or to FAQ 2. The word cost is roughly 25 words.
3. **The compliance plaque artwork still asserts marks beyond the two claimable ones.** No copy on
   this page repeats them and the alt text does not, but the plaque now sits under a headline that
   invites counsel to verify. The fix is a HIPAA + SOC 2 only asset produced once for all six pages;
   it is a design-system task, not a page fix. Held per ruling C9, which permits reuse with rewritten
   alt.
4. **"audit documentation shared under NDA during evaluation"** (S9 card 2) is a sales-process claim,
   not a product-doc claim, and it is phrased differently here than on the five sibling pages. Confirm
   with sales, or align it to the house string "Security documentation is available during
   evaluation."
5. **Full Mode is an unstated precondition for the entire program.** The page says task availability
   depends on configuration and that Mindful Minutes trends are Full Mode only, but it never says that
   a Lite Mode account cannot run this program at all, and that Full → Lite is irreversible. That is
   probably correct for a marketing page and wrong for a pre-sales conversation. Confirm sales knows
   to raise it.

**Assumed, and safe to leave assumed**

6. **All mock figures are interface fiction**, visibly labelled, and never restated as outcomes.
   Every outcome claim lives in S7 with a named source.
7. **"Vantage Points"** is the default point label; the admin can rename it
   (`admin-how-wellness-rewards-work.md:59`). The page uses the default. If a reviewer prefers a
   product-agnostic string, "points" is a one-word swap in the S3 lead.
8. **Sibling links point at local mock files** in the same directory for reviewer navigation, and at
   live URLs for pages not yet rebuilt in this system. Both local targets exist on disk.
9. **`noindex, nofollow`** is set for the mock and must be removed for production.
10. **The nav mega banner links to the hub mock file** rather than a live URL, matching the sibling
    pages.
11. **"Mindful March"** is used as the challenge name in both mocks because it is a real shipped
    template name, not an invented one. The 4-week structure attached to it is illustrative.
12. **The page assumes the buyer already runs, or could run, a step challenge.** The whole hero
    argument ("the scoreboard your employees are already on") is weaker for a first-time Vantage Fit
    buyer with no existing program. That is the intended trade: the reader who converts here is the
    one widening an existing program, and S10 catches the other case.

---

## 10. Known gaps

Things no source in either repo could answer, and which the page therefore does not claim:

1. **How long a mental health program takes to stand up end to end.** The only sourced timing figure
   is "5-10 minutes" for the creation wizard (`admin-how-do-i-create-a-challenge.md:13`). There is no
   figure for Full Mode activation, HRA enablement, or rollout. The adjacent Lite Mode figure
   ("1–2 days, not weeks") exists but **cannot** be borrowed, because Lite Mode cannot run this
   program.
2. **Any tie-break rule for a Custom challenge leaderboard.** None is stated anywhere. The only
   documented tie-break in the corpus is Streak's, which is steps-only and was not borrowed.
3. **Any verification mechanism for self-logged wellbeing.** Meditation, mindfulness, yoga, sleep and
   mood are self-logged and no source describes a check on them. The page never writes "verified"
   near a wellbeing log, and S3's "How it logs" chips disclose which tasks are manual.
4. **Whether an organisational mood figure can legitimately exist.** The gate file approves one, the
   dashboard ground truth says mood has no model in either repo. Unresolved; see §9 item 1.
5. **Who authored the mindfulness content, and on what evidence base.** The library is "curated and
   maintained centrally by Vantage Fit" and nothing names a clinical author or review board. The page
   never says "clinically designed", "evidence-based" or "therapeutic".
6. **Whether the mood history screen is the Trends section.** `how-do-i-track-my-mood.md:35` says
   mood entries appear in Trends; the dedicated Trends article lists only Steps, Active
   Calories/Minutes, Mindful Minutes and Sleep (`what-are-trends.md:23-41`). The page does not name
   the screen.
7. **Whether an admin can curate the Marketplace.** The employee doc says yes
   (`what-is-the-marketplace.md:63`), the dedicated admin doc says no
   (`admin-how-does-marketplace-work.md:95-99`). The admin-specific article wins, and the topic stays
   off the page entirely.
8. **Any Slack or Microsoft Teams delivery path.** Zero spec coverage in either tree. The page says
   push notification and email, or says nothing.
9. **Any wellbeing ROI, absenteeism or claims-cost outcome.** No approved Vantage Fit figure exists.
   Every ROI question redirects to participation, which is why there is no CFO persona on this page.
10. **Any approved mental-health participation percentage.** The four large approved percentages all
    measure physical challenges. This is the reason S7 has no stat band, and it is the single biggest
    proof gap on the page. If the account ever clears a mental-health participation figure from a
    named US employer, S7 is where it goes.
