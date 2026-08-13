# Vantage Fit — For HR feature pages (locked facts)

Companion to `FEATURES-HR-PROMPT.md`. This file is the **facts lock** for the four HR feature pages. Product claims, must-cover items, do-not-claim items, tier flags, keywords, and accuracy guardrails here are mandatory.

**This bake-off run ships only Admin Dashboard & Analytics** (page 8). The other three page cards stay as sibling / facts context. Do not build them.

Must-cover is a **proof checklist**, not a section outline. Fold items into the product UI, a photo, or a one-line label. Do not write a paragraph per bullet.

Section order is free. Word count, visual language, and images are locked by `FEATURES-HR-PROMPT.md` (existing design system, lean SaaS page, real `<img>` assets).

Source: Features Page Build Briefs (re-cut for variation bake-off). Employee and enterprise pages are out of scope for this run.

---

## What kind of page this is

These are **feature pages**, not solution pages. A solution page sells an outcome ("cut absenteeism," "hit 70% participation"). A feature page proves a **capability** is real, specific, and honest. It answers "what exactly does this do, and can I trust it." Lead with the mechanic and the specific. Let the buyer connect it to their outcome. Do not turn a feature page into a generic benefits essay.

## The participation through-line

Vantage Fit's differentiator: **everything an employee logs counts toward the same participation score and the same challenges** — steps, a GPS run, a logged meal, a glass of water, a mindfulness session, a lab-report upload. Every feature page must show its capability plugging into that single participation surface. A feature only earns its page by showing *how it becomes participation*.

On HR pages this usually means: the admin surface measures, launches, aims, or nudges that same participation, rather than a parallel wellness story.

## Copy bar (house rules)

- Lead with a specific insight, not a category truism. Open on something only Vantage Fit's actual mechanics let you say. Never "wellness matters."
- Banned filler: "actually," "seamlessly," "one tap away," "your people," "empower," "holistic journey." Cut them on sight.
- No formulaic problem → solution clichés. Do not open every section with "The problem? … The solution?"
- No symmetry for its own sake. Three benefits do not need three identical-length cards.
- Specifics do the work. "27 task types" beats "comprehensive builder." Numbers and named mechanics carry the page.
- Sentence case for all headings and buttons. No em-dashes (use commas, periods, or restructure). No exclamation marks.
- HR is the reader. Write to a US HR / benefits leader evaluating a platform: precise, skeptical, time-poor.
- Verb-led CTAs: "Book a walkthrough," "See the dashboard," "Compare the tiers." Never "Learn more," never "Click here."
- Exact figures only. Use the spec-verified number. Never round up. Never soften a VERIFY flag into a hard claim.

## Accuracy guardrails (platform-wide)

- **Android steps** = Google Fit / selected Android device source, **not** Health Connect. Health Connect is legitimate for Android *import* of workouts, sleep, weight, heart rate, calories, distance — never for the live step pipeline.
- **Android auto-tracked task sync source** is a live contradiction (guardrail says Google Fit; code-verified challenges table says Health Connect). If a page would name the Android task-sync source, hedge or omit. Do not silently pick one.
- **HIPAA**: only "BAA provisions for HIPAA compliance," scoped to the lab-report pipeline. Write "HIPAA-guideline aligned," never "HIPAA-compliant platform."
- **SOC2 / ISO 27001**: zero spec mentions. Do not claim either.
- **GDPR**: zero spec mentions. "EU data residency available" is fine. "GDPR compliant" is not.
- **13+ languages**, never 14.
- **AI honesty**: only two features are genuinely AI today — the admin's **Leadership Insights** and the **lab-report extraction** pipeline. **Recommended Actions are rule-based.** Never label rule-based features "AI." Conversational AI food logging and AI content recommendations are roadmap, not live.
- **Camera heart-rate**: "awareness-level, not medical-grade." Never "accurate" or "clinical."
- **Web-app parity**: most employee logging is mobile-only. Do not imply full web tracking. Lab-report *upload* is the web exception (enterprise page, not this set).
- **Lite Mode** strips to steps-only. Tier-flag every Full-Mode-only feature.
- **Encryption specifics** (AES-256, TLS versions): not in specs. Do not invent.
- **Activity level is not a targeting dimension.** Anywhere. Product spec ("health profile" / health-risk code) wins.
- **Mood tracking** is private, not scored, not HR-visible. Do not treat daily mood as an engagement metric HR can see.
- **Org Wellness Score is retired.** Do not claim it, show it, explain its 20/30/30/20 mix, or publish a 0–100 / 0–~108 ceiling. Help docs and OS specs still describe it — ignore them. The north-star number is **participation rate**. Do not market a Score Report or individual wellness scores. Wellness Leagues and Health Insights are separate surfaces, not the score.
- Any research point marked **VERIFY** ships only after sign-off. If you want it, phrase as a hypothesis and flag `[VERIFY WITH PRODUCT]`.

## Proof hygiene

- 100+ organizations is the approved aggregate trust signal.
- Every single-program client stat must be labeled to its exact program and marked VERIFY for currency before anyone would publish it.
- Do not reuse a stat as a general / cumulative benchmark across sibling pages.
- Do not invent customers, metrics, or capabilities.
- Do not borrow Tata / Wipro / IBS / Brazosport figures onto a page that has no causal link in the source.

## Live contradictions (do not silently resolve)

1. **League rolling-average window** — legacy 21-day vs code-verified "7 or 30 days typical." Use "a configurable rolling average window (7 or 30 days typical)."
2. **Android auto-tracked task sync source** — hedge or omit. (Step source is unambiguous: Google Fit / selected source.)
3. **Journey template count** — product spec says "3 built-in + custom" but only 2 are named. Say "2+ built-in journey templates" or VERIFY the third.
4. **Org Wellness Score** — retired. Help, OS, and old mocks still mention it. Do not ship it.
5. **Activity level as targeting** — not a dimension. Do not use it on Dashboard, Program Builder, Targeting, or Communications.

## What this set absorbed

- **Admin Dashboard & Analytics** absorbs the old standalone Reports & exports (Employee, Leaderboard, Transaction, Redemption, League reports — all CSV; League annual-gated). **Score Report died with the Wellness Score.** Do not absorb it as a live export.
- **Audience Targeting** is a newly-built page replacing a former dead link.
- **Communications & Nudges** is the fourth HR page (not Reports, not Health data upload).
- **Health data upload** is an **enterprise** page. Out of scope. Cross-link only if useful; do not build it.

## Not in this IA (do not invent pages or claims from these)

- Surveys / eNPS exist in product but have no `/features/` slug in the locked IA.
- SOLI multi-wallet / multi-currency surfaces inside the dashboard (Incentivization KPI, Transaction and Redemption reports). Do not spin up a rewards page. You may mention SOLI conversion where the dashboard brief requires it.

---

# THE FOUR PAGES

## 8. Admin Dashboard & Analytics — `/features/admin-dashboard-analytics/`

**Covers:** The Overview, insights, and all absorbed reports / exports. Org Wellness Score is retired — do not cover it.

**Angle:** *The participation number, without the spreadsheet.*

**Primary keyword:** `corporate wellness dashboard`  
**Secondary:** "employee wellness analytics dashboard"

**Must cover**
- Overview: 4 KPI cards with delta + sparkline — Enrolled Users, Active Users, Incentivization (rewards spend, SOLI-converted to admin currency), Participation Rate.
- Overview filters: date presets (7d / 30d / quarter / year / custom) + country, department, age group, gender.
- **Leadership Insights** — AI-generated via an internal ML API, **no PII sent** (only aggregated buckets); two columns, Key Insights + Focus Areas. Read-only observations.
- **Recommended Actions** — **rule-based** navigational shortcuts, max 5, priority-ordered (e.g. "View Inactive Employees (92 users inactive 30+ days)," "Nudge Inactive Users"). Links, not automations.
- "At a Glance" (This Month): Avg Steps, Active Minutes, Mindful Minutes, Avg Sleep, each with sparkline + trend.
- Admin sees **aggregate only** — never individual health profiles (weight, BMI, HRA). HIPAA-guideline aligned on this point.
- Absorbed reports (all CSV export): Employee Report (active / inactive / dormant, search / filter), Leaderboard CSV (per-challenge), Transaction Report (points / rewards, SOLI-converted, date + category filter), Redemption Report. League Reports also CSV / streamed — **annual-gated**. No Score Report.
- Certificates: automated per-campaign PDF generation / download.

**Do NOT claim**
- Leadership Insights are "predictive" or auto-change config (read-only).
- Recommended Actions are "AI" (rule-based).
- Admins can ever see an individual's health / biomarker data.
- **Org Wellness Score**, a composite wellbeing score, individual wellness scores, or a Score Report — **retired**. Do not show a locked/gated teaser for it either.
- A live admin audit log (Backlog).
- Self-serve toggling of Leagues / Health Insights (account-manager contract work).

**Tier flags:** Annual-client — Wellness Leagues, Health Insights (shown grayscale-locked with "Contact Account Manager" for others). **Flag:** Health Insights is narrower still — whitelist-gated in code, not merely "any annual client"; verify with product before pitching it alongside a plain annual plan. Standard — KPI cards, filters, Recommended Actions, Employee / Transaction / Redemption reports, certificates. Do **not** list Wellness Score as a gated annual feature. It is gone.

**Proof:** 100+ organizations (approved aggregate). Brazosport ISD 86% engagement — label as the Fit Wars campaign (2-week, May 2024), not a general dashboard stat. Wipro 3X participation — cumulative across 3 named 2025 challenges; **VERIFY** before tying to "dashboard" specifically (case study attributes it to the program).

---

## 9. Program Builder & Templates — `/features/program-builder/`

**Covers:** The self-serve challenge-creation wizard, formats, task types, templates, lifecycle, certificates.

**Angle:** *A challenge live before lunch.*

**Primary keyword:** `wellness challenge builder`  
**Secondary:** "corporate wellness program builder"

**Must cover**
- 5 self-serve formats via wizard: Custom Challenge (multi-week, drag-and-drop task config, weekly themes), Race Challenge (simple step competition), Journey Challenge (milestone-based), Streak Challenge (daily-target streaks), E-Marathon (steps-to-distance, default 1,000 steps = 1 km).
- Shared setup: name, description, image, dates, privacy, target audience, team config, point rewards, certificate config.
- **27 task types** (product spec's stated count — use as-is, don't recompute) spanning steps, distance, calories, active minutes, water, mood, sleep, weight, meal log, heart rate, yoga, aerobics, strength, meditation, squats, mindfulness, video watch, content reading, book reading, smoking cessation, HRA, lab report, bite-size content, adherence (custom habits), loggable activity (employer-branded).
- Drag-and-drop task config is **Custom Challenge only** (per-week, multiple tasks) — don't generalize to all 5.
- Named built-in Journey templates that genuinely exist: **"Backpacking through Europe"** (9 stations, cumulative to 70,000 steps) and **"Journey to 7 Wonders"** (7 landmarks, cumulative to 50,000 steps).
- Lite Mode: steps-only clients get Race format + step_count task only; deployable in 1–2 days; for one-time campaigns / strict data-privacy clients.
- Campaign lifecycle: 6 states (NOT_PROCESSED, NOT_STARTED, STARTED, ENDED, MANUALLY_STOPPED, PURGED), automated start / end on scheduled dates, plus admin override (reschedule, force-start-today, end-today-no-points).
- Certificates: per-challenge configurable (logo, seal, signature image, signer name / designation, custom description).

**Do NOT claim**
- A visual scheduling calendar UI (scheduling is start / end date fields + reschedule / force-start).
- Self-serve creation of Level, Marathon Event, Weight Burn, or Training Plans (ops-configured only).
- Freely-enabled monetary / point rewards (account-manager-gated; live for **only 1 company** today).
- Employees create / manage their own teams by default (ops-enabled toggle, off by default).
- Self-serve custom scoring formulas (ops-only).
- Team score = sum ("combined team total") — it's the **average** of member scores.
- A wearable is required for any format (auto-tracked tasks sync from phone / device; manual and content / adherence tasks need neither).
- **Journey template count:** do not say "3 named templates" — only 2 are named. Say "2+ built-in journey templates" or VERIFY the third.
- **Android task-sync source:** hedge or omit. Do not assert Google Fit or Health Connect for auto-tracked *tasks* until confirmed.

**Tier flags:** Standard / self-serve — Custom, Race, Journey (2 templates + custom), Streak, E-Marathon, Lite Mode. Select-partner / whitelist — monetary point rewards (1 company); Custom Journey template design (annual + sufficient order value + designer + setup call). Ops-only (any client, not a tier) — Level, Marathon, Weight Burn, Training Plans, custom scoring, user-team creation / management.

**Proof:** Wipro multi-week custom challenges + 3X participation — but 3X is cumulative across 3 distinct 2025 challenges; qualify it or avoid tying to the Custom format. 70,000-step Europe journey ≈ 50 km cumulative (approved illustrative, not a client result).

---

## 10. Audience Targeting — `/features/audience-targeting/`

**Covers:** Targeting dimensions, privacy-safe health-risk targeting, enrollment mechanics. (Was a dead link, now built.)

**Angle:** *Aim a challenge at exactly the right people — without ever seeing who they are.*

**Primary keyword:** `employee wellness program targeting`  
**Secondary:** "wellness challenge audience segmentation"  
Thin-volume; treat as a supporting page, not a primary SEO driver.

**Must cover**
- Target dimensions (confirmed in both trees): **country, city, department, gender, age range, language, health-risk code** (from HRA).
- Health-risk targeting returns a **count only**, never a name list — UI disclaimer: *"The list of users is not displayed to protect individual privacy."*
- **Targeted challenges are automatically marked private.**
- Enrollment: employees don't self-join; admin adds directly (search or bulk CSV) or audience-rule auto-enrollment matches and enrolls instantly. The legacy email-invite / accept flow still exists in code but is effectively dead — don't pitch invitations as the modern flow.
- Late-joiners: leaderboard score counts from join / add date forward; no retroactive credit or penalty.

**Do NOT claim**
- "Activity level" as a targeting dimension (doesn't exist in either tree — trap).
- Admins can see who's in a health-risk cohort (count-only, company-scoped, no export / screen exposes identities).
- Targeting below health-risk-code granularity ("target high-cholesterol people specifically") — it's risk *codes / categories* (diabetes, heart, liver, kidney, thyroid, blood health, Vitamin D / B12 deficiency, inflammation), not arbitrary biomarker thresholds.
- Self-join / browse-and-join (manual join / QR-code join is Backlog only).

**Tier flags:** Standard / self-serve — country / city / department / gender / age / language targeting. **Health-risk-code targeting depends on Workforce Health being enabled** for that company (itself whitelist / premium-gated) — frame as available only to Workforce-Health-enabled companies, not universally.

**Proof:** No targeting-specific client stat in approved sources. Do not borrow Tata / Wipro / IBS figures without a direct causal link. Use qualitative framing or mark `[Data point needed]`.

---

## 11. Communications & Nudges — `/features/communications-nudges/`

**Covers:** Lifecycle emails, push notifications, custom sends, nudges, branding, localization.

**Angle:** *Re-engage the quiet 40% automatically.*

**Primary keyword:** `employee wellness engagement notifications`  
**Secondary:** "corporate wellness program communications," long-tail "wellness challenge reminder emails"

**Must cover**
- **29 email templates** covering the full challenge / user lifecycle (this is the "how many" figure).
- The 13 named lifecycle email moments (for describing triggers, not the count): Welcome, App Introduction, Challenge Enrollment, Challenge Started, Weekly Progress, Challenge Completion, Challenge Reminder (24–72h before start), Weekly Summary, Team Invite, Challenge Invitation, Event Confirmation, Device Connection, Custom Email.
- **34+ push notification types** with deep-link routing (iOS + Android).
- Self-serve today: preview email templates (Configuration → Preview Emails); send custom branded email to all users (Community → Send Custom Email, attachments + template selection); bulk challenge notifications / invitations (Manage Challenge → Notify / Invite); publish push with preview + audience selection (Community → Publish Notifications).
- "Nudge Inactive Users" exists as a named rule-based **Recommended Action** (alongside "View Inactive Employees (92 users inactive 30+ days)"). The exact send mechanism it triggers (push vs email vs manual-send screen) is **not specified** — flag `[VERIFY]` before describing it as one-click / automatic.
- Master email switch (disable all system emails company-wide); individual types toggleable — but **all these toggles are account-manager-only today** (self-serve toggles are Backlog).
- Branding: custom banner, logo, background / accent color, program name, applied per company; full copy customization is account-manager-mediated.
- Localization: **13+ languages** via i18n. Custom T&C sections need client-provided translations.
- Reminder timing (24h / 48h / 72h before start) configurable, via account manager.

**Do NOT claim**
- A **"segment-from-report picker"** (selecting a filtered cohort and pushing it into a send flow) — not documented; the closest real things (Employee Report filter / export, and the "Nudge Inactive Users" label) are not confirmed wired together. Treat as unverified / aspirational; phrase any mention as a hypothesis with `[VERIFY WITH PRODUCT]`.
- Self-serve toggling of individual email types (account-manager-only; Backlog for self-serve).
- Web-app push or in-app bell notifications (Backlog; web gets emails only).
- Per-employee notification preferences (company-level only; Backlog).
- Rich push (images / action buttons) — Backlog.
- AI personalization of email / nudge content (templated + rule-based branching by timezone / language / branding).

**Tier flags:** Standard / self-serve — preview templates, custom email, challenge notifications / invitations, publish push, Recommended Actions. Account-manager-mediated (a process gate for all clients, not a contract tier) — master email disable, per-type toggles, custom banner / branding, reminder timing. No annual-only gating specific to this page.

**Proof:** No client-attributed notifications / nudges stat in approved sources. Do not attach Tata / Wipro / Brazosport figures without a causal claim the source supports. Use thematically relevant industry stats sparingly, never as if caused by notifications. The "quiet 40%" in the angle is a framing device, not a Vantage Fit measured stat — do not present it as a product result.

---

## Sibling URLs (for internal links only — do not build these in this run)

**Hub:** `/features/`

**For employees (7):**  
`/features/activity-tracking/` · `/features/fitness-exercise/` · `/features/nutrition-hydration/` · `/features/health-metrics/` · `/features/mental-wellbeing/` · `/features/wellness-leagues/` · `/features/personalized-programs/`

**Enterprise (3):**  
`/features/integrations-sso/` · `/features/security-compliance/` · `/features/health-data-upload/`

Each child page should link up to `/features/` and laterally to 2–3 siblings when it earns the click.
