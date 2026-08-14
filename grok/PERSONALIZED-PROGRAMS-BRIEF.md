# Personalized Programs

**URL:** `/features/personalized-programs/`  
**Mock:** `vantage-fit-personalized-programs-v1.html`  
**Angle:** A plan, and the content to follow it.

## Page job

Prove two systems on one page, visually separate. Lead with Training Plans: 2 live (Couch to 5K, Walking Habit Plan), 7 coming soon, 3 enrollment questions, starts next Monday, runs as a personal challenge, employee-quit-only, no certificate, select-partner. Content Library is supporting: article / video / podcast / webinar / Health Bites / quizzes, content-as-task, `activity_id 1015`, targeting by health profile, admin CRUD once Programs is on.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See the two live plans.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Catalog (lock + OS training-plans.md):** 9 plans. **2 Available:** Couch to 5K, Walking Habit Plan. **7 Coming Soon:** Shredded in 12 Weeks, Quit Smoking in 30 Days, Ride to Thrive, Mindful Moments, + 3 unnamed. VFit-managed. Not admin-created. Do not imply a large live catalog. Help `what-are-training-plans.md` says “currently 9 plans” without the 2/7 split. Page uses the lock split.
- **Enrollment (lock + help start-a-training-plan):** 3 questions: weeks 4–8 slider, training days 3–6 radio, which days checkboxes. Week-by-week preview. “Start Challenge.” Starts **next Monday**.
- **Couch to 5K (lock + OS):** Linear ~1 km → 5–6 km. Final-week taper. Rest days on unselected days. Walking Habit Plan: OS says fixed weekly step targets, no progression. Page uses that.
- **Personal challenge (lock + help):** Appears in Challenges tab. Auto-sync or manual. **Only the employee can stop / quit.** HR cannot stop, create, or modify plans. Admin visibility is a read-only “ongoing programs” report. No completion certificate (unlike HR-run challenges).
- **Enablement (lock):** Select-partner / ops-enabled as a whole. Do not publish the ~11-company internal figure. Lite Mode: Programs tab only if a section is enabled; Lite clients get none by default.
- **AI (lock):** No “AI-personalized training plans.” OS FAQ mentions optional AI pace distributions. VERIFY. Not a headline. Omitted.
- **Content Library (lock + OS health-content-library + bite-sized-content):** Types: Article, Video, Podcast, Webinar, Health Bites (2–3 min micro-lessons). Content-as-task: watch / read / complete bite. Quizzes optional; radio / checkbox; all-correct-to-pass. Health Bites log `activity_id 1015`; pass or fail both still log.
- **Targeting (lock):** Demographics (age, gender, health profile). **Not activity level.** OS content library still lists activity level as a filter. Flagged. Page follows lock.
- **Admin (lock):** Self-serve CRUD for articles, videos, podcasts, quiz questions, categories (Programs → On-Demand Content) once Programs is on. Ops-required: Marketplace, Health Bites creation (API-only, no dashboard UI), multi-language versions, demographic targeting.
- **Marketplace (lock + help):** Partner offerings, external links + disclaimer. One brief mention.
- **Web:** Content library has a limited web view. Do not imply full web parity for training-plan enrollment (mobile).
- **Proof:** None. Do not invent completion %. Do not reuse WHO or IBS mood / mental challenge-task numbers.

### Conflicts left unresolved (not silently fixed)

1. Help: “9 plans” without 2/7 split. Lock: 2 available / 7 coming soon. Page uses lock.
2. OS content targeting includes activity level. Lock: health profile, not activity level. Page uses lock.
3. OS FAQ: optional AI pace. Lock: VERIFY, no AI-personalized headline. Omitted.
4. Do not publish ~11-company enablement figure.

## Why this structure

Two bands, two palettes, two catalogs. Training Plans first. Content Library second. Do not blend.

| Section | Job |
|---|---|
| Hero + campus photo + 2 / 7 chip | First screen: two live plans, not a huge catalog. |
| Training Plans band | 2 available, 7 coming soon, 3 questions, next Monday, personal challenge, employee-quit, no certificate. Journey shot. |
| Contrast vs HR challenges | Personal / no certificate vs admin-run / competitive / certificates. |
| Content Library band | Types, content-as-task, 1015, health-profile targeting. Challenge shot. |
| Marketplace one-liner + gates | Ops vs self-serve. Lite default none. |
| No proof band | Lock: none. |
| 3 FAQs + siblings | Can HR stop a plan. Certificates. Activity-level targeting. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** Same chrome. `../styles/enterprise.css`. Current mega item: Personalized programs. Generated campus-walk photograph plus the two assigned CDN shots. Training Plans band and Content Library band must not look like one card grid.

## Copy deck

**Title:** Structured workplace wellness plans | Vantage Fit  
**Meta:** Two live training plans, seven coming soon. A personal challenge the employee can quit. Content as a challenge task. Not an HR-built catalog.

**Eyebrow:** Features · For employees  
**H1:** A plan, and the content to follow it.  
**Lead:** Two live training plans. A library of articles, videos, bites, and quizzes. The plan is a personal challenge. Watching or reading can be a challenge task.  
**Hero notes:** 2 live · 7 coming soon · Employee can quit  
**CTAs:** Book a walkthrough · See the two live plans

**H2:** Two available. Seven on the way.  
Couch to 5K. Walking Habit Plan. Coming soon named. VFit-managed, not admin-created.

**H2:** Three questions. Starts next Monday.  
Weeks 4–8. Days 3–6. Which days. Preview. Start Challenge. Couch to 5K ~1 km → 5–6 km, final-week taper.

**H2:** Personal. The employee can quit. HR cannot.  
Challenges tab. No certificate. Read-only ongoing-programs report.

**H2:** Content is a different system.  
Article, video, podcast, webinar, Health Bites, quizzes. Watch / read / complete bite as tasks. 1015 on bites. Targeting by health profile, not activity level.

**H2:** Who can change what.  
Select-partner for Training Plans. Self-serve content CRUD once Programs is on. Ops for Marketplace, Health Bites creation, multi-language, demographic targeting.

**FAQ**  
1. Can HR create or stop a training plan?  
2. Do training plans issue certificates?  
3. Can we target content by activity level?

**Close H2:** Give them a plan they own, and tasks they can finish.

## Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` platform rules + page 7
- `vc-os/vfit-os/specs/product/07-training-programs/training-plans.md`
- `vc-os/vfit-os/specs/07-training-programs/personal-training-programs.md`
- `vc-os/vfit-os/specs/06-content-education/health-content-library.md`
- `vc-os/vfit-os/specs/06-content-education/bite-sized-content.md`
- `vantagefit-astro/content/en/help/employee/programs/what-are-training-plans.md`
- `vantagefit-astro/content/en/help/employee/programs/how-do-i-start-a-training-plan.md`
- `vantagefit-astro/content/en/help/employee/programs/how-do-i-browse-content.md`
- `vantagefit-astro/content/en/help/employee/programs/what-is-bite-size-content.md`
- `vantagefit-astro/content/en/help/employee/programs/how-do-content-quizzes-work.md`
- `vantagefit-astro/content/en/help/employee/programs/what-is-the-marketplace.md`

## Assumptions

- The unnamed 3 coming-soon plans stay unnamed.
- AI pacing omitted (VERIFY, not a headline).
- ~11-company figure unpublished.
- Marketplace is one sentence plus an ops tag.
- Content web view mentioned only as limited. Enrollment stays mobile.
- Org Wellness Score, IBS stats, and Wipro minutes are absent.

## Critic

Run after the mock.

- 2 live / 7 coming soon is unmistakable.
- HR cannot create, stop, or customize training plans.
- No training-plan certificate.
- Not AI-personalized.
- Targeting is health profile, not activity level.
- Two systems look like two systems.
- No invented proof. No Group A / Mental stats.
- Annual / select-partner / Lite gates visible.
- No em-dashes, exclamation marks, or banned filler.
- `../styles/enterprise.css` linked. Product shots + photograph present.

**Pass.** Marketing copy in `<main>` is ~618 words including mock labels (in the 450–750 band). Training Plans and Content Library are two separate bands. Images: two CDN product shots + campus-walk photograph + logos. Visual chrome matches Group B.
