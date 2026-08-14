# Audience Targeting

**URL:** `/features/audience-targeting/`  
**Mock:** `vantage-fit-audience-targeting-v1.html`  
**Angle:** Aim a challenge at the right people without seeing who they are.

## Page job

Prove HR can aim the same participation surface by country, city, department, gender, age, language, and health-risk code, and that a health-risk cohort returns a **count only**. Targeted challenges are private. Enrollment is admin-add or rule-enroll. Not a 27-task reprint. Not a Solutions page.

**Reader:** US enterprise HR / CHRO / Benefits.  
**Primary CTA:** Book a walkthrough. **Secondary:** See the count (hero), Compare the tiers (close).

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Dimensions (lock + OS challenges FAQ + help target-audience):** country, city, department, gender, age range, language, health-risk code (from HRA). **Activity level is not a dimension.** Help still tips “combine age and activity level.” Ignored.
- **Health-risk targeting (lock + Workforce Health spec):** returns a **count only**. UI disclaimer: *The list of users is not displayed to protect individual privacy.* Company-scoped. No export or screen exposes identities.
- **Risk codes / categories:** diabetes, heart, liver, kidney, thyroid, blood health, Vitamin D / B12 deficiency, inflammation. Not arbitrary biomarker thresholds (“high-cholesterol people specifically”).
- **Targeted challenges are automatically marked private.**
- **Enrollment (lock):** employees do not self-join. Admin adds by search or bulk CSV, or an audience rule matches and enrolls instantly. Legacy email-invite / accept still exists in code. Do not pitch invitations as the modern flow.
- **Late joiners (lock + help add/remove):** leaderboard score from join / add date forward. No retroactive credit or penalty.
- **Tier:** Standard / self-serve for country / city / department / gender / age / language. **Health-risk-code targeting depends on Workforce Health** (whitelist / premium). Frame as available only to Workforce-Health-enabled companies.
- **Self-join / browse-and-join / QR-code join:** Backlog. Not claimed.
- **Proof:** none assigned. No Tata / Wipro / IBS / Brazosport. No 100+ reuse on this page.

### Conflicts left unresolved (not silently fixed)

1. Help target-audience article treats HRA as the gate and mentions activity level. Lock: Workforce Health for health-risk targeting; activity level is not a dimension.
2. Help describes “Enroll when active” as a second auto-enroll mode. Lock: rule-enroll matches and enrolls instantly. Page follows lock.
3. Help / OS still document Org Wellness Score. Retired. Absent here.

## Why this structure

| Section | Job |
|---|---|
| Hero + photo + count-only overlay | First screen: you see a number, not a name list. |
| Seven dimension chips | Catalog without activity level. Categories, not thresholds. |
| Large HTML privacy mock + campaign shot | Prove the disclaimer and private-by-default. Campaign shot is supporting only. |
| Add vs rule-enroll + late joiners | Modern enrollment. Invite flow not pitched. |
| Workforce Health lock card | Gate is visible. |
| 3 FAQs + sibling links | Names, self-join, late joiners. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** same chrome as Admin Dashboard and Program Builder. Signature is the count-only mock, not KPI cards and not the 27-task palette.

## Copy deck

**Title:** Employee wellness program targeting | Vantage Fit  
**Meta:** Target a wellness challenge by country, department, age, gender, or health-risk count. The list of users is not displayed. Book a walkthrough.

**Eyebrow:** Features · For HR teams  
**H1:** Aim the challenge. Never see the names.  
**Lead:** Employee wellness program targeting uses country, city, department, gender, age, language, and health-risk code. A targeted challenge is marked private. Health-risk targeting returns a count only.  
**Hero notes:** 7 dimensions · Count only · Private by default  
**CTAs:** Book a walkthrough · See the count

**H2:** Seven filters. No activity level.  
List the seven. Health-risk is a code / category.

**H2:** A count. Not a roster.  
Disclaimer quoted. Challenge marked private. Campaign screenshot supporting.

**H2:** Add people, or write the rule.  
Search / CSV vs rule-enroll. Late joiners from the join date forward.

**FAQ**  
1. Can I see who is in a health-risk cohort?  
2. Do employees join themselves?  
3. What happens if someone is added late?

**Close H2:** Aim the same surface. Keep the names off the screen.

The 142-person count on the mock is labeled **illustrative**.

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md` page 10 + shared HR physics
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md` (dimensions, private; activity-level tip discarded)
- `vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-add-remove-participants.md` (search, CSV, late join)
- `vc-os/vfit-os/specs/product/02-challenges-gamification/challenges.md` (filters, private, late joiners)
- `vc-os/vfit-os/specs/product/03-health-wellness/workforce-health.md` (count-only disclaimer, categories, premium / whitelist)

## Assumptions

- Illustrative match count (142) is a mock label, not product data.
- Help’s “enroll when active” mode is not marketed.
- Email-invite exists in code and is mentioned only as not the modern flow, if at all. Safer: omit.
- Health-risk codes come from HRA but the **feature gate** is Workforce Health, per lock.

## Critic

Run after the mock. Failures found in draft and fixed:

- Activity level not listed or implied.
- No name list, no export of identities.
- Health-risk shown as count + exact disclaimer.
- Targeted = private, on the mock.
- Enrollment is admin-add or rule-enroll. Invite not pitched.
- Late joiners scored from join date.
- Workforce Health gate visible.
- No 27-task reprint. No Org Wellness Score. No client stats.
- No em-dashes or exclamation marks in copy.
- Photograph + campaign CDN shot + large HTML privacy mock.

**Pass.** Marketing copy in `<main>` is **459 words** outside nav, footer, and mock labels. Verified at 1440 and 390: count-only mock + disclaimer render, FAQ opens, sibling links resolve. Activity level appears only as “not a targeting dimension.”
