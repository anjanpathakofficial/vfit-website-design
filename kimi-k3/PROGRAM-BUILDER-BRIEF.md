# Program Builder & Templates — brief

**Slug:** `/features/program-builder/` · **Mock:** `vantage-fit-program-builder-v1.html` · **Angle:** a challenge live before lunch.

## Meta

- Title: `Wellness challenge builder and templates | Vantage Fit`
- Description: `Five self-serve challenge formats, 27 task types, and journey templates like Backpacking through Europe. Launch a corporate wellness challenge before lunch.`
- Primary keyword: wellness challenge builder. Secondary: corporate wellness program builder. Used honestly in title, H1 lead area, and one body line. No stuffing.

## Research takeaways (facts lock)

- 5 self-serve formats in the wizard: Custom (multi-week, weekly themes, drag-and-drop task config, the only format with drag-and-drop), Race (simple steps), Journey (milestone map), Streak (daily targets), E-Marathon (steps to distance, default 1,000 steps = 1 km).
- 27 task types, stated count, not recomputed. Named examples come straight from the facts lock. Mood is a loggable task but stays private to the employee; HR sees counts, never answers.
- Journey templates: 2+ built-in. Only Europe (9 stations, 70,000 cumulative steps, ≈ 50 km illustrative) and 7 Wonders (7 landmarks, 50,000 steps) are named. Spec says 3 built-in; third is unnamed, so page says 2+ and names two.
- Shared setup: name, description, image, dates, privacy, target audience, team config, points, certificates. Team score is the average of member scores, not a sum.
- Lifecycle: 6 states (NOT_PROCESSED, NOT_STARTED, STARTED, ENDED, MANUALLY_STOPPED, PURGED), automated start and end, admin override (reschedule, force-start-today, end-today-no-points). No calendar UI; date fields only.
- Certificates configurable per challenge: logo, seal, signature image, signer name and designation, custom description.
- Lite Mode = Race + step_count only, deployable in 1–2 days, for one-time campaigns and strict data-privacy clients.
- Gates, stated plainly: monetary/point rewards are account-manager gated and live for 1 company today. Custom Journey template design is select-partner (annual + order value + designer + setup call). Level, Marathon Event, Weight Burn, and Training Plans are ops-configured, not in this wizard. No wearable required for any format.

## Structure (why)

Hero → formats + task chips → templates with campaign console shot → setup and lifecycle → gated/ops panel with Lite Mode → FAQ → siblings → final CTA. Formats and the 27-task chip list carry the density; gates get their own hatched panel (same treatment as Admin Dashboard locks) so they are visible, not buried. Admin Dashboard owns KPI cards, so the hero fragment here is a format picker, not a dashboard.

## Copy deck (compressed)

- H1: `Launch a challenge before lunch.` Lead: the self-serve wizard line, one paragraph.
- Section 2: `Five formats. Twenty-seven tasks.` Five format cards + 25 named task chips (count stated as 27) + drag-and-drop Custom-only note + mood privacy note.
- Section 3: `Start from a template, not a blank page.` Europe and 7 Wonders cards, custom-template gate note, campaign console screenshot.
- Section 4: `The calendar runs itself.` Six-state pipeline fragment, override list, shared setup chips, certificates line, team-average line.
- Section 5: `What is gated, and what is not in this wizard.` Locks: monetary rewards (1 company), custom Journey design (select partner), Level / Marathon Event / Weight Burn / Training Plans (ops-only). Lite Mode card.
- FAQ (3): wearable, drag-and-drop scope, cash prizes.

## Images

- CDN: challenge-system-overview desktop (hero), campaign-management-dashboard desktop (templates section).
- Photo: `../styled-homepage/card-measure-generic.jpg` (setup/lifecycle split).
- Logos: `../styled-homepage/logo.png`, `logo-white.png`.

## Proof

Europe journey 70,000 steps ≈ 50 km, labeled illustrative. Wipro 3X skipped (not a builder KPI). 100+ organizations used once in the final band.

## Sources

`FEATURES-HR-REMAINING-BRIEFS.md` (facts lock, preferred over spec where it disagrees), `FEATURES-HR-REMAINING-PROMPT.md`, grok Admin Dashboard mock for chrome and density.

## Critic result

Checked against the prompt's critic list: no Org Wellness Score, no activity-level targeting, team score is an average, only 2 named Journey templates ("2+"), rewards gated to 1 company, no calendar UI, no Training Plans / Level / Marathon / Weight Burn as self-serve, no wearable requirement, no Health Connect, no em-dashes or exclamation marks, links `../styles/enterprise.css`, one product screenshot + one photograph minimum, copy inside 450–750 words.
