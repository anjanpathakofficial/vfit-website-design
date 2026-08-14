# Wellness Leagues — page brief

Intended URL: `/features/wellness-leagues/` · Mock: `vantage-fit-wellness-leagues-v1.html`

## Research takeaways

- Angle: always-on competition that outlasts any one challenge. Leagues are persistent, company-wide step tiers recalculated on a rolling average, not a campaign object.
- Tiers: Gold above 7,000 average daily steps, Silver 5,000 to 7,000, Bronze below 5,000. These are defaults, adjustable per company. Locked shield hexes used in the mock: Gold `#B9924E`, Silver `#798C92`, Bronze `#7F573D`. No Platinum or Diamond; custom tier names are backlog.
- Rolling window: live contradiction between legacy 21-day and code-verified "7 or 30 days typical." Page uses "a configurable rolling average window, 7 or 30 days typical" and never picks 21. Flagged here per the facts lock.
- Versus leaderboards: a challenge leaderboard ranks inside a time-bound campaign and resets when it ends. A league has no start or end, spans the whole company, and recalculates on the rolling window while enabled. The same steps feed both.
- Admin reporting once enabled is self-serve: standings, trends (weekly / monthly / yearly), distribution by department and country, paginated reports, CSV export. Employees see their tier in the mobile app only; there is no employee web league UI.
- Setup honesty: leagues are annual and ops-configured. Enabling leagues, setting thresholds, and choosing the window go through the account manager; it is not a day-one toggle. Disabled in Lite Mode. No wearable required; the phone pedometer suffices.
- No client-attributed proof exists for this page and none was invented. The 7,000-steps health-benefits line was skipped (VERIFY unresolved).

## Why this structure

There is no dedicated league screenshot in the asset library, so the hero carries a large HTML tier mock with the locked shield colors plus a movement photograph; the badges shot appears later strictly as supporting gamification art, captioned as badges, not leagues. Then: the tier table with default-adjustable framing, a leagues-versus-leaderboards contrast pair, what HR gets once enabled (standards, trends, distribution, CSV), a setup band carrying the annual / ops-configured gate, FAQ, done.

## Copy deck (as shipped)

- H1: "Competition that outlasts the challenge."
- Lead: employee wellness league system where the same steps that feed challenges also rank a persistent league.
- Sections: "Three tiers, on a rolling average." / "A league is not a leaderboard." / "What HR sees once it is on." / "Setup, stated plainly." / FAQ / final "Keep the competition after the challenge ends."
- Full copy is in the HTML; marketing copy is ~590 words outside nav, footer, and mock labels.

## Sources

- All mechanics, tier defaults, shield hexes, tier flags, do-not-claim list: `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` (Wellness Leagues card, platform guardrails, score table).
- Admin reporting surface (standings, trends, distribution, CSV): same file, Leagues card, consistent with `vc-dashboard-design` leagues UX prototype scope.
- "100+ organizations" approved aggregate, used once in the final band.
- No client proof used, per the facts lock.

## Meta drafts

- Title: `Employee wellness league system | Vantage Fit`
- Description: `Vantage Fit's employee wellness league system ranks Gold, Silver, and Bronze tiers on a rolling step average, an always-on competition that outlasts any challenge.`

## Critic result

Pass. Checked: tiers stated as default and adjustable; window stated as a configurable rolling average (7 or 30 days typical), never fixed at 21 days; leagues contrasted with challenge leaderboards, never conflated and never compared to the retired Org Wellness Score; no Platinum or Diamond tiers; no employee web league UI; no wearable requirement; annual / ops-configured gate stated in the setup band and FAQ; no Health Connect step claim; no invented tier-distribution stat; badges shot captioned as badges and achievements, not leagues; one large HTML tier mock plus one photograph minimum met; no em-dashes, exclamation marks, or banned filler; copy under 750 words.
