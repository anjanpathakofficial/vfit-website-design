# Vantage Fit — Enterprise feature pages (locked facts)

Companion to `FEATURES-ENTERPRISE-PROMPT.md`. This file is the **facts lock** for Group D: the three **Enterprise** pages.

**This bake-off run ships only these three pages.** Do not rebuild employee or HR pages. Do not build the Features hub (that is the last group).

Must-cover is a **proof checklist**, not a section outline. Fold items into the product UI, a photo, or a one-line label. Do not write a paragraph per bullet.

Section order is free. Word count, visual language, and images are locked by `FEATURES-ENTERPRISE-PROMPT.md`.

Source: Features Page Build Briefs (re-cut for variation bake-off), pages 12–14, **overridden** by later locks (Org Wellness Score retired; step normalization disabled globally; 65 activity types not 47+; no SOC2 / ISO / GDPR claims). Prefer this file over live marketing, help, and OS when they still show certification badges or a live org Wellness Score.

Already shipped (do not redo): Groups A–C and Admin Dashboard.

---

## What kind of page this is

These are **feature pages**, not solution pages. They prove an enterprise **capability** is real to a skeptical buyer: IT / security on Integrations (SSO half) and Security; HR / benefits on Health Data Upload and the wearables half of Integrations.

Do not write a generic "we take security seriously" essay. Do not invent certifications. A page that could be swapped onto any vendor with a find-and-replace has failed.

## The participation through-line

Everything an employee logs still counts toward the **same participation score and the same challenges**. On these pages:

- Integrations: a Garmin run or a phone-only step day lands on that same surface. SSO / HRIS is how people get onto the surface without a second account.
- Security: HR can trust the number because they never see a person's labs or HRA.
- Health Data Upload: a lab PDF becomes a private employee view and, if enabled, another log / risk-targeted challenge on that same surface. Lead with **availability**. Most buyers will not get this module.

## Copy bar (house rules)

- Lead with a specific insight. Never "security matters" or "wellness matters."
- Banned filler: "actually," "seamlessly," "one tap away," "your people," "empower," "holistic journey."
- No problem → solution openers. No symmetry for its own sake.
- Specifics do the work. "India, US, EU, or UAE" beats "global data centers."
- Sentence case. No em-dashes. No exclamation marks.
- Verb-led CTAs: "Book a walkthrough," "Talk to security," "Compare the tiers." Never "Learn more."
- Exact figures only. Never soften a VERIFY flag into a hard claim.

## Accuracy guardrails (platform-wide)

- **Android steps** = Google Fit / selected Android device source, **not** Health Connect. Health Connect is legitimate for Android *import* of workouts, sleep, weight, heart rate, calories, distance.
- **Android auto-tracked task sync source** is a live contradiction. Hedge or omit.
- **HIPAA**: only "BAA provisions for HIPAA compliance," scoped to the lab-report pipeline. Write "HIPAA-guideline aligned," never "HIPAA-compliant platform."
- **SOC2 / ISO 27001**: do **not** claim. Zero usable spec for this bake-off. Do not put badges on the page.
- **GDPR**: do **not** claim. "EU data residency available" is fine. Residency ≠ compliance.
- **13+ languages**, never 14.
- **AI honesty**: only Leadership Insights and **lab-report extraction** are AI. Recommended Actions are rule-based. Do not name OpenAI / ChatGPT.
- **Org Wellness Score is retired.** Do not claim it, show it, or list it as an annual-gated feature.
- **Step normalization / daily cap** exists in code but is **disabled globally**. Do not claim it is active. Trusted step-source filtering is real.
- **47+ activity types** is a stray number. If you mention manual logging, say **65** or omit (Group A owns the catalog).
- **BambooHR** is not in the code-verified HRIS list. Do not add it.
- Encryption specifics (AES-256, TLS versions, at-rest): **not in specs**. Do not invent.
- Audit logs: Backlog. Biometric app lock: Planned.
- **Activity level is not a targeting dimension.**
- **Mood** is private, not HR-visible.

## Shared enterprise physics (write once, reuse)

1. **Four regions:** India, US, EU, UAE. Chosen at onboarding. Cannot change later without migration.
2. **Company-scoped multi-tenant isolation.** Lab / health-risk queries are company-scoped.
3. **HR sees aggregates only.** Never an individual's health profile, HRA, lab values, or a health-risk name list. Count-only + disclaimer: *"The list of users is not displayed to protect individual privacy."*
4. **SSO = SAML 2.0**, integration-team setup, not a self-serve toggle.
5. **One primary device.** Fitbit / Garmin override Apple Health / Google Fit as the step source.
6. **No wearable required.** Phone sensors suffice for steps.
7. **Lite Mode** hides Health Data Upload entirely. Wearable connect still works; SSO/HRIS are not Lite questions.

## Proof hygiene (assigned — do not double-count)

Do not reuse Group A–C client stats (Tata / Wipro / IBS / Brazosport / 3X / mindfulness minutes).

- **100+ organizations** is the approved aggregate. Fine once per page, lightly.
- **Integrations:** no integration-specific client stat. Garmin "vs 15–30 min competitor polling" is **uncited** — soften to "real-time webhook push, not periodic polling" or mark `[VERIFY WITH PRODUCT]`. No competitor number.
- **Security:** no security-specific client stat. 100+ organizations only. Do not invent a downloadable SOC2 packet's contents.
- **Health Data Upload:** no named-client stat. Optional low-risk recency: "Q2 2025 launch with AI analysis capability." Never dress sample prevalence (Diabetes 65%, etc.) up as a client result.

## Live contradictions (do not silently resolve)

1. **Risk-targeted challenges** — one spec says usable; the same spec's roadmap says Backlog / used internally so far. Do **not** assert as shipped, client-facing. Phrase as available to Workforce-Health-enabled companies **or** mark `[VERIFY WITH PRODUCT]`.
2. **Biomarker count** — use **~104**, marked VERIFY (other docs say 100+).
3. **Org Wellness Score** — retired. Help still describes it.
4. **Step cap / normalization** — disabled globally. Do not claim it is on.
5. **Android task-sync source** — hedge or omit.

## Split of ownership

| Topic | Owner page | Other two |
|---|---|---|
| Wearables, one-primary-device, Garmin 60-day tokens, Fitbit not real-time, SSO/SAML, HRIS roster, provisioning, VC ecosystem SSO | Integrations & SSO | Two hard-separated modules on **one** page. Security mentions SAML as an auth fact only. Do not reprint the device catalog on Security |
| Multi-tenant isolation, residency, lockout / OTP / reset rules, what HR cannot see, Leadership Insights no-PII, account deletion, BAA scope | Security & Compliance | Integrations mentions region at onboarding only. Health Data owns lab privacy in depth |
| Lab upload, AI extraction, ~104 biomarkers, risk bands, org-level prevalence, count-only targeting, whitelist / annual, bulk SFTP = one company | Health Data Upload | Security mentions BAA + aggregate-only. Do not rebuild the lab pipeline on Security |

## Not in this run

- Features hub (next / last group)
- All employee and HR pages already built (href only)
- Surveys / eNPS, SOLI as standalone pages
- Splitting Integrations into two URLs (locked IA is one slug; two H2 modules)

---

# THE THREE PAGES

## 12. Integrations & SSO — `/features/integrations-sso/`

**Covers:** Wearables / device sync **and** SSO / HRIS / provisioning. Two personas. **Two clearly separated H2 modules.** Do not blend into one narrative.

**Angle:** *Works with what employees wear and what IT runs.*

**Primary keyword:** `employee wellness platform integrations`  
**Secondary:** "corporate wellness SSO," "wellness app HRIS integration," "wearable integration corporate wellness"  
BOFU / technical-evaluation intent.

**Must cover — Wearables & device sync**
- No wearable required. Steps via **Apple Health (iOS)** and **Google Fit (Android default)**.
- **Apple Health** (steps, workouts, weight, calories, sleep, heart rate, distance). **Apple Watch** automatic via paired iPhone.
- **Fitbit** (OAuth; steps / workouts / HR zones / sleep stages; historical sync up to 30 days; **not** real-time; syncs on app open + on-demand).
- **Garmin** (OAuth 1.0a, 3-step flow, **real-time webhook** push, daily + activity summaries + GPS routes, 50 MB payloads, historical backfill; the only real-time integration; tokens **expire after 60 days**).
- **Samsung Watch** as an Android device option. **70+** trusted third-party apps via Apple Health (Amazfit / Zepp, Mi Band, Huawei, Nike Run Club, Strava, etc.).
- One primary device at a time.
- Trusted step-source filtering. Do **not** claim the daily step cap / normalization is active.
- Vantage Circle ecosystem: shared user / company / auth; `FitnessConfig` with 15+ feature flags; an employee in R&R can reach VFit without a separate account.

**Must cover — SSO / provisioning / global access**
- SSO = **SAML 2.0** — Okta, Azure AD, OneLogin, Ping Identity, etc. IdP metadata exchange with the VFit integration team. **Not self-serve.**
- SSO uses the employer's IdP login / branding; the VFit sign-in screen keeps VFit branding. Full white-labeling is a separate build.
- Other auth: password; OTP (email; 4-digit mobile / 6-digit web; 10-min validity; SMS for select companies only); Google Sign-In (GSuite enterprise domains only); employee-ID login (whitelist).
- Provisioning: HR Admin CSV, SFTP, **HRIS** — Workday, DarwinBox, ADP, Zoho People, SAP, Infor ION, Synergita, Adrenalin, Workline, Knit. Most are client-specific. **Confirm readiness with the integration team.** Do not add BambooHR.
- Self-registration by work-email domain (on by default). Blocked examples exist (infosys.com, accenture.com, matthey.com, cognizant.com) — a one-line fact, not a headline.
- Region: India, US, EU, or UAE at onboarding.
- 13+ languages.

**Do NOT claim**
- Android steps via Health Connect.
- Wearable required. Fitbit as real-time / webhook.
- 14 languages. Full white-label login for non-SSO flows. SSO as a self-serve toggle.
- Biometric lock, QR-code sign-in, deep-link SSO from HRMS (Backlog / Planned).
- Withings / Polar / Oura / Whoop (Backlog).
- Manual step entry as a general feature (few companies; account-manager).
- Active step-cap / normalization.
- 47+ activity types.

**Tier flags:** Wearable connection — standard, employee self-serve. SSO / SAML, HRIS, SFTP — VC integration team, lead-time dependent. Manual step entry, SMS OTP, employee-ID login — whitelist. Region — standard at onboarding.

**Proof:** 100+ organizations. Soften Garmin to spec-supported "real-time webhook push, not periodic polling."

---

## 13. Security & Compliance — `/features/security-compliance/`

**Covers:** Multi-tenant isolation, data residency, auth-layer facts, what HR can / cannot see, HIPAA scope.

**Angle:** *Data your security team can sign off.*

**Primary keyword:** `employee wellness platform data privacy`  
**Secondary:** "corporate wellness platform security"  
Deliberately **not** "HIPAA compliant" / "SOC2 certified." Due-diligence-stage intent. Reader: IT / security, with HR in the room.

**Must cover**
- Company-scoped multi-tenant isolation (companyId throughout); lab / health-risk queries company-scoped.
- Data residency: India, US, EU, UAE; in-region endpoints; no post-setup region change without migration.
- Auth facts: SAML 2.0 SSO; lockout after **5** failed password attempts; reset links single-use, expire in **1 hour** (min **8** chars for reset, **6** chars for in-app change — two flows); OTP **10 min** (configurable per country); SSL pinning (TrustKit) on mobile; captcha on non-mobile web / admin.
- HR sees aggregate org / department metrics only. **Cannot** see individual health profiles or lab / biomarker data. Health-risk target = **count only** + privacy disclaimer.
- Leadership Insights: AI, **no PII**, aggregated buckets only, internal ML API. Read-only.
- Account deletion: name / email hashed, tokens cleared, historical activity / transaction records kept for reporting; company-configurable.
- HIPAA: "BAA provisions for HIPAA compliance," lab-report pipeline only. "HIPAA-guideline aligned."

**Do NOT claim**
- SOC2 or ISO 27001. GDPR compliance (residency ≠ compliance).
- Blanket HIPAA-compliant platform.
- Encryption specifics (AES-256, TLS versions, at-rest).
- Audit logs. Biometric app lock.
- Department / team drill-down on individual health data.
- Org Wellness Score as a gated annual feature.
- A "dedicated data center within your region" overclaim. Say four regional instances.

**Tier flags:** Region — standard at onboarding. SSO — VC integration team, all tiers. Wellness Leagues — annual. Health Insights — whitelist, narrower than "any annual plan." Do **not** list Wellness Score.

**Proof:** 100+ organizations. You may point at a "request a security packet" CTA without inventing the packet's certifications.

---

## 14. Health Data Upload — `/features/health-data-upload/`

**Covers:** Lab Reports (Workforce Health) — upload, AI extraction, risk flagging, privacy, risk-targeted challenges.

**Angle:** *Turn a lab report into a private, personal plan.* **Lead with availability.** Annual / whitelist. Strongest tier flag of the three.

**Primary keyword:** `workforce health risk analytics`  
**Secondary:** "employee lab report upload wellness platform"  
Narrow ICP. Do not target generic "corporate wellness app" keywords.

**Must cover**
- Employee upload: **PDF, JPG, or PNG** (images → PDF) on iOS, Android, or **web**. PDF max 30 MB. JPEG / PNG only for images.
- AI extraction, 5 stages: PDF extract → test-name match → insight → summary viz → recommendations. **No manual typing.** Do not name the vendor.
- Coverage: **~14 health areas across ~104 biomarkers** (VERIFY). Areas: diabetes / metabolic, heart, liver, kidney, thyroid, blood health / anaemia, Vitamin D / B12, inflammation.
- Risk levels: **low** (in range), **medium** (≤20% from nearest bound), **high** (>20%, or critical / alert / abnormal on the source). Vitamin D has its own bands (deficient / insufficient / sufficient / toxic).
- Suggestions are **general wellness guidance, not medical advice.** Disclaimer stays.
- Employee: Lab Reports history; permanent self-delete.
- HR: **org-level prevalence only** ("% of workforce flagged at risk" per health area). **Not** sliced by department / team / location. No screen or export exposes an individual's report.
- Private targeted challenge by health-risk cohort = **count only** + privacy disclaimer. Client-rollout status is **contradictory** — do not assert as generally shipped. `[VERIFY WITH PRODUCT]` or "for Workforce-Health-enabled companies."
- Intake: employee self-upload once enabled. HR / SFTP bulk is **one company (355)** — do not market as generally available.
- Hidden in Lite Mode.

**Do NOT claim**
- Department / team / location breakdown of lab-risk data.
- Broadly available bulk SFTP.
- OpenAI / ChatGPT by name.
- 100% extraction accuracy.
- Diagnostic / medical-advice framing.
- Full HIPAA compliance (BAA only).
- Recommended Actions as AI.
- Sample metrics (Diabetes 65%, Hypertension 45%, Heart 75%, Hormonal 58%, "65% normal range") as a real client result. If shown, label **sample**.

**Tier flags:** **Annual / premium, whitelist.** Lead the page with it: available for annual partners running health check-up programs; enabled per company by the account manager; currently limited to selected organisations. Bulk SFTP — one company.

**Proof:** no named-client stat. Optional: Q2 2025 AI analysis launch. 100+ organizations as generic trust only.

---

## Sibling URLs (for internal links only)

**Hub (do not build):** `/features/`

**This set (build these):**  
`/features/integrations-sso/` · `/features/security-compliance/` · `/features/health-data-upload/`

**Already built (href only):**  
`/features/admin-dashboard-analytics/` · `/features/program-builder/` · `/features/audience-targeting/` · `/features/communications-nudges/`  
`/features/activity-tracking/` · `/features/fitness-exercise/` · `/features/nutrition-hydration/`  
`/features/health-metrics/` · `/features/mental-wellbeing/` · `/features/wellness-leagues/` · `/features/personalized-programs/`

Each child page should link up to `/features/` and laterally to the other two enterprise pages. Security ↔ Health Data for BAA / aggregate-only. Integrations ↔ Security for SAML / residency.
