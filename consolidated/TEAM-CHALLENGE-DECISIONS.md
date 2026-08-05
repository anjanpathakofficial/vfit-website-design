# Team Challenge — consolidated (best-of) decisions

Best-of consolidation of the four bake-off Team Challenge variants, built in our shared design system and made SEO/AEO-first.

## What was taken from where
- **Content core: Claude Fable** — the most SEO/content-complete variant: the fair-scoring angle, the average-scoring math with a leaderboard visual, the accurate "teams are a *mode*, not a format" framing, deep privacy (what admins can/can't see + regional hosting), the real Tata Motors "Step Up & Elevate" proof, practical FAQ, and internal cross-links.
- **Problem beat: Kimi K3** — "Solo challenges crown the already-fit. Team challenges move everyone," with the three failure modes.
- **Team-setup framing: GPT Sol / Grok** — build squads three ways (dashboard, CSV bulk upload, captain-led).
- **Design system: ours (Poppins)** — same look as the shipped Steps consolidated page, so the site stays consistent. (Per-page rule: the winning base varies — for Steps it was GPT Sol; for Team it's Claude Fable.)

## SEO / AEO layer (per solution-page-seo-aeo-standard)
Keyword `<title>` ("Corporate Team Challenge Platform for HR"), meta description, canonical, Open Graph; inline JSON-LD (FAQPage + SoftwareApplication + BreadcrumbList); an answer-first "What is a corporate team challenge?" block; one H1; query-matched H2s; internal links. Keyword terms are interim (domain-informed) pending the SEO team's validated research.

## Accuracy
Team score = average (not sum); teams enabled on Custom/Journey/Streak, NOT Race; max team size set at launch; leaderboard opt-out still counts to the team; 3-day sync buffer; regional hosting (India/US/EU/UAE); HIPAA guidelines + SOC 2 Type II. Tata Motors figures are from a published case study — VERIFY approval before publishing. All app/dashboard figures illustrative.
