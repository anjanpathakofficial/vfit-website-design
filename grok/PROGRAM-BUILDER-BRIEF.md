# Program Builder & Templates

**URL:** `/features/program-builder/`  
**Mock:** `vantage-fit-program-builder-v1.html`  
**Angle:** A challenge live before lunch.

## Page job

Prove the self-serve wizard is real: five formats, 27 task types as a compact palette, 2+ named Journey templates, shared setup, six lifecycle states plus admin override. This is how HR launches the same participation surface Admin Dashboard already measures. Not a Solutions outcome page. Not a 27-task essay.

**Reader:** US enterprise HR / CHRO / Benefits. Secondary: the program manager who opens the wizard tomorrow.  
**Primary CTA:** Book a walkthrough. **Secondary:** See the formats (hero), Compare the tiers (close).

## Research takeaways

Preferred the facts lock when sources disagreed.

- **5 self-serve formats (lock + help + OS + dashboard):** Custom (multi-week, weekly themes, drag-and-drop task config), Race (step competition), Journey (milestones), Streak (daily-target streaks), E-Marathon (steps-to-distance, default 1,000 steps = 1 km). Help formats article matches.
- **Drag-and-drop is Custom only.** Other formats do not get that builder.
- **27 task types:** use the stated count. Lock list shown as chips. Mood may be a task. Answers stay private (not scored, not HR-visible).
- **Journey templates:** OS names **Backpacking through Europe** (9 stations, cumulative 70,000 steps ≈ 50 km, illustrative) and **Journey to 7 Wonders** (7 landmarks, 50,000 steps). Help and OS product FAQ say **3 built-in + custom** and name **Everest Run**. Lock: say **2+**, name only Europe and 7 Wonders. Page follows lock.
- **Custom Journey template:** annual + sufficient order value + designer + setup call.
- **Shared setup:** name, description, image, dates, privacy, target audience, team config, point rewards, certificates (logo, seal, signature image, signer name / designation, custom description). Audience is a field only. Aiming the cohort belongs on Targeting.
- **Lifecycle (lock + campaign-management.md):** NOT_PROCESSED, NOT_STARTED, STARTED, ENDED, MANUALLY_STOPPED, PURGED. Automated start / end. Overrides: reschedule, force-start-today, end-today-no-points. Date fields, not a calendar UI.
- **Lite Mode:** Race + `step_count` only. Deployable in 1 to 2 days. One-time campaigns and strict data-privacy clients.
- **Point / monetary rewards:** account-manager-gated. Live for **1 company** today.
- **Team score:** average of member scores, not the sum. User-team creation / management is an ops toggle, off by default.
- **Not in this wizard:** Level, Marathon Event, Weight Burn, Training Plans, custom scoring. Group B owns Training Plans.
- **Wearable:** not required for any format. Android task-sync vendor omitted (live contradiction).
- **Proof:** Europe 70,000 ≈ 50 km labeled illustrative. Wipro 3X omitted (three 2025 challenges, not a builder KPI). 100+ organizations used once, lightly, on the close.

### Conflicts left unresolved (not silently fixed)

1. Journey template count: help / OS product FAQ say 3 (incl. Everest Run). Lock: 2+, name Europe and 7 Wonders.
2. Help Overview and OS still describe Org Wellness Score as live. Retired. Not on this page.
3. Help targeting article still mentions activity level in a tip. Not a dimension. Not on this page.
4. OS challenge-system-overview status set is shorter (NOT_STARTED / STARTED / COMPLETED). Campaign-management 6-state set matches the lock.

## Why this structure

No required spine. Folded must-cover into UI, not one section per bullet.

| Section | Job |
|---|---|
| Hero + photo + format-picker fragment | First screen: this is the wizard, not the KPI console. Photograph + HTML fragment. |
| Five format cards + 27-task palette + CDN overview shot | Prove the catalog without an essay. Drag-and-drop labeled Custom only. |
| Two named journeys + shared setup + campaign shot | Templates and the fields every format shares. Certificates folded into setup. |
| Lifecycle strip + Lite / rewards / team gates | Six states, overrides, no calendar. Tier flags visible. |
| 3 FAQs + sibling links | Teams, wearable, ops-only formats. Lateral HR pages. |
| Close | Book a walkthrough / Compare the tiers. |

Skipped a customer-result band so the page stays a capability page. Did not clone Admin Dashboard KPI cards.

**Visual:** `../styles/enterprise.css`, Noto Sans, coral / ink / mint, homepage nav/footer chrome, `logo.png` / `logo-white.png`. Features → For HR updated to the locked IA. No SOC 2 / GDPR / ISO.

## Copy deck

**Title:** Wellness challenge builder and templates | Vantage Fit  
**Meta:** Launch a corporate wellness program with the Vantage Fit wellness challenge builder. Five formats, 27 task types, and 2+ journey templates. Book a walkthrough.

**Eyebrow:** Features · For HR teams  
**H1:** A wellness challenge builder that goes live before lunch.  
**Lead:** Pick Custom, Race, Journey, Streak, or E-Marathon. Shared setup covers audience, teams, points, and certificates. This is how HR launches the surface every employee log counts toward.  
**Hero notes:** 5 self-serve formats · 27 task types · 2+ journey templates  
**CTAs:** Book a walkthrough · See the formats

**H2:** Five formats. Twenty-seven tasks.  
Custom is the multi-week format. Drag-and-drop lives there only. Race, Journey, Streak, E-Marathon are simpler. Ops-only formats named so they are not implied.

**H2:** Two named journeys. One shared setup.  
Europe 70,000 / 7 Wonders 50,000. Shared fields listed once. Certificates as labels. Audience field points to Targeting.

**H2:** Six states. Admin override. No calendar.  
Six status names. Three override actions. Team score = average. Lite Mode. Rewards gated (1 company).

**FAQ**  
1. Can employees manage their own teams?  
2. Is a wearable required?  
3. Are Training Plans in this wizard?

**Close H2:** Launch the surface everything logs into.

Journey step totals and the format-picker fragment are labeled **illustrative** where they could be misread as client results.

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md` page 9 + shared HR physics
- `FEATURES-HR-BRIEFS.md` platform rules (Org Wellness Score retired, activity level not a dimension)
- `vantagefit-astro/content/en/help/admin/challenges/admin-what-challenge-formats.md`
- `vantagefit-astro/content/en/help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md`
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-journey-challenge.md` (3 templates named; lock wins)
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-configure-certificates.md`
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-use-templates.md`
- `vc-os/vfit-os/specs/02-challenges-gamification/challenge-journey.md`
- `vc-os/vfit-os/specs/02-challenges-gamification/campaign-management.md`
- `vc-os/vfit-os/specs/product/02-challenges-gamification/challenges.md`
- `vc-os/vfit-os/specs/product/09-admin-platform/admin-dashboard.md` (Create Challenge wizard list)
- `vc-dashboard-design/docs/superpowers/specs/2026-07-19-create-challenge-wizard-redesign-PROMPT.md` (recognizable wizard families)

## Assumptions

- Help’s third named Journey template (Everest Run) stays off the page per lock.
- Target audience is mentioned as a setup field only.
- Certificate output described as configurable, not re-litigated as PDF vs image (Admin Dashboard already shipped PDF).
- Wipro 3X left off.

## Critic

Run after the mock. Failures found in draft and fixed:

- Did not clone Overview KPI cards or Leadership Insights.
- Did not reprint a 27-task essay. Chips inside a Custom palette mock.
- Journey count is 2+. Only Europe and 7 Wonders named.
- Team score described as an average.
- Monetary / point rewards gated, 1 company.
- No calendar UI. Date fields + three override actions.
- Training Plans / Level / Marathon Event / Weight Burn labeled ops-only.
- Employees do not manage teams by default.
- No wearable required.
- Org Wellness Score absent.
- Activity level not used.
- No em-dashes or exclamation marks.
- `../styles/enterprise.css` linked. Photograph + two CDN product shots.

**Pass.** Marketing copy in `<main>` is **567 words** outside nav, footer, and mock labels (picker, chips, states). Visual peer: `vantage-fit-admin-dashboard-analytics-v1.html`. Verified at 1440 and 390: Noto Sans + coral tokens, images load, FAQ opens, sibling links resolve.
