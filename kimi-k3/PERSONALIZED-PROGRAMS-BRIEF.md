# Personalized Programs — page brief

Intended URL: `/features/personalized-programs/` · Mock: `vantage-fit-personalized-programs-v1.html`

## Research takeaways

- One page, two systems, kept visually separate: **Training Plans** (the lead) and the **Content Library** (supporting proof). They must not read as one blended catalog.
- Training Plans: VFit-managed catalog browsed by category, 9 plans total with exactly 2 Available (Couch to 5K, Walking Habit Plan) and 7 Coming Soon (Shredded in 12 Weeks, Quit Smoking in 30 Days, Ride to Thrive, Mindful Moments, plus 3 more). Never imply a large live catalog.
- Enrollment tunes the plan with 3 questions: weeks (4 to 8 slider), training days per week (3 to 6 radio), which days (checkboxes). The employee gets a week-by-week preview, taps Start Challenge, and the plan starts next Monday. Couch to 5K progresses linearly from about 1 km to 5 to 6 km with a final-week taper; rest days sit on unselected days.
- A plan runs as a **personal** challenge in the Challenges tab, tracked by auto-sync or manual entry. Only the employee can quit. HR cannot stop it, create plans, or modify them; admin visibility is a read-only ongoing-programs report. No completion certificate, unlike HR-run challenges. Enabled per company via account manager (select-partner).
- Content Library: articles, videos, podcasts, webinars, Health Bites (interactive 2 to 3 minute micro-lessons), and optional auto-evaluated quizzes (all-correct-to-pass; pass or fail both log `activity_id 1015`). Content-as-task is the through-line: "watch this video," "read this article," "complete bite-size content" are valid challenge tasks with automatic completion tracking.
- Targeting is by demographics (age, gender, health profile), never activity level. Content CRUD is admin self-serve once the Programs tab is enabled; Marketplace, Health Bites creation (API-only), multi-language versions, and demographic targeting are ops-required. Marketplace gets one brief mention. Lite Mode gets none of this by default.
- No AI claims anywhere: no AI pacing, no AI content recommendations (backlog, rule-based curation only). No proof stats exist for this page and none were invented. IBS challenge-task numbers were not used.

## Why this structure

Hero leads with the plan idea and the journey shot, a photograph, and a "starts next Monday" chip. A two-card split introduces the systems side by side with different chrome so they never blend. Training Plans gets the deeper section: plan grid with exact Available / Coming Soon badges, the three enrollment questions as a UI fragment, and the personal-challenge mechanics beside the challenge shot. Content Library gets a compact section: format chips, content-as-task callout, quizzes, targeting, admin self-serve, marketplace line. A gates band carries the tier flags. FAQ handles the HR-control objections. Done.

## Copy deck (as shipped)

- H1: "A plan, and the content to follow it."
- Lead: structured workplace wellness plans where a training plan runs as a personal challenge and content can be a challenge task.
- Sections: "Two systems. One Programs tab." / "Training Plans: a challenge of one." / "Content Library: the follow-through." / "Who controls what." / FAQ / final "Give the plan a place to live."
- Full copy is in the HTML; marketing copy is ~700 words outside nav, footer, and mock labels.

## Sources

- All mechanics, plan names and split, enrollment questions, tier flags, do-not-claim list: `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` (Personalized Programs card, platform guardrails, ownership split).
- "100+ organizations" approved aggregate, used once in the final band.
- No client proof used, per the facts lock.

## Meta drafts

- Title: `Structured workplace wellness plans | Vantage Fit`
- Description: `Vantage Fit's structured workplace wellness plans run as personal challenges employees own, backed by a corporate wellness content library of articles, videos, and Health Bites.`

## Critic result

Pass. Checked: exactly 2 Available and 7 Coming Soon, named as listed; Training Plans VFit-managed, admins cannot create, modify, stop, or disable them, stated plainly; employee-quit-only stated; no completion certificate; personal challenge contrasted with HR-run challenges; no AI pacing or AI recommendations; content targeting by demographics and health profile, never activity level; Health Bites completion logs activity_id 1015 with pass or fail both logging; Marketplace one brief mention; select-partner and ops gates stated in the gates band; the two systems visually separated with distinct card chrome; no IBS or borrowed stats; no Org Wellness Score; one product shot plus one photograph minimum met (two shots, one photo); no em-dashes, exclamation marks, or banned filler; copy under 750 words.
