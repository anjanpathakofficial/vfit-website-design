# Audience Targeting — brief

**Slug:** `/features/audience-targeting/` · **Mock:** `vantage-fit-audience-targeting-v1.html` · **Angle:** aim a challenge at the right people without seeing who they are.

## Meta

- Title: `Employee wellness program targeting | Vantage Fit`
- Description: `Target wellness challenges by country, city, department, gender, age, language, and health-risk code. Health-risk targeting returns a count, never a list of names.`
- Primary keyword: employee wellness program targeting. Secondary: wellness challenge audience segmentation. Thin-volume supporting page; keywords in title, H1 area, one body line.

## Research takeaways (facts lock)

- Dimensions: country, city, department, gender, age range, language, health-risk code (from HRA). Activity level is not a dimension, anywhere.
- Health-risk targeting returns a count only, with the in-product disclaimer: "The list of users is not displayed to protect individual privacy." Risk codes are categories (diabetes, heart, liver, kidney, thyroid, blood health, Vitamin D / B12 deficiency, inflammation), not arbitrary biomarker thresholds.
- Targeted challenges are automatically marked private.
- Enrollment: employees do not self-join. Admin adds directly (search or bulk CSV), or audience rules auto-enroll on match, instantly. The legacy email-invite / accept flow is effectively dead; do not pitch it.
- Late joiners score from join / add date forward. No retroactive credit or penalty.
- Health-risk targeting depends on Workforce Health (whitelist / premium). Other six dimensions are standard and self-serve.
- No targeting-specific client stat exists. Proof is qualitative; the count-only mock carries the page.

## Structure (why)

Hero with the count-only privacy mock as the hero visual (the one thing no generic vendor can show) → seven dimensions as chips with the Workforce Health flag → privacy section (count only, private by default) with the campaign console shot as supporting proof → enrollment mechanics (admin-add / rule-enroll / late joiners) with a workplace photograph → FAQ → siblings → final CTA. No 27-task reprint; builder is cross-linked for "when you create a challenge."

## Copy deck (compressed)

- H1: `Aim at the right people. Never see who they are.` Lead: scope any challenge by the six standard dimensions, plus health-risk codes with Workforce Health, and the match comes back as a count.
- Section 2: `Seven dimensions. One of them answers with a number.` Chips for all seven; health-risk chip flagged Workforce Health.
- Section 3: `Health-risk targeting is a count, not a list.` Enlarged mock fragment with the verbatim disclaimer; risk-code examples; private-by-default line; campaign console shot.
- Section 4: `Enrollment is admin work, not an invitation.` Admin-add (search, bulk CSV), audience rules (match and enroll instantly), late-joiner scoring from join date forward. Photograph.
- FAQ (3): activity level (no), health-risk identities (count only), self-join (no).

## Images

- HTML count-only privacy mock (hero + enlarged in section 3). No dedicated targeting screenshot exists; the mock is the assigned proof vehicle.
- CDN: campaign-management-dashboard desktop (supporting only).
- Photo: `../styled-homepage/card-participate.jpg` (enrollment section).
- Logos: `../styled-homepage/logo.png`, `logo-white.png`.

## Proof

None assigned. Count "1,284 employees match" in the mock is labeled illustrative. No Tata / Wipro / IBS / Brazosport figures.

## Sources

`FEATURES-HR-REMAINING-BRIEFS.md` (facts lock), `FEATURES-HR-REMAINING-PROMPT.md`, grok Admin Dashboard mock for chrome and density.

## Critic result

Checked against the critic list: no activity-level targeting (the FAQ names it only to rule it out), health-risk shown as count only with the verbatim disclaimer, no name lists or implied export, private-by-default stated, admin-add / rule-enroll only (no invite flow pitched), late-joiner scoring stated, Workforce Health gate stated, no borrowed client stats, no em-dashes or exclamation marks, links `../styles/enterprise.css`, privacy mock + campaign shot + photograph all present, copy inside 450–750 words.
