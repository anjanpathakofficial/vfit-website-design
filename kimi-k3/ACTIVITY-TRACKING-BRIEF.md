# Activity Tracking — page brief

Intended URL: `/features/activity-tracking/` · Mock: `vantage-fit-activity-tracking-v1.html`

## Research takeaways

- Facts lock (`FEATURES-EMPLOYEE-LOGGING-BRIEFS.md`) is the authority; help docs confirmed it: rings help (`what-are-activity-rings.md`) matches Ring 1 = steps always, Ring 2 = calories or active minutes set company-wide, defaults 10,000 / 250.
- Step source stack is Apple Health (iOS), Google Fit / selected Android source, Fitbit, Garmin. Health Connect is for Android *imports*, never the step pipeline. Page avoids naming any Android task-sync source (live contradiction, hedge by omission).
- Step capping exists in code but is disabled globally. The page says so plainly, which is the page's honesty angle.
- Lite Mode = steps only. Everything else on this page is Full Mode. Tier flags: VC Support for Ring 2 metric, manual steps, overlapping-activity prevention, Lite Mode enablement; self-serve for custom activities.

## Why this structure

Hero proves "no wearable, real logging" with the Log Activity product shot plus a movement photo and the 100-steps conversion as a chip. Then: sources (how data gets in), the math (how it counts), the catalog (65 types, compressed to categories plus three rollout-relevant details), integrity (why HR can trust the number), proof band, FAQ for rollout objections. Must-cover items became cards, list lines, and screenshot captions, not paragraphs.

## Copy deck (as shipped)

- H1: "One surface. Every log counts."
- Lead: employee activity tracking software, phone as system of record, no wearable required.
- Sections: "Three sources. One count." / "100 steps. One active minute." / "65 types. Plus the ones you name." / "Counted honestly." / FAQ "Before rollout" / final "See every log become one number."
- Full copy is in the HTML; marketing copy is ~560 words outside nav, footer, and mock labels.

## Sources

- Step formula, 100 steps = 1 active minute, duplicate detection, 15 s sync floor, capping disabled, Lite Mode, tier gates: `FEATURES-EMPLOYEE-LOGGING-BRIEFS.md` (shared logging physics, Activity card).
- Rings defaults and configuration: help doc `content/en/help/employee/health-tracking/what-are-activity-rings.md`.
- Proof: Tata Motors 6,400+ activities logged and IBS Software 100+ → 236 employees, both from the facts lock, both labeled `[VERIFY WITH PRODUCT]` on the page.
- "100+ organizations" aggregate trust signal (approved).

## Meta drafts

- Title: `Employee activity tracking software | Vantage Fit`
- Description: `Vantage Fit's employee activity tracking software logs steps, workouts, and daily activity from any phone. No wearable required. 65 activity types, one honest count.`

## Critic result

Pass. Checked: no Health Connect as step source, no capping-as-active, no 47+, no AI labels, no Org Wellness Score, no SOC 2 / GDPR / ISO, no em-dashes or banned filler, Lite Mode and VC Support gates stated, Tata 472 / Wipro stats kept off this page, one product shot plus one photograph minimum met (two shots, one photo).
