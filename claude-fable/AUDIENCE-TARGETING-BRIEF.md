# Audience Targeting — build brief

**Page:** `/features/audience-targeting/`
**Mock:** `claude-fable/vantage-fit-audience-targeting-v1.html`
**Group:** C, page 2 of 3 (For HR teams)
**Angle:** Aim a challenge at the right people without ever seeing who they are.

---

## Research takeaways

1. **The whole page rests on one screen that does not exist as a screenshot.** There is no targeting product shot in the approved CDN set, and the single most important thing a skeptical buyer needs to see is what the health-risk filter returns: a count and a privacy line, not a list. So the largest visual on this page is a built HTML mock of the Target Audience panel, drawn to the design system, with the real disclaimer copy in it.
2. **Seven dimensions, AND logic.** `admin-how-do-i-set-target-audience.md` confirms country, city, department, gender, age range, language and health risk code, combined with AND. That is the honest capability, and it is narrower than most vendors imply, so the page states it plainly rather than gesturing at "advanced segmentation."
3. **Filtering flips privacy automatically.** Apply any filter and the challenge is marked Private: non-matching employees never see it in the app or on the public listing. This is the detail that makes targeting feel safe rather than exclusionary, so it gets its own card next to the panel.
4. **Enrollment is admin-side, not employee-side.** Help documents two auto-enrollment modes, Enroll Immediately and Enroll When Active, plus direct add by search or CSV. The legacy email-invite and accept flow still exists in code but is effectively dead, so the page does not pitch invitations as the modern path.
5. **Late joiners are a scoring question, not a fairness problem.** Score counts from the join or add date forward. No retroactive credit, no penalty. Worth saying because it is the first objection a program manager raises.

## Conflicts flagged (facts lock preferred)

- **"Activity level" appears in help** (`admin-how-do-i-set-target-audience.md` best-practice section suggests combining age and activity level, and targeting employees with "low activity levels"). It is **not** a targeting dimension. The page names seven dimensions and no others.
- **Help implies biomarker-level aiming** ("target employees with high stress risk"). Targeting is by health risk **code or category**, not by an arbitrary threshold. The page says codes and names the categories generically.
- **Health-risk targeting availability.** Help says HRA must be enabled. The facts lock scopes this to **Workforce Health** as a whitelist or premium capability. The page uses the lock's framing and marks the dimension gated.

## Why this structure

Five content sections. Deliberately the shortest of the three pages, because the capability is narrow and the honesty is the product:

| Section | Job |
|---|---|
| Hero | State the trade the page exists to prove: aim it, do not see it. Photograph plus a small count-only card. |
| Seven dimensions | The complete list, as a filter panel, so a buyer can check for what is missing. |
| Count only | The large privacy mock. The health-risk filter with the real disclaimer, beside a plain do/does-not list. |
| Enrollment | Auto-enroll modes, direct add, and late-joiner scoring. Campaign screenshot as supporting evidence. |
| Gates | What is self-serve, what depends on Workforce Health. |

No KPI cards, no task catalogue, no email list. Builder's 27 task types and Comms' 29 templates are not reprinted. The word "audience" appears on Program Builder only as a setup field, which is where the lock puts it.

## Copy deck

- **Eyebrow:** Features · For HR teams
- **H1:** Aim a challenge at the right people. Without seeing who they are.
- **Lead:** Employee wellness program targeting runs on seven attributes you already hold in the HRIS, plus one you never get to read.
- **CTAs:** Book a walkthrough (primary) · See the privacy panel (secondary)
- **Section heads:** "Seven dimensions. All of them AND." · "The health-risk filter returns a number." · "Nobody joins a targeted challenge by browsing." · "What targeting needs on your plan."
- **Closer:** Bring your org chart. We will aim a challenge at it.

## Proof used

**None.** The facts lock assigns no client statistic to this page and forbids borrowing Tata, Wipro, IBS or Brazosport. Where a number would normally go, the page uses the product's own behaviour instead: a count, a disclaimer, two enrollment modes. The one figure shown in the mock is labelled illustrative. `100+ organizations` is used on Program Builder only and is not repeated here.

## Images

| Asset | Placement | Type |
|---|---|---|
| Count-only Target Audience panel (built HTML, not a screenshot) | Privacy section, largest visual | Product mock |
| `vantage-fit-campaign-management-dashboard-desktop.png` (CDN) | Enrollment section, supporting | Product screenshot |
| `../styled-homepage/card-measure-generic.jpg` | Hero | Photograph |
| `../styled-homepage/card-invite.jpg` | Enrollment section | Photograph |
| `../styled-homepage/logo.png` / `logo-white.png` | Nav, footer | Wordmark (does not count) |

No name list, no HRA answers, no lab values, no mood answers appear anywhere on the page, including inside mocks. The health-risk mock shows categories and a count, never a person.

## Meta

- **Title:** Employee wellness program targeting | Vantage Fit
- **Description:** Target a wellness challenge by country, city, department, gender, age, language or health-risk code. Health-risk targeting returns a count, never a name list.
- **Primary keyword:** employee wellness program targeting (H1 area, title, opener)
- **Secondary:** wellness challenge audience segmentation
- Thin-volume page. Supporting, not an SEO driver, so no keyword stuffing and no FAQ schema bloat.

## Critic pass

| Check | Result |
|---|---|
| Activity level used as a dimension | Not present. Seven dimensions named, nothing else |
| Health-risk cohort shown as a name list | No. Count plus the disclaimer, verbatim |
| Identities implied as exportable | Explicitly ruled out in the does-not column |
| Targeting below risk-code granularity | Categories only. No biomarker thresholds |
| Targeted challenges described as private | Stated in the hero note and its own card |
| Email invite pitched as the modern flow | No. Auto-enroll and direct add. Invitations not mentioned as current practice |
| Self-join, browse-and-join, QR join | Not claimed. Section head says nobody joins by browsing |
| Late-joiner scoring | From join date forward, no retroactive credit or penalty |
| Workforce Health gate on health-risk targeting | Stated in the dimension panel and the gates section |
| Org Wellness Score | Not present |
| 27 task types or 29 email templates reprinted | No. Cross-linked instead |
| HIPAA, SOC2, ISO, GDPR claimed | No. Privacy claims are product behaviour only |
| `../styles/enterprise.css` linked | Yes. No new tokens, brand face or primary colour |
| Product mock + photograph | Large count-only mock, one campaign screenshot, two photographs |
| Client stats borrowed | None used |
| Em-dashes, exclamation marks, "Learn more" | None |
| Marketing word count outside chrome | 574, excluding labels inside the drawn targeting panel |
| Links up and laterally | `/features/`, Program builder, Communications & nudges, Admin dashboard |

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md` (facts lock, page 10)
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md`
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-add-remove-participants.md`
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-a-challenge.md` (Step 5, Target Audience)
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-manage-challenge.md` (participants, CSV, late joiners)
- `vc-os/vfit-os/specs/02-challenges-gamification/`
