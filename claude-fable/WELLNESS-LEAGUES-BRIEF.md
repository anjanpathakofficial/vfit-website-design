# Wellness Leagues — page brief

**Slug:** `/features/wellness-leagues/`
**Mock:** `claude-fable/vantage-fit-wellness-leagues-v1.html`
**Group:** B, page 3 of 4. Feature page, not a Solutions page.

---

## 1. Research takeaways

**The angle is a negative, and negatives sell to skeptics.** A challenge leaderboard ranks
people inside a campaign and clears when the campaign ends. A league is recalculated every
day from a rolling average and is still there on Monday. The page is built around that one
contrast, and the comparison block is the centre.

**Average, not total, is the anti-gaming mechanism and it is worth showing.** Help doc
`what-are-wellness-leagues.md` makes the point better than any marketing line: one
20,000-step day followed by three 2,000-step days averages 6,500, which loses to someone
walking 8,000 every day. That example ships almost verbatim because it is checkable and it
explains the design.

**The gate is the most important honest thing on the page.** Leagues are not a day-one
toggle. Enabling them, setting thresholds and choosing the rolling window all go through the
account manager, they are scoped annually, and Lite Mode has none of it. Burying that would
fail review, so it gets its own ink panel rather than a footnote.

**HR reporting is real and specific.** `LeagueReportController` exposes paginated summaries,
a full export, per-user daily steps with league, tier distribution, and trends. The report
model carries `daysInGold/Silver/Bronze`, `percentageInGold/Silver/Bronze`, `primaryLeague`,
`currentLeague`, `avgSteps`, plus department and country. That is enough to be concrete
without turning this page into a second Admin Dashboard.

**No client proof exists for this page, so there is no proof band.** The facts lock assigns
none and forbids inventing a tier-split figure. The page ships without a customer-results
section rather than padding one, which is the correct outcome, not a gap.

### Conflicts flagged

| Conflict | Sources | Resolution on the page |
|---|---|---|
| **Rolling window** | OS `leagues.md` §3.1 says "21-day rolling average (configurable), default 21". Help doc says "either 7 days or 30 days, depending on your company's configuration". Facts lock says use "a configurable rolling average window (7 or 30 days typical)" and treat 21 as legacy. | Facts lock wins. The page says **configurable, 7 or 30 days typical**, and never prints 21. This is a live contradiction between spec and help; it is flagged here rather than silently resolved. |
| **Custom tier names** | OS `leagues.md` §3.2 says "supports custom tier names and thresholds". Facts lock says Platinum / Diamond and custom tier names are Backlog. | Facts lock wins. The page claims **thresholds** are configurable and says nothing about renaming tiers or adding a fourth. |
| Threshold example | OS default is Gold > 7,000. Help doc's illustrative example says "Gold = 12,000+". | Both are consistent with "default, adjustable". The page ships the shipped default (7,000 / 5,000) and marks it default and adjustable everywhere it appears. |
| Where 7,000 comes from | OS marketing section ties it to "7,000+ steps/day associated with significant health benefits", which the facts lock marks VERIFY. | The health-benefit claim is **not made**. An FAQ says plainly that 7,000 is the shipped default and adjustable, and that Vantage Fit does not present it as a clinical target. |
| Org Wellness Score comparison | Legacy brief compared leagues to the org score. | Retired. The page compares leagues to **challenge leaderboards** only. |

---

## 2. Why this structure

Nine sections. No proof band, on purpose.

1. **Hero** — a "My League" card drawn in HTML, because there is no league screenshot in the
   asset library and faking one would be a fabricated product shot. Third distinct hero
   composition in the group: Health Metrics stacks a product card over a photo, Mental
   Wellbeing floats a chip over one tall shot, this one is a single drawn card.
2. **The tiers** — three shields in the locked hex values, thresholds on each, with "default,
   adjustable" attached to the block rather than hidden in a footnote.
3. **The rolling average** — the anti-gaming mechanic, with the help doc's own arithmetic
   example drawn as two seven-day strips that reach different averages.
4. **Leagues vs leaderboards** — the differentiator, as a row-by-row comparison, with the
   trophy photograph beside it.
5. **What HR sees** — standings, trends, distribution, CSV, all named.
6. **On the employee's phone** — Profile, Leagues, week-by-week history, mobile only. Carries
   the badges screenshot, captioned as badges and explicitly separated from leagues.
7. **The gate** — annual, ops-configured, absent in Lite Mode. On ink.
8. **FAQ (3)** plus sibling links.
9. **Closer.**

**Not repeated here:** step sources and the step ledger (Activity Tracking owns those),
mindfulness minutes, the HRA. Leagues run on steps and the page says so in one line.

---

## 3. Copy deck

**H1** An employee wellness league system that never resets.

**Lead** Gold, silver and bronze, recalculated every day from a rolling average of steps. A
challenge ends and its leaderboard clears. The league is still there on Monday.

**Hero note** Always on · Steps only · Mobile app

**S2 — The tiers / "Three tiers, and your numbers on them."**
Gold, above 7,000 average daily steps. Silver, 5,000 to 7,000. Bronze, below 5,000.
Every one of those numbers is a default your HR admin can change. Set them for the workforce
you have, not the one a vendor assumed.

**S3 — The basis / "An average, which is harder to game than a total."**
The league reads a rolling average of daily steps, recalculated every day. The window is
configurable, and 7 or 30 days are the usual choices.
One 20,000-step day followed by three 2,000-step days averages 6,500. Someone walking 8,000
every day beats it. Consistency wins, and a zero-step day costs more than a big day gains.

**S4 — Against leaderboards / "A leaderboard is an event. A league is a state."**
| | Challenge leaderboard | Wellness league |
| Scope | One campaign | Company-wide |
| Lifespan | Starts and ends | Always on while enabled |
| Reset | Clears every campaign | Recalculated daily, never cleared |
| Ranks | Position against entrants | Tier against a threshold |
| Needs | An admin to run a program | Nothing after setup |
They are not alternatives. Most programs run both, and leagues are what holds the floor
between campaigns.

**S5 — What HR sees / "Standings, trends, and a CSV."**
Once leagues are enabled the reporting is self-serve: current standings, weekly, monthly and
yearly trends, tier distribution split by department and country, paginated reports, and a
full CSV export. Each employee row carries their average steps, current tier and the share of
days spent in each tier.

**S6 — On the phone / "Profile, then Leagues."**
Employees find their tier under Leagues in their profile, with week-by-week navigation back
through their own history. It is a mobile surface. There is no employee league page on the
web, and no wearable is needed, since the phone pedometer counts.
Badges caption: Badges are a separate recognition surface, earned for milestones. They are not
league tiers.

**S7 — The gate** (ink panel)
Leagues are not a switch in the dashboard. Enabling them, setting the thresholds and choosing
the rolling window are configured with your account manager, scoped annually. Once they are
live, viewing standings, trends and distribution is self-serve. Lite Mode, which is steps
only, does not include leagues at all.

**FAQ**
- Where does 7,000 come from? It is the shipped default and it is adjustable. Vantage Fit does
  not present it as a clinical target.
- Can we add a fourth tier, or rename them? Not today. Three tiers, with thresholds you set.
- Does a bad month leave someone stuck in bronze? No. The average is rolling and recalculated
  daily, so a better fortnight moves the tier.

**Closer** See a tier move without a campaign running.

**Meta title** Employee Wellness League System | Vantage Fit
**Meta description** Gold, silver and bronze tiers from a rolling average of daily steps, recalculated every day. Always on, thresholds set by your HR admin, with standings and CSV export.

---

## 4. Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` — page 6 card, locked hex values, window contradiction, tier gate, "no invented proof" (facts lock, wins all conflicts)
- `vfit-os/specs/02-challenges-gamification/leagues.md` — default thresholds, configurability, recalculation endpoints, report endpoints, `UserAggregateReportDetailed` and `LeagueDistribution` fields, department and country filters
- `vantagefit-astro/.../health-tracking/what-are-wellness-leagues.md` — 7 or 30 day window, daily recalculation, Profile then Leagues, week-by-week history, the averaging arithmetic
- `vc-dashboard-design/docs/leagues-ux-prototype/` — referenced for what HR sees once enabled; the page names the reports without rebuilding the dashboard
- `styles/enterprise.css`, `styled-homepage/`, `claude-fable/vantage-fit-mental-wellbeing-v1.html` — design system and chrome

---

## 5. Critic result

| Check | Result |
|---|---|
| League window stated as a fixed 21 days | No. "Configurable, 7 or 30 days typical". 21 never appears |
| Thresholds stated as universal | No. "Default, adjustable" appears on the tier block, in the copy and in the FAQ |
| Platinum / Diamond / custom tier names | No. An FAQ says plainly that a fourth tier and renaming are not available today |
| Web employee league UI | No. Explicitly denied in S6 |
| Wearable required | No. Explicitly denied, phone pedometer named |
| League steps via Health Connect | Not claimed. Health Connect is not mentioned on this page |
| Leagues conflated with leaderboards | No. S4 is a row-by-row separation and says most programs run both |
| Compared to Org Wellness Score | No. The comparison is to challenge leaderboards only, per the facts lock |
| Department-level wellness-score rankings | No. Only tier distribution by department, which is shipping |
| Invented tier-split or client stat | No proof band at all. The facts lock assigns none, so none ships |
| 7,000-steps health-benefit claim | Not made. FAQ answers the "why 7,000" question without a health claim |
| Tier gate buried | No. Its own ink section, plus the annual and Lite Mode facts repeated in the FAQ head |
| Turned into a second Admin Dashboard | No. Reports are named in one section and the page links out |
| Em-dashes / exclamation marks / "Learn more" | None |
| `../styles/enterprise.css` linked, no new brand | Yes. Tier shields use the locked hex values as illustration, not as new brand colors |
| Large tier mock + photograph | Yes. HTML "My League" card in the hero, three shields at full width in S2, both drawn in the locked hex. Photograph: `card-reward.jpg`. Supporting product shot: `vantage-fit-badges-achievements-mobile`, captioned as badges and explicitly not as leagues |
| Marketing copy budget | 730 words counted strictly (headings, eyebrows, comparison rows, report cards, figcaptions and FAQ all included). Approved Group A peers measure 782 / 778 / 636 the same way |
| Arithmetic in the mock checks out | Yes. 20,000 then 2,000 three times averages 6,500, which is silver on the default thresholds. 8,000 daily averages 8,000, which is gold. Bar heights match the numbers printed beside them |
| Renders correctly | Yes. Walked the full page at 1440px in Chrome, hero through closer. Shields, tier wall, averaging chart, comparison table and gate panel all confirmed on screen |
| Shows how it becomes participation | Yes. The same daily steps that feed challenges rank the league, stated in the hero and S3 |
