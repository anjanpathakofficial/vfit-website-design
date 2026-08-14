# Communications & Nudges

## Page job

Prove that HR can support challenge participation with lifecycle email, mobile push, custom sends, and a rule-based inactive-user prompt. The page must distinguish self-serve work from account-manager changes and preserve the unresolved Nudge send path.

## Research takeaways

- Vantage Fit has 29 email templates across the user and challenge lifecycle.
- The 13 named moments are Welcome, App Introduction, Challenge Enrollment, Challenge Started, Weekly Progress, Challenge Completion, Challenge Reminder, Weekly Summary, Team Invite, Challenge Invitation, Event Confirmation, Device Connection, and Custom Email. These are trigger examples, not the template count.
- There are 34+ mobile push notification types on iOS and Android, with deep links to the relevant screen. The web app receives email, not push or an in-app bell.
- Self-serve admin work includes previewing templates, sending a custom branded email to all users with attachments and template selection, notifying or inviting challenge participants, and publishing push with preview and audience selection.
- “Nudge Inactive Users” is a rule-based Recommended Action beside the inactive-employee view. Its send destination and action path are unspecified, so any one-click or automatic-send language must remain `[VERIFY]`.
- Master and per-type email toggles, branding changes, full copy changes, and reminder timing at 24, 48, or 72 hours are account-manager-mediated today.
- Branding supports banner, logo, background/accent color, and program name. Vantage Fit supports 13+ languages. Clients provide translations for custom terms.
- “Quiet 40%” is a planning frame only and cannot appear as a Vantage Fit result.

## Structure and visual direction

1. Hero: a branded email preview, mobile push fragment, and invite photograph around a clearly labeled planning scenario.
2. Lifecycle pulse: 13 named trigger moments grouped into start, sustain, and close phases beneath the 29-template count.
3. Push proof: 34+ mobile types, deep links, and the required challenge dashboard screenshot.
4. Control split: precise self-serve actions beside account-manager-mediated controls.
5. Recommended Action: “Nudge Inactive Users” shown as rule-based with a visible `[VERIFY]` send path, never as a live send control.
6. Branding and language boundary, followed by CTA and sibling links.

The signature element is the lifecycle pulse, an operational communications map rather than a marketing email gallery. The page remains in the Vantage Fit Noto Sans, ink, coral, mint, canvas, rounded-panel, nav, and footer system.

## Copy deck

- H1: Give every quiet week a next step.
- Lead: Employee wellness engagement notifications connect challenge moments to the screen where participation resumes.
- Primary CTA: Book a walkthrough
- Secondary CTA: See the message lifecycle
- Scenario label: Planning frame, not a Vantage Fit result
- Key heads: Twenty-nine emails across thirteen moments. / Push opens the place to act. / Know which controls are yours today. / Nudge Inactive Users is a rule, not AI. / Brand the system. Localize the standard messages.
- Closing: Map the next challenge from welcome to completion.

## Meta

- Title: Employee wellness engagement notifications | Vantage Fit
- Description: Use 29 lifecycle email templates, 34+ deep-linked mobile push types, branded custom sends, and rule-based nudges to sustain participation.

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md`, Communications & Nudges card
- `vantagefit-astro/content/en/help/admin/communication/`
- `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-customize-branding.md`
- `vantagefit-astro/content/en/help/admin/settings/admin-how-do-i-change-language-settings.md`
- `vfit-os/specs/product/09-admin-platform/notifications.md`
- `vfit-os/specs/product/09-admin-platform/admin-dashboard.md`, Recommended Actions only

## Critic result

Pass. The page separates 29 templates from 13 named moments, states 34+ mobile push with deep links, does not claim web push, per-employee preferences, rich push, AI copy, or a report-based segment picker, and keeps the Nudge send path `[VERIFY]`. The quiet 40% is labeled as a scenario, not a metric. The page includes the assigned CDN product shot and real photography, links `enterprise.css`, and stays within the requested copy budget.
