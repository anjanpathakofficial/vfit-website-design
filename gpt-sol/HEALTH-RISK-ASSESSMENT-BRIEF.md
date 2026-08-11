# Health Risk Assessment page brief

## Page job

Position Vantage Fit Health Risk Assessment as the private, voluntary baseline that employees complete for themselves and that contributes useful aggregate signal to the organization’s wellness program. This page owns the **data in** role in the workforce health and rewards chain.

**Intended URL:** `/solutions/health-risk-assessment/`

## Audience and buying question

- Primary: US enterprise HR, benefits, wellbeing, and people leaders
- Secondary: security, privacy, and program stakeholders evaluating health-data boundaries
- Core question: “How can we establish a useful workforce baseline without giving HR access to private employee answers?”

## Product truth used

- The HRA is a voluntary questionnaire in the employee experience, separate from onboarding.
- It covers health measurements and lifestyle factors including BMI inputs, waist size, blood pressure, diabetes status, cholesterol, smoking, alcohol, and exercise habits.
- Employees receive their own fitness percentage, risk category, and personalized health tips. The result is informational and is not a medical diagnosis.
- Employees can retake the assessment when their circumstances change.
- Individual HRA answers are not shared with HR. Organizational use is aggregate.
- HRA data provides baseline input for aggregate workforce health patterns. Not completing the HRA does not block the wider wellness experience.
- Company-enabled HRA risk codes can support targeted challenge audiences without making individual answers part of the HR view.
- HRA is not available in Lite Mode.

No completion-rate claim, assessment-duration claim, customer result, diagnosis claim, or compliance certification is used on the page.

## Privacy wording decision

The help documentation contains admin reporting language that can be read too broadly. The current OS HRA specification is explicit: individual HRA data is never shared with HR and only aggregate analytics are visible at the organizational level. This page follows that narrower privacy boundary.

The page does not claim anonymity, HIPAA compliance, medical-device status, or any legal standard that the sources do not establish. It says exactly what the source supports: individual answers stay private from HR, while aggregate patterns can inform program design.

## Narrative and structure

1. **Lean hero with the privacy boundary visible immediately:** The hero diagram separates the employee’s answers and personal result from HR’s aggregate program view.
2. **One clear workflow:** Employees complete, understand, and can retake the assessment. HR receives aggregate signal for program planning.
3. **Assessment scope:** Show the categories of information collected without reproducing the questionnaire or making it feel clinical.
4. **Data-in chain:** Make HRA’s specific role clear: baseline in, workforce insight out, relevant program action next.
5. **Privacy objection section:** Answer what employees see, what HR sees, and what the assessment is not.
6. **Short FAQ and CTA:** Resolve rollout, retake, Lite Mode, and diagnosis questions.

The page is intentionally leaner than the challenge library. It is a single-program conversion page with one primary objection: trust.

## Visual direction

The page uses the same enterprise tokens, Noto Sans, shared nav, button language, and section rhythm as the Solutions set.

Its signature element is the **privacy boundary diagram**: a warm employee-side assessment card and a cool aggregate-side program card separated by a labeled data boundary. It turns an abstract promise into visible information architecture. No decorative health imagery is used, because the most important visual is how data moves and where it stops.

## Full copy deck

### Hero

**Eyebrow:** Health Risk Assessment

**Headline:** A health baseline employees can trust

**Body:** Give employees a private way to understand their health risk factors. Use the aggregate signal to plan a more relevant wellness program, without giving HR access to individual answers.

**Primary CTA:** Book a demo

**Secondary CTA:** See how data flows

**Employee-side label:** Private to the employee

**Employee-side content:** Health measurements, habits, personal fitness percentage, risk category, and tips

**Boundary label:** Individual answers stop here

**HR-side label:** Aggregate program view

**HR-side content:** Workforce baseline patterns that can inform program design

### How it works

**Eyebrow:** One assessment, a clearer starting point

**Heading:** Turn self-reported health context into a useful baseline

1. Employees complete the HRA: The questionnaire covers core measurements and everyday health habits.
2. Each person sees their own result: Employees receive a fitness percentage, risk category, and personalized tips.
3. The baseline can improve over time: Employees can retake the assessment as their health context changes.
4. HR plans from aggregate signal: Organizational patterns inform program priorities, without exposing individual answers.

### Assessment scope

**Heading:** Focused enough to complete. Broad enough to be useful.

- Body measurements: Height, weight, BMI inputs, and waist size
- Cardiometabolic context: Blood pressure, cholesterol, and diabetes status
- Everyday habits: Smoking, alcohol consumption, and exercise frequency
- Personal context: Age, activity level, fitness goal, and applicable health context

**Disclaimer:** The HRA is an informational wellness tool, not a medical diagnosis. Employees should consult a qualified healthcare professional about health concerns.

### Data-in chain

**Eyebrow:** Data in → data out → action

**Heading:** Give the wellness program a better starting point

- Data in: A voluntary HRA establishes personal health context.
- Data out: The assessment contributes to aggregate workforce baseline patterns.
- Action: Program leaders can use those patterns to choose more relevant wellness initiatives and supported audience strategies.

**Related link 1:** Explore workforce health insights

**Related link 2:** Explore wellness rewards

### Privacy section

**Eyebrow:** Privacy by role

**Heading:** Be clear about who sees what

- Employees see: Their own answers, result, category, and tips.
- HR sees: Aggregate organizational patterns for wellness planning.
- HR does not see: An employee’s individual HRA answers.
- The HRA does not do: Diagnose a condition or replace clinical care.

**Supporting copy:** If health-risk audience targeting is enabled, Vantage Fit can use risk codes to support relevant challenge eligibility without turning individual answers into an HR-facing record.

### FAQ

**Is the HRA mandatory?** No. It is voluntary and separate from employee onboarding.

**Can employees update their answers?** Yes. Employees can retake the HRA when their health context changes.

**What happens if someone does not complete it?** The wider wellness experience can continue. Their HRA responses simply are not available as baseline input.

**Can HR view an employee’s answers?** No. HR’s use is limited to aggregate organizational patterns.

**Is the HRA a medical diagnosis?** No. It is an informational wellness assessment and does not replace advice from a qualified healthcare professional.

**Is HRA available in Lite Mode?** No. HRA is part of the fuller Vantage Fit experience and is not available in the simplified steps-only Lite Mode.

### CTA

**Heading:** Start with a baseline people can understand

**Body:** See how the HRA can fit into a privacy-conscious workforce wellness program.

**Primary CTA:** Book a demo

**Secondary CTA:** See pricing

## Metadata draft

**Meta title:** Employee Health Risk Assessment Tool | Vantage Fit

**Meta description:** Give employees a private health risk assessment and use aggregate workforce patterns to guide a more relevant corporate wellness program.

## Solutions IA fit

This page opens mega-menu column ②, **Workforce health and rewards**, as **Data in**. It should link forward to Workforce health insights as **Data out**, then Wellness rewards program as **Action**. Those sibling links reinforce the system story without asking this page to explain analytics or rewards in depth.

## Sources

- `../../../vantagefit-astro/content/en/help/employee/health-tracking/what-is-hra.md`
- `../../../vantagefit-astro/content/en/help/admin/workforce-health/admin-what-is-workforce-health.md`
- `../../../vantagefit-astro/content/en/help/admin/workforce-health/admin-what-is-org-wellness-score.md`
- `../../../vc-os/vfit-os/specs/03-health-wellness/health-risk-assessment.md`
- `../../../vc-os/vfit-os/specs/03-health-wellness/wellness-score.md`
- `../../../vc-dashboard-design/docs/modules/wellness.md`
- `../../../vc-dashboard-design/docs/superpowers/specs/2026-07-18-wellness-live-ground-truth.md`
- `../menu/vantage-fit-solutions-menu-preview.html`
- `../styles/enterprise.css`
