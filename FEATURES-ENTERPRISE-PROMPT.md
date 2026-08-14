# Shared prompt — Vantage Fit enterprise feature pages (Group D)

Copy everything below the line into each model. Paths are **relative**. Do not hardcode machine-specific home directories.

**How to use:** paste this prompt **once** into Claude / Kimi / GPT / Grok. Each model ships **all three** pages in this group. Research shared enterprise physics once, then **loop page by page**. Stop when the three rows are done. Do not rebuild employee or HR pages. Do not build the Features hub.

This is **not** a Solutions bake-off. These pages prove an enterprise **capability** is real to IT / security and to HR.

The failed feature run shipped essay sites with invented brands, zero images, and fake certification badges. Admin Dashboard and Groups A–C recovered by staying inside the design system, keeping copy lean, and putting real photographs and product shots on the page. Repeat that. **Do not invent SOC2, ISO, or GDPR.**

This is the highest legal-risk group. If you are tempted to put a trust-badge row on Security, delete it.

---

You are an expert product-marketing designer for enterprise B2B SaaS (HR tech + IT due diligence). You design and implement high-fidelity UI **inside an existing design system**. You do not invent a new brand for a bake-off.

You have been hired to design **Group D** of the Features IA for Vantage Fit (http://www.vantagefit.io): the three **Enterprise** pages.

Vantage Fit is not a meditation brand. It is the system HR uses to turn everyday employee logs into one participation number, on infrastructure IT can review. These pages prove devices, identity, residency, and (for a few annual partners) lab-report upload.

If a page could be swapped onto a generic wellness vendor with a find-and-replace, you have failed. If Security looks like a HIPAA / SOC2 landing page, you have failed. If Health Data Upload hides that it is whitelist / annual, you have failed.

## Goal

Design the three Enterprise pages.

This is what a buyer opens from Features → **Enterprise**. It is not the homepage, not the hub, not a Solutions page, and not Groups A–C.

**Ship:** three high-fidelity mocks + three short briefs.

Do **not** invent a new page-type visual language. Do **not** write a page-type theory file. Do **not** rebuild any earlier page. Do **not** build `/features/` (hub is last).

## Pages to ship (this run only)

Work **in this order**. Finish brief + HTML for a page before starting the next.

| # | Page | Intended URL | Angle (the one idea, not a headline you must use) | Brief filename | Mock filename |
|---|---|---|---|---|---|
| 1 | **Integrations & SSO** | `/features/integrations-sso/` | Works with what employees wear and what IT runs | `INTEGRATIONS-SSO-BRIEF.md` | `vantage-fit-integrations-sso-v1.html` |
| 2 | **Security & Compliance** | `/features/security-compliance/` | Data your security team can sign off | `SECURITY-COMPLIANCE-BRIEF.md` | `vantage-fit-security-compliance-v1.html` |
| 3 | **Health Data Upload** | `/features/health-data-upload/` | Turn a lab report into a private, personal plan. Lead with availability | `HEALTH-DATA-UPLOAD-BRIEF.md` | `vantage-fit-health-data-upload-v1.html` |

Integrations is **one URL, two hard-separated H2 modules** (wearables vs SSO / HRIS). Do not merge them into one story. Do not split into two files.

**Done when:** all **3** briefs and **3** HTML mocks exist in your model folder, each page follows the design system, each has real images, and a time-poor buyer can scan each page in under a minute.

## Loop workflow (required)

1. **Shared research first (once)**  
   Read `FEATURES-ENTERPRISE-BRIEFS.md` (all of it). Open `grok/vantage-fit-admin-dashboard-analytics-v1.html` for density. Skim `grok/vantage-fit-fitness-exercise-v1.html` so you do not rewrite the device catalog from scratch — inherit Group A rules.

2. **Then loop pages 1 → 3**  
   For each row:
   - Re-read only that page card.
   - Decide a short SaaS structure. Must-cover is a checklist, not a section outline.
   - Write the brief.
   - Build the HTML mock.
   - Cross-link the other two enterprise slugs plus `/features/`.
   - Move on only after both deliverables exist.

3. **System consistency, not sameness**  
   Share nav, footer, tokens, type, and buttons. Security should feel more due-diligence than a fitness hero. Health Data must put the whitelist / annual flag in the first screen. Integrations must look like two modules, not one blended integrations soup.

4. **If you run long**  
   Prefer finishing all three at solid quality. If interrupted, resume from the first missing filename.

## Locked vs free (read this twice)

### Locked (mandatory)

- These three slugs, jobs, and angles. This order.
- Everything in `FEATURES-ENTERPRISE-BRIEFS.md`
- Feature pages, not Solutions pages
- Keywords from the brief (honest use; do not stuff; do not target "HIPAA compliant")
- Sentence case, no em-dashes, no exclamation marks, verb-led CTAs
- No invented customers, metrics, capabilities, **or certifications**
- **The existing Vantage Fit design system**
- **Real images**
- **Lean copy.** 450–750 words. The original 11-section / 1,300-word spine is **off**
- **Org Wellness Score is retired**
- **No SOC2 / ISO / GDPR / blanket-HIPAA badges**
- Integrations stays one page with two H2 modules

### Free (this is the bake-off)

- Section set and order (except Integrations: two distinct modules, each with its own FAQ if you use FAQ)
- How you compose each hero
- Whether you mention the Q2 2025 lab-AI recency line
- Schema / JSON-LD. Optional. If you use FAQ schema, Integrations should not blend wearables and SSO into one FAQ blob

## Design system (non-negotiable)

Match the system already in this repo.

- `styles/enterprise.css` — **link it**. Do not re-declare `--ink`, `--coral`, `--mint`, or a new font stack
- `styled-homepage/` — Noto Sans, coral CTAs, ink / mint / canvas, 22px radius, `.shell` / `.btn` / `.eyebrow` / `.nav` / `.mega`
- `grok/vantage-fit-admin-dashboard-analytics-v1.html` — primary visual peer for chrome and density
- `grok/vantage-fit-fitness-exercise-v1.html` — device facts already shipped; inherit, do not contradict
- `consolidated/vantage-fit-steps-challenge-consolidated.html` — quality bar, not a Solutions template

Live visual fallback: https://vantagefit.pages.dev/enterprise

**How to implement**

1. Each HTML mock **must** `<link rel="stylesheet" href="../styles/enterprise.css">`.
2. Load Noto Sans the same way `styled-homepage/index.html` does.
3. Reuse nav / footer / button / eyebrow / shell. Page-specific CSS in a small `<style>` block is fine. A second design system is not.
4. Update the Features mega-menu to the locked IA (below). **No SOC 2 / GDPR / ISO in the Enterprise column or footer.** No "activity level" targeting.

**Fail the page if any of these are true**

- No `../styles/enterprise.css` link
- A new brand face or a new primary color
- An invented wordmark instead of `../styled-homepage/logo.png`
- A trust-badge row with SOC2 / ISO / GDPR / HIPAA-compliant-platform
- The page would not be recognized as the same site as Admin Dashboard

## Images (non-negotiable)

A page with zero `<img>` tags fails. Fake SOC2 seals are not images. They are a fail.

**Local assets** (from inside your model folder):

| File | Use |
|---|---|
| `../styled-homepage/logo.png` | Nav wordmark |
| `../styled-homepage/logo-white.png` | Footer / dark band |
| `../styled-homepage/card-measure-generic.jpg` | Review / due-diligence photography |
| `../styled-homepage/card-participate.jpg` | Wearables / movement photography |
| `../styled-homepage/hero-man-popout-v2.png` | Optional |
| `../styled-homepage/card-invite.jpg`, `card-reward.jpg` | Optional |

**Required product shots** (CDN):

Integrations (wearables module):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772104740/product-images-hub/v-fit/vantage-fit-connected-devices-sync-mobile.png
```

Security (no dedicated security screenshot — photograph + a short HTML facts panel; do not use Wellness Score shots):

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1771579792/product-images-hub/v-fit/vfit-analytics-dashboard-desktop.png
```

Health Data Upload:

```
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194230/product-images-hub/v-fit/vantage-fit-ai-lab-report-summary-mobile.png
https://cdn.vantagecircle.com/image/upload/f_auto,q_auto,w_820/v1772194231/product-images-hub/v-fit/vantage-fit-workforce-biomarker-dashboard-desktop.png
```

Caption the biomarker dashboard as **org-level / sample** if numbers are visible. Never as a named client.

**Do not use** `vantage-fit-wellness-score-desktop.png` or `vantage-fit-wellness-score-trend-desktop.png`.

**Minimum bar, each page**

- At least one large product screenshot (or, on Security, a large HTML facts panel plus the analytics shot)
- At least one photograph, not a logo
- Every `<img>` has a real `alt`
- Do not put an individual's lab values, a named health-risk roster, or fake certification badges on screen

You may generate additional images if your tools allow it. Save them in your model folder. Generated "ISO 27001" seals fail the page.

## Density (this is a SaaS page)

- **Marketing copy budget:** about **450–750 words** outside nav, footer, and labels inside a product mock. Over ~800 words fails
- **H1:** one line, or two short lines
- **Lead:** one short paragraph
- **Section heads:** short and specific (`Four regions. No later move.` / `Count only. Never a name list.`)
- **FAQ:** optional, max 3 per page. On Integrations, do not mix wearables and SSO into one FAQ
- No "The problem? The solution?"

Match Admin Dashboard density, not a whitepaper.

## What each page must prove (without writing it all out)

From `FEATURES-ENTERPRISE-BRIEFS.md`. Show it.

**Integrations & SSO**

- Two modules. Wearables first or IT first — your call — but a hard break between them
- No wearable required. Apple Health / Google Fit. Fitbit not real-time. Garmin real-time, tokens expire at 60 days. Samsung. 70+ via Apple Health
- One primary device
- SAML 2.0, not self-serve. Named IdPs. HRIS list **without BambooHR**, with "confirm readiness"
- Four regions. 13+ languages. VC ecosystem single account
- Through-line: devices and identity exist so logs can become one participation number

**Security & Compliance**

- Four regional instances, not "a dedicated data center in your region"
- Multi-tenant isolation. Precise auth numbers (5 lockouts, 1-hour reset, 8 vs 6 char, 10-min OTP, TrustKit, captcha)
- HR sees the crowd, not the person. Count-only health-risk
- Leadership Insights: AI, no PII
- BAA for the lab pipeline only. HIPAA-guideline aligned
- No SOC2 / ISO / GDPR / encryption-spec inventions
- Through-line: the participation number is usable upstairs because individual health never leaves the employee

**Health Data Upload**

- **First screen states annual / whitelist / limited availability**
- PDF / JPG / PNG, web works for upload, 30 MB
- 5-stage AI extraction, no vendor name, not medical advice
- ~104 biomarkers, VERIFY, ~14 areas, risk bands including Vitamin D
- HR: org prevalence only, not department slices
- Bulk SFTP is one company. Risk-targeted challenges not asserted as generally shipped
- Hidden in Lite Mode
- Through-line: a lab upload is another private log on the same surface, for the few companies that have the module

## Important: do not treat the current marketing site as the source of truth

Live Security pages claim SOC 2 / GDPR / ISO. **Those claims are out of scope for this bake-off.** Do not copy them.

Locked Features mega-menu (mark the current page):

**For employees**

1. Activity tracking
2. Fitness & exercise
3. Nutrition & hydration
4. Health metrics
5. Mental wellbeing & mindfulness
6. Wellness leagues
7. Personalized programs

**For HR teams**

1. Admin dashboard & analytics
2. Program builder & templates
3. Audience targeting
4. Communications & nudges

**Enterprise**

1. Integrations & SSO
2. Security & compliance
3. Health data upload

No Reports & exports in HR. No SOC 2 / GDPR / ISO in Enterprise or footer.

## Path resolution (main tree vs model worktrees)

| Checkout | Typical path |
|---|---|
| **Main tree** | `…/gitcode/vfit-website-design/` |
| **Model worktree** | `…/gitcode/vfit-website-design/.worktrees/<model>/` |

**In-repo files:**

- `FEATURES-ENTERPRISE-PROMPT.md` (this file)
- `FEATURES-ENTERPRISE-BRIEFS.md` (**read this**)
- `grok/vantage-fit-admin-dashboard-analytics-v1.html`
- `grok/vantage-fit-fitness-exercise-v1.html`
- `styled-homepage/`, `styles/enterprise.css`, `consolidated/`

**Sibling research repos** (depth +1 under `.worktrees/`):

| Resource | From main tree | From `.worktrees/<model>/` | Remote |
|---|---|---|---|
| Marketing + help docs | `../vantagefit-astro` | `../../../vantagefit-astro` | https://github.com/VantageCircle/vantagefit-astro |
| HR admin dashboard | `../vc-dashboard-design` | `../../../vc-dashboard-design` | https://github.com/VantageCircle/vc-dashboard-design |
| Vantage Fit OS | `../vc-os/vfit-os` | `../../../vc-os/vfit-os` | https://github.com/VantageCircle/vfit-os |

If a sibling path is missing, walk up or clone. Do not invent claims. Pull latest `main` on each research repo before you start.

## Research sources

### 1. The facts lock (start here)

`FEATURES-ENTERPRISE-BRIEFS.md`. Prefer it over live marketing when they disagree.

### 2. Help docs

In `vantagefit-astro`:

- `content/en/help/employee/getting-started/` — devices, Health Connect vs steps, Lite Mode
- `content/en/help/employee/health-tracking/how-do-i-upload-lab-reports.md`
- `content/en/help/admin/settings/admin-how-do-i-enable-sso.md`
- `content/en/help/admin/workforce-health/`
- `content/en/help/admin/settings/admin-data-privacy-security.md`

### 3. Vantage Fit OS

- `FEATURE-INDEX.md`
- `specs/10-integrations/` — Fitbit, Garmin, VC ecosystem
- `specs/product/10-integrations/device-integrations.md` if present
- `specs/product/00-platform/auth-login-signup.md` — SSO, OTP, HRIS roster, residency
- `specs/03-health-wellness/lab-reports-biomarkers.md`
- `specs/09-admin-platform/admin-dashboard.md` — Leadership Insights no-PII only

Live Security copy and `wellness-score.md` are **not** sources of truth for certifications or Org Wellness Score.

## Audience

- **Integrations:** split brain — HR for wearables, IT for SSO / HRIS
- **Security:** IT / security reviewer, HR sitting next to them
- **Health Data:** HR / benefits at annual health-check enterprises
- **Primary CTA:** Book a walkthrough. Security may use "Talk to security" or "Request a security packet" as secondary, without inventing packet contents

## Lessons (do not repeat)

- Do not invent a visual language or skip `enterprise.css`
- Do not ship a page with no photograph
- Do not invent SOC2 / ISO / GDPR / AES-256 / TLS versions
- Do not say HIPAA-compliant platform
- Do not put Org Wellness Score on the page
- Do not claim Android steps via Health Connect
- Do not claim step-cap / normalization is active
- Do not add BambooHR
- Do not name OpenAI
- Do not market bulk SFTP as generally available
- Do not assert risk-targeted challenges as generally shipped
- Do not dress sample prevalence as a case study
- Do not blend wearables and SSO into one Integrations narrative
- Do not build the hub

## What we want from you

1. **Research** product truth (briefs + help + OS).
2. **Decide** a short SaaS structure per page.
3. **Write** accurate, scannable copy. Specifics over adjectives.
4. **Design** three high-fidelity mocks that look like Vantage Fit, with real images and no fake badges.

## Deliverables

Write into **your model folder at the repo root**:

- Claude → `claude-fable/`
- Kimi → `kimi-k3/`
- GPT → `gpt-sol/`
- Grok → `grok/`

For **each** of the three pages:

1. **`{PAGE}-BRIEF.md`** — Research takeaways, why this structure, copy deck, sources, meta title / description, critic result. Keep it short.
2. **`vantage-fit-{slug}-v1.html`** — High-fidelity mock. Links `../styles/enterprise.css`. UTF-8. Responsive. Opens from the model folder.

Do **not** add extra research dumps or any page outside the table.

## Critic list (run on every page before you stop)

Fail the page and fix if any of these are true:

- A capability, number, customer, or certification not in the briefs / help / OS is stated as fact
- SOC2, ISO 27001, GDPR-compliant, or HIPAA-compliant platform claimed or badged
- Encryption specifics invented
- Org Wellness Score shown or listed as gated
- Health Connect named as the Android **step** source
- Fitbit called real-time / webhook
- Step normalization / daily cap claimed as active
- 47+ activity types, or 14 languages
- BambooHR listed as HRIS
- SSO described as a self-serve toggle
- Wearable required
- Withings / Polar / Oura / Whoop claimed live
- OpenAI / ChatGPT named
- Bulk SFTP marketed as generally available
- Risk-targeted challenges asserted as generally shipped without hedge / VERIFY
- Sample lab prevalence presented as a client result
- Department / team slices of lab-risk data
- Individual lab values or a health-risk name list on screen
- Medical-advice / diagnostic framing
- Audit logs or biometric lock claimed live
- "Dedicated data center in your region" overclaim
- Em-dashes, exclamation marks, "Learn more," or banned filler
- Integrations is one blended narrative with no hard module break
- Health Data Upload buries annual / whitelist availability
- Visual language is a new brand, or `../styles/enterprise.css` is missing
- Fewer than one product screenshot (or Security facts panel) and one photograph
- Marketing copy ~800+ words outside chrome
- You built the hub or a page that is not in the table

## Quality bar

- Same site as Admin Dashboard
- A skeptical IT or HR buyer can tell, from the first screen, what is real and what is gated
- Claims traceable to the briefs, help, or OS
- Three pages share chrome and do not repeat each other's catalogs
- If something material is unclear, ask; otherwise assume and state it in the brief

Ask questions only if you need clarifications that would change the facts lock or the design system.

---

## First message to the agent (paste this alone if you want a short kickoff)

```
Build Group D only: Integrations & SSO, Security & Compliance, and Health Data Upload.

Read FEATURES-ENTERPRISE-PROMPT.md and FEATURES-ENTERPRISE-BRIEFS.md. Follow styles/enterprise.css and styled-homepage. Use grok/vantage-fit-admin-dashboard-analytics-v1.html as the visual density peer. Do not invent a new brand. Use the listed CDN product shots plus at least one photograph per page. Keep copy lean (450–750 words).

No SOC2, ISO, GDPR, or HIPAA-compliant-platform claims. Org Wellness Score is retired. Health Connect is not the Android step source. Integrations is one page with two hard-separated modules (wearables vs SSO/HRIS). Health Data Upload must lead with annual / whitelist availability. Do not name OpenAI. Do not market bulk SFTP as generally available. Do not build the Features hub or rebuild earlier pages.

Work in order. Write both the brief and the HTML into your model folder for each page before starting the next. Stop after the three pages.
```
