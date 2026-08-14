# Mental Wellbeing & Mindfulness — page brief

Intended URL: `/features/mental-wellbeing/` · Mock: `vantage-fit-mental-wellbeing-v1.html`

## Research takeaways

- Locked angle: minutes count as participation. Completing a guided session logs a mindfulness activity (`activity_id 1010`, unit minute, 0 calories) that feeds challenges and the participation surface exactly like steps. Mood is omitted entirely, per the default in the facts lock.
- Library facts: 30+ sessions across 7 categories (Top Picks, Meditation, Yoga, Relaxation, Sleep, White Noise, Self-Awareness), each roughly 1 to 34 minutes. Delivered as MP3 over CDN, playable offline, progress batch-syncs later.
- "Complete a mindfulness session" is a valid challenge task with automatic completion tracking. That is the proof the feature is not a bolt-on content tab.
- Content is localized in 13+ languages (never 14). Select organizations can request additional or tailored sessions through the account manager; the client is not named.
- Honesty set: this is a fixed, curated catalog, not unlimited streaming, not Calm-scale, not AI-curated, not therapy, and not wearable-dependent.

## Why this structure

Hero leads with the participation idea and the session-player shot, plus a photograph and a chip showing the log event ("12 min session complete, activity logged"). Then the library as a concrete category grid with honest counts beside the wellbeing shot, a "how minutes count" band that walks session to activity_id 1010 to challenge task, the two assigned VERIFY stats, an honesty band (not therapy, not unlimited, not AI, phone only), FAQ, done. Mood never appears.

## Copy deck (as shipped)

- H1: "Meditation minutes that count like steps."
- Lead: corporate mindfulness meditation app where finishing a session logs a mindfulness activity.
- Sections: "A small library, honestly sized." / "Minutes count. Mood does not." (participation mechanics) / proof band / "What this is not." / FAQ / final "Count the quiet minutes too."
- Full copy is in the HTML; marketing copy is ~600 words outside nav, footer, and mock labels.

## Sources

- All mechanics, tier flags, do-not-claim list, proof assignment: `FEATURES-EMPLOYEE-PROGRAMS-BRIEFS.md` (Mental Wellbeing card, platform guardrails, score table).
- Wipro Wellbeing Fest 1,980 mindfulness minutes: assigned proof, single program, marked VERIFY on the page.
- Tata Step & Stride 7-minute average daily mindfulness: assigned optional second proof, marked VERIFY on the page.
- 30+ sessions, 7 categories, 1 to 34 minutes: spec-verified, safe without a flag.
- "100+ organizations" approved aggregate, used once in the final band. WHO 12-billion-days stat not used (sourcing unverified).

## Meta drafts

- Title: `Corporate mindfulness meditation app | Vantage Fit`
- Description: `Vantage Fit's corporate mindfulness meditation app logs every completed session as a mindfulness activity, so minutes count toward challenges and participation.`

## Critic result

Pass. Checked: minutes-as-participation is the hero, mood never mentioned; activity_id 1010 framed as an activity log, not a score and not the retired Wellness Score; library described as 30+ curated sessions, never unlimited, streaming, or AI-curated; no therapy or clinical claim; no wearable dependence; 13+ languages, not 14; extras gated to account manager; both stats labeled to their exact programs and marked VERIFY, no Inbox to Inner Peace or Step Up & Elevate numbers mixed in; one product shot plus one photograph minimum met (two shots, one photo); no Org Wellness Score; no em-dashes, exclamation marks, or banned filler; copy under 750 words.
