# Communications & Nudges — brief

**Slug:** `/features/communications-nudges/` · **Mock:** `vantage-fit-communications-nudges-v1.html` · **Angle:** re-engage the quiet 40% automatically (framing only, not a measured VFit stat).

## Meta

- Title: `Employee wellness engagement notifications | Vantage Fit`
- Description: `29 lifecycle email templates, 34+ push notifications with deep links, and rule-based nudges for inactive users. Corporate wellness communications in 13+ languages.`
- Primary keyword: employee wellness engagement notifications. Secondary: corporate wellness program communications, wellness challenge reminder emails.

## Research takeaways (facts lock)

- 29 email templates cover the full challenge and user lifecycle. 13 named trigger moments: Welcome, App Introduction, Challenge Enrollment, Challenge Started, Weekly Progress, Challenge Completion, Challenge Reminder (24–72h before start), Weekly Summary, Team Invite, Challenge Invitation, Event Confirmation, Device Connection, Custom Email.
- 34+ push notification types with deep-link routing, iOS and Android app only. Web gets emails, not push or an in-app bell.
- Self-serve today: preview templates (Configuration → Preview Emails), send custom branded email to all users (Community → Send Custom Email, attachments and template selection), bulk challenge notifications and invitations (Manage Challenge → Notify / Invite), publish push with preview and audience selection (Community → Publish Notifications).
- Account-manager-mediated for all clients: master email switch, per-type toggles, custom banner / branding (logo, background and accent color, program name), reminder timing (24 / 48 / 72h). Full copy customization is also AM-mediated. Self-serve per-type toggles are Backlog, so the page must not claim them.
- Nudge Inactive Users is a named, rule-based Recommended Action (alongside View Inactive Employees, "92 users inactive 30+ days"). Send path is unspecified: [VERIFY], so no "one-click" or "automatic send" claim. Not AI; copy is templated.
- 13+ languages, never 14. Custom T&C need client-provided translations.
- No segment-from-report picker. No per-employee notification preferences (company-level only). No rich push. No AI personalization.
- "Quiet 40%" is a framing device, labeled as such on the page. No client stat attaches to this page.

## Structure (why)

Hero with a branded-email mock fragment plus a push chip (the two things an admin actually sends) → 29 templates / 13 moments as chips → self-serve vs account-manager split panel → rule-based nudge section tied to Admin Dashboard's Recommended Actions, with the [VERIFY] hedge and the quiet-40% framing disclaimer → localization line → FAQ → siblings → final CTA. The challenge dashboard desktop shot anchors the nudge section so the page shows where the rule fires from.

## Copy deck (compressed)

- H1: `Re-engage the quiet ones, automatically.` Lead: lifecycle email and push fire on enrollment, start, progress, and completion, so people who stop logging get a reason to come back.
- Section 2: `29 templates. 13 named moments.` Moment chips; self-serve preview note.
- Section 3: `Self-serve today, account-manager for the rest.` Two-column panel.
- Section 4: `The quiet 40% gets a nudge, not a campaign.` Rule-based Recommended Actions; "quiet 40%" labeled framing; [VERIFY] on the send path; product shot; no-AI line.
- Localization one-liner: 13+ languages; client-provided translations for custom T&C.
- FAQ (3): per-type toggles (AM today), AI (no, rule-based and templated), web push (no, email on web).

## Images

- Hero: branded email mock (HTML fragment; allowed, no segment-from-report picker) + push chip.
- CDN: vfit-challenge-dashboard desktop (nudge section).
- Photo: `../styled-homepage/card-invite.jpg` (templates section).
- Logos: `../styled-homepage/logo.png`, `logo-white.png`.

## Proof

None assigned. "Quiet 40%" appears only as labeled framing. No Tata / Wipro / Brazosport figures.

## Sources

`FEATURES-HR-REMAINING-BRIEFS.md` (facts lock), `FEATURES-HR-REMAINING-PROMPT.md`, grok Admin Dashboard mock for chrome and density.

## Critic result

Checked against the critic list: no segment-from-report picker, no self-serve per-type toggles claimed, no web push or in-app bell, no per-employee prefs, no rich push, no AI labels, Nudge send path hedged with [VERIFY], quiet 40% labeled as framing, 13+ languages (not 14), no client stats, no em-dashes or exclamation marks, links `../styles/enterprise.css`, product screenshot + photograph + email mock present, copy inside 450–750 words.
