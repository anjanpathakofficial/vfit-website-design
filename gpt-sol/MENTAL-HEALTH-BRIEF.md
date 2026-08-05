# Mental health & wellbeing challenge page brief

## Page assignment

- **Locked solution:** Mental health & wellbeing
- **Live URL, context only:** `https://www.vantagefit.io/mental-health-and-wellbeing-challenges/`
- **Primary audience:** US enterprise CHROs, Benefits and Wellbeing leaders
- **Secondary audience:** program managers who build, launch, and report challenges
- **Single job:** Help an HR buyer see how Vantage Fit turns everyday mental wellbeing practices into an approachable, measurable challenge without turning personal reflection into employer-visible data.

## Strategic position

Vantage Fit should not present itself here as therapy, diagnosis, crisis support, or a replacement for an EAP. The product truth is stronger and more credible: it is a habit and participation product. HR can build multi-week programs around guided mindfulness, meditation, relaxation, sleep, content, and custom daily habits. Employees see their own mood and personal trends. HR sees whether the program is being used and where challenge tasks are landing.

The page therefore leads with the tension that matters most for this program: employees need a low-pressure way to take part, while HR needs enough program evidence to improve and report the initiative. Privacy is part of the product story, not a compliance footer.

## Research takeaways

### Product capabilities that matter for this page

- Custom Challenges support distinct weekly themes, multiple tasks per week, daily or weekly targets, task-level points, optional teams, audience rules, certificates, and post-launch notifications. This is the right format for a progressive mental wellbeing program. Source: `../../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-create-custom-challenge.md`.
- Full Mode exposes mental and emotional wellbeing tasks including meditation, mindfulness, mood logging, sleep, yoga, content, and custom adherence habits. Mood values are explicitly private to the employee and are not shown to admins or leaderboards. Source: `../../../../vantagefit-astro/content/en/help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md`.
- Employees can complete auto-tracked, manual-log, custom, adherence, content, and upload tasks. Challenge screens show per-task progress, today’s work, and week navigation. Source: `../../../../vantagefit-astro/content/en/help/employee/challenges/how-do-i-complete-challenge-tasks.md`.
- Employees log mood on a five-point scale, may add reasons and a comment, and can view patterns over time. The mood record is private to the employee, not visible to HR, managers, or colleagues. Source: `../../../../vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-track-my-mood.md`.
- The employee Summary page shows seven-day Mindful Minutes and Sleep trends in Full Mode. Source: `../../../../vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-read-my-dashboard.md`.
- Vantage Fit supports manual mind-and-body activities such as meditation, mindfulness, yoga, book reading, and journaling, plus custom employer activities and daily habits. Source: `../../../../vantagefit-astro/content/en/help/employee/health-tracking/what-activities-can-i-track.md`.
- Guided mindfulness content includes meditation, relaxation, sleep, self-awareness, yoga, and white-noise categories. Playback duration is recorded as a mindfulness activity and can contribute to a challenge. Source: `../../../../vc-os/vfit-os/specs/03-health-wellness/mindfulness-meditation.md`.
- Challenges are the product’s core engagement mechanism. Custom challenges support weekly themes and 27 task types; employees can opt out of leaderboard visibility and still participate. Source: `../../../../vc-os/vfit-os/specs/product/02-challenges-gamification/challenges.md`.
- Health content can be an article, video, podcast, or webinar and can be linked to a challenge task. Source: `../../../../vc-os/vfit-os/specs/06-content-education/health-content-library.md`.
- Admins can monitor enrollment status, challenge performance, task and week breakdowns, points, and exportable reports. Source: `../../../../vantagefit-astro/content/en/help/admin/reports/admin-what-reports-are-available.md`.
- The admin dashboard supports challenge creation, audience management, reports, push notifications, emails, content, events, and rewards. Source: `../../../../vantagefit-astro/content/en/help/admin/workforce-health/admin-dashboard-overview.md`.
- The dashboard prototype distinguishes executive participation, challenge performance, and activity trends instead of blending them into an untraceable wellness score. It also uses separate Move, Mind, and Rest lenses without recombining them into a composite. Sources: `../../../../vc-dashboard-design/docs/modules/wellness.md` and `../../../../vc-dashboard-design/vc-data.js`.
- The current dashboard challenge builder keeps Setup, Duration, Audience, type-specific Configuration, Rewards, and Review in one shared spine. Custom is the rich multi-week builder. Source: `../../../../vc-dashboard-design/docs/superpowers/specs/2026-07-19-create-challenge-wizard-redesign-PROMPT.md`.
- The company mission explicitly says Vantage Fit is a habit product, not a clinical or surveillance product, and puts employee privacy ahead of HR data hunger. Source: `../../../../vc-os/vfit-os/MISSION.md`.

### What the legacy page under-sells or gets wrong

The legacy YAML is a background source only: `../../../../vantagefit-astro/content/en/pages/use-cases/mental-health-and-wellbeing-challenges.yaml`.

- It reads as a generic list of mental health resources rather than a challenge employees can follow week by week.
- It makes broad “support” and stress-reduction claims without showing the actual program builder, task mechanics, employee progress, or admin reporting.
- Its privacy answer is vague. Product help offers a much clearer promise: personal mood ratings, reasons, and comments stay with the employee.
- It claims counseling and partner services without adequate product documentation in the reviewed sources. Those claims are excluded.
- Its proof combines steps, mindfulness, BMI, and mood within mixed wellness programs. Those results do not isolate a mental wellbeing intervention, so this page does not use them as mental-health outcome proof.

### Proof decision

No customer-result section. Brazosport ISD and IBS Software are real stories, but their published results come from mixed physical and holistic wellness programs, not a mental-wellbeing-only challenge. Sources reviewed: `../../../../vantagefit-astro/content/en/casestudy/brazosport-case-study.md` and `../../../../vantagefit-astro/content/en/casestudy/ibs-software-case-study.md`. Omitting a proof band is more credible than implying clinical or isolated mental-health outcomes.

## Design plan

### Visual thesis

The page should feel calm without becoming spa-like, and product-led without treating emotional wellbeing as a score. The hero opens on a real challenge card and guided-session player. Slow “breathing” rings sit behind the product mock as the one expressive motion. The rings stop under reduced-motion preferences.

### Tokens

- **Ink:** `#29294C` for enterprise authority
- **Canvas:** `#F8F8F9` for the shared site ground
- **Paper:** `#FFFFFF` for product surfaces
- **Coral:** `#F15162` for primary action and brand energy
- **Mint:** `#41D8B4` for completion and supportive status
- **Mist:** `#EEF7F5` for low-pressure wellbeing surfaces

Typography stays inside the established Vantage Fit system: Noto Sans for display and body, with small uppercase utility labels differentiated by weight and spacing rather than a new brand font.

### Layout concepts considered

**A. Resource library first**

```text
[headline + CTA] [content tiles]
[sessions] [articles] [sleep] [mood]
```

Rejected. It reads like a feature catalog and repeats the legacy page’s weakest choice.

**B. Weekly program first**

```text
[hero copy]        [employee challenge + session player]
[product truths: doable / private / measurable]
[interactive 4-week path] [phone task preview]
[employee view] || privacy boundary || [HR view]
[launch workflow + admin dashboard]
[FAQ] [CTA]
```

Selected. The sequence mirrors how the product is bought and used: define an approachable routine, show how employees participate, make the data boundary explicit, then show HR operations.

### Signature element

The **privacy boundary** is the page’s memorable device. It visually separates “Personal to the employee” from “Visible to the program team,” with mood rating, reasons, and comments visibly stopping at the boundary. It embodies a real product promise and answers the central buyer objection.

### Plan critique and revision

The first concept leaned on lavender gradients, serenity language, and a proof-led hero. That treatment could fit almost any meditation app and would weaken the Vantage Fit enterprise system. It also risked implying wellbeing outcomes the available evidence cannot isolate.

Revision:

- Keep the established ink, coral, mint, canvas, radius, and Noto Sans system from `../styles/enterprise.css` and `../styled-homepage/index.html`.
- Use the breathing-ring moment once, behind a product-real challenge player, instead of decorative wellness motifs across the page.
- Replace “structured mental health support” with an accurate non-clinical promise about daily practice and program participation.
- Make privacy the signature proof point and omit mixed-program customer outcomes.
- Use the consolidated Steps page as the quality and rhythm reference, not as a forced section template. Sources: `../consolidated/vantage-fit-steps-challenge-consolidated.html` and `../consolidated/STEPS-CHALLENGE-DECISIONS.md`.

### Post-build critique

- The product mock and four-week explorer make this read as a specific challenge page rather than a mental-health resource catalog.
- The privacy boundary is the only large expressive device. Supporting sections stay quiet, and the breathing-ring motion appears only in the hero.
- The admin mock never renders a mood value. Its non-approved metrics are labeled illustrative in the mock and on each KPI.
- The page keeps the non-clinical limit visible in the main narrative and FAQ without letting caution overwhelm the conversion story.
- Browser discovery returned no available browser, so screenshot QA was not possible in this environment. Fallback checks covered HTML5 validation, JavaScript syntax, local assets, internal anchors, source-path resolution, and live navigational URLs.

## Page structure and rationale

1. **Hero:** Establishes the product category and core tension in one line. Product UI shows a guided session inside an active multi-week challenge.
2. **Three product truths:** Doable routines, employee choice, and useful program signals. This earns confidence without a long problem section.
3. **Interactive example program:** Shows how HR can sequence a four-week Custom Challenge and how the employee task view changes week by week. The configuration is explicitly illustrative.
4. **Ways to participate:** Guided audio, manual reflection and logging, and linked learning content. Shows breadth without a 27-item feature dump.
5. **Privacy boundary:** States exactly what stays personal and what HR can use. Includes the non-clinical boundary.
6. **Admin workflow:** Shape, target, guide, and review. Product-real dashboard makes the operating model concrete.
7. **FAQ:** Handles clinical scope, data visibility, wearables, rollout, and parallel programs.
8. **Closer:** Invites the buyer to review an example challenge, employee flow, and reporting boundary in a demo.

## Full copy deck

### Navigation

- Product
- Solutions
- Resources
- Pricing
- Book a demo

### Hero

- **Eyebrow:** Mental health & wellbeing challenges
- **H1:** Make mental wellbeing easier to practice, not harder to disclose.
- **Body:** Run guided, multi-week challenges around mindfulness, recovery, and reflection. Employees get a simple daily way in. HR gets the participation signals needed to improve the program.
- **Primary CTA:** Book a demo
- **Secondary CTA:** See pricing
- **Product notes:** Guided sessions and flexible tasks · Mood entries stay private · Participation and completion reporting
- **Challenge mock:** Reset & recharge · Week 2 of 4 · 5-minute body scan · Check in with your mood · Wind down before bed

### Product truths

- **Heading:** Everyday support, with a clear boundary.
- **Doable on a busy day:** Use short guided sessions, content, or a simple daily check-in.
- **Flexible by design:** Build weekly themes from mindfulness, meditation, sleep, yoga, content, and custom habits.
- **Measurable as a program:** Follow enrollment, participation, completion, and task patterns without exposing personal mood entries.

### Example program

- **Eyebrow:** One program, one clear rhythm
- **H2:** Give each week one job.
- **Body:** Build a progressive Custom Challenge instead of dropping a resource library into the app and hoping employees return.
- **Label:** Illustrative 4-week configuration
- **Week 1, Notice:** Introduce a short wellbeing read and an optional private mood check-in.
- **Week 2, Pause:** Pair a guided mindfulness session with a small daily target.
- **Week 3, Restore:** Add sleep logging and a wind-down session employees can complete on their schedule.
- **Week 4, Continue:** Reinforce one custom daily habit and recognize challenge completion.
- **Product caveat:** Mental wellbeing task types require Full Mode. Challenge design and availability vary by account configuration.

### Participation modes

- **Eyebrow:** Built for real workdays
- **H2:** More than one way to take part.
- **Guided practice:** Employees can choose from meditation, relaxation, self-awareness, sleep, yoga, and white-noise sessions. Listening time records as mindful minutes.
- **Personal logging:** Employees can log meditation, mindfulness, yoga, sleep, or a mood check-in. Their mood rating, reasons, and comments stay private.
- **Learning in the flow:** Add an article, video, podcast, or webinar as a challenge task so learning becomes part of the weekly rhythm.

### Privacy boundary

- **Eyebrow:** Privacy by product design
- **H2:** Personal reflection stays personal.
- **Body:** Vantage Fit is a habit and engagement product. It is not telehealth, diagnosis, crisis support, or employee surveillance.
- **Personal to the employee:** Mood rating · Selected reasons · Optional comment · Personal mood history
- **Boundary label:** Does not cross to HR or the leaderboard
- **Visible to the program team:** Enrollment status · Challenge participation and completion · Task and week progress · Filtered, exportable program reports
- **Clarifier:** If mood logging is included as a challenge task, HR may see that the task was completed as part of challenge progress, not the mood selected, its reasons, or the employee’s comment.
- **Employee control note:** Employees can also opt out of leaderboard visibility and continue participating.

### HR workflow

- **Eyebrow:** Control for HR
- **H2:** Launch, guide, and learn from one program view.
- **Shape:** Choose weekly themes, tasks, targets, dates, and optional points.
- **Target:** Enroll everyone or use audience rules for a defined group. Filtered challenges are private.
- **Guide:** Send invitations and timely notifications while the challenge is active.
- **Review:** Track participation, completion, and task patterns, then export the relevant report.
- **Dashboard labels:** Mindful month · Illustrative program view · Participation · Completion · Task mix · Next action · Nudge employees with incomplete tasks

### FAQ

**Is Vantage Fit a replacement for an EAP, therapist, or crisis service?**

No. Vantage Fit helps employees practice everyday wellbeing habits and helps HR run participation programs. It does not diagnose, treat, or provide crisis care. Employers should keep their clinical and emergency resources clearly available alongside any challenge.

**What mental wellbeing information can HR see?**

HR can review enrollment, challenge participation, completion, score, and task or week progress. Personal mood ratings, selected reasons, comments, and mood history are private to the employee and do not appear to HR or on leaderboards.

**Do employees need a wearable?**

No. Guided sessions, mood check-ins, content, meditation, yoga, sleep, and custom habits can be completed or logged in the app. A connected wearable can make sleep logging automatic, but it is not required for the mental wellbeing program described here.

**Can we run this for one group before going company-wide?**

Yes. HR can target a challenge to all employees or filter the audience by available workforce attributes such as department, country, or location. Available filters depend on your company configuration.

**Can a mental wellbeing challenge run alongside another program?**

Yes. Vantage Fit supports parallel challenges, and each challenge keeps its own tasks, progress, points, and leaderboard.

### Closing CTA

- **Eyebrow:** See the program before you launch it
- **H2:** Build a mental wellbeing challenge employees can enter quietly and HR can run confidently.
- **Body:** In one demo, review an example program, walk through the employee experience, and see exactly what the admin dashboard does and does not reveal.
- **Primary CTA:** Book a demo
- **Secondary CTA:** See pricing
- **Callouts:** Example challenge build · Employee app walkthrough · Admin reporting · Privacy boundary review

## SEO drafts

- **Meta title:** Employee Mental Wellbeing Challenges | Vantage Fit
- **Meta description:** Run mental wellbeing challenges with guided mindfulness, private mood check-ins, flexible weekly tasks, and participation reporting for HR.
- **Suggested H1:** Make mental wellbeing easier to practice, not harder to disclose.

## Claim and language guardrails

- Never promise reduced stress, anxiety, burnout, depression, absenteeism, or healthcare cost.
- Never describe mood data as an HR sentiment signal.
- Never imply Vantage Fit provides therapy, counseling, helplines, crisis intervention, diagnosis, or medical advice.
- Never expose a mood value, reason, or comment in the admin mock.
- Any non-approved mock metric must be labeled **illustrative**.
- Use “mental wellbeing” for the product experience and “mental health & wellbeing challenge” where needed for category and search intent.
- Use sentence case, short card copy, verb-led CTAs, and no em dashes.
