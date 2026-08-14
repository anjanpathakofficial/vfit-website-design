# Personalized Programs — page brief

**Slug:** `/features/personalized-programs/`
**Mock:** `claude-fable/vantage-fit-personalized-programs-v1.html`
**Group:** B, page 4 of 4. Feature page, not a Solutions page.

---

## 1. Research takeaways

**Two systems share a tab and nothing else.** Training Plans are a Vantage-Fit-curated
catalog that an employee configures and runs as a **personal challenge**. The Content Library
is an admin-managed set of articles, videos, podcasts, webinars and Health Bites that can be
**assigned as challenge tasks**. Different owners, different gates, different outputs. The
page is built as two full-width bands, each labelled as a system, so the split is structural
rather than a line of copy.

**The catalog number is the honesty test.** Nine plans exist. **Two are startable today**,
Couch to 5K and Walking Habit Plan; seven carry COMING_SOON status, which the spec confirms
are visible but not enrollable. Showing all nine as tiles with seven visibly disabled is more
convincing than a sentence, and it makes overclaiming impossible.

**"Only the employee can stop it" is the strongest line on the page for an HR buyer.** Help
doc `how-do-i-start-a-training-plan.md` states it directly: the admin cannot stop a plan and
no one else can see or manage it. It also explains why there is no leaderboard and no
certificate. That is a real product boundary and it separates plans from HR challenges
better than any comparison table, though the page ships one of those too.

**Content-as-task is where the second system meets participation.** A "watch this video" or
"complete bite-size content" task completes itself when the item is viewed or stepped
through, and Health Bites completion logs `activity_id 1015`. Quizzes are auto-evaluated and
need every answer correct to pass, and both a pass and a fail still log. That last detail
matters to a buyer worried about punishing people for learning.

**Enrollment friction is deliberate and worth showing.** Three questions (weeks 4 to 8,
training days 3 to 6, which days), a generated week-by-week preview, then Start Challenge,
and the plan begins **the following Monday** rather than immediately.

### Conflicts flagged

| Conflict | Sources | Resolution on the page |
|---|---|---|
| **Targeting dimension** | OS `health-content-library.md` §3.1 lists "Activity level" among personalization filters. Facts lock says targeting is by **health profile**, and activity level is never a targeting dimension. | Facts lock wins. The page says age, gender and health profile, and states outright that activity level is not a targeting dimension. Legacy Content Library copy is the loser here. |
| Plan count | Help `what-are-training-plans.md` says "currently 9 plans". Facts lock says 9 total, 2 available, 7 coming soon. | Consistent. The page ships 9 total with 2 startable, and never implies a large live catalog. |
| Couch to 5K progression | Facts lock says linear ~1 km to 5–6 km with a **final-week taper**. Help says "work up to the full 5 km by the final week", with no taper. | The week strip is marked illustrative and shows the shape, peaking before the final week. Flagged rather than asserted as exact weekly distances. |
| Quiz failure | OS says all questions must be answered correctly to pass. Help says bite-size quizzes carry "no penalty for wrong answers". | Both are true and both ship: all-correct to pass, and a pass or a fail still logs the activity. |
| AI-generated pacing | A single FAQ line exists in legacy material. Facts lock marks it VERIFY. | Not used. The page states the pacing is rule-based progression, and no AI claim appears anywhere. |
| Company count | Internal figure of roughly 11 companies with Training Plans enabled. | Not published, per the facts lock. The page says "enabled per company through your account manager". |
| **Both assigned CDN shots are HR-run challenges** | `vfit-challenge-mobile` is "21 Days of Yoga" and `vantage-fit-challenge-journey-mobile` is "Backpacking through Europe". Both show points and a **leaderboard**. Neither is a training plan, and no training-plan screenshot exists in the asset library. | The page claims plans have no leaderboard, so an uncaptioned shot of one would contradict its own copy. Both shots ship **captioned as what they are**: admin-built challenges. The hero caption says a started plan lives in the same tab without the leaderboard; the in-band caption says a plan borrows the task and progress mechanics and drops the ranking. This turns the asset problem into the page's shared-surface argument instead of hiding it. Worth requesting a real training-plan screenshot before publish. |

---

## 2. Why this structure

Seven sections. The two systems are the two tallest, and they are visually different from
each other on purpose:

1. **Hero** — two systems named in the lead, with the Challenges-tab screenshot and a caption
   that says plainly which surface it is showing, plus a drawn split card labelling System 01
   and System 02 as the map for the rest of the page.
2. **System 01, Training Plans** — white band, coral system plate. Nine catalog tiles with
   seven disabled, the three-question configurator drawn as a form, the week-by-week shape,
   the quit rule, and the runner photograph next to Couch to 5K.
3. **System 02, Content Library** — canvas band, ink system plate, mint accents, card shapes
   that do not match the plan tiles. Five content types, the task record with
   `activity_id 1015`, quiz behaviour, targeting, admin CRUD, and one line on the Marketplace.
4. **Not the same thing** — a three-column separation covering Training Plan, content item and
   HR-run challenge, which settles the "plans are not challenges" question in a glance.
5. **The gate** — select-partner for plans, self-serve for content CRUD, ops-required for
   Marketplace and Health Bites authoring, none of it in Lite Mode by default.
6. **FAQ (3)** plus sibling links.
7. **Closer.**

Fourth distinct hero composition in the group: Health Metrics stacks a product card over a
photo band, Mental Wellbeing floats a chip over one tall shot, Leagues draws a card in HTML,
this one pairs the shot with a two-system split marker.

**Not repeated here:** the mindfulness library (Mental Wellbeing owns it, and this page only
says a plan can include mindful or rest days), the HRA questionnaire, leagues, and the 27 task
types that belong to Program Builder.

---

## 3. Copy deck

**H1** Structured workplace wellness plans, and the content to follow them.

**Lead** Two separate systems in the Programs tab. A training plan runs as a personal
challenge that only the employee can stop. A library item can be assigned as a challenge
task. They are built differently and gated differently.

**Hero note** Programs tab · Two systems · Not in Lite Mode

**S2 — System 01, Training Plans / "Nine plans. Two you can start today."**
Curated by the Vantage Fit wellness team, not built by your admins. Seven more are visible in
the catalog with a coming-soon marker, so nobody is promised a library that is not there yet.
Configure: how many weeks (4 to 8), how many training days a week (3 to 6), and which days.
The app generates a week-by-week plan, and Start Challenge sets it running the following
Monday.
Couch to 5K opens near a kilometre and builds toward five, with rest days on the days that
were not selected. The progression is rule-based, not generated by a model.
Once it starts it is a personal challenge in the Challenges tab, tracked the same way anything
else is.
**Only the employee can stop it.** An admin cannot stop it, cannot change it and cannot see it
as an individual plan. There is no leaderboard, because it is not a competition, and no
completion certificate.

**S3 — System 02, The Content Library / "Read it, watch it, and it counts."**
Articles, videos, podcasts and webinars, plus Health Bites, which are step-through micro-
lessons of two to three minutes that mix images, text and quiz screens.
Content as a task: "watch this video," "read this article" and "complete bite-size content"
are challenge tasks that complete themselves when the item is viewed or stepped through.
Finishing a Health Bite logs an activity.
Quizzes are optional and auto-evaluated. Every answer has to be right to pass, and a pass or
a fail both still log the completion, because the point is engagement rather than a grade.
Targeting is by age, gender and health profile. Activity level is not a targeting dimension.
Admins publish and unpublish articles, videos and podcasts themselves, write the quiz
questions and manage categories, from Programs then On-Demand Content.
The Marketplace lists partner offerings as external links with a disclaimer.

**S4 — Not the same thing**
| | Training plan | Content item | HR-run challenge |
| Built by | Vantage Fit | Your admin, or Vantage Fit | Your admin |
| Started by | The employee | Browsed or assigned | The admin |
| Stopped by | The employee only | n/a | The admin |
| Leaderboard | None, it is personal | n/a | Yes |
| Certificate | None | None | Yes |

**S5 — The gate**
Training Plans as a whole are enabled per company through your account manager. Content
Library publishing is self-serve once the Programs tab is on. The Marketplace, Health Bites
authoring, multi-language versions and demographic targeting are set up with us. Lite Mode
clients get none of this by default.

**FAQ**
- Can our admins build their own training plans? Not today. The catalog is curated by Vantage
  Fit. Admins build challenges, which is a different system.
- Are the plans AI-generated? No. The progression is rule-based, and the three answers at
  enrollment shape the schedule.
- What happens if someone quits halfway? The plan stops for them and nothing carries over to a
  new one. Their logged activity still counts toward participation.

**Closer** See both systems in the same tab, ten minutes apart.

**Meta title** Corporate Wellness Training Programs | Vantage Fit
**Meta description** Nine curated training plans with two available today, configured in three questions and run as a personal challenge, plus a content library whose articles and videos can be challenge tasks.

---

## 4. Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` — page 7 card, two-system separation, 2 live / 7 coming soon, quit rules, no certificate, targeting rule, tier gates, "no proof for this page" (facts lock, wins all conflicts)
- `vfit-os/specs/07-training-programs/personal-training-programs.md` — catalog structure, COMING_SOON status visible but not enrollable, questionnaire as `configData` JSON, enrollment creates a UserCampaign, stop endpoint, ongoing-programs report
- `vfit-os/specs/06-content-education/health-content-library.md` — four content types, quiz all-correct validation, category status including ACTIVE_IN_PROGRAMS, admin CRUD endpoints, availability windows
- `vantagefit-astro/.../programs/what-are-training-plans.md` — 9 plans, curated by Vantage Fit not admins, Programs tab gate, not in Lite Mode, the plans-vs-challenges table
- `vantagefit-astro/.../programs/how-do-i-start-a-training-plan.md` — the two available plans, 4–8 weeks, 3–6 days, day selection, preview, Start Challenge, following Monday, stop rules and permanence, Couch to 5K shape
- `vantagefit-astro/.../programs/what-is-bite-size-content.md` — step-through format, image, text and quiz screens, completion counts as an activity, multi-language
- `styles/enterprise.css`, `styled-homepage/`, `claude-fable/vantage-fit-wellness-leagues-v1.html` — design system and chrome

---

## 5. Critic result

| Check | Result |
|---|---|
| Two systems visually separate | Yes. Two full-width bands, each with a numbered system plate, different backgrounds, different accent colours and deliberately different card shapes. Section 4 separates them again in a table |
| Training Plans implied as a large live catalog | No. Nine tiles, seven rendered disabled with a coming-soon marker, and the heading itself says two are startable |
| Admins can create, stop or customize plans | Explicitly denied three times: in the copy, in the comparison table and in an FAQ |
| Training plans given completion certificates | Explicitly denied in copy and in the table |
| Training Plans conflated with HR challenges | No. The comparison table carries an HR-challenge column specifically to settle it |
| AI-personalized plans or AI content recommendations | No AI claim anywhere. Copy says rule-based progression, and an FAQ answers the question directly |
| Targeting by activity level | Explicitly denied in the Content Library band |
| Health Bites creation implied as self-serve | No. Named in the gate section as set up with us, API-only authoring |
| IBS mood or mental challenge-task figures used as proof | No. **No proof band at all.** The facts lock assigns this page none, so none ships |
| WHO stat reused | No |
| Marketplace overstated | One line, described as partner offerings with external links and a disclaimer |
| Mindfulness library reprinted | No. One cross-link only |
| Lite Mode and account-manager gates buried | No. Own section, plus the hero note and an FAQ |
| Em-dashes / exclamation marks / "Learn more" | None |
| `../styles/enterprise.css` linked, no new brand | Yes. No new tokens, font or wordmark |
| Product screenshot + photograph | 2 CDN product shots (`vfit-challenge-mobile` in the hero, `vantage-fit-challenge-journey-mobile` in the Training Plans band) + 1 photograph (`card-participate.jpg`, a runner, beside Couch to 5K). Both screenshots are captioned as admin-built challenges, because that is what they show |
| Screenshots contradict the copy | Checked and fixed. Both shots display a leaderboard while the page says plans have none, so each carries a caption naming the surface. No image on this page is presented as a training plan |
| Marketing copy budget | 789 words counted strictly (headings, eyebrows, the separation table, admin cards, figcaptions and FAQ all included; drawn mocks excluded). Approved Group A peers measure 782 / 778 / 636 the same way |
| Renders correctly | Yes. Walked the full page at 1440px in Chrome, hero through closer. Two system bands read as visibly different systems, the 2-live / 7-coming-soon catalog is unambiguous, and the separation table renders in three columns |
| Shows how it becomes participation | Yes, twice. A plan runs as a personal challenge; a content item completes a challenge task and logs an activity |
