# Vantage Fit — Remaining For-HR feature pages (locked facts)

Companion to `FEATURES-HR-REMAINING-PROMPT.md`. This file is the **facts lock** for Group C: the three remaining **For HR teams** pages.

**This bake-off run ships only these three pages.** Do not rebuild Admin Dashboard. Do not rebuild employee pages. Do not build enterprise pages or the hub.

Must-cover is a **proof checklist**, not a section outline. Fold items into the product UI, a photo, or a one-line label. Do not write a paragraph per bullet.

Section order is free. Word count, visual language, and images are locked by `FEATURES-HR-REMAINING-PROMPT.md`.

Source: Features Page Build Briefs (re-cut for variation bake-off), pages 9–11, plus later locks (Org Wellness Score retired; FEATURES-HR-BRIEFS.md). Prefer this file over help docs and OS when they still describe a live org-level Wellness Score, a third named Journey template, or self-serve email-type toggles.

Already shipped (do not redo):

- For HR — Admin Dashboard & Analytics
- Group A — Activity Tracking, Fitness & Exercise, Nutrition & Hydration
- Group B — Health Metrics, Mental Wellbeing, Wellness Leagues, Personalized Programs

---

## What kind of page this is

These are **feature pages**, not solution pages. A solution page sells an outcome ("hit 70% participation"). A feature page proves an HR **capability** is real: what the admin can launch, aim, or send, and what they cannot see.

These three pages sit under Features → **For HR teams**, next to the Admin Dashboard already built. The reader is a US HR / benefits leader. Write to someone who will launch a challenge before lunch, aim it without seeing names, and nudge the people who went quiet.

## The participation through-line

Everything an employee logs counts toward the **same participation score and the same challenges**. On these HR pages that means:

- Program Builder is how HR *launches* that surface (27 task types, five formats).
- Audience Targeting is how HR *aims* it without seeing who is in a health-risk cohort.
- Communications & Nudges is how HR *re-engages* people so those logs keep happening.

A feature only earns its page by showing how this admin action serves that one participation surface. Do not write three generic "engagement" essays.

## Copy bar (house rules)

- Lead with a specific insight, not a category truism. Never "wellness matters."
- Banned filler: "actually," "seamlessly," "one tap away," "your people," "empower," "holistic journey."
- No problem → solution openers. No symmetry for its own sake.
- Specifics do the work. "27 task types" and "29 email templates" beat "comprehensive comms."
- Sentence case. No em-dashes. No exclamation marks.
- HR is the reader. Precise, skeptical, time-poor.
- Verb-led CTAs: "Book a walkthrough," "See the dashboard," "Compare the tiers." Never "Learn more."
- Exact figures only. Never soften a VERIFY flag into a hard claim.

## Accuracy guardrails (platform-wide)

- **Android steps** = Google Fit / selected Android device source, **not** Health Connect.
- **Android auto-tracked task sync source** is a live contradiction. If a page would name it, hedge or omit.
- **HIPAA**: only "BAA provisions for HIPAA compliance," scoped to the lab-report pipeline. Write "HIPAA-guideline aligned," never "HIPAA-compliant platform."
- **SOC2 / ISO / GDPR**: do not claim. "EU data residency available" is fine.
- **13+ languages**, never 14.
- **AI honesty**: only Leadership Insights and lab-report extraction are AI. Recommended Actions (including "Nudge Inactive Users") are **rule-based**. Email / nudge copy is templated, not AI-personalized.
- **Activity level is not a targeting dimension.** Anywhere. Targeting is country / city / department / gender / age / language / health-risk code.
- **Mood** is private, not scored, not HR-visible. Program Builder may list "mood" as one of 27 task types (employees can be asked to log it). Do not imply HR can see mood answers or use mood as an engagement metric.
- **Org Wellness Score is retired.** Do not claim it, show it, gate it, or explain a 20 / 30 / 30 / 20 mix. North-star number is **participation rate**.
- **Web-app parity:** employees get emails on web, not push / in-app bell (Backlog). Most logging is mobile-only.
- **Lite Mode** = steps only. Race + `step_count` on the builder. Targeting and comms still exist; do not invent Lite-only comms products.
- Encryption specifics: not in specs. Do not invent.

## Shared HR physics (write once, reuse)

1. **Admin sees aggregates**, never an individual's health profile, HRA answers, lab values, or a health-risk name list.
2. **Health-risk targeting returns a count only**, with the disclaimer: *"The list of users is not displayed to protect individual privacy."*
3. **Targeted challenges are automatically marked private.**
4. **Team score is the average** of member scores, not the sum.
5. **Monetary / point rewards** are account-manager-gated and live for **1 company** today. Do not pitch them as freely on.
6. **Training Plans are not created in this builder.** They are select-partner / ops, employee-enrolled. Group B already owns that page.
7. **Org Wellness Score is gone.** Do not tease it as a locked annual feature.

## Proof hygiene (assigned — do not double-count)

Already used earlier. **Do not reuse** as general proof: Tata 6,400+ activities, Tata 472 GPS, Tata BMI 24, Wipro 12,236 squats, Wipro 163 yoga, Wipro Wellbeing Fest 1,980 min, IBS 100+ → 236, Brazosport 86% (Fit Wars, dashboard / program).

- **100+ organizations** is the approved aggregate. Fine once, lightly.
- **Assigned for this run:**
  - **Program Builder only:** 70,000-step Europe journey ≈ 50 km (approved **illustrative**, not a client result). Wipro 3X participation is **cumulative across 3 named 2025 challenges** — qualify it or skip tying it to the Custom format. Do not present 3X as a builder KPI.
  - **Audience Targeting:** no targeting-specific client stat. Do not borrow Tata / Wipro / IBS. Qualitative or `[Data point needed]`.
  - **Communications & Nudges:** no notifications stat. The **"quiet 40%"** in the angle is a **framing device, not a Vantage Fit measured result**. Do not present it as product data. Do not attach Brazosport / Tata / Wipro.

## Live contradictions (do not silently resolve)

1. **Journey template count** — product spec says "3 built-in + custom"; only **2 are named**. Say **"2+ built-in journey templates"** or VERIFY the third. Name only Europe and 7 Wonders.
2. **Android auto-tracked task sync source** — hedge or omit.
3. **Nudge Inactive Users send path** (push vs email vs manual screen) — **not specified**. `[VERIFY]` before "one-click" or "automatic send."
4. **Segment-from-report picker** — not documented. Do not design it as a live product.
5. **Org Wellness Score** — retired. Help `admin-what-is-org-wellness-score.md` is stale.
6. **Activity level as targeting** — not a dimension.

## Split of ownership (so the three pages do not repeat)

| Topic | Owner page | Other two |
|---|---|---|
| 5 formats, 27 task types, 2 named Journey templates, 6 lifecycle states, certificates, Lite = Race + steps | Program Builder | Targeting may say "when you create a challenge." Comms may say "when a challenge starts." Do not reprint the 27 types |
| Dimensions, count-only health-risk, private-by-default, admin-add / rule-enroll, late-joiner scoring | Audience Targeting | Builder mentions "target audience" as a setup field only |
| 29 emails, 13 named moments, 34+ push, self-serve vs account-manager toggles, branding, 13+ languages | Communications & Nudges | Builder mentions certificate / notify as a setup field only |

Do not rebuild Admin Dashboard Overview, KPI cards, or Leadership Insights. Href to `/features/admin-dashboard-analytics/`.

## Not in this run

- Admin Dashboard (already built)
- All 7 employee pages (already built — href only)
- Integrations & SSO, Security & Compliance, Health Data Upload
- Features hub
- Surveys / eNPS, SOLI as standalone pages
- Training Plans as a builder format (Group B)

---

# THE THREE PAGES

## 9. Program Builder & Templates — `/features/program-builder/`

**Covers:** The self-serve challenge-creation wizard, formats, task types, templates, lifecycle, certificates.

**Angle:** *A challenge live before lunch.*

**Primary keyword:** `wellness challenge builder`  
**Secondary:** "corporate wellness program builder"

**Must cover**
- 5 self-serve formats via wizard: Custom Challenge (multi-week, drag-and-drop task config, weekly themes), Race Challenge (simple step competition), Journey Challenge (milestone-based), Streak Challenge (daily-target streaks), E-Marathon (steps-to-distance, default 1,000 steps = 1 km).
- Shared setup: name, description, image, dates, privacy, target audience, team config, point rewards, certificate config.
- **27 task types** (use the stated count; do not recompute) spanning steps, distance, calories, active minutes, water, mood, sleep, weight, meal log, heart rate, yoga, aerobics, strength, meditation, squats, mindfulness, video watch, content reading, book reading, smoking cessation, HRA, lab report, bite-size content, adherence (custom habits), loggable activity (employer-branded).
- Drag-and-drop task config is **Custom Challenge only**.
- Named Journey templates: **"Backpacking through Europe"** (9 stations, cumulative to 70,000 steps) and **"Journey to 7 Wonders"** (7 landmarks, cumulative to 50,000 steps).
- Lite Mode: Race format + `step_count` only; deployable in 1–2 days; for one-time campaigns / strict data-privacy clients.
- Campaign lifecycle: 6 states (NOT_PROCESSED, NOT_STARTED, STARTED, ENDED, MANUALLY_STOPPED, PURGED), automated start / end, plus admin override (reschedule, force-start-today, end-today-no-points).
- Certificates: per-challenge configurable (logo, seal, signature image, signer name / designation, custom description).

**Do NOT claim**
- A visual scheduling calendar UI (start / end date fields + reschedule / force-start).
- Self-serve creation of Level, Marathon Event, Weight Burn, or Training Plans (ops-configured only).
- Freely-enabled monetary / point rewards (account-manager-gated; **1 company** today).
- Employees create / manage their own teams by default (ops toggle, off by default).
- Self-serve custom scoring formulas (ops-only).
- Team score = sum. It is the **average**.
- A wearable is required for any format.
- "3 named Journey templates."
- A single Android task-sync vendor.

**Tier flags:** Standard / self-serve — Custom, Race, Journey (2 templates + custom), Streak, E-Marathon, Lite Mode. Select-partner / whitelist — monetary point rewards (1 company); Custom Journey template design (annual + sufficient order value + designer + setup call). Ops-only — Level, Marathon, Weight Burn, Training Plans, custom scoring, user-team creation / management.

**Proof (this page only):** Europe journey 70,000 steps ≈ 50 km (illustrative). Wipro 3X only if labeled as three 2025 challenges, not a Custom-format result.

---

## 10. Audience Targeting — `/features/audience-targeting/`

**Covers:** Targeting dimensions, privacy-safe health-risk targeting, enrollment mechanics.

**Angle:** *Aim a challenge at exactly the right people — without ever seeing who they are.*

**Primary keyword:** `employee wellness program targeting`  
**Secondary:** "wellness challenge audience segmentation"  
Thin-volume; supporting page, not a primary SEO driver.

**Must cover**
- Target dimensions: **country, city, department, gender, age range, language, health-risk code** (from HRA).
- Health-risk targeting returns a **count only**, never a name list — UI disclaimer: *"The list of users is not displayed to protect individual privacy."*
- **Targeted challenges are automatically marked private.**
- Enrollment: employees do not self-join; admin adds directly (search or bulk CSV) or audience-rule auto-enrollment matches and enrolls instantly. The legacy email-invite / accept flow still exists in code but is effectively dead — do not pitch invitations as the modern flow.
- Late-joiners: leaderboard score counts from join / add date forward; no retroactive credit or penalty.

**Do NOT claim**
- "Activity level" as a targeting dimension.
- Admins can see who is in a health-risk cohort (count-only, company-scoped, no export / screen exposes identities).
- Targeting below health-risk-code granularity ("high-cholesterol people specifically") — it is risk *codes / categories* (diabetes, heart, liver, kidney, thyroid, blood health, Vitamin D / B12 deficiency, inflammation), not arbitrary biomarker thresholds.
- Self-join / browse-and-join / QR-code join (Backlog).

**Tier flags:** Standard / self-serve — country / city / department / gender / age / language. **Health-risk-code targeting depends on Workforce Health** (whitelist / premium). Frame as available only to Workforce-Health-enabled companies.

**Proof:** none. Do not borrow client stats.

---

## 11. Communications & Nudges — `/features/communications-nudges/`

**Covers:** Lifecycle emails, push notifications, custom sends, nudges, branding, localization.

**Angle:** *Re-engage the quiet 40% automatically.* (Framing only — not a measured VFit stat.)

**Primary keyword:** `employee wellness engagement notifications`  
**Secondary:** "corporate wellness program communications," long-tail "wellness challenge reminder emails"

**Must cover**
- **29 email templates** covering the full challenge / user lifecycle (this is the "how many" figure).
- The 13 named lifecycle email moments (triggers, not the count): Welcome, App Introduction, Challenge Enrollment, Challenge Started, Weekly Progress, Challenge Completion, Challenge Reminder (24–72h before start), Weekly Summary, Team Invite, Challenge Invitation, Event Confirmation, Device Connection, Custom Email.
- **34+ push notification types** with deep-link routing (iOS + Android).
- Self-serve today: preview email templates (Configuration → Preview Emails); send custom branded email to all users (Community → Send Custom Email, attachments + template selection); bulk challenge notifications / invitations (Manage Challenge → Notify / Invite); publish push with preview + audience selection (Community → Publish Notifications).
- "Nudge Inactive Users" exists as a named rule-based **Recommended Action** (alongside "View Inactive Employees (92 users inactive 30+ days)"). Send path **unspecified** — `[VERIFY]` before one-click / automatic.
- Master email switch and per-type toggles exist — **account-manager-only today** (self-serve toggles are Backlog).
- Branding: custom banner, logo, background / accent color, program name, applied per company; full copy customization is account-manager-mediated.
- Localization: **13+ languages**. Custom T&C need client-provided translations.
- Reminder timing (24h / 48h / 72h before start) configurable, via account manager.

**Do NOT claim**
- A **segment-from-report picker**.
- Self-serve toggling of individual email types.
- Web-app push or in-app bell notifications (Backlog; web gets emails only).
- Per-employee notification preferences (company-level only; Backlog).
- Rich push (images / action buttons) — Backlog.
- AI personalization of email / nudge content.
- "Quiet 40%" as a Vantage Fit measured result.

**Tier flags:** Standard / self-serve — preview templates, custom email, challenge notifications / invitations, publish push, Recommended Actions. Account-manager-mediated (a process gate for all clients, not a contract tier) — master email disable, per-type toggles, custom banner / branding, reminder timing. No annual-only gate specific to this page.

**Proof:** none. Do not attach Tata / Wipro / Brazosport.

---

## Sibling URLs (for internal links only)

**Hub:** `/features/`

**This set (build these):**  
`/features/program-builder/` · `/features/audience-targeting/` · `/features/communications-nudges/`

**Already built (href only):**  
`/features/admin-dashboard-analytics/`  
`/features/activity-tracking/` · `/features/fitness-exercise/` · `/features/nutrition-hydration/`  
`/features/health-metrics/` · `/features/mental-wellbeing/` · `/features/wellness-leagues/` · `/features/personalized-programs/`

**Enterprise (later):**  
`/features/integrations-sso/` · `/features/security-compliance/` · `/features/health-data-upload/`

Each child page should link up to `/features/` and laterally to 2–3 siblings. Prefer the other two pages in this set plus Admin Dashboard.
