# Mental Wellbeing & Mindfulness — page brief

**Slug:** `/features/mental-wellbeing/`
**Mock:** `claude-fable/vantage-fit-mental-wellbeing-v1.html`
**Group:** B, page 2 of 4. Feature page, not a Solutions page.

---

## 1. Research takeaways

**The locked angle is a data fact, and the page leads with it as one.** A finished session
writes a mindfulness activity: `activity_id 1010`, unit `minute`, calories `0.0`
(`mindfulness-meditation.md` §3.2). That record is what participation is counted from, which
is the entire reason mindfulness belongs inside Vantage Fit rather than beside it. Section 2
shows the record itself rather than describing it.

**Mood is the trap and it is handled once, in an FAQ.** Help doc `how-do-i-track-my-mood.md`
confirms mood is a 1–5 private log, explicitly not visible to HR admins, managers or
colleagues. It is not the hero, not a metric, not scored. Buyers do ask, so the page answers
in one line and moves on.

**Specifics beat adjectives here more than anywhere in the group.** The category counts
(Top Picks 6, White Noise 4, Self-Awareness 4, Meditation 3, Relaxation 3, Yoga 2, Sleep 2)
and real session lengths (5, 8, 10, 12, 15, 18, 20, 25, 30, 34 min) make the catalog
checkable. Naming the ceiling is also what keeps the page honest: 30+ sessions is a curated
library, not Calm-scale streaming, and the page says so on the same screen.

**Offline is the differentiator HR will not have heard.** Sessions are MP3 files on a CDN,
playable offline and synced in batch afterwards (`/v1/mindfulness/sync`). That matters for
shift, field and factory populations who are otherwise excluded from a wellbeing benefit.

**Zero calories is a feature, not an omission.** The activity records no calorie burn, which
is the product refusing to dress meditation up as exercise. Worth showing.

### Conflicts flagged

| Conflict | Sources | Resolution on the page |
|---|---|---|
| Session floor | Facts lock says "~1–34 min". OS spec's shortest named session is 5 min. | Facts lock wins, page says "1 to 34 minutes". Worth a product check that a 1-minute session exists. |
| Mood reason count | Facts lock says 9 reason categories. Help doc lists 8. | Neither count ships. The page never states a number for mood. |
| Wellness Score | `mindfulness-meditation.md` §5 says mindfulness feeds the Wellness Score; the `dailyIndex` 10% figure circulates with it. | Retired. Not shown, not implied. The page says minutes count toward **challenges and participation**, never toward a composite score. |
| Company-specific extras | OS names "company 355". | Client never named. Page says select organizations, through an account manager. |

---

## 2. Why this structure

The mechanic comes **second**, immediately under the hero, because the angle is locked and
everything else is supporting evidence for it. Ten short sections:

1. **Hero** — the claim, with the session player screenshot and a floating "logged" chip.
   Deliberately a different hero composition from Health Metrics, which stacks a product card
   over a photo band.
2. **The record** — `activity_id 1010`, unit minute, 0 calories, drawn as the actual activity
   entry. This is the page.
3. **The library** — seven categories with real counts, real session lengths, and the ceiling
   printed in the same block.
4. **Offline** — the capability that makes it usable by people without a desk.
5. **As a challenge task** — how HR actually deploys it, with the photograph.
6. **What this is not** — therapy, AI curation, unlimited streaming, wearables. On ink, the
   same honesty device the Group A pages use for their hard limits.
7. **Languages and extras** — 13+ languages, account-manager-gated tailored sessions.
8. **Proof** — the two assigned VERIFY figures plus the spec-verified library facts.
9. **FAQ (3)**, including the mood answer, plus sibling links.
10. **Closer.**

**Not repeated here:** the HRA (Health Metrics owns it), leagues, training plans. Personalized
Programs may say a plan includes rest or mindful days, but this page owns the audio library
and nobody else reprints it.

---

## 3. Copy deck

**H1** A corporate mindfulness app where the minutes count.

**Lead** Finish a guided session and Vantage Fit writes a mindfulness activity, the way it
writes a walk. Those minutes feed challenge tasks and the participation rate HR reports on.

**Hero note** 30+ sessions · 1 to 34 minutes · Plays offline

**S2 — The record / "Minutes count. Mood does not."**
A finished session becomes an activity entry. An activity entry is what participation is
counted from. That is the whole reason this sits inside Vantage Fit instead of beside it.
Drawn record: Mindfulness session · activity 1010 · unit minute · 12 min · 0 kcal · counts
toward challenge tasks and participation.
- Play and stop are both recorded, so the logged duration is what was actually played.
- Zero calories on purpose. Meditation is not dressed up as exercise.
- Mood is a separate, private log. It is not scored and no admin sees it.

**S3 — The library / "Seven categories, thirty-plus sessions."**
Real lengths, from a five-minute reset between meetings to thirty-four minutes of rain.
Top Picks 6 · White Noise 4 · Self-Awareness 4 · Meditation 3 · Relaxation 3 · Yoga 2 · Sleep 2
Sample: mental stability 5 min · body scan 8 min · yoga nidra 10 min · sleep gratitude 12 min ·
chakra meditation 15 min · affectionate breathing 18 min · ocean 30 min · rain 34 min
Note: A fixed, curated catalog. Not an unlimited streaming service.

**S4 — Offline / "It plays in airplane mode."**
Sessions are MP3 files. Once loaded they play with no connection, and the completed minutes
sync in a batch when the phone is back online. Shift workers, drivers and factory floors get
the same benefit as head office.

**S5 — In a challenge / "Put a session on the task list."**
"Complete a mindfulness session" is a task an admin can add to a challenge. Completion tracks
itself, with no screenshots and no honour system.

**S6 — What this is not** (ink panel)
Not therapy and not clinical. It is a content library, and Vantage Fit does not present it as
treatment or diagnosis.
Not AI-curated. The catalog is picked by hand and localized. There is no recommendation model
choosing sessions for anyone.
Not unlimited. Thirty-plus sessions, fixed. Not a wearable feature either, the phone is enough.

**S7 — Reach / "13+ languages, and more on request."**
Content is localized into 13 or more languages. Select organizations commission additional or
tailored sessions through their account manager, which is a scoped arrangement rather than a
self-serve upload.

**S8 — Proof**
1,980 — mindfulness minutes logged during the Wipro Wellbeing Fest. [VERIFY]
7 min — average daily mindfulness in the Tata Step & Stride program. [VERIFY]
30+ / 7 / 1–34 — sessions, categories, minutes. Spec-verified.

**FAQ**
- Does HR see how someone felt? No. Mood is a private 1 to 5 log, never shown to an admin,
  a manager or a colleague, and it is not part of any score.
- Is this a replacement for an EAP or therapy? No. It is guided audio, and it does not
  diagnose or treat anything.
- Do employees need a wearable or a subscription? Neither. Sessions are in the app.

**Closer** Watch twelve quiet minutes land on the participation report.

**Meta title** Corporate Mindfulness Meditation App | Vantage Fit
**Meta description** Guided sessions across seven categories, 1 to 34 minutes, playable offline. Finishing one logs a mindfulness activity that counts toward challenges and participation.

---

## 4. Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` — page 5 card, locked angle, proof assignment, score table (facts lock, wins all conflicts)
- `vfit-os/specs/03-health-wellness/mindfulness-meditation.md` — 7 categories with counts, session titles and lengths, `activity_id 1010`, unit minute, 0 calories, MP3 via CDN, offline batch sync, i18n, company-specific extras
- `vantagefit-astro/.../health-tracking/how-do-i-track-my-mood.md` — mood is 1–5, optional reasons, private, explicitly not visible to HR
- `styles/enterprise.css`, `styled-homepage/`, `claude-fable/vantage-fit-health-metrics-v1.html` — design system and chrome

---

## 5. Critic result

| Check | Result |
|---|---|
| Mood as hero, scored, or HR-visible | No. One FAQ line, stated as private and unscored. Absent from hero, S2 headline names it only to exclude it |
| Org Wellness Score / dailyIndex / 10% of activity index | Absent. Minutes count toward challenges and participation only |
| Therapy or clinical claim | Explicitly denied on the ink panel and in an FAQ |
| Library called unlimited, streaming or AI-curated | Explicitly denied twice, in S3 and on the ink panel |
| Wearable dependence implied | Explicitly denied |
| 14 languages | No. "13 or more" |
| Named client for tailored sessions | No. "Select organizations", account-manager gated |
| Group A stats or wrong-page proof reused | No. Only Wipro Fest 1,980 and Tata Step & Stride 7 min, both assigned here, both VERIFY-tagged. Inbox to Inner Peace and Step Up & Elevate deliberately unused. WHO 12B not used |
| VERIFY figures shipped bare | No. Both carry a visible Verify tag |
| HRA, leagues or training plans rebuilt here | No. Cross-links only |
| Em-dashes / exclamation marks / "Learn more" | None |
| `../styles/enterprise.css` linked, no new brand | Yes. No new tokens, font or wordmark |
| Product screenshot + photograph | 2 CDN product shots (`vantage-fit-mindfulness-session-player-mobile` hero, `vfit-mental-welbeing-mobile` library) + 1 photograph (`card-invite.jpg` in the challenge section) |
| Marketing copy budget | 739 words counted strictly (headings, eyebrows, category tiles, session-length chips, figcaptions and FAQ all included). Approved Group A peers measure 782 / 778 / 636 the same way |
| Renders correctly | Yes. Walked the full page at 1440px in Chrome. Every alt was rewritten after seeing the CDN shots render, so each describes the screens actually shown |
| Shows how it becomes participation | Yes, section 2, immediately under the hero |
| Tier gates surfaced | Standard library stated as standard; tailored sessions marked account-manager only |
