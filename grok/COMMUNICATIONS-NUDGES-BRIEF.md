# Communications & Nudges

**URL:** `/features/communications-nudges/`  
**Mock:** `vantage-fit-communications-nudges-v1.html`  
**Angle:** Re-engage the quiet 40% automatically. Framing only. Not a measured VFit stat.

## Page job

Prove HR can re-engage people so logs keep happening: 29 email templates, 13 named lifecycle moments, 34+ deep-linked push types, a clear self-serve vs account-manager split, branded email, 13+ languages. Nudge Inactive Users is a rule-based Recommended Action. Send path is `[VERIFY]`. Not a Solutions outcome page. Not an AI comms product.

**Reader:** US enterprise HR / CHRO / Benefits.  
**Primary CTA:** Book a walkthrough. **Secondary:** See the templates (hero), Compare the tiers (close).

## Research takeaways

Preferred the facts lock when sources disagreed.

- **29 email templates** is the how-many figure (lock + OS notifications overview).
- **13 named moments (lock + OS emails.md):** Welcome, App Introduction, Challenge Enrollment, Challenge Started, Weekly Progress, Challenge Completion, Challenge Reminder (24 to 72 hours before start), Weekly Summary, Team Invite, Challenge Invitation, Event Confirmation, Device Connection, Custom Email.
- **34+ push types** with deep-link routing, iOS + Android. Web push and in-app bell are Backlog. Web gets emails only.
- **Self-serve:** Configuration → Preview Emails. Community → Send Custom Email (attachments + template selection, **all users** per lock). Manage Challenge → Notify / Invite. Community → Publish Notifications (preview + audience selection). Recommended Actions.
- **Account-manager (process gate, not a contract tier):** master email switch, per-type toggles (self-serve toggles are Backlog), custom banner / branding, reminder timing (24h / 48h / 72h). Full copy customization is account-manager-mediated.
- **Branding:** custom banner, logo, background / accent color, program name, applied per company.
- **Localization:** 13+ languages. Never 14. Custom T&C need client-provided translations.
- **Nudge Inactive Users:** named rule-based Recommended Action, alongside View Inactive Employees (92 users inactive 30+ days). Send path unspecified. Not one-click. Not automatic send. Not AI.
- **Quiet 40%:** framing for the gap buyers talk about. Not a Vantage Fit measured result. No notifications stat. No Tata / Wipro / Brazosport.
- Help custom-email article allows department / country filters. Lock: custom branded email **to all users**. Page follows lock. No segment-from-report picker.

### Conflicts left unresolved (not silently fixed)

1. Help notifications article lists 8 toggleable email types. Lock / OS use 29 templates and 13 named moments. Page uses lock counts.
2. Older OS notifications spec mentions SSE / in-app bell as live channels. Product notifications spec: web push and in-app bell are Backlog. Page follows lock / product spec.
3. Nudge send path (push vs email vs manual screen) is unspecified. `[VERIFY]`. Shown as a shortcut that opens a screen.
4. Org Wellness Score still appears as a Recommended Action example in OS admin-dashboard.md. Retired. Not shown.

## Why this structure

| Section | Job |
|---|---|
| Hero + desk photo + branded email fragment | First screen: a real email, not a report picker. Quiet 40% labeled framing. |
| 13 moments + 29 / 34+ proof | Catalog without reprinting the builder’s 27 tasks. |
| Self-serve vs account manager | Gates visible. Toggles are not self-serve. |
| Nudge Recommended Action | Rule-based. Send path unverified. Not AI. |
| Branding + 13+ languages + invite photo + campaign shot | Branding is AM-mediated. Photograph + CDN shot. |
| 3 FAQs + siblings | Web push, per-employee prefs, reminder timing. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** same chrome. Signature is the branded email mock plus the Nudge action, not KPI cards.

## Copy deck

**Title:** Employee wellness engagement notifications | Vantage Fit  
**Meta:** 29 email templates, 13 lifecycle moments, and 34+ push types for corporate wellness program communications. Book a walkthrough.

**Eyebrow:** Features · For HR teams  
**H1:** Notifications that restart the logs.  
**Lead:** Employee wellness engagement notifications cover 29 email templates and 34+ deep-linked push types. Buyers often call the gap the quiet 40 percent. That is framing, not a Vantage Fit measured result.  
**Hero notes:** 29 email templates · 13 named moments · 34+ push types  
**CTAs:** Book a walkthrough · See the templates

**H2:** Thirteen moments. Twenty-nine templates.  
Named list. Push is mobile, deep-linked. Web gets email only.

**H2:** What you send. What you request.  
Self-serve vs account manager. No self-serve per-type toggles.

**H2:** Nudge is a shortcut, not a send button.  
Rule-based Recommended Action. Send path not specified.

**H2:** Your banner. Their language.  
Branding fields. 13+ languages. Reminder timing via AM.

**FAQ**  
1. Can I turn off one email type from the dashboard?  
2. Do web users get push?  
3. Is Nudge Inactive Users automatic?

**Close H2:** Get the quiet people logging again.

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md` page 11 + shared physics
- `vc-os/vfit-os/specs/product/09-admin-platform/emails.md`
- `vc-os/vfit-os/specs/product/09-admin-platform/notifications.md`
- `vc-os/vfit-os/specs/product/09-admin-platform/admin-dashboard.md` (Recommended Actions; Score example discarded)
- `vantagefit-astro/content/en/help/admin/communication/admin-what-emails-does-vfit-send.md`
- `vantagefit-astro/content/en/help/admin/communication/admin-what-notifications-can-i-control.md`
- `vantagefit-astro/content/en/help/admin/communication/admin-how-do-i-send-custom-emails.md` (lock wins on all-users)

## Assumptions

- Custom email is marketed as all-users + template + attachments, not as report-segmented send.
- Publish push may select an audience (documented). That is not a segment-from-report picker.
- The 92-user inactive example is an OS sample string, labeled illustrative.
- Quiet 40% appears once, labeled framing.

## Critic

Run after the mock. Failures found in draft and fixed:

- Quiet 40% labeled framing. Not a KPI. Not a VFit result.
- Nudge is rule-based. Send path `[VERIFY]`. Not one-click. Not AI.
- No segment-from-report picker.
- No self-serve per-type email toggles.
- No web push or in-app bell claimed as live.
- No per-employee prefs. No rich push. No AI copy.
- 13+ languages, not 14.
- No 27-task reprint. No Org Wellness Score. No client stats.
- Photograph (desk) + assigned invite photo + CDN challenge dashboard + HTML email mock.
- No em-dashes or exclamation marks in copy.

**Pass.** Marketing copy in `<main>` is **~540 words** outside nav, footer, and mock labels. Quiet 40% is framed in the lead. Nudge send path is written as “not specified,” not as a one-click send. Verified at 1440 and 390.
