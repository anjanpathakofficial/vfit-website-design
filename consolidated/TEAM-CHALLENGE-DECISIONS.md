# Team Challenge — consolidated (best-of) decisions

Best-of consolidation of the four bake-off Team Challenge variants, built in our shared design system and made SEO/AEO-first.

## What was taken from where
- **Headings & copy core: Grok + GPT Sol** — the team preferred their headings and copy. Grok: "Team challenges that pull everyone in, not just top athletes," "Average scoring keeps non-athletes in the game," "Build squads your way: org chart, spreadsheet, or captains," "Team mode on the programs people stick with," "Participation data your security team can review," "Straight answers for team programs." GPT Sol: the hero subhead, "Keep the competition moving without keeping a shadow spreadsheet" (HR workflow: build the field / read the standings / nudge / close with a record), "Tata Motors made wellness a team-owned habit," "See how a shared score can change who shows up."
- **Design system: ours (Poppins)** — same look as the shipped Steps consolidated page, for site consistency. (Per-page rule: the winning base varies — Steps was GPT Sol's copy; Team is Grok + GPT Sol.)
- **Not used:** Claude Fable was tried as the base first but the team found Grok/GPT Sol's headings sharper; Kimi's problem beat was dropped to match their structure.

## SEO / AEO layer (per solution-page-seo-aeo-standard)
Keyword `<title>` ("Corporate Team Challenge Platform for HR"), meta description, canonical, Open Graph; inline JSON-LD (FAQPage + SoftwareApplication + BreadcrumbList); an answer-first "What is a corporate team challenge?" definition, folded in as the first FAQ item (also in the FAQPage schema); one H1; query-matched H2s; internal links. Keyword terms are interim (domain-informed) pending the SEO team's validated research.

## Copy length
Supporting copy under the headings was trimmed ~27% per stakeholder feedback ("keep less text in the subsections"). Headings, FAQ answers, and the answer-first definition were kept intact for SEO/AEO.

## Accuracy
Team score = average (not sum); teams enabled on Custom/Streak/Journey, NOT Race; max team size set per challenge (guide 4-6, range ~3-10); build via dashboard/CSV/captain; leaderboard opt-out still counts to the team; regional hosting (India/US/EU/UAE); HIPAA/SOC 2/GDPR/ISO 27001/27701. Tata Motors figures are from a published case study — VERIFY approval before publishing. All app/dashboard figures illustrative.
