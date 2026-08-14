# Program Builder & Templates — build brief

**Page:** `/features/program-builder/`
**Mock:** `claude-fable/vantage-fit-program-builder-v1.html`
**Group:** C, page 1 of 3 (For HR teams)
**Angle:** A challenge live before lunch.

---

## Research takeaways

1. **The wizard is the product here.** Help (`admin-how-do-i-create-a-challenge.md`) describes a seven-step flow: format → basic details → tasks → teams → audience → certificates and rewards → review and publish. That flow, not an essay about engagement, is what a buyer needs to recognise. The page is built around it.
2. **The 27 task types are the real differentiator, and they are nameable.** `admin-what-tasks-can-i-include-in-a-custom-challenge.md` groups them (movement, fitness logs, mind and focus, nutrition, health metrics, mood, content, habits and programs). Naming all 27 as a picker panel is both accurate and dense. It reads as a screen, not as prose.
3. **Formats split into "one fast one" and "one flexible one."** Race is the simplest publish; Custom is the only format with weekly themes and drag-and-drop task config. Journey, Streak and E-Marathon sit between. Help even tells first-time admins to start with Race. That asymmetry is more useful to a buyer than five equal cards, so the format rail leads with Custom and Race.
4. **Lifecycle is states plus overrides, not a calendar.** Six campaign states run automatically off the start and end dates; the admin gets reschedule, force start and force stop. There is no visual scheduling calendar in the product, so the page shows a state rail and an override row instead.
5. **Templates are the "before lunch" mechanism.** The template library sits beside the format picker with tasks, targets, scoring and weekly themes pre-set. Journey additionally ships built-in maps.

## Conflicts flagged (facts lock preferred)

- **Journey template count.** Help `admin-how-do-i-create-journey-challenge.md` states **3 built-in Journey templates** and names a third, "Everest Run." The facts lock permits only **Europe and 7 Wonders**, phrased as **"2+ built-in."** The page prints "Journey adds 2+ built-in maps" and names only those two. The third is unverified here.
- **"Activity level" appears in help.** `admin-how-do-i-set-target-audience.md` suggests combining "age and activity level." Activity level is not a targeting dimension. This page does not mention targeting dimensions at all beyond "target audience" as a setup field, which is Audience Targeting's territory.
- **Task-type count.** Help hedges ("over a dozen, depends on configuration"). The facts lock states 27 and says not to recompute. The page uses 27 and names 27.

## Why this structure

Six content sections, no problem-solution spine:

| Section | Job |
|---|---|
| Hero | Show the wizard itself. A drawn format picker with the step rail, so the first screen answers "what would I click." |
| Five formats | The self-serve set, with Custom's drag-and-drop scoped correctly, plus the challenge system screenshot. |
| 27 task types | The catalogue, drawn as a task picker panel rather than written out. Ties back to the participation surface. |
| Templates | Where "before lunch" is actually earned. Named Journey maps and the custom-map gate. |
| Shared setup + lifecycle | The fields every format shares, then the six states and the admin overrides, beside the campaign management screenshot. |
| Gates | Self-serve vs account manager vs ops, in one grid, so nothing is buried. |

Hero deliberately differs from Admin Dashboard: that page opens on a photograph with floating KPI cards, this one opens on a wizard fragment. No KPI cards are reprinted. Targeting dimensions and the email catalogue are left to their own pages.

## Copy deck

- **Eyebrow:** Features · For HR teams
- **H1:** The wellness challenge builder, live before lunch.
- **Lead:** Pick a format, drop in tasks, set dates and audience, publish. What employees log against it lands in the same participation rate you already report.
- **CTAs:** Book a walkthrough (primary) · See the formats (secondary)
- **Section heads:** "Five formats. One wizard." · "Twenty-seven task types. One score." · "Start from a shape that already works." · "The setup every format shares." · "Six states, plus your override." · "What you publish yourself, and what needs a call."
- **Closer:** Publish your first challenge on the call.

## Proof used

- **Backpacking through Europe: 9 stations, cumulative to 70,000 steps, roughly 50 km.** Labelled illustrative on the page, not a customer result.
- **100+ organizations**, once, in the closer strip. Not repeated on the other two pages in this set.
- Wipro 3X **not used**. It is cumulative across three 2025 challenges and would read as a Custom-format result here.
- No Tata, IBS or Brazosport figures.

## Images

| Asset | Placement | Type |
|---|---|---|
| `vantage-fit-challenge-system-overview-desktop.png` (CDN) | Formats section, full width | Product screenshot |
| `vantage-fit-campaign-management-dashboard-desktop.png` (CDN) | Lifecycle section | Product screenshot |
| `../styled-homepage/card-participate.jpg` | Templates section | Photograph |
| `../styled-homepage/logo.png` / `logo-white.png` | Nav, footer | Wordmark (does not count) |

Every `<img>` carries a descriptive `alt`. No health-risk name list, HRA answer or mood answer appears anywhere.

## Meta

- **Title:** Wellness challenge builder for HR teams | Vantage Fit
- **Description:** Launch a wellness challenge in five self-serve formats and 27 task types. Set audience, teams, points and certificates, then publish. Book a walkthrough.
- **Primary keyword:** wellness challenge builder (H1, title, opener)
- **Secondary:** corporate wellness program builder

## Critic pass

| Check | Result |
|---|---|
| Org Wellness Score shown or claimed | Not present |
| Third named Journey template | Only Europe and 7 Wonders. Copy says "two named maps" and "2+ built-in" |
| Team score described as a sum | Stated as the average of member scores |
| Monetary rewards implied freely on | Gated card: account manager, live for one company today |
| Visual scheduling calendar claimed | No calendar. State rail plus reschedule / force start / end today |
| Level, Marathon, Weight Burn, Training Plans as self-serve | Listed under ops-configured, explicitly not in this wizard |
| Employees manage own teams by default | Stated as off by default |
| Wearable required | Stated as not required, in FAQ |
| Activity level as targeting | Not mentioned |
| Health-risk names, HRA or mood answers on screen | Not present. Mood noted as private to the employee |
| Drag-and-drop scoped | Custom Challenge only, stated twice |
| `../styles/enterprise.css` linked | Yes. No new tokens, brand face or primary colour |
| Product screenshot + photograph | Two screenshots, one photograph |
| Em-dashes, exclamation marks, "Learn more" | None |
| Marketing word count outside chrome | 752, excluding labels inside the drawn wizard and task picker |
| Reads as a capability page, not Solutions | Wizard, catalogue, states and gates. No program outcome promised |
| Links up and laterally | `/features/`, Admin dashboard, Audience targeting, Communications & nudges |

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md` (facts lock, page 9)
- `vantagefit-astro/content/en/help/admin/challenges/`: create-a-challenge, what-challenge-formats, create-custom-challenge, create-journey-challenge, create-race-challenge, create-streak-challenge, create-e-marathon, use-templates, configure-certificates, manage-challenge, manage-teams, what-tasks-can-i-include-in-a-custom-challenge
- `vantagefit-astro/content/en/help/admin/settings/admin-what-is-lite-mode.md`
- `vc-os/vfit-os/specs/02-challenges-gamification/`
