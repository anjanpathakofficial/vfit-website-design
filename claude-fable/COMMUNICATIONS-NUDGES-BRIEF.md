# Communications & Nudges — build brief

**Page:** `/features/communications-nudges/`
**Mock:** `claude-fable/vantage-fit-communications-nudges-v1.html`
**Group:** C, page 3 of 3 (For HR teams)
**Angle:** Re-engage the people who went quiet. (Framing device. Not a Vantage Fit measured result.)

---

## Research takeaways

1. **The interesting split is not email vs push. It is what you can send today vs what needs a call.** Help is unambiguous: publishing push, sending custom email, previewing templates and notifying a challenge are all self-serve, while every email *toggle*, the master switch, branding and reminder timing route through an account manager. That gate is the honest, differentiating content on this page, so it gets a full section rather than a footnote.
2. **The 13 lifecycle moments read better as a timeline than a list.** They are triggers on a single employee's arc: welcome, app intro, device connection, enrollment, challenge start, weekly progress, reminder, weekly summary, team invite, challenge invitation, event confirmation, completion, custom. Laying them on a rail also makes the "29 templates" figure legible: moments are the triggers, 29 is the template count.
3. **Challenge Reminder is off by default.** Help states this explicitly and gives the reason (spam risk on long challenges). It is the single most useful thing an HR buyer can learn from this page before launch, so it is called out on the timeline rather than buried.
4. **Nudge Inactive Users is a rule-based Recommended Action, and its send path is not specified.** The dashboard surfaces it beside "View Inactive Employees." Where it goes when clicked is undocumented. The page shows it as a shortcut with an explicit `[VERIFY]` marker on the send path, and never as a one-click send.
5. **Web is email-only.** Employees on the web app get emails, not push or an in-app bell. Push is mobile, iOS and Android, with deep-link routing. The page states the channel boundary rather than implying parity.

## Conflicts flagged (facts lock preferred)

- **Toggleable email count.** `admin-what-notifications-can-i-control.md` says "8 toggleable types," while `admin-what-emails-does-vfit-send.md` lists 13 send moments and the facts lock states **29 templates**. These count different things (toggles vs moments vs templates). The page uses 29 for templates and 13 for named moments, and does not print a toggle count.
- **Nudge Inactive Users send path.** Not specified anywhere in help or OS. Marked `[VERIFY]` on the page, in visible copy, not just in this brief.
- **Notifications spec mentions SSE and in-app bell.** `specs/09-admin-platform/notifications.md` lists four channels including in-app bell and web. The facts lock says web-app parity is Backlog: employees get emails on web, no push or bell. The page follows the lock and does not claim a bell.

## Why this structure

Five content sections:

| Section | Job |
|---|---|
| Hero | The quiet-employee framing, stated as framing. Photograph plus a branded-email fragment showing company logo and colours, which is what branding actually means here. |
| Channels | 29 templates, 34+ push types with deep links, 13+ languages, and the web-is-email-only boundary. Three counts, one row. |
| 13 moments | The lifecycle rail, with Challenge Reminder marked off by default. |
| Send it yourself vs ask | The gate section. Two columns, plainly labelled, no euphemism. |
| Nudge | Recommended Actions as rule-based links, with the `[VERIFY]` marker and the explicit "not AI" line. Challenge dashboard screenshot. |

No KPI cards from Admin Dashboard, no task catalogue from Builder, no dimension list from Targeting. Targeting is cross-linked for who receives a send.

## Copy deck

- **Eyebrow:** Features · For HR teams
- **H1:** Quiet employees do not need another all-hands email.
- **Lead:** Employee wellness engagement notifications run on 29 branded templates, 34+ push types and one shortcut that finds who stopped logging.
- **CTAs:** Book a walkthrough (primary) · See what you can send today (secondary)
- **Section heads:** "Three channels, one company voice." · "Thirteen moments on one employee's arc." · "What you send today, and what your account manager sets." · "The inactive-user shortcut is a rule, not a robot."
- **Closer:** See what lands in an employee's inbox.

## Proof used

**None.** The facts lock assigns no statistic to this page and forbids attaching Tata, Wipro or Brazosport. The "quiet 40%" idea appears only as an explicitly labelled framing device in a single hero note, never as a Vantage Fit measurement, and no percentage is printed as product data. `100+ organizations` is used on Program Builder only and is not repeated here. Numbers on the page are capability counts (29, 34+, 13, 13+), all from the facts lock.

## Images

| Asset | Placement | Type |
|---|---|---|
| `vfit-challenge-dashboard-desktop.png` (CDN) | Nudge section, large | Product screenshot |
| Branded email fragment (built HTML) | Hero | Product mock |
| `../styled-homepage/card-invite.jpg` | Hero photograph | Photograph |
| `../styled-homepage/card-participate.jpg` | Moments section | Photograph |
| `../styled-homepage/logo.png` / `logo-white.png` | Nav, footer | Wordmark (does not count) |

The email mock shows a subject line, a company logo placeholder and an accent colour. It does not show a segment-from-report picker, a per-type toggle UI, or any recipient's name.

## Meta

- **Title:** Employee wellness engagement notifications | Vantage Fit
- **Description:** 29 branded email templates, 34+ push notification types with deep links, and 13+ languages. See what is self-serve and what your account manager configures.
- **Primary keyword:** employee wellness engagement notifications (H1 area, title, opener)
- **Secondary:** corporate wellness program communications; wellness challenge reminder emails

## Critic pass

| Check | Result |
|---|---|
| "Quiet 40%" presented as a VFit stat | No percentage printed. The hero note says the framing is not a Vantage Fit measurement |
| Segment-from-report picker | Not designed, not claimed. The email mock has no audience picker beyond all users |
| Nudge described as one-click or automatic send | No. Marked `[VERIFY]` in visible copy and described as opening an admin screen |
| Recommended Actions or emails labelled AI | Explicitly labelled rule-based and templated, with a "not AI" line |
| Self-serve per-type email toggles claimed live | No. Toggles and the master switch sit in the account-manager column |
| Web push or in-app bell claimed | No. Web is stated as email-only |
| Per-employee notification preferences | Stated as company-level, not per person |
| Rich push (images, action buttons) | Not claimed. Push is described as text with deep-link routing |
| 14 languages | 13+ used |
| Challenge Reminder default | Marked off by default on the timeline |
| Org Wellness Score | Not present |
| Client stats attached | None |
| 27 task types or targeting dimensions reprinted | No. Cross-linked instead |
| HIPAA, SOC2, ISO, GDPR claimed | No |
| `../styles/enterprise.css` linked | Yes. No new tokens, brand face or primary colour |
| Product screenshot + photograph | One large screenshot, one built email mock, two photographs |
| Em-dashes, exclamation marks, "Learn more" | None |
| Marketing word count outside chrome | 597, excluding labels inside the drawn email mock and moment rail |
| Links up and laterally | `/features/`, Program builder, Audience targeting, Admin dashboard |

## Sources

- `FEATURES-HR-REMAINING-BRIEFS.md` (facts lock, page 11)
- `vantagefit-astro/content/en/help/admin/communication/admin-what-emails-does-vfit-send.md`
- `vantagefit-astro/content/en/help/admin/communication/admin-what-notifications-can-i-control.md`
- `vantagefit-astro/content/en/help/admin/communication/admin-how-do-i-preview-emails.md`
- `vantagefit-astro/content/en/help/admin/communication/admin-how-do-i-send-custom-emails.md`
- `vantagefit-astro/content/en/help/admin/communication/admin-how-do-i-send-notifications.md`
- `vc-os/vfit-os/specs/09-admin-platform/notifications.md`, `specs/09-admin-platform/admin-dashboard.md` (Recommended Actions context)
