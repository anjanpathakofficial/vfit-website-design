# Wellness Leagues

**URL:** `/features/wellness-leagues/`  
**Mock:** `vantage-fit-wellness-leagues-v1.html`  
**Angle:** Always-on competition that outlasts any one challenge.

## Page job

Prove leagues are a persistent Gold / Silver / Bronze step tier, not a challenge leaderboard: default thresholds that HR can adjust, a configurable rolling window (7 or 30 days typical), always-on recalculation, mobile employee view, admin standings / trends / department / country / CSV once enabled. Annual / ops-configured. Same steps that feed challenges also rank the league.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See the tiers.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Tiers (lock + OS leagues):** Gold (>7,000 avg daily steps), Silver (5,000–7,000), Bronze (<5,000). **Default, fully configurable.** Always say “default, adjustable by your HR admin.” Hex: Gold `#B9924E`, Silver `#798C92`, Bronze `#7F573D`. Platinum / Diamond are backlog. Not shown.
- **Window (lock vs OS vs help):** Lock: “a configurable rolling average window (7 or 30 days typical).” OS leagues.md still defaults to 21 days. Help `what-are-wellness-leagues.md` already says 7 or 30. Page uses 7 or 30 typical. 21-day treated as legacy in this brief only.
- **Always-on (lock + help):** Recalculates on the rolling window. Unlike a start / end challenge. Help: recalculated every day. Week-by-week history on mobile (Profile → Leagues).
- **Vs leaderboards (lock):** Leaderboards rank inside a time-bound challenge and reset each campaign. Leagues are persistent, company-wide, always active while enabled. Do **not** compare leagues to Org Wellness Score.
- **Admin (lock + dashboard leagues handoff):** Once enabled: standings, trends (weekly / monthly / yearly), distribution by department / country, paginated reports, CSV. Enabling leagues, thresholds, and the window require the account manager. Not a day-one toggle. Do not turn this employee page into a second Admin Dashboard.
- **Employee surface (lock):** Mobile only. No employee web UI. Phone pedometer suffices. Wearable not required. Disabled in Lite Mode.
- **Through-line:** The same steps that feed challenges also rank the league. No Health Connect as a league step source.
- **Proof:** None client-attributed. Do not invent a tier-split stat. Skip the 7,000-steps health-benefits line (VERIFY if ever used).

### Conflicts left unresolved (not silently fixed)

1. OS default window = 21 days. Lock + current help = 7 or 30 typical. Page uses 7 or 30. 21-day flagged here as legacy.
2. Help: HR admin sets thresholds. Lock: enabling, thresholds, and window are annual / ops-configured via account manager. Viewing reports is self-serve once enabled. Page uses lock.
3. OS / help still mention Wellness Score. Retired. Left off. Contrast is leagues vs **challenge leaderboards** only.

## Why this structure

Different hero from Mental’s minutes card. Signature is three metal shields plus a leagues-vs-leaderboards pair. Badges screenshot is supporting only.

| Section | Job |
|---|---|
| Hero + stairs photo + three shields | First screen: Gold / Silver / Bronze, always on. |
| Defaults, adjustable + 7 or 30 | Thresholds and window, labeled default. |
| Always-on vs a campaign | Recalc vs start/end. Same steps. |
| Leagues vs leaderboards | The one contrast that is allowed. |
| Admin once enabled | Standings, trends, dept/country, CSV. Compact. |
| Annual / mobile / Lite | Honest gates. No web employee UI. |
| No proof band | Lock: no client tier stat. |
| 3 FAQs + siblings | Window, wearable, who turns it on. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** Same chrome. `../styles/enterprise.css`. Current mega item: Wellness leagues. Generated stairwell photograph + HTML shields in the locked hex + badges CDN shot captioned as badges, not leagues. No wellness-score screenshots.

## Copy deck

**Title:** Employee wellness league system | Vantage Fit  
**Meta:** Gold, Silver, and Bronze on a rolling step average. Default thresholds, adjustable. Always on. Not a challenge leaderboard. Annual, ops-configured.

**Eyebrow:** Features · For employees  
**H1:** The league outlasts the campaign.  
**Lead:** Gold, Silver, and Bronze on a rolling step average. Always on while enabled. The same steps that feed a challenge also rank the league.  
**Hero notes:** Default, adjustable · 7 or 30 days typical · Annual / ops-configured  
**CTAs:** Book a walkthrough · See the tiers

**H2:** Three tiers. Defaults, not dogma.  
Gold > 7,000. Silver 5,000–7,000. Bronze < 5,000. Default, adjustable by your HR admin.

**H2:** A rolling window. Not a fixed 21 days.  
Configurable rolling average. 7 or 30 days typical.

**H2:** Always on. Challenges still start and end.  
Leagues recalculate. Campaigns have a start and an end. Leaderboards reset with the campaign. Leagues do not.

**H2:** HR sees the mix. Employees see a shield.  
Once enabled: standings, weekly / monthly / yearly trends, department and country, paginated reports, CSV. Employee view is mobile only.

**H2:** Annual. Ops turns it on.  
Account manager for enablement, thresholds, and the window. Phone pedometer is enough. Not in Lite Mode. No employee web UI.

**Proof:** none.

**FAQ**  
1. Is this a challenge leaderboard?  
2. Do employees need a wearable?  
3. Can HR flip leagues on from the dashboard tomorrow?

**Close H2:** Keep the competition running after the banner comes down.

## Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` platform rules + page 6
- `vc-os/vfit-os/specs/02-challenges-gamification/leagues.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/what-are-wellness-leagues.md`
- `vc-dashboard-design/docs/superpowers/specs/2026-08-01-wellness-leagues-snapshot-HANDOFF.md` (admin once enabled; not cloned onto this page)

## Assumptions

- Window copy follows the lock (7 or 30 typical), not OS 21-day default.
- Enablement / thresholds / window follow lock (account manager), not help’s “HR admin sets.”
- No 7,000-steps health-benefits claim.
- Badges CDN shot is captioned as badges / achievements, not as the league product.
- Org Wellness Score comparison is absent.

## Critic

Run after the mock.

- Thresholds always “default, adjustable.”
- Window never stated as a fixed 21 days.
- No Platinum / Diamond. No employee web UI. No wearable required.
- Contrast is leagues vs challenge leaderboards, not vs Org Wellness Score.
- No invented client tier-split.
- Annual / ops-configured is on the first screen and in gates.
- No em-dashes, exclamation marks, or banned filler.
- `../styles/enterprise.css` linked. HTML tier mock + photograph + supporting badges shot.

**Pass.** Marketing copy in `<main>` is ~630 words including mock labels (in the 450–750 band). HTML shields use `#B9924E` / `#798C92` / `#7F573D`. Photograph + badges shot (captioned as badges, not leagues). Visual chrome matches the other Group B pages.
