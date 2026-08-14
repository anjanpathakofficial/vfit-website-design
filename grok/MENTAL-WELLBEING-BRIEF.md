# Mental Wellbeing & Mindfulness

**URL:** `/features/mental-wellbeing/`  
**Mock:** `vantage-fit-mental-wellbeing-v1.html`  
**Angle:** It counts as participation (minutes, not mood).

## Page job

Prove the guided audio library is real and already on the activity log: 30+ sessions, 7 categories, 1–34 min, offline MP3 with later sync. Completing a session logs `activity_id 1010` (minutes, 0 calories) and can be a challenge task. Not therapy. Not mood. Not an org score.

**Reader:** US enterprise HR / CHRO / Benefits. **Primary CTA:** Book a walkthrough. **Secondary:** See a session.

## Research takeaways

Preferred the facts lock when sources disagreed.

- **Library (lock + OS mindfulness-meditation):** 7 categories: Top Picks, Meditation, Yoga, Relaxation, Sleep, White Noise, Self-Awareness. **30+ sessions, ~1–34 min.** Legacy per-category counts kept off the wall (Top Picks 6, Yoga 2, White Noise 4, Self-Awareness 4, Meditation 3, Relaxation 3, Sleep 2). Rain / ocean / jungle white noise up to 34 min is the long end.
- **Delivery (lock + OS):** MP3 via CDN. Playable offline. Batch sync later (`/v1/mindfulness/sync`). Phone / app only. No wearable required.
- **Participation through-line (lock + OS):** Completing a session logs mindfulness activity `activity_id 1010`, unit minute, 0 calories. Feeds challenges and participation. Assignable as a challenge task (“complete a mindfulness session”). Frame as minutes that count, not a standalone minutes score, and not the retired Wellness Score. OS still says sessions contribute to wellness scores. Flagged. Left off.
- **Languages (lock):** 13+. Never 14.
- **Extras (lock + OS):** Select organizations can request additional / tailored sessions via account manager. OS names company 355. Do not name the client.
- **Mood (lock + help mood):** 5-point scale, 9 reason categories, optional comment. Private. Not scored. Not HR-visible. Default: omit. Page: one private-perk line in gates only.
- **Not (lock):** Therapy / clinical. AI-personalized recommendations. Unlimited / streaming catalog. Wearable dependence. dailyIndex / 10% of activity index.
- **Proof (this page only):** Wipro Wellbeing Fest 1,980 mindfulness minutes (VERIFY). Case study `wipro-global-wellbeing.md`, April 7–20 2025. Optional: Tata Step & Stride 7 min avg daily (VERIFY). Inbox to Inner Peace 1,279 and Step Up & Elevate 9 min unused. WHO 12B unused.

### Conflicts left unresolved (not silently fixed)

1. OS / help still feed mindfulness into Wellness Score. Lock: retired. Left off.
2. OS names company 355 for extra sessions. Lock: do not name the client. Unnamed.
3. Help mood article exists and is real. Lock: not the hero. One private-perk line only.

## Why this structure

Different hero from Health Metrics’ sleep clock. Signature is the complete-session → activity-log mechanic.

| Section | Job |
|---|---|
| Hero + desk photo + minutes chip | First screen: minutes count. Mood does not. |
| 7 categories / 30+ / 1–34 | Catalog as facts, not an essay. |
| Complete → 1010 + player shot | Through-line. Challenge-task line. |
| Offline MP3 + later sync | Factory / field honesty. Library shot. |
| Languages + extras | 13+. Account-manager sessions. |
| What it is not | Not therapy. Not AI. Not unlimited. Mood private. |
| Compact proof | Assigned Wipro + Tata only, VERIFY. |
| 3 FAQs + siblings | Therapy, mood, Lite. Lateral Group B. |
| Close | Book a walkthrough / Compare the tiers. |

**Visual:** Same chrome. `../styles/enterprise.css`. Current mega item: Mental wellbeing & mindfulness. Generated desk-headphones photograph plus the two assigned CDN shots. No mood UI. No wellness-score screenshots.

## Copy deck

**Title:** Corporate mindfulness meditation app | Vantage Fit  
**Meta:** 30+ sessions, 1 to 34 minutes. Completing a session logs a mindfulness activity that counts toward the same challenges as steps. Not therapy. Not mood.

**Eyebrow:** Features · For employees  
**H1:** Minutes count. Mood does not.  
**Lead:** Finish a session and it logs a mindfulness activity. Same challenges. Same participation number as a walk.  
**Hero notes:** 30+ sessions · 7 categories · 1–34 min  
**CTAs:** Book a walkthrough · See a session

**H2:** Thirty-plus sessions. Seven shelves.  
Top Picks, Meditation, Yoga, Relaxation, Sleep, White Noise, Self-Awareness. About 1 to 34 minutes. A fixed, curated catalog.

**H2:** Finish it. It logs like steps.  
`activity_id 1010`, unit minute, 0 calories. Can be a challenge task. Not a standalone minutes score.

**H2:** Play offline. Sync later.  
MP3 via CDN. Batch sync when the phone is back. No wearable required.

**H2:** 13+ languages. Extra sessions on request.  
Account manager for tailored sessions. Do not name the client.

**H2:** A library. Not a clinic.  
Not therapy. Not AI-curated. Not unlimited streaming. Mood is a private perk if it exists on the phone. HR cannot see it.

**Proof:** Wipro Wellbeing Fest 1,980 min `[VERIFY]`. Tata Step & Stride 7 min avg daily `[VERIFY]`.

**FAQ**  
1. Is this therapy or a clinical program?  
2. Does mood feed participation?  
3. Is the library available in Lite Mode?

**Close H2:** Put the minutes on the number you take upstairs.

## Sources

- `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` platform rules + page 5
- `vc-os/vfit-os/specs/03-health-wellness/mindfulness-meditation.md`
- `vantagefit-astro/content/en/help/employee/health-tracking/how-do-i-track-my-mood.md` (privacy confirm; omitted from hero)
- Case studies: `wipro-global-wellbeing.md` (1,980 min); Tata Step & Stride 7 min avg daily via lock (VERIFY)

## Assumptions

- Category micro-counts stay off the wall. 30+ / 7 / 1–34 do the work.
- WHO 12 billion working days unused (VERIFY WITH PRODUCT if ever used).
- Mood: one private-perk line in the “not a clinic” panel, not a section.
- Extra sessions stay unnamed (no company 355).
- Org Wellness Score and dailyIndex formula are absent.

## Critic

Run after the mock.

- Minutes-as-participation is the hero. Mood is not.
- Not therapy. Not AI. Not unlimited / streaming.
- 13+, never 14.
- Assigned proof only, VERIFY. IBS / Inbox / Step Up unused.
- Org Wellness Score not shown.
- No em-dashes, exclamation marks, or banned filler.
- `../styles/enterprise.css` linked. Product shots + photograph present.

**Pass.** Marketing copy in `<main>` is ~577 words including mock labels (in the 450–750 band). Images: two CDN product shots + desk photograph + logos. Visual chrome matches Health Metrics / Activity Tracking.
