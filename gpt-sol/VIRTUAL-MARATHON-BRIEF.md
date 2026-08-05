# Virtual Marathon solutions page brief

## Page objective

- **Subject:** Vantage Fit virtual marathon programs for employees.
- **Primary audience:** US enterprise HR, benefits, wellbeing, and program leaders. Program managers are the secondary audience.
- **Single job:** Help an HR buyer choose the correct marathon format, then make a demo feel like the natural next step.
- **Primary CTA:** Book a demo.
- **Secondary CTA:** See pricing.
- **Live URL context:** `https://www.vantagefit.io/virtual-marathon/`

"Virtual marathon" is the buyer-facing program category. Product research shows two delivery mechanics:

1. **E-Marathon:** a self-serve step challenge. Synced steps convert into cumulative distance over a chosen date range. HR sets a target distance and km or miles.
2. **Marathon Event:** an account-team configured, single-day format. Employees complete GPS-tracked distance in run, cycle, or wheelchair modes, choose from distance tiers, and receive points scaled to the chosen tier.

This distinction corrects the current page's one-day-only framing without hiding the event it is known for.

## Product research takeaways

| Product truth | Page implication |
|---|---|
| E-Marathon is self-serve, converts synced steps to distance, and supports a target plus km/mile unit. | Lead with a flexible, no-GPS route option the current page omits. |
| Marathon Event is separate, exactly one day, GPS-based, tiered, and account-team configured. | Label setup ownership and avoid calling it a self-serve E-Marathon. |
| HR can target or upload participants, notify them, inspect leaderboards, filter results, and export CSV. | Show a real admin workflow instead of an abstract event pitch. |
| One primary step source prevents double-counting; GPS pace and vehicle checks protect event results. | Answer fairness with product behavior. |
| Employees can opt out of individual rankings and continue participating. | Make competition visibly optional. |
| Branded completion certificates are supported. | Use recognition as the final employee benefit, not an invented reward claim. |

### Source reconciliation: E-Marathon vs one-day Marathon Event

One help article calls the one-day option a special E-Marathon. Dashboard and code-verified OS sources instead define E-Marathon as the self-serve step format and Marathon Event as a separate operations-configured GPS format. This page follows the code-grounded distinction: **Virtual marathon** is the umbrella, **E-Marathon** is the step format, and **Marathon Event** is the one-day GPS format. The help article informs event strategy only; its unsourced benchmark ranges are excluded. Exact paths are in the source map.

## Page narrative and information architecture

1. **Hero:** Inclusive promise plus a product-real view of both paths converging.
2. **Format decision:** Accessible tabs compare setup, duration, input, and participant view.
3. **Employee experience:** Step conversion, GPS tracking, progress, rankings, and choice.
4. **HR workflow:** Configure, target, notify, inspect, and export.
5. **Data confidence:** Step-source, GPS integrity, privacy, and reporting controls.
6. **Named proof:** One sourced Rajagiri result.
7. **FAQ and closer:** Resolve rollout objections, then ask for the demo.

## Design plan

### Token system

The page inherits the enterprise system from `styles/enterprise.css` and the product/UI rhythm of `styled-homepage/index.html` and `consolidated/vantage-fit-steps-challenge-consolidated.html`.

- **Midnight ink:** `#29294C` for primary text and product UI.
- **Course dark:** `#1D2228` for the route stage, proof band, and closer.
- **Vantage coral:** `#F15162` for primary actions and the E-Marathon path.
- **Progress mint:** `#41D8B4` for completion, GPS validation, and the Marathon Event path.
- **Canvas:** `#F8F8F9` for page background.
- **Paper:** `#FFFFFF` for product panels and cards.

Typography stays brand-consistent:

- **Display and body:** Noto Sans, with compact line-height and strong weight contrast.
- **Course data and utility labels:** the system monospace stack, used only for km, time, status, and route markers.

### Layout concept

The desktop page alternates wide white canvases and focused dark product stages. Mobile collapses to one column without changing reading order.

```text
+---------------------------------------------------------------+
| NAV                                                           |
+------------------------------+--------------------------------+
| GIVE EVERY EMPLOYEE          | employee phone + HR result      |
| A FINISH LINE                | two route lines -> one finish    |
| CTAs                         | illustrative product UI          |
+------------------------------+--------------------------------+
| ONE FINISH LINE, TWO WAYS TO RUN IT                            |
| [E-Marathon tab] [Marathon Event tab] | product config panel   |
+---------------------------------------------------------------+
| PARTICIPANT STORY              | phone progress / leaderboard   |
+---------------------------------------------------------------+
| HR WORKFLOW 1 -> 2 -> 3 -> 4  | admin manage view              |
+---------------------------------------------------------------+
| DATA CONFIDENCE: source | GPS | privacy | export               |
+---------------------------------------------------------------+
| RAJAGIRI PROOF | FAQ | FINAL CTA | FOOTER                      |
+---------------------------------------------------------------+
```

### Signature element

The memorable element is a **paired course map**: a coral steps path and mint GPS path start separately, pass product-specific checkpoints, and converge at a single checkered finish marker. It embodies the true product distinction and the buyer-facing promise in one visual device.

Motion is spent once. A small route tracer moves along the hero course on capable devices. Reduced-motion users see the completed static route.

## Design critique and revision

### What was rejected

- **A giant 42.2 headline:** visually easy, but it implies every employee must complete a full marathon and turns inclusion into an afterthought.
- **A race-poster hero:** energetic, but it could advertise any event vendor and would conceal the product/admin experience.
- **One generic "virtual marathon" feature list:** repeats the current page's central ambiguity and risks presenting an account-team configured event as self-serve.
- **A full analytics section filled with sample percentages:** visually impressive but easy to mistake for customer outcomes.

### What changed

- Distance markers appear only inside clearly labelled product views.
- The two formats are named before benefits and carry explicit **Admin self-serve** and **Account-team setup** labels.
- Product UI links participant progress to HR control. It is labelled **Illustrative product view** wherever sample values appear.
- A compact, named Rajagiri result supplies proof. No unsourced benchmark ranges or invented outcomes appear.
- Trust is a short operational band, not generic compliance filler.

The result is specific to virtual marathons while remaining visually aligned with the Vantage Fit enterprise system.

## Full copy deck

### Navigation

- Product
- Solutions
- Resources
- Pricing
- Book a demo

### Hero

**Eyebrow:** Virtual marathon challenges

**H1:** Give every employee a finish line.

**Body:** Run a step-powered distance challenge over days, or create a one-day GPS event with target tiers. Vantage Fit brings every route into one visible program HR can manage and report.

**Primary CTA:** Book a demo

**Secondary CTA:** See pricing

**Support points:**

- Step or GPS formats
- Phone-first participation
- Exportable results

**Product visual labels:**

- Extended E-Marathon
- Everyday steps, converted to distance
- One-day Marathon Event
- GPS distance with target tiers
- One shared finish
- Employee progress
- 31.8 km
- of 42.2 km target
- Company leaderboard
- HR program view
- Participants selected
- Notification ready
- CSV export available
- Illustrative product view

### Format decision

**Eyebrow:** Choose the right course

**H2:** One finish line. Two ways to run it.

**Body:** Start with the behavior you want, then choose the format that measures it accurately.

#### Tab 1: E-Marathon

**Badge:** Admin self-serve

**Heading:** Make everyday steps feel like distance.

**Body:** Set a finish-line target, choose km or miles, and let synced steps accumulate across the challenge window. Employees do not need to record a GPS route.

**Details:**

- **Best for:** A flexible campaign across days or weeks
- **Activity input:** Synced daily steps
- **HR configures:** Dates, audience, target distance, unit, and reward
- **Employees see:** Cumulative distance and leaderboard rank

**Visual fields:**

- E-Marathon configuration
- Target distance: 42.2
- Unit: km
- Conversion: 1,000 steps = 1 km
- Audience: Selected employees
- Review challenge

#### Tab 2: Marathon Event

**Badge:** Account-team setup

**Heading:** Turn one day into a company-wide event.

**Body:** Create one shared calendar moment with GPS-tracked distance, multiple target tiers, and run, cycle, or wheelchair modes.

**Details:**

- **Best for:** A wellness day, launch, anniversary, or finale
- **Activity input:** Validated GPS distance
- **Account team configures:** One event date, activity modes, distance tiers, and scaled points
- **Employees see:** Their chosen distance, time, completion, and rank

**Visual fields:**

- Marathon Event
- One event day
- Choose a distance
- 5K, 10K, 21.1K, 42.2K
- Run, cycle, wheelchair
- Account-team configured

**Inline CTA:** Help me choose a format

### Employee experience

**Eyebrow:** Built for participation

**H2:** Make distance feel close enough to chase.

**Body:** Progress stays concrete, whether it comes from ordinary steps or a GPS event route.

**Cards:**

1. **Count the movement people already make.** E-Marathon turns synced phone or wearable steps into distance without asking employees to record a route.
2. **Show the next marker.** Employees can see total distance, rank, and time remaining from the challenge view.
3. **Keep competition optional.** An employee can hide from individual rankings and continue participating.
4. **Recognize the finish.** Completion certificates can carry your logo, signer, seal, and message.

**Phone visual:**

- Company E-Marathon
- Your progress
- 31.8 km
- 75% of target
- 10.4 km to finish
- #14 company rank
- 6 days left
- Synced today
- Illustrative product view

### HR workflow

**Eyebrow:** Control for HR

**H2:** Run the program, not the spreadsheet.

**Body:** E-Marathon follows one admin flow. Marathon Event setup happens with your account team, then HR manages participation and results from Vantage Fit.

**Steps:**

1. **Set the challenge.** Name the event, choose dates, add the story, and select your program image.
2. **Choose the audience.** Select employees with filters, add people directly, or upload a CSV.
3. **Keep the field moving.** Manage participants and send challenge-specific notifications from the dashboard.
4. **Close with a record.** View rankings, search and filter results, then export the leaderboard to CSV.

**Admin visual:**

- Manage challenge
- Company E-Marathon
- Ongoing
- Participants
- Leaderboard
- Notify participants
- Export CSV
- Search employees
- Department filter
- Rank, employee, distance
- Illustrative product view

### Data confidence

**Eyebrow:** Results people can trust

**H2:** Keep the finish fair and the reporting clear.

**Items:**

- **One step source:** Vantage Fit uses one primary device at a time to avoid double-counting.
- **Validated GPS:** Implausible pace and vehicle-like movement can be flagged and excluded.
- **Leaderboard choice:** Employees can opt out of individual rankings without leaving the challenge.
- **Exportable record:** HR can filter leaderboard results and download a CSV for review and recognition.

### Customer proof

**Eyebrow:** A global finish line, already proven

**Heading:** Rajagiri brought more than 5,000 participants into a 15-day e-Marathon.

**Body:** The program paired a 21.1 km Fit Run with a 42.2 km Challenge Run and reported more than a 15% increase in wellness participation between phases.

**Stat labels:**

- 5,000+ global participants
- 15-day program
- 15%+ participation increase

**Link:** Read the Rajagiri story

### FAQ

**Eyebrow:** Questions before rollout

**H2:** Choose the course with confidence.

**Q: What is the difference between E-Marathon and Marathon Event?**

A: E-Marathon is a self-serve challenge that converts synced steps into cumulative distance over a date range. Marathon Event is a separate, account-team configured format for one day, with GPS distance, multiple target tiers, and run, cycle, or wheelchair modes.

**Q: Do employees need a fitness tracker?**

A: No tracker is required for E-Marathon. A supported phone step source can provide the steps, and employees may also use connected devices. Marathon Event uses the Vantage Fit phone app to record a GPS workout.

**Q: Can employees participate without appearing on the leaderboard?**

A: Yes. Employees can hide themselves from individual rankings while their activities and challenge progress continue to count.

**Q: What can HR report after the challenge?**

A: HR can view challenge rankings, search and filter participants, and export leaderboard data to CSV. Available columns include participant, department, score or steps, rank, and team where applicable.

### Final CTA

**Eyebrow:** Pick the date. Set the distance.

**H2:** Build a virtual marathon your workforce can finish together.

**Body:** Bring your audience, timing, and participation goal. We will help you choose the right format and show the employee and HR experience end to end.

**Primary CTA:** Book a demo

**Secondary CTA:** See pricing

**Support points:**

- Format recommendation
- Employee app walkthrough
- Admin reporting
- Rollout planning

## Proof and claims used

The only customer outcome used on-page is from the Rajagiri case study:

- More than 5,000 global participants.
- 15-day e-Marathon.
- More than 15% increase in wellness participation between Fit Run and Challenge Run.

Source: `../../../vantagefit-astro/content/en/casestudy/rajagiri-e-marathon.md`

The page does **not** use the unsourced "typical participation" and "average completion" ranges in `../../../vantagefit-astro/content/en/help/admin/challenges/admin-when-to-use-a-one-day-virtual-marathon.md`.

All numbers in product mockups are labelled illustrative.

## Meta drafts

**Meta title:** Virtual Marathon for Employees | Vantage Fit

**Meta description:** Run an employee virtual marathon with step-to-distance or a one-day GPS event. Manage audiences, progress, leaderboards, notifications, and reports.

**Suggested H1:** Give every employee a finish line.

## Accessibility and responsive notes

- Semantic `nav`, `main`, `section`, headings, `details`, and `footer` landmarks.
- Skip link targets main content.
- All CTAs are real anchors with visible keyboard focus.
- Format selector uses buttons with tab semantics, keyboard arrow navigation, and an adjacent non-JavaScript fallback message.
- Product visuals are coded interface illustrations and include text equivalents in the surrounding copy. Decorative SVGs are hidden from assistive technology.
- Mobile order preserves the narrative: copy before visual, selector before selected panel, workflow before dashboard.
- Motion is limited to the hero route tracer and small UI transitions, all disabled under `prefers-reduced-motion`.
- Color is never the only carrier of format or status. Every path, badge, and state also has a text label.

## Local source map

Paths below are resolved from the model worktree repo root.

### Marketing and help docs

- E-Marathon behavior and setup: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-e-marathon.md`
- Employee E-Marathon experience: `../../../vantagefit-astro/content/en/help/employee/challenges/what-is-an-e-marathon.md`
- One-day program strategy and the noted terminology conflict: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-when-to-use-a-one-day-virtual-marathon.md`
- Step syncing: `../../../vantagefit-astro/content/en/help/employee/getting-started/how-does-step-syncing-work.md`
- One primary step device: `../../../vantagefit-astro/content/en/help/employee/getting-started/can-i-connect-multiple-devices.md`
- GPS tracking and integrity checks: `../../../vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-track-a-gps-workout.md`
- Leaderboard privacy: `../../../vantagefit-astro/content/en/help/employee/challenges/can-i-opt-out-of-leaderboard.md`
- HR leaderboard views and export: `../../../vantagefit-astro/content/en/help/admin/reports/admin-how-do-i-view-leaderboard.md`
- Participant management: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-add-remove-participants.md`
- Challenge notifications: `../../../vantagefit-astro/content/en/help/admin/communication/admin-how-do-i-send-notifications.md`
- Completion certificates: `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-configure-certificates.md`
- Rajagiri proof: `../../../vantagefit-astro/content/en/casestudy/rajagiri-e-marathon.md`
- Historical live-page copy, used only to identify gaps: `../../../vantagefit-astro/content/en/pages/use-cases/virtual-marathon.yaml`

### HR admin dashboard

- Code-grounded five-format wizard and E-Marathon configuration: `../../../vc-dashboard-design/docs/superpowers/specs/2026-07-19-create-challenge-wizard-redesign-PROMPT.md`
- Admin challenge labels and live-ground-truth terminology: `../../../vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md`
- Challenge management fields and divergent format behavior: `../../../vc-dashboard-design/CRUD_FLOWS_AND_COMPONENTS.md`

### Vantage Fit OS

- One-day Marathon Event behavior: `../../../vc-os/vfit-os/specs/02-challenges-gamification/challenge-marathon.md`
- Leaderboards, opt-out, suspicious activity, and exports: `../../../vc-os/vfit-os/specs/02-challenges-gamification/leaderboards.md`
- Admin management and reporting: `../../../vc-os/vfit-os/specs/product/09-admin-platform/admin-dashboard.md`
- Code-verified self-serve vs operations-configured format split: `../../../vc-os/vfit-os/audit/site-refresh-2026-07/product-code-specs.md`

### Visual system

- Enterprise tokens and reusable components: `styles/enterprise.css`
- Homepage nav, spacing, product UI, and footer: `styled-homepage/index.html`
- Steps quality bar: `consolidated/vantage-fit-steps-challenge-consolidated.html`
- Steps structure decisions and guardrails: `consolidated/STEPS-CHALLENGE-DECISIONS.md`
