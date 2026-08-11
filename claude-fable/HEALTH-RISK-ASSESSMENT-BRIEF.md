# Vantage Fit: Health Risk Assessment solutions page brief (v1)

**Page:** 2 of 6 in the Solutions set
**URL:** `/solutions/health-risk-assessment/`
**Archetype:** Program page, Section ② "data in"
**Mock to build:** `claude-fable/vantage-fit-health-risk-assessment-v1.html`
**Stylesheet:** `../styles/enterprise.css` and nothing else. Everything else is a page-local `<style>` block.
**Chrome:** paste nav, trust band shell, related shell, closer and footer from
`scratchpad/research/chrome.html`. Add `is-current` to the Solutions trigger and
`is-page` + `aria-current="page"` to the Health Risk Assessment mega-link.

---

## 1. Research takeaways that decided this page

Source shorthand:
`astro/` = `/Users/anjanpathak/work/gitcode/vantagefit-astro/`
`vfit-os/` = `/Users/anjanpathak/work/gitcode/vc-os/vfit-os/`
`dash/` = `/Users/anjanpathak/work/gitcode/vc-dashboard-design/`

### 1.1 The product facts that set the architecture

| # | Fact | Why it changed the page | Source | Status |
|---|---|---|---|---|
| T1 | The HRA is a **self-reported questionnaire in the mobile app**, reached from **Profile**. iOS and Android only. **No web and no admin-dashboard entry point.** | The assessment mock must be a phone. A desktop HRA form would be invented UI. | `astro/content/en/help/employee/health-tracking/what-is-hra.md`; `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` Platform Comparison | SHIPPED |
| T2 | It asks across **nine health areas**, with real input controls per factor (selection, cm, "120/80" string, yes/no, never/occasionally/frequently). Max **95 points** across the nine components. | Section 2 can be concrete instead of vague. The input controls are what make the mock believable. | `astro/.../what-is-hra.md`; `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` | SHIPPED |
| T3 | Result = a **fitness percentage from 0 to 100%**, a **category**, **personalized health suggestions**, and a component breakdown. Plus the in-doc line "The HRA is an informational tool, not a medical diagnosis." | Section 3 exists and has real content. The disclaimer is the medical-liability answer, quoted rather than paraphrased. | `astro/.../what-is-hra.md`; `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` | SHIPPED |
| T4 | Five bands: **Excellent 85%+ / Good 70 to 84% / Average 50 to 69% / Below Average 35 to 49% / Critical below 35%**, each with a verbatim meaning string. | Rendered as a 0 to 100 band scale, which is this page's second product-real visual. | `astro/.../what-is-hra.md` | SHIPPED |
| T5 | **There is no HRA cycle, campaign object or scheduler.** The HRA is always-on and employee-initiated. The only shipped way HR drives completion is a **Custom Challenge with the "Health Vitals (HRA)" task**, best used for "Risk stratification, baseline profiling at program launch". The docs' own recipe: **"Health-screening campaign = Lab Report Upload + Health Vitals (HRA) + Doctor Visit"**. | Killed the "set up an annual HRA cycle" section the suggested spine implied. Replaced with a four-step campaign that is actually shipped. This is the page's biggest honesty decision. | `astro/content/en/help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md`; `dash/docs/superpowers/specs/2026-08-09-wellness-admin-dashboard-IMPLEMENTATION.md` (cycles are DESIGN-INTENT) | SHIPPED / cycles DESIGN-INTENT |
| T6 | Admin CANNOT see, verbatim: **individual health data (weight, BMI, body measurements) · Health Risk Assessment details: individual answers and risk categories · Lab report results: biomarker values and health indicators · Personal tracking data: mood logs, food diary, sleep patterns.** Admin CAN see: aggregate metrics, challenge data, participation reports ("These are participation reports, not health reports"). | This is the firewall's right-hand panel, lifted near-verbatim. | `astro/content/en/help/admin/settings/admin-data-privacy-security.md` | SHIPPED |
| T7 | Health-risk **target-audience selection returns a count only**, with the literal on-screen disclaimer **"The list of users is not displayed to protect individual privacy."** No admin screen or export exposes one person's results. All queries are company-scoped. "See an individual's report: Admin Dashboard **No (by design)**." | The single strongest proof on the page, and the mechanism that makes "act on risk without seeing who" literally true. Gets the dark `.fairband` inset. | `vfit-os/specs/product/03-health-wellness/workforce-health.md:75-77, :97` | SHIPPED |
| T8 | Applying **any** audience filter automatically marks the challenge **Private**, invisible to non-matching employees. Enrollment is by rule (**Enroll Immediately** or **Enroll When Active**), never browse-and-join. | Second half of the count-only proof: the cohort cannot be inferred from the challenge listing either. | `astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md` | SHIPPED |
| T9 | The one nuance that must not be flattened: admins **do** get an employee-level **Wellness Score Report** with the four component sub-scores, exportable to CSV. The **Baseline component is derived from HRA data**, so an admin sees a number derived from health data. The guardrail is policy, not technical: "not for individual performance evaluation… not for HR decisions about specific employees." | The firewall states this out loud instead of hiding it. Hiding it is how this page would get killed in a security review. | `astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md`; `astro/content/en/help/admin/reports/admin-what-reports-are-available.md` | SHIPPED |
| T10 | **n = 5 cohort suppression, versioned consent, a 30-day erasure SLA and per-class retention windows are NOT SHIPPED.** The design repo's own note says the live module today runs on "a static, unversioned consent, a withdrawal form that dead-ends, and no erasure or retention path", and that "a right-to-erasure request literally cannot be honored today". The Governance tab sits in `parkedTabs`. | Produced the "What is shipped, and what is not" strip inside the firewall. Claiming any of these would be the fastest way to fail this page. | `dash/vc-data.js:1028, :1084-1100, :1494-1501`; `dash/docs/modules/wellness.md` | DESIGN-INTENT, do not claim |
| T11 | Retention, deletion and residency that **are** shipped: four isolated regions (**India, US, EU, UAE**), chosen at signup, permanent, no cross-region sharing; encryption at rest for sensitive fields and TLS in transit; CAPTCHA on sign-in and **OTP on sensitive actions**; **employee-initiated account deletion** (Profile > Delete Account, OTP, identity anonymized, activity preserved unlinked); **admins cannot delete an employee's account**; notifications deleted after 14 days; **custom terms and conditions** added per company. | Fills the trust band with sourced, specific facts instead of generic security copy. | `astro/content/en/help/admin/settings/admin-data-privacy-security.md`; `astro/content/en/help/employee/getting-started/what-is-data-privacy.md` | SHIPPED |
| T12 | **Lite Mode collects no health data at all.** HRA: No. Wellness Score: No. Lab Reports: No. | The answer for privacy-sensitive or unionized sites. Genuinely underused and it is a trust card. | `astro/content/en/help/admin/settings/admin-what-is-lite-mode.md:34-36` | SHIPPED |
| T13 | HRA is **Full Mode only** and is **enabled per company by the account manager** ("HRA (Health Risk Assessment): Enable the health assessment questionnaire"). Org Wellness Score is also account-manager provisioned, for annual clients, and needs **2 to 4 weeks of data collection** before the baseline is reliable. | Both gates are stated on the page rather than discovered in procurement. | `astro/content/en/help/admin/settings/admin-what-is-configurable.md:111`; `astro/content/en/help/admin/workforce-health/admin-what-is-org-wellness-score.md` | SHIPPED-GATED |
| T14 | HRA feeds the **Baseline component, 20%** of the Wellness Score. **Without an HRA the baseline defaults to 50.** | Answers "what if only some people complete it" with a mechanism instead of a promise. | `astro/.../what-is-hra.md`; `astro/content/en/help/admin/workforce-health/admin-what-is-org-wellness-score.md` | SHIPPED |
| T15 | The nine areas contain **no family medical history question and no genetic question**. Completion is voluntary. Results are not visible to the employer. | Directly relevant to the US legal reviewer, and statable as fact without a legal conclusion. | `astro/.../what-is-hra.md` question list | SHIPPED (fact), legal conclusion NOT sourced |

### 1.2 Conflicts hit, and which side this page took

| # | Conflict | Sides | Ruling used, and why |
|---|---|---|---|
| C1 | HRA bands: **5** vs **7** | `astro/.../what-is-hra.md` says Excellent / Good / Average / Below Average / Critical. `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` lists seven (adds Poor, Decent). | **Ship 5.** Precedence rule 1: help docs beat specs, and the dedicated HRA article beats a generic onboarding summary. Flagged for product in §9. |
| C2 | Wellness Score range: **0 to 100** vs **0 to ~108** | `astro/.../admin-what-is-org-wellness-score.md:13,:26` and `vfit-os/specs/product/09-admin-platform/admin-dashboard.md:55` say 0 to 100. Only `vfit-os/specs/product/02-challenges-gamification/leagues-wellness-score.md:46` says ~108. | **0 to 100.** Settled ruling G3, and the production audit shows the shipped calculator writes `scoring_version 'v1.1'` with the additive formula and no multiplier. Never 108, never the 1.1x multiplier. |
| C3 | HRA scoring internals: **"max 95 points across nine components"** vs Draft-spec **Metabolic 50 / Habits 30 / Exercise 20** | help doc vs `vfit-os/specs/03-health-wellness/health-risk-assessment.md` (Draft) | **Publish neither weighting as a formula.** The page says "nine health factors" and "a maximum of 95 points across the nine components", both help-doc sourced. |
| C4 | Lab-report insight granularity: **org-level only** vs **org + department + country** | `vfit-os/specs/product/03-health-wellness/workforce-health.md` vs `astro/.../admin-what-is-workforce-health.md` | **Org-level only.** Precedence rule 2 on what an admin can actually do. The page never promises department-level health-risk breakdowns. |
| C5 | HRA completion report: named in a spec Self-Serve table vs **absent from the help-doc report catalog** | `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` vs `astro/content/en/help/admin/reports/admin-what-reports-are-available.md` | **Do not draw it.** No named "HRA completion report" screen appears in any mock on this page. |
| C6 | Wellness Score component labels | Help-doc **Baseline / Participation / Activity / Adherence** vs production **Health Baselines / Participation / Activity Levels / Program Adherence** | Settled ruling G3: **help-doc names in prose and diagrams; production strings only inside the screenshot-accurate admin mock.** Both appear on this page, in exactly those two places. |
| C7 | `/solutions/` prefix vs the root-level rule in `vfit-os/.claude/rules/seo-conventions.md:69,83` | signed-off menu vs SEO conventions | **Follow the signed-off menu URL** `/solutions/health-risk-assessment/`. Flagged in §9, not silently resolved. |

### 1.3 Facts deliberately left on the cutting-room floor

- **"About 20% of employees complete it"** (`astro/.../what-is-hra.md`). Real, documented, and a sales liability. Not published. FAQ 5 answers the participation question with the mechanism instead.
- **The "42% of employees completed the HRA" example** (`astro/.../what-is-my-health.md`). A hypothetical inside a privacy explainer, not a measurement.
- **Time to complete and question count.** Genuinely unsourced. The page is designed so no section depends on either. Section 2 is built around the nine areas and their input controls, which need no duration claim.
- **Prenatal status** (Draft spec only). UNVERIFIED, not rendered.
- **Draft-spec internals**: the wellness formula, the 0.7 to 1.1 multiplier, participation thresholds, activity index divisors, the 30MB file cap, the five-stage extraction pipeline.
- **Every figure in `dash/vc-data.js`**: 1,120 assessed, 77% coverage, 72/28 split, the 2026/2025/2024 Annual HRA cycles, wellbeing dimension scores, modifiable-risk percentages. Seeded fiction for a fake tenant.
- **Production dummy fixtures**: Workforce Health Snapshot 82/18, Vitamin D 32%, Sleep Quality 28%, Stress Levels 22%, Industry Benchmark 74.
- **"Insights Hub"**. Nav commented out, all five sub-pages blank iframes. Not named, not drawn, not linked.
- **"HIPAA Compliant"**, the string the shipped Health Insights compliance card actually prints. Not reproduced anywhere on this page or in any mock.
- **OpenAI / ChatGPT** as the lab extraction engine. Deliberately kept out of customer docs.
- **Lab reports as a headline.** They appear once, as a qualified add-on in the rollout note, because the capability is premium and whitelist-gated. This page is about the questionnaire.

---

## 2. Strategy

### 2.1 The buyer

An **HR Director or Benefits Manager** who has been asked to "do something about health costs" and has landed on a health risk assessment as the starting point. Their two blockers are real and both are internal:

1. **Employees will not answer honestly** if they believe HR can read the answers. A dishonest HRA is worse than no HRA, because it produces a baseline that is confidently wrong.
2. **Legal or works council will not sign off** on a vendor collecting blood pressure, cholesterol and diabetes status from employees without an airtight, verifiable answer on what the employer can see.

Secondary reader: the **security or privacy reviewer** who will be handed this page as the first artifact. They are looking for one thing, which is whether the vendor over-claims.

### 2.2 The one thing this page must land

**The employer never sees the answers, and that is a property of the product, not a promise in a contract.**

Everything else on the page is in service of that. If the buyer leaves believing only this, the page has done its job, because it is the sentence they need to repeat to their legal reviewer and to their employees.

### 2.3 Why this section order

The suggested spine put the privacy firewall at position 4, after the assessment, the employee result, and before the HR view. That ordering is right, and the page keeps it, for one reason: **a firewall diagram is meaningless until the reader knows what is on each side of it.** Show the questionnaire, show the employee's result, then show what crosses and what does not. Moving the firewall to position 2 would force it to explain the assessment and the privacy model at the same time.

Three changes from the suggested spine, each deliberate:

**Change 1. "How a cycle runs" becomes "How a screening campaign runs", and moves after the HR section.**
There is no HRA cycle object in the shipped product (T5). Writing a "set up your annual HRA cycle" section would have been the single largest fabrication available on this page, and it is exactly what the `vc-dashboard-design` prototype would have tempted a builder into. The honest shipped path is a four-step assembly, and it lands better **after** the buyer has seen the aggregate view, because step 4 ("nudge and track") only makes sense once they know what tracking means here.

**Change 2. The HR section and the "action" step are merged.**
The suggested spine had "What HR gets" at 5 and "where it leads" at 7. But the count-only cohort targeting is simultaneously the strongest privacy proof, the aggregate view, and the action. Splitting it across two sections would have weakened all three. One section, `.fairband` inset carrying the targeting mock, three aggregate cards underneath.

**Change 3. The "data in, data out, action" chain becomes the related-programs section rather than a standalone band.**
The chain is an IA fact, not a product mechanic. It is three links. Giving it a full section would have padded the page and duplicated the cross-links that the related grid carries anyway. The related section takes the eyebrow "Data in, data out, action" and does both jobs.

### 2.4 The page's signature, and how it stays unique

**The privacy firewall as a designed, two-sided section with a physical divider, plus an explicit "what is not shipped" strip inside it.**

No sibling page gets this. Specifically:
- The Wellness challenges library page gets a formats explorer. This page has none.
- Step, multi-activity, remote and virtual marathon pages get leaderboard-integrity and fairness bands. This page has none.
- Workforce health insights gets the four analytics stories. This page shows exactly one HR surface, and only to prove what it does not contain.
- Rewards gets a catalogue.

The two things that make the firewall structurally different from any "trust" section in the set:
1. **It is symmetric and adversarial.** Two panels facing each other across a divider, each opening with the *same* assessment rendered as the two things it becomes. The employee sees "78%, Good, your suggestions." HR sees "Health Baselines 13/20." Same data, two views, and the reader can see the information loss.
2. **It publishes the gaps.** A "what is not shipped" column naming cohort suppression, versioned consent and an erasure SLA as things Vantage Fit does not have. Nothing in the set does this. It is also the highest-conversion element on the page for this buyer, because a vendor that names its own gaps is a vendor whose other claims can be believed.

### 2.5 What was deliberately left out, and why

| Left out | Why |
|---|---|
| A `.results-grid` customer-result strip | **No approved metric exists for HRA or health screening.** Tata Motors' org BMI 24 and Brazosport's BMI 30 to ~27 are approved but they measure challenge programs, and placing them under an HRA heading manufactures a causal link that `content-standards.md:14-25` forbids. Vantage Circle's own three-year workforce study (94 employees, three check-ups, ~47% measurable improvement) is the right proof for this page and is **not in `data-accuracy.md`**. Flagged for allowlisting in §9. Prompt guidance is explicit that a results section is optional. |
| Lab reports as a section | Premium, limited-availability, whitelist-gated in code to a single company today. One qualified mention in the rollout note. Leading with it would over-claim. |
| An HRA completion-rate stat tile | C5. No documented report screen and no approved figure. |
| A department or team health breakdown | C4. Org-level only. |
| Any wellness leagues content | Leagues are step-average driven and have nothing to do with the HRA. Mixing them is a documented trap. |
| A "clinically validated" or outcomes claim | Zero source. The product's own position is "informational tool, not a medical diagnosis", and the page adopts it. |
| An ADA or GINA compliance statement | No legal-review material exists in any repo. The page states the factual question set and stops. |
| A duration claim ("takes 5 minutes") | Unsourced. Designed around. |

---

## 3. Section-by-section copy deck

Every string below ships as written. The builder writes zero new copy.
Sentence case for all H2s. This page uses **no terminal period on H1 and H2**, held consistently. No em-dashes anywhere.

### Page furniture

| Slot | Copy |
|---|---|
| `<title>` | `Corporate Health Risk Assessment \| Vantage Fit` |
| `<meta name="description">` | `Run a baseline health risk assessment employees will answer honestly. Private results for them, aggregate-only reporting for HR. Book a Vantage Fit demo.` |
| `<meta name="robots">` | `noindex, nofollow` |
| `<meta name="theme-color">` | `#18262b` |
| Skip link | `Skip to main content` |
| Nav state | `is-current` on the Solutions trigger; `is-page` + `aria-current="page"` on the `Health Risk Assessment` mega-link |
| Footer state | In the footer Solutions column, `Health Risk Assessment` gets `aria-current="page"` and `style="color:#fff;font-weight:700"` |

Section id / ground map (band alternation, never two identical adjacent):

| # | id | Section | Ground |
|---|---|---|---|
| S1 | `hero` | Hero + logo band | hero gradient |
| S2 | `assessment` | What the assessment asks | `var(--canvas)` |
| S3 | `result` | What the employee gets back | `#fff` |
| S4 | `privacy` | The privacy firewall | `var(--canvas)` |
| S5 | `aggregate` | What HR gets | `#fff`, with the dark `.fairband` inset |
| S6 | `rollout` | How a screening campaign runs | `var(--canvas)` |
| S7 | `proof` | Evaluation quote | `#f6f7f4` |
| S8 | `security` | Trust band | dark gradient |
| S9 | `faq` | FAQ | `#fff` |
| S10 | `related` | Data in, data out, action | `var(--canvas)` |
| S11 | `demo` | Closer | dark gradient |

Dark moments: the `.fairband` inset in S5, `.trust-screen` in S8, `.final` in S11. None adjacent. Within budget.

---

### S1. Hero

```
eyebrow:   Baseline health screening
h1:        Every employee gets a private health baseline. HR gets the <em>aggregate</em>
lead:      The Health Risk Assessment is a self-reported questionnaire in the Vantage Fit app.
           Nine health factors, a private result for the employee, aggregate-only reporting for HR.
btn 1:     Book a demo            -> https://www.vantagefit.io/request-demo/
btn 2:     See pricing            -> https://www.vantagefit.io/pricing/
hero-note: Full Mode feature, enabled for your company by your account manager
```

`.visual-caption` under the hero visual:
```
The same assessment, two views. No individual answers appear on any admin screen.
```

Logo band (paste as the last child of `<header class="hero">`):
```
Trusted by 100+ organizations worldwide
TATA MOTORS · WIPRO · TEVA · GODREJ · TEXAS INSTRUMENTS · HEIDRICK & STRUGGLES · BRAZOSPORT ISD
```

**Hero visuals:** `.dash` (admin, left/back) + `.phone` (employee, right/front). Full spec in §4.1 and §4.2.

---

### S2. What the assessment asks

```
eyebrow: The assessment
h2:      Nine health areas, answered by the employee
lead:    It lives in the mobile app under Profile. Completion is voluntary, and employees can
         retake it whenever their situation changes.
```

Layout: `.employee-cols` (`1.04fr .96fr`, gap 56px). Left = the questionnaire mock (§4.3). Right = `.area-list`, a two-column grid of nine rows.

`.area-list` rows, `<b>` then `<span>`:

| Area (b) | Input (span) |
|---|---|
| Blood group | Select from A+, B+, AB+, O+, A-, B-, AB-, O- |
| Waist size | Entered in centimetres |
| Blood pressure | Systolic and diastolic, entered as 120/80 |
| Cholesterol level | A single number from a recent reading |
| Diabetes status | Yes or no |
| Smoking habits | Never, occasionally or frequently |
| Alcohol consumption | Never, occasionally or frequently |
| Exercise frequency | Never, occasionally or frequently |
| Age and BMI | Pulled from the health profile, not asked again |

Trailing note (`.assessment-note`, `.8rem`, muted, sits under the `.area-list`):
```
Scored across the nine components, to a maximum of 95 points. The assessment does not ask for
family medical history and does not ask for genetic information.
```

---

### S3. What the employee gets back

```
eyebrow: The employee's result
h2:      A score they can act on, and nobody else can read
lead:    On submit the app returns a fitness percentage from 0 to 100%, a category, and
         personalized suggestions built from their own answers.
```

Primary visual: `.band-scale`, a 0 to 100 track with the five real categories (§4.4).

Under the scale, five `.band-meaning` cells (one per band), copy verbatim from the help doc:

| Category | Range | Meaning |
|---|---|---|
| Excellent | 85% and above | Low health risk, strong fitness indicators |
| Good | 70% to 84% | Moderate health with room for improvement |
| Average | 50% to 69% | Some risk factors present |
| Below Average | 35% to 49% | Multiple risk factors, attention needed |
| Critical | Below 35% | High risk, consult a healthcare professional |

Below the scale, a `.note-card` (white card, coral 3px left rule, radius `0 14px 14px 0`):
```
Quoted line:  "The HRA is an informational tool, not a medical diagnosis. For any health
               concerns, always consult your doctor."
Attribution:  Shown to every employee with their result.
```

Trailing note (`.result-note`, `.8rem`, muted):
```
Employees can retake the assessment at any time. There is no enforced cadence and no penalty
for skipping it.
```

---

### S4. The privacy firewall  ← the page-defining section

```
eyebrow: The privacy firewall
h2:      What the employee sees, and what HR can ever see
lead:    No admin screen and no export shows one person's assessment answers or risk category.
         That is how the product is built, not a promise in a contract.
```

Primary visual: `.firewall`, a three-column grid (`1fr 78px 1fr`). Full spec in §4.5.

**LEFT panel. Header: `The employee sees`**

Mini-surface strip at the top of the panel (tinted mint `rgba(65,216,180,.10)`):
```
Health Risk Assessment      78%   Good
```

Rows (`✓` glyph, mint, `#169d7e`):
1. `Their fitness percentage, 0 to 100%`
2. `Their category: Excellent, Good, Average, Below Average or Critical`
3. `The component breakdown behind the score`
4. `Personalized suggestions built from their own risk factors`
5. `Their weight graph, BMI and ideal weight range in My Health`
6. `Their own lab report biomarkers, where lab reports are enabled`
7. `A delete button on their own lab reports, and on their own account`

Panel footer (`.fw-foot`, `.74rem`, muted):
```
Account deletion runs from Profile > Delete Account with an emailed one-time code. Admins cannot
delete an employee's account for them.
```

**CENTRE divider.** Vertical dashed rule with a lock glyph at mid-height. Rotated label reading bottom-to-top:
```
Nothing individual crosses this line
```

**RIGHT panel. Header: `HR ever sees`**

Mini-surface strip at the top of the panel (tinted ink `rgba(41,41,76,.05)`):
```
Org Wellness Score      68      Health Baselines 13/20
```

Sub-header `Can see`, three rows (`•` glyph, ink):
1. `Aggregate metrics: enrollment rates, active user percentages, wellness scores`
2. `A derived Baseline sub-score in the Wellness Score report, never the answers behind it`
3. `A count when targeting a health risk cohort, never the names in it`

Sub-header `Cannot see`, four rows, struck through, `--coral-deep`, verbatim from the admin privacy doc:
1. `Health Risk Assessment details: individual answers and risk categories`
2. `Lab report results: biomarker values and health indicators`
3. `Individual health data: weight, BMI, body measurements`
4. `Personal tracking data: mood logs, food diary, sleep patterns`

Panel footer (`.fw-foot`, `.74rem`, muted):
```
The employee report an admin can pull shows registration status, last active date and device
type. Those are participation reports, not health reports.
```

**Under the diagram, full width: the quoted HR line** (`.fw-quote`, white card, coral left rule):
```
Quote:        "Your HR team sees whether you are participating and your challenge rankings, but
               we cannot see your weight, health assessment results, lab reports, or personal
               health data."
Attribution:  The sentence the Vantage Fit admin guide gives HR to share with employees.
```

**Under that: the honest-scope strip** `.fw-scope`, a two-column bordered panel.

Strip header:
```
h3:   What is shipped, and what is not
copy: Privacy controls are where wellness vendors over-claim. Here is the line.
```

Left column, header `Shipped today`, five rows (`✓`, mint):
1. `Aggregate-only health reporting, with no individual assessment or lab view in the admin dashboard`
2. `Count-only cohort targeting, with the privacy disclaimer printed on screen`
3. `Four isolated data regions: India, US, EU and UAE, chosen at signup and permanent`
4. `Employee-initiated account deletion with a one-time code, after which the identity is anonymized`
5. `Custom terms and conditions added to employee onboarding, in the languages you supply`

Right column, header `Not built yet`, three rows (`×`, muted, `rgba(41,41,76,.45)`):
1. `A minimum cohort size that suppresses small groups inside breakdowns`
2. `Versioned consent with a re-acceptance register`
3. `A self-service erasure workflow with a published turnaround`

Strip footer (`.fw-scope-foot`, `.8rem`):
```
If any of those three are procurement requirements, raise them on the first call. We would rather
lose the deal than tell you they exist.
```

---

### S5. What HR gets, and what HR does with it

```
eyebrow: The aggregate view
h2:      HR gets a number, a trend, and a cohort count
lead:    The assessment feeds the Baseline component of the Org Wellness Score, and it powers
         health risk targeting. Neither surface exposes one person's answers.
```

**Primary visual: the `.fairband` dark inset.**

Left column of the fairband:
```
eyebrow (lime): Count-only targeting
h2:             Act on a health risk without ever seeing who is in it
lead:           Once the assessment is enabled, Health Risk Code becomes one of the challenge
                audience filters. It behaves differently from the others.
```

`.fair-list`, four items (`<b>` then `<p>`):

| Title (b) | Body (p) |
|---|---|
| Target by Health Risk Code | One of seven audience filters, available once the assessment is enabled for your company. |
| The system returns a count | You see how many employees match. You never see which ones. |
| The challenge goes Private on its own | Any audience filter marks the challenge Private, so non-matching employees never see it exists. |
| Enrollment happens by rule | Matching employees are enrolled automatically, immediately or when they next become active. |

`.fair-fine` (top hairline, `.72rem`, `rgba(255,255,255,.6)`):
```
Risk-targeted challenges are a live capability. Ask your account manager about enabling it for
your organization.
```

Right column of the fairband: the **target-audience mock**, `.audit-board` shell. Full spec in §4.6.

**Below the fairband: `.agg-grid`, three cards.**

| Card title (h3) | Body |
|---|---|
| Baseline, 20% of the score | The assessment sets the Baseline component of each employee's wellness score. Without an assessment, the baseline sits at a default of 50. |
| One organizational number, 0 to 100 | Baseline, Participation, Activity and Adherence, weighted into a single Org Wellness Score on the Workforce Health page. |
| A trend worth reviewing monthly | Component breakdown and trend over time. Allow 2 to 4 weeks of data collection before the first baseline is reliable. |

Trailing note (`.agg-note`, `.8rem`, muted):
```
Org Wellness Score is provisioned by your account manager for annual clients. It is not a
self-serve toggle, and it needs your employee data indexed before it will report.
```

---

### S6. How a screening campaign runs

```
eyebrow: Rollout
h2:      Four steps, and none of them is a project
lead:    The assessment is always available in the employee app. HR drives completion by running
         a Custom Challenge that carries it as a task.
```

`.steps`, four numbered cards:

| No. | h3 | p | step-tag |
|---|---|---|---|
| 1 | Turn the assessment on | Your account manager enables the Health Risk Assessment for your company. It needs Full Mode. | 01 |
| 2 | Build the screening campaign | A Custom Challenge with the Health Vitals (HRA) task, a one-time task designed for baseline profiling at launch. | 02 |
| 3 | Set the audience, let enrollment run | Filter by country, city, department, gender, age range or language. Matching employees are enrolled automatically. | 03 |
| 4 | Nudge, then read the aggregate | Push notifications go out to a chosen audience, with a preview before you send. Branded custom emails and social-feed announcements run alongside them. | 04 |

Trailing note (`.rollout-note`, `.8rem`, muted):
```
For a fuller screening program, pair the assessment with the Lab Report Upload and Doctor Visit
tasks. Lab report upload is a premium capability, enabled per company by your account manager.
```

---

### S7. Evaluation

```
eyebrow: Evaluation
h2:      Bring your privacy requirements to the first call
lead:    Data residency, consent language and what your admins can see are configuration
         questions. They get answered before rollout, not after it.
```

One `.quote-band.text-only`, full width:
```
blockquote:  "From the first call, the team was extremely transparent, collaborative and
              considerate of all our corporate requirements."
quote-who:   Teva Pharmaceuticals
```

`.proof-fine` under it:
```
small:      Approved customer testimonial, October 2025.
text-link:  Read customer stories ->   https://www.vantagefit.io/casestudy/
```

> Builder note: attribute to the company only. No individual name or title is on record for this quote, and inventing one is a documented prior defect.

---

### S8. Trust band (paste the `chrome.html` shell, swap the copy below)

```
eyebrow: Enterprise security and compliance
h2:      Health data lands in one region and stays there
lead:    Your organization picks a region at signup. It is permanent, isolated from the others,
         and nothing crosses between them.
btn:     Book a demo                     -> https://www.vantagefit.io/request-demo/
link:    Explore security & compliance ->  https://www.vantagefit.io/features/security-and-compliance/
```

Four `.trust-card`s (replace all four bodies from the chrome default; glyphs stay):

| Glyph | h3 | p |
|---|---|---|
| `&#9673;` | Aggregate only, by design | No admin screen and no CSV export shows an individual's assessment answers, risk category or biomarker values. |
| `&#9737;` | Four separate regions | India, US, EU and UAE. The region is chosen at signup and stays fixed, with no cross-region sharing. |
| `&#8644;` | Your consent language | Custom terms and conditions can be added to employee onboarding, in each language you supply. |
| `&#10003;` | Or no health data at all | Lite Mode runs steps only. The assessment, Wellness Score, Lab Reports and My Health are all switched off. |

`.mark-strip`, exactly three strings, unchanged from `chrome.html`:
```
Follows HIPAA guidelines · SOC 2 Type II · Secured regional data hosting
```
`.trust-support`:
```
Security documentation is available during evaluation.
```

> **Hard rule for the builder.** Do not restore the Cloudinary certification raster. Do not write
> "HIPAA compliant". Do not add ISO 27001, ISO 27701, GDPR or CCPA anywhere. Do not reuse the
> chrome's default third trust card (the SSO / HRIS one); its integration list is inherited from
> another page and is not sourced for this one.

---

### S9. FAQ (five items, first one `open`)

```
eyebrow: Questions HR asks
h2:      Before you take this to legal
```

**1. What is a corporate health risk assessment?** *(answer-first, for AEO)*
```
A corporate health risk assessment is a short self-reported questionnaire that gives each employee
a baseline picture of their own health. In Vantage Fit it covers nine areas, including blood
pressure, cholesterol, diabetes status, waist size, smoking, alcohol and exercise frequency, and
returns a fitness percentage from 0 to 100% with a category and personalized suggestions. The
employer receives aggregate results only.
```

**2. Can our HR team see an employee's answers or risk category?**
```
No. Admins cannot see Health Risk Assessment details, meaning individual answers and risk
categories, and they cannot see lab report results, individual weight or BMI, or personal tracking
data such as mood logs, food diary and sleep patterns. There is one thing to be precise about: if
your organization has the Org Wellness Score enabled, admins can see each employee's composite
score and its four component sub-scores, one of which is derived from the assessment. That is a
number, not the answers behind it, and the product documentation states plainly that individual
wellness scores are for program design, not for HR decisions about specific employees.
```

**3. Is completion mandatory, and can results affect benefits or employment?**
```
Completion is voluntary and employees can skip it entirely. There is no mechanism in Vantage Fit
to gate a benefit on completing the assessment, and no mechanism to tier an incentive by a health
outcome. The only lever an administrator has is a challenge task that awards points for completing
the assessment. The questionnaire does not ask for family medical history and does not ask for
genetic information. Your legal team should still run their own review, and we will supply the
full question set and the data flows for it.
```

**4. Is this a medical assessment?**
```
No. In the employee's own words on screen: "The HRA is an informational tool, not a medical
diagnosis. For any health concerns, always consult your doctor." The suggestions it generates are
general wellness guidance. Nothing in Vantage Fit is a clinical service, and no result is reviewed
by a clinician.
```

**5. What happens if only some of our employees complete it?**
```
The program still works. Where an employee has not completed the assessment, the Baseline component
of their wellness score uses a default value of 50 and the other three components carry on as
normal. Completion rises when the assessment is packaged as a task inside a challenge with
automatic enrollment and targeted reminders, rather than left as something employees have to go
looking for in their profile.
```

---

### S10. Related: data in, data out, action

```
eyebrow: Data in, data out, action
h2:      Where the baseline goes next
lead:    The assessment is the first link. Insights prove what changed, and rewards keep people
         coming back to change it.
```

Exactly three `.related-row`s:

| h3 | p | href |
|---|---|---|
| Workforce health insights | Participation, challenge and activity analytics your board can read. | `https://www.vantagefit.io/solutions/workforce-health-insights/` |
| Wellness rewards program | Points and gift cards tied to real effort. | `https://www.vantagefit.io/solutions/wellness-rewards-program/` |
| Wellness challenges | The full library of ready-to-run challenges, including the one that carries the assessment task. | `https://www.vantagefit.io/solutions/wellness-challenges/` |

Glyph guidance: chart/bars for insights, gift/card for rewards, grid/tiles for the library. 18px inline SVG, `stroke-width 1.8`, `currentColor`.

---

### S11. Closer

```
h2:            See what your workforce baseline would look like
p:             In a 30-minute demo we will walk the assessment on a phone, show the aggregate view
               your admins actually get, and answer your residency and consent questions.
btn 1:         Book a demo   -> https://www.vantagefit.io/request-demo/
btn 2:         See pricing   -> https://www.vantagefit.io/pricing/
final-checks:  Aggregate-only reporting · Four data regions · No obligation
final-note:    Measure first. Then improve.
```

---

## 4. Product-real UI spec

Universal rules, from `design-system.md` §5, non-negotiable:
1. Outer container gets `role="img"` and an `aria-label` that describes the screen and **ends with "Figures shown are illustrative."**
2. Every decorative child gets `aria-hidden="true"`.
3. Every mock carries a visible `<span class="mock-tag">Illustrative data</span>`.
4. All digit runs get `font-variant-numeric: tabular-nums`.
5. Only real product nouns. Every label below is sourced in §5.

All numbers in all mocks are invented and labelled. Internal consistency to preserve: **78% maps to Good (70 to 84%)**, and **13 + 22 + 19 + 14 = 68**.

### 4.1 Hero `.dash` : the admin aggregate view

Standard `.dash` placement: absolute inside `.hero-visual`, `top:6px; left:0; width:min(100%,430px)`, rotate `1.1deg`, shadow `0 30px 74px rgba(41,41,76,.18)`.

`aria-label`: *"Admin dashboard showing an organization wellness score of 68 out of 100 with its four component contributions, labelled aggregated insights only. Figures shown are illustrative."*

```
.dash-top        three grey dots + a 42%-wide pill standing in for the URL
.dash-title      small:  Admin · Workforce Health
                 strong: Org Wellness Score
                 right:  <span class="mock-tag">Illustrative data</span>
.dash-sub        a pill chip reading: Aggregated insights only        <- real product string
.metric-card
  .metric-lab    Org Wellness Score
  .metric-value  68
  .dash-asof     As of yesterday                                       <- real freshness rule
.dash-brk-head   SCORE BREAKDOWN                                       <- real product string, uppercase
.dash-brk rows   4 rows, each: label (left) · value (right) · a 3px progress rail underneath
                   Health Baselines (20%)      13 / 20     rail 65%    <- add a small chip: from HRA
                   Participation (30%)         22 / 30     rail 73%
                   Activity Levels (30%)       19 / 30     rail 63%
                   Program Adherence (20%)     14 / 20     rail 70%
```

Rail colors, taken from the production Wellness Score palette so the mock is screenshot-plausible:
Health Baselines `#9BAFC8` · Participation `#21B8A6` · Activity Levels `#7A56E4` · Program Adherence `#F59E0B`. Rail track `rgba(41,41,76,.08)`.

> **Production strings only, here.** `Health Baselines`, `Activity Levels` and `Program Adherence`
> appear **only** inside this mock and the S4 right-hand mini strip. In prose the page uses the
> help-doc names `Baseline`, `Participation`, `Activity`, `Adherence`. That split is a settled
> ruling, not a preference.

### 4.2 Hero `.phone` : the employee's result

Standard `.phone` placement: absolute, `right:-16px; bottom:2px; width:194px`, rotate `-3deg`, `z-index:2`.

`aria-label`: *"Employee app showing a completed health risk assessment result of 78 percent in the Good category, with personalized suggestions and a note that the assessment is not a medical diagnosis. Figures shown are illustrative."*

```
.phone-head      Vantage Fit                    + .avatar
.hra-result      small:  PROFILE · HEALTH RISK ASSESSMENT
                 b:      Your result
                 .hra-pct:   78%                            (2.5rem, 800, tabular-nums)
                 .hra-band:  Good                           (pill, mint tint, #169d7e)
                 .hra-range: 70% to 84% · Moderate health with room for improvement
.hra-sug-head    YOUR SUGGESTIONS
.hra-sug rows    2 rows, each a small mint dot + one line:
                   Add two more active days a week
                   Recheck blood pressure and cholesterol at your next visit
.hra-fine        The HRA is an informational tool, not a medical diagnosis.
.mock-tag        Illustrative data
```

The `.challenge-art` teal gradient block from the shipped `.phone` pattern is **not** used here. This screen is a result card, not a challenge card.

### 4.3 S2 `.hra-form` : the questionnaire (bezel-less screen crop)

Deliberately **not** wrapped in the `.phone` device shell, so the page does not render two identical devices. Style it as a `.phone-screen`: background `#f5f7f4`, radius 24px, `max-width 320px`, `padding 16px`, `box-shadow 0 22px 54px rgba(41,41,76,.12)`, with a 6px `--line` hairline border.

`aria-label`: *"The health risk assessment questionnaire in the Vantage Fit mobile app, showing health area 4 of 9, blood pressure entered as systolic and diastolic values, with a progress bar. Figures shown are illustrative."*

> **Counter reads `Area 4 of 9`, never `4 of 9`.** There is no published question count for the
> HRA; the docs describe nine health *areas*. A bare "4 of 9" next to a progress bar asserts a
> nine-screen questionnaire, which is exactly the inference `health-hra.md:80` forbids.

```
.hf-head         left:  Health Risk Assessment
                 right: Area 4 of 9
.hf-progress     a 4px rail, 44% filled, coral
.hf-q            Blood pressure
.hf-help         Enter your most recent reading
.hf-inputs       two side-by-side input boxes with labels above:
                   Systolic   [ 120 ]
                   Diastolic  [  80 ]
.hf-prev         a dimmed completed row above the current question, to show progress:
                   ✓ Waist size          86 cm
                   ✓ Blood group         O+
.hf-next         a full-width coral button:  Next
.hf-fine         Answer honestly. Only you can see this.
.mock-tag        Illustrative data
```

> `.hf-fine` paraphrases the help doc's own tip ("Answer honestly. The HRA is private and exists
> to help you understand your own health"). It reads as app microcopy and is inside a labelled
> illustrative mock. If the builder prefers zero paraphrase, replace it with the exact doc line.

### 4.4 S3 `.band-scale` : the 0 to 100 category ladder

A horizontal track, `height 54px`, `border-radius 12px`, `overflow:hidden`, split into five proportional segments by the real thresholds. Widths derive from the real ranges:

| Segment | Range | Width | Fill |
|---|---|---|---|
| Critical | 0 to 34 | 35% | `rgba(241,81,98,.22)` |
| Below Average | 35 to 49 | 15% | `rgba(246,185,59,.26)` |
| Average | 50 to 69 | 20% | `rgba(246,185,59,.14)` |
| Good | 70 to 84 | 15% | `rgba(65,216,180,.20)` |
| Excellent | 85 to 100 | 15% | `rgba(65,216,180,.38)` |

- Each segment carries its category name centred, `.72rem`, 800 weight, ink.
- Tick labels under the track at `0`, `35`, `50`, `70`, `85`, `100`, `.68rem`, muted, tabular-nums.
- A coral marker pin at 78% with a small flag reading `78% · Good`, mirroring the hero phone. Give it `aria-hidden="true"`; the scale's `aria-label` covers it.
- Below the track, a `repeat(5,1fr)` row of `.band-meaning` cells: category name in `<b>`, range in a `.band-range` chip, meaning as a `<p>`.
- Under 860px the scale becomes a vertical stack of five rows: chip, name, meaning.

`aria-label` on the scale wrapper: *"Health risk assessment category scale from 0 to 100 percent: Critical below 35, Below Average 35 to 49, Average 50 to 69, Good 70 to 84, Excellent 85 and above, with an example result marked at 78 percent. Figures shown are illustrative."*

Add `<span class="mock-tag">Illustrative data</span>` because of the 78% marker. The thresholds themselves are real and sourced.

### 4.5 S4 `.firewall` : the page-defining diagram

Grid: `grid-template-columns: 1fr 78px 1fr; align-items: stretch; gap: 0;`
Collapses at 900px to a single column, with the divider becoming a horizontal dashed rule and the label reading left to right.

Both panels: `background: var(--paper); border: 1px solid var(--line); padding: 26px 28px;`
Left panel `border-radius: 18px 0 0 18px`. Right panel `border-radius: 0 18px 18px 0`.
Left panel gets a 3px mint top edge (`--mint`). Right panel gets a 3px ink top edge (`rgba(41,41,76,.35)`).

**Panel headers:** `.fw-head`, `.68rem`, 800, uppercase, `letter-spacing .13em`. Left header ink, right header ink. Under each, a `.fw-sub` one-liner:
- left: `In the app, on their own phone`
- right: `In the admin dashboard`

**Mini-surface strips** (`.fw-surface`, `height 44px`, radius 10px, `padding 0 12px`, flex, space-between, tabular-nums):
- Left, background `rgba(65,216,180,.10)`, border `1px solid rgba(65,216,180,.28)`:
  `Health Risk Assessment` (left, `.7rem` muted) · `78%` (`1.05rem`, 800) · `Good` (mint pill)
- Right, background `rgba(41,41,76,.05)`, border `1px solid var(--line)`:
  `Org Wellness Score` (left, `.7rem` muted) · `68` (`1.05rem`, 800) · `Health Baselines 13/20` (`.66rem` muted)

These two strips carry the whole argument: same assessment, two renderings, visible information loss. Do not omit them, and do not let the builder swap in generic icons.

**Row lists.** `.fw-row` is `grid-template-columns: 16px 1fr; gap: 10px; padding: 9px 0; font-size: .84rem; line-height: 1.45;` with a bottom hairline on all but the last.
- Left glyphs: `✓` via CSS `content`, `color:#169d7e`, weight 800.
- Right "Can see" glyphs: `•`, `color: var(--muted)`.
- Right "Cannot see" glyphs: `✕`, `color: var(--coral-deep)`, and the row text gets `text-decoration: line-through; text-decoration-thickness: 1.5px; text-decoration-color: rgba(182,46,64,.55); color: rgba(41,41,76,.6);`

**Sub-headers** inside the right panel (`.fw-subhead`, `.62rem`, 800, uppercase, `letter-spacing .12em`, `margin: 18px 0 6px`): `Can see` in `--mint-dark`, `Cannot see` in `--coral-deep`.

**Centre divider** `.fw-divider`:
```css
.fw-divider { position: relative; display: grid; place-items: center; }
.fw-divider::before { content:""; position:absolute; top:14px; bottom:14px; left:50%;
  border-left: 2px dashed rgba(41,41,76,.22); }
.fw-lock { position: relative; width: 40px; height: 40px; border-radius: 50%;
  background: var(--paper); border: 1px solid var(--line); display: grid; place-items: center;
  box-shadow: var(--shadow-soft); }
.fw-label { position: absolute; writing-mode: vertical-rl; transform: rotate(180deg);
  font-size: .6rem; font-weight: 800; letter-spacing: .14em; text-transform: uppercase;
  color: rgba(41,41,76,.5); background: var(--canvas); padding: 10px 0; }
```
The lock is an 18px inline SVG padlock, `stroke-width 1.8`, `currentColor` at `--coral-deep`.
`.fw-label` text: `Nothing individual crosses this line`.
At `max-width: 900px` the divider becomes a horizontal dashed rule with the lock centred and the label rendered normally underneath.

**`.fw-quote`** below the diagram: white card, full width, `border-left: 4px solid var(--coral)`, `border-radius: 0 18px 18px 0`, `padding: 22px 26px`, `box-shadow: var(--shadow-soft)`, `margin-top: 18px`. Quote `.98rem`, ink, line-height 1.55. Attribution `.74rem`, muted, `margin-top: 10px`.

**`.fw-scope`** below that: `margin-top: 18px`, `border: 1px solid var(--line)`, `border-radius: 18px`, `background: var(--paper)`, `padding: 26px 28px`. Inside, `grid-template-columns: 1fr 1fr; gap: 34px;` collapsing to 1 column at 760px. Column headers `.62rem`/800/uppercase: left `--mint-dark`, right `rgba(41,41,76,.5)`. Rows use the same `.fw-row` geometry. `.fw-scope-foot` sits full width with a `1px solid var(--line)` top rule, `padding-top: 16px`, `margin-top: 18px`, `.8rem`, ink at 800 weight for the last sentence.

No `.mock-tag` on the firewall. It contains only two illustrative numbers, both inside `.fw-surface` strips, and both already carry the tag through the strips' own inline `.mock-tag` if the builder prefers. Simplest correct answer: put one `.mock-tag` in the top-right corner of the `.firewall` wrapper.

### 4.6 S5 target-audience mock (`.audit-board` shell)

White 380px panel floating on the dark `.fairband`, `box-shadow: 0 26px 60px rgba(0,0,0,.32)`, radius 18px.

`aria-label`: *"Challenge creation panel with a health risk code audience filter selected, showing that 412 employees match and that the list of users is not displayed to protect individual privacy. Figures shown are illustrative."*

```
.audit-head      b:    Create challenge · Target audience
                 right: a pill reading  Step 5 of 7                <- help-doc wizard, Target
                                                                      Audience is step 5 of 7
.ta-rows         3 filter rows, each: label left, value right
                   Country            All
                   Department         All
                   Health Risk Code   At risk for diabetes
                 the third row is highlighted: background rgba(241,81,98,.06),
                 1px solid rgba(241,81,98,.22), radius 12px, margin 4px -8px, padding 11px 14px
.ta-count        a tinted block, background #e8f7f1, radius 12px, padding 14px 16px:
                   .ta-num    412            (1.9rem, 800, tabular-nums, --ink)
                   .ta-lab    employees match
.ta-disclaimer   a row with a small 14px lock SVG then, in italics:
                   "The list of users is not displayed to protect individual privacy."
                                                        <- verbatim product string, do not edit
.ta-chip         a pill: Challenge marked Private
.audit-caption   Enrollment runs by rule. Non-matching employees never see the challenge.
.mock-tag        Illustrative data
```

> The filter value `At risk for diabetes` is the code-verified spec's own worked example. The real
> health risk code labels are undocumented, so the mock uses the spec's phrasing rather than
> inventing a code format. Noted in §9.

### 4.7 Component CSS the builder must add page-locally

None of these exist in `enterprise.css`. Copy the shared ones from the named source, write the new ones.

| Needed | Classes | Source |
|---|---|---|
| Section shell, heads, reveal, skip link, contrast lifts, `.btn-primary` fix, forced-colors, `.mock-tag` | `.hub-section` `.hub-head` `.reveal` `.skip-link` | `design-system.md` §3.B, plus `chrome.html` which already carries most of it |
| FAQ | `.faq-screen` `.faq-list` `.faq-item` | `design-system.md` addendum F3, paste verbatim |
| Objection inset | `.fairband` `.fair-list` `.fair-item` `.fair-fine` | `design-system.md` §3.B, from `vantage-fit-steps-challenge-v1.html` |
| Targeting mock shell | `.audit-board` `.audit-head` `.audit-caption` | `design-system.md` §5.4 |
| Two-column media split | `.employee-cols` (`1.04fr .96fr`, gap 56px; 1 col at 1100px with `.employee-media { order:-1 }`) | `design-system.md` §3.B |
| Quote | `.quote-band.text-only` `.quote-who` `.proof-fine` | `design-system.md` §3.B |
| Related | `.related-screen` `.related-grid` `.related-row` `.related-icon` | `chrome.html` |
| Trust variant | `.solutions-trust` four overrides + `.mark-strip` | `chrome.html`, already patched |
| **New on this page** | `.area-list` `.hra-form` and `.hf-*` `.band-scale` and `.band-*` `.firewall` and `.fw-*` `.agg-grid` `.ta-*` `.note-card` `.dash-sub` `.dash-asof` `.dash-brk*` `.hra-result` and `.hra-*` | Specified above |

`.area-list`:
```css
.area-list { display: grid; grid-template-columns: 1fr 1fr; gap: 2px 26px; margin-top: 6px; }
.area-list > div { padding: 11px 0; border-bottom: 1px solid var(--line); }
.area-list b { display: block; font-size: .95rem; font-weight: 750; letter-spacing: -.015em; }
.area-list span { display: block; margin-top: 3px; font-size: .8rem; color: var(--muted); line-height: 1.45; }
@media (max-width: 640px) { .area-list { grid-template-columns: 1fr; } }
```

`.agg-grid`:
```css
.agg-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 14px; margin-top: 26px; }
.agg-grid article { padding: 22px 24px; border: 1px solid var(--line); border-radius: 18px; background: var(--paper); }
.agg-grid h3 { font-size: 1.02rem; letter-spacing: -.02em; }
.agg-grid p { margin-top: 8px; font-size: .85rem; color: var(--muted); line-height: 1.5; }
@media (max-width: 900px) { .agg-grid { grid-template-columns: 1fr; } }
```

Accessibility layer to carry over unchanged from `vantage-fit-multi-activity-challenge-v1.html`: skip link, `esc-closed` mega dismissal with focus return, `aria-expanded` synced on all three paths, `.seg-btn:focus-visible` coral override, reduced-motion reveal branch, `@media (forced-colors: active)` fallback for gradient-clipped text, and the `?gray` query-param grayscale hook.

This page has **no segmented tab control and no video modal.** The `chrome.html` handlers for both are null-guarded, so they can stay in the script block untouched.

---

## 5. Claims table

Every factual assertion that reaches the rendered page. Anything not in this table does not ship.

### 5.1 Product claims

| # | Claim as it appears | Section | Source | Status |
|---|---|---|---|---|
| 1 | "self-reported questionnaire in the Vantage Fit app" | S1 lead | `astro/.../what-is-hra.md` | SHIPPED |
| 2 | "Nine health factors" / "Nine health areas" | S1, S2 | `astro/.../what-is-hra.md` | SHIPPED |
| 3 | "It lives in the mobile app under Profile" | S2 lead | `astro/.../what-is-hra.md` "How to Access the HRA" | SHIPPED |
| 4 | "Completion is voluntary" and "employees can retake it" | S2 lead, S3 note, FAQ 3 | `astro/.../what-is-hra.md` | SHIPPED |
| 5 | The nine areas and their input controls (blood group values, cm, 120/80, yes/no, never/occasionally/frequently, age and BMI pulled from profile) | S2 `.area-list`, S2 mock | `astro/.../what-is-hra.md`; `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` | SHIPPED |
| 6 | "a maximum of 95 points" across the nine components | S2 note | `astro/.../what-is-hra.md` | SHIPPED |
| 7 | "does not ask for family medical history and does not ask for genetic information" | S2 note, FAQ 3 | Absence across the documented nine-area question set, `astro/.../what-is-hra.md` | SHIPPED (factual negative). **No legal conclusion drawn.** |
| 8 | "a fitness percentage from 0 to 100%" | S1, S3, FAQ 1 | `astro/.../what-is-hra.md` | SHIPPED |
| 9 | The five categories and their exact ranges and meanings | S3 `.band-scale` and `.band-meaning` | `astro/.../what-is-hra.md` | SHIPPED. Conflicts with a seven-status list in a spec; help doc wins (C1). |
| 10 | "personalized suggestions built from their own answers" | S1 phone, S3 lead | `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` "Fitness percentage + health status + personalized health suggestions" | SHIPPED |
| 11 | "The HRA is an informational tool, not a medical diagnosis. For any health concerns, always consult your doctor." | S3 note-card, S1 phone, FAQ 4 | `astro/.../what-is-hra.md`, verbatim | SHIPPED |
| 12 | "component breakdown behind the score" | S4 left panel | `astro/.../what-is-hra.md` screenshot note | SHIPPED |
| 13 | Weight graph, BMI, ideal weight range in My Health | S4 left panel | `astro/content/en/help/employee/health-tracking/what-is-my-health.md` | SHIPPED |
| 14 | Employees can delete their own lab reports, permanently | S4 left panel | `astro/content/en/help/employee/health-tracking/how-do-i-upload-lab-reports.md` | SHIPPED |
| 15 | "Profile > Delete Account with an emailed one-time code. Admins cannot delete an employee's account for them." | S4 left footer, S4 scope | `astro/content/en/help/admin/settings/admin-data-privacy-security.md` | SHIPPED |
| 16 | Admins CAN see: aggregate metrics (enrollment rates, active user percentages, wellness scores) | S4 right panel | same, verbatim | SHIPPED |
| 17 | Admins CANNOT see: HRA details (individual answers and risk categories) · lab report results (biomarker values and health indicators) · individual health data (weight, BMI, body measurements) · personal tracking data (mood logs, food diary, sleep patterns) | S4 right panel, FAQ 2, trust card 1 | same, verbatim | SHIPPED |
| 18 | "registration status, last active date and device type. Those are participation reports, not health reports." | S4 right footer | same, near-verbatim | SHIPPED |
| 19 | "Your HR team sees whether you are participating and your challenge rankings, but we cannot see your weight, health assessment results, lab reports, or personal health data." | S4 `.fw-quote` | same, verbatim | SHIPPED |
| 20 | "No admin screen and no export shows one person's assessment answers or risk category" | S4 lead, trust card 1 | `vfit-os/specs/product/03-health-wellness/workforce-health.md:75, :97` combined with claim 17 | SHIPPED |
| 21 | Employee-level Wellness Score with four component sub-scores is visible to admins, and the documented guardrail against using it for HR decisions | FAQ 2 | `astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md`; `astro/.../admin-what-is-org-wellness-score.md` | SHIPPED. Stated deliberately, not hidden. |
| 22 | "Health Risk Code" is one of seven challenge audience filters, available once HRA is enabled | S5 fair-list, S5 mock | `astro/content/en/help/admin/challenges/admin-how-do-i-set-target-audience.md` | SHIPPED |
| 23 | Health-risk targeting "returns a count only" | S5 fair-list, S5 mock | `vfit-os/specs/product/03-health-wellness/workforce-health.md:76` | SHIPPED |
| 24 | "The list of users is not displayed to protect individual privacy." | S5 mock, verbatim | same | SHIPPED |
| 25 | Any audience filter marks the challenge Private, invisible to non-matching employees | S5 fair-list, S5 mock caption | `astro/.../admin-how-do-i-set-target-audience.md` | SHIPPED |
| 26 | Auto-enrollment by rule, "immediately or when they next become active" | S5 fair-list, S6 step 3 | same (Enroll Immediately / Enroll When Active) | SHIPPED |
| 27 | "Risk-targeted challenges are a live capability. Ask your account manager about enabling it." | S5 `.fair-fine` | `vfit-os/specs/product/03-health-wellness/workforce-health.md` Roadmap: "capability live; used internally so far", Backlog | SHIPPED capability, ROADMAP rollout. Phrasing deliberately avoids "every client runs this". |
| 28 | HRA sets the Baseline component, 20% of the wellness score; without an HRA the baseline defaults to 50 | S5 card 1, S4 right strip, FAQ 5 | `astro/.../what-is-hra.md`; `astro/.../admin-what-is-org-wellness-score.md` | SHIPPED |
| 29 | "One organizational number, 0 to 100" from Baseline, Participation, Activity, Adherence | S5 card 2, S1 dash | `astro/.../admin-what-is-org-wellness-score.md:13, :26`; `vfit-os/specs/product/09-admin-platform/admin-dashboard.md:55` | SHIPPED. **0 to 100. Never 108.** (C2) |
| 30 | Component weights 20 / 30 / 30 / 20 | S1 dash mock | `astro/.../admin-what-is-org-wellness-score.md` | SHIPPED |
| 31 | "Allow 2 to 4 weeks of data collection before the first baseline is reliable" | S5 card 3 | `astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md` | SHIPPED |
| 32 | "Org Wellness Score is provisioned by your account manager for annual clients. It is not a self-serve toggle" | S5 note | `astro/.../admin-what-is-org-wellness-score.md` "not a self-serve feature"; `vfit-os/specs/product/09-admin-platform/admin-dashboard.md` gating | SHIPPED-GATED |
| 33 | "As of yesterday" freshness caption in the dash | S1 dash | `dash/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md` §4 | SHIPPED behaviour |
| 34 | "Aggregated insights only" chip | S1 dash | `dash/.../2026-07-18-wellness-live-ground-truth.md` §1d, real product string | SHIPPED string |
| 35 | HRA requires Full Mode and account-manager enablement | S1 hero-note, S6 step 1, FAQ context | `astro/content/en/help/admin/settings/admin-what-is-lite-mode.md:34`; `astro/.../admin-what-is-configurable.md:111` | SHIPPED |
| 36 | "Health Vitals (HRA)" is a Custom Challenge task, one-time, "best used for risk stratification, baseline profiling at program launch" | S6 step 2 | `astro/content/en/help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md` | SHIPPED |
| 37 | Audience filters: country, city, department, gender, age range, language | S6 step 3 | `astro/.../admin-how-do-i-set-target-audience.md` | SHIPPED |
| 38 | "Push notifications go out to a chosen audience, with a preview before you send. Branded custom emails and social-feed announcements run alongside them." | S6 step 4 | `astro/content/en/help/admin/workforce-health/admin-dashboard-overview.md`; `astro/content/en/help/admin/communication/admin-how-do-i-send-notifications.md` | SHIPPED. **Only push notifications are documented as audience-targeted.** Custom emails are documented as branded, announcements as posted to the social feed. Do not write "all using the same audience filters". |
| 39 | "pair the assessment with the Lab Report Upload and Doctor Visit tasks", lab upload premium and enabled per company | S6 note | `astro/.../admin-what-tasks-can-i-include-in-a-custom-challenge.md` ("Health-screening campaign") + `vfit-os/specs/product/03-health-wellness/workforce-health.md` Availability | SHIPPED, qualified (C9) |
| 40 | Four separate regions: India, US, EU, UAE; permanent; no cross-region sharing | S4 scope, S8 card 2, closer checks | `astro/content/en/help/admin/settings/admin-data-privacy-security.md` | SHIPPED |
| 41 | Custom terms and conditions added to onboarding, in the languages you supply | S4 scope, S8 card 3 | same, plus `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` | SHIPPED |
| 42 | Lite Mode runs steps only; HRA, Wellness Score, Lab Reports and My Health all off | S8 card 4 | `astro/content/en/help/admin/settings/admin-what-is-lite-mode.md:34-36` | SHIPPED |
| 43 | "Follows HIPAA guidelines", "SOC 2 Type II", "Secured regional data hosting" | S8 mark-strip | `vfit-os/sources/VFit-Marketing-Content-Compacted.md` 2.15; `chrome.html` cleared strings | APPROVED-CLAIM |
| 44 | "Trusted by 100+ organizations worldwide" | S1 logo band | `vfit-os/.claude/rules/data-accuracy.md:252-261` | APPROVED-CLAIM. The only permitted aggregate scale claim. |
| 45 | Logo words: Tata Motors, Wipro, Teva, Godrej, Texas Instruments, Heidrick & Struggles, Brazosport ISD | S1 logo band | `data-accuracy.md:22` approved names list | APPROVED-CLAIM |
| 46 | Teva quote, verbatim, company attribution only | S7 | `data-accuracy.md:203` | APPROVED-CLAIM |
| 47 | Cohort suppression, versioned consent and a self-service erasure workflow named as **not built** | S4 `.fw-scope` right column | `dash/vc-data.js:1100` and `dash/docs/modules/wellness.md` `parkedTabs` | DESIGN-INTENT, stated as absent. This is the only correct way to reference it. |
| 48 | "Step 5 of 7" wizard chip | S5 mock | `astro/content/en/help/admin/challenges/admin-how-do-i-create-a-challenge.md:15-104` — the 7-step wizard, with **Target Audience at step 5** | SHIPPED. The `dash/docs/modules/wellness.md` route order (Setup, Duration, Privacy, Config, Review) is the design-prototype's own routing, loses to the help doc under the source-precedence rule, and does not contain a "Target Audience" step at all. Never label this chip "Setup"; the panel it sits on is Target Audience. |

### 5.2 Claims considered and cut

| Cut claim | Why |
|---|---|
| Any HRA completion rate, including 20% and 42% | 20% is documented but is a sales liability and is not an approved marketing stat. 42% is a hypothetical in a privacy explainer. |
| A time-to-complete figure | No source anywhere. |
| "9 questions" | The doc describes nine areas, not nine screens. |
| Wellness Score "up to 108" or a 1.1x multiplier | Settled ruling G3. |
| An n = 5 or any suppression threshold as a feature | Not shipped. Named only in the "not built yet" column. |
| Versioned consent, a consent register, a 30-day erasure SLA | Not shipped. Same treatment. |
| "Health-data admin" as an RBAC role | Design intent only. |
| Department, team or location breakdowns of health risk | Org-level only (C4). |
| "HIPAA compliant", ISO 27001, ISO 27701, GDPR, CCPA | Banned or unsourced. The product UI itself prints "HIPAA Compliant" on a compliance card. Not reproduced here. |
| An ADA or GINA compliance statement | No legal-review material exists. |
| Any customer result on health outcomes | No approved metric. See §7. |
| OpenAI or ChatGPT as the extraction engine | Deliberately excluded from customer docs. |
| "Insights Hub" | Nav commented out, sub-pages blank. |
| "monitor employee wellness", "health monitoring" | Surveillance framing, forbidden category error. |
| Any Slack or Microsoft Teams capability | Zero spec coverage. |
| "Start free trial" | No trial exists. |
| Any figure from `dash/vc-data.js` | Seeded fiction for a fake tenant. |

### 5.3 Pre-ship gates, run against the rendered HTML

1. `grep` the file for `—` and `&mdash;`. Expected count: **zero**, including inside the nav mega column headers. Use a colon there, consistently with the rest of the set.
2. `grep -i` for: `robust`, `seamless`, `comprehensive`, `user-friendly`, `user friendly`, `holistic`, `empower`, `leverage`, `game-changer`, `best-in-class`, `all-in-one`, `revolutionize`, `cutting-edge`, `synergy`, `monitor`, `behavior change`. Expected: **zero**.
3. `grep -i "HIPAA compliant"`, `grep -i "ISO 27"`, `grep -i "GDPR"`, `grep -i "CCPA"`. Expected: **zero**.
4. `grep -i "free trial"`. Expected: **zero**.
5. `grep "108"`, `grep "n = 5"`, `grep -i "erasure"` outside the "not built yet" column. Expected: zero, zero, one.
6. `grep -c "mock-tag"` must equal **six**, one per drawn surface carrying a number: hero dash, hero phone, S2 questionnaire, S3 band scale, S4 firewall wrapper, S5 targeting board.
7. Every `role="img"` label ends with `Figures shown are illustrative.`
8. Exactly one `<h1>`. Every `<section>` has an `id` and `aria-labelledby`.
9. `Health Baselines`, `Activity Levels` and `Program Adherence` appear **only** inside the S1 dash mock and the S4 right-hand `.fw-surface`. Everywhere else the words are `Baseline`, `Activity`, `Adherence`.
10. Load `?gray` and confirm nothing on the firewall relies on hue alone: the struck-through rows must still read as struck, and the divider must still read as a divider.
11. Confirm the sums: `13 + 22 + 19 + 14 = 68`, and `78%` sits inside `70% to 84%` under the `Good` label.

---

## 6. Meta title and meta description

**Title (45 characters):**
```
Corporate Health Risk Assessment | Vantage Fit
```
Matches the target keyword `corporate health risk assessment tool` (50/mo, KD 4, the easiest win in the set). No em-dash, no benefit clause needed because the keyword is already specific.

**Meta description (151 characters):**
```
Run a baseline health risk assessment employees will answer honestly. Private results for them, aggregate-only reporting for HR. Book a Vantage Fit demo.
```

Alternate, if a stakeholder wants the mechanic named (154 characters):
```
Baseline health screening in the Vantage Fit app: nine health factors, a private result for each employee, aggregate-only reporting for HR. Book a demo.
```

**Optional SEO/AEO layer**, per the consolidated quality bar. If the builder adds it:
- `<link rel="canonical" href="https://www.vantagefit.io/solutions/health-risk-assessment/">`
- `og:type` `website` · `og:title` matching `<title>` · `og:description` matching the meta · `og:url` matching canonical · `twitter:card` `summary_large_image`
- Three `application/ld+json` blocks: `FAQPage` (all five questions, answers matching the rendered copy **word for word**), `SoftwareApplication` (Vantage Fit, category Corporate Wellness, parent Vantage Circle), `BreadcrumbList` (Home / Solutions / Health Risk Assessment).
- The FAQPage schema must carry **no stat** and must not include any string this brief cut. `schema-data.js` drifting from visible copy is a documented site-wide defect; do not add to it.

---

## 7. Menu fit

**Placement.** Solutions mega-menu, **column ②, row 1.** Verbatim from the signed-off preview:

| Field | Value |
|---|---|
| Column header | `Workforce health & rewards: measure and motivate` |
| Menu label | `Health Risk Assessment` |
| Description line | `Baseline health screening with aggregate insights` |
| URL | `/solutions/health-risk-assessment/` |
| Badge | `Data in` |
| Footer Solutions column | Row 7 of 9 |

**Capitalization is load-bearing.** `Health Risk Assessment` is **Title Case** because it is a product noun, while its three column siblings are sentence case (`Workforce health insights`, `Wellness rewards program`). Match the preview exactly. Do not "fix" it.

**Chain position: data in.** Section ②'s stated logic is *"Data in, data out, action: HRA feeds insights, insights prove impact, rewards drive behavior."* This page is the first link and it plays that role in three concrete places:

1. **S5** shows the assessment becoming the Baseline component of an aggregate score, which is literally the handoff to the "data out" page.
2. **S5** shows the assessment becoming a Health Risk Code, which is literally the handoff to the "action" page (a targeted private challenge).
3. **S10** carries the eyebrow `Data in, data out, action` and links forward to both siblings plus the challenges library where the action runs.

The page still stands alone: a reader who arrives from search on "corporate health risk assessment tool" gets a complete answer without clicking anything.

**Badge treatment.** The `Data in` badge is a nav artifact. Do not render a "Data in" badge in the page body. The chain is expressed as copy in S10, not as a chip.

---

## 8. Cross-links

Outbound, in order of appearance:

| From | Anchor text | Destination | Why |
|---|---|---|---|
| S8 trust band | `Explore security & compliance ->` | `https://www.vantagefit.io/features/security-and-compliance/` | Sends the security reviewer to the Features page rather than expanding this one |
| S7 proof | `Read customer stories ->` | `https://www.vantagefit.io/casestudy/` | Proof depth |
| S10 related, row 1 | `Workforce health insights` | `/solutions/workforce-health-insights/` | Data out |
| S10 related, row 2 | `Wellness rewards program` | `/solutions/wellness-rewards-program/` | Action |
| S10 related, row 3 | `Wellness challenges` | `/solutions/wellness-challenges/` | Where the screening campaign is built |
| S1, S5, S8, S11 CTAs | `Book a demo` | `https://www.vantagefit.io/request-demo/` | Primary, four placements |
| S1, S11 | `See pricing` | `https://www.vantagefit.io/pricing/` | Secondary |

That is **three internal Solutions links plus one Features link**, inside the 2 to 3 internal links per page guidance once the mega menu is discounted.

Inbound this page should expect:
- `/solutions/workforce-health-insights/` links **back** here as the data source for the Baseline component.
- `/solutions/wellness-rewards-program/` does **not** need to link here.
- `/solutions/wellness-platform/` links down here as one of the section ② capabilities.
- `/solutions/` hub lists it as card 6 of 9.
- The footer Solutions column, row 7, on every page in the set.

**Do not link:** `/wellness-challenge` (the shipped page, slug collision unresolved), `/health-fitness-analytics/` (retired), `/slack-integration/` (orphan), and never draw or link `Insights Hub`.

---

## 9. Assumptions and gaps

### 9.1 Flagged for a human, blocking nothing

1. **URL prefix conflict.** `vfit-os/.claude/rules/seo-conventions.md:69,83` says solution pages are root-level with no `/solutions/` prefix and says not to propose URL changes. The signed-off menu and the shipping brief both use `/solutions/`. This mock follows the menu. Someone has to reconcile the two rules before launch.
2. **Slug collision.** `/solutions/wellness-challenges/` versus the shipped `/solutions/wellness-challenge`, and whether the new library page replaces or sits above the live `vantagefit.io/wellness-challenges/`. Not this page's problem, but it affects the S10 row-3 link. Follow the menu URL for now.
3. **Five bands versus seven.** `astro/.../what-is-hra.md` ships five. `vfit-os/specs/product/03-health-wellness/onboarding-health-profile.md` lists seven statuses. Product needs to say which the app renders today. If it is seven, S3's `.band-scale` needs rebuilding, so confirm before the page goes live.
4. **Health Risk Code labels are undocumented.** No source gives the actual code format or the human-readable label set. The S5 mock renders `At risk for diabetes`, which is the code-verified spec's own worked example. If real codes look different, swap the mock value.
5. **The Vantage Circle three-year workforce study is the right proof for this page and is not approved.** 94 employees tracked across three health check-ups, Jan 2023 to Dec 2025, ~47% showing measurable health improvement, 79% blood-sugar improvement among improvers, with a named employee testimonial (HbA1c 10.4 to 5.9). It is the only longitudinal health-outcome asset in the corpus and it maps exactly to this page. It is **not in `data-accuracy.md`**. Recommend allowlisting it, labelled as Vantage Circle's own workforce, then adding a two-tile results strip between S6 and S7. Until then the page ships without a results strip.
6. **"HIPAA Compliant" is printed in the shipped product UI** on the Health Insights compliance card. That is a live liability for a company whose approved phrasing is "operates under HIPAA guidelines". Route to product.
7. **SOC 2 Type II** is approved by the claims gate but flagged "not documented in KB" in the site audit. Expect a legal check.
8. **ADA and GINA.** The page states the factual question set and the voluntary, employer-invisible facts, and states no legal conclusion. There is zero legal-review material in any repo. If marketing wants a compliance sentence here, it has to come from counsel, not from the product docs.
9. **`chrome.html` mega column headers** use a colon where the signed-off preview uses an em-dash. Either is acceptable per the dossier. This page uses the **colon**. Whichever the set picks, all six pages must match.

### 9.2 Assumptions this brief made

| Assumption | Basis | Risk if wrong |
|---|---|---|
| The buyer's blocker is honesty and legal sign-off, not price or breadth | The prompt names it as the page's defining objection, and the product's own docs lead with the privacy story | Low. If the real blocker were breadth, S2 and S3 would need to grow. |
| Naming three unbuilt privacy features increases trust rather than losing deals | Standard enterprise-procurement behaviour: a vendor that discloses gaps is trusted on the rest. It also removes the risk of a false claim surviving into a security questionnaire. | Medium. A stakeholder may want the "Not built yet" column softened. **Do not soften it into vagueness.** If it must go, delete the whole strip rather than blurring it, and note the removal. |
| Two phone-shaped surfaces on one page (hero result, S2 questionnaire) read as one product rather than as repetition | They show different screens, and S2's is bezel-less | Low |
| The mock's illustrative 78% and 68 will not be read as customer data | `.mock-tag` on every mock plus the `aria-label` suffix | Low, given the disclosure |
| `/casestudy/` is the correct customer-stories URL | `chrome.html:352, :600, :614` | Low |

### 9.3 Known gaps in the source material

- **No published question count and no time-to-complete.** Designed around. Do not let a reviewer talk the builder into "takes about five minutes".
- **No documented HRA completion report screen** (C5). The page shows no completion tile and no completion export.
- **No HRA-specific reminder email or nudge template.** S6 step 4 describes the generic notification tools only.
- **No approved health-outcome customer metric.** See 9.1 item 5.
- **HRA retake cadence is an open roadmap question**, "currently ad-hoc". The page says "no enforced cadence", which is the honest present-tense statement.
- **Consent today is static and unversioned.** The page claims only custom terms and conditions per company, which is what is shipped, and lists versioned consent as not built.
