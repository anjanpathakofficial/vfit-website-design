# Remaining Solutions set notes (Grok)

Shipped 2026-08-11 against `REMAINING-SOLUTIONS-PROMPT.md`. Shared research first, then six pages in parallel with one visual system.

## Order shipped

| # | Page | Archetype | Brief | Mock |
|---|---|---|---|---|
| 1 | Wellness challenges | Library / flagship | `WELLNESS-CHALLENGES-BRIEF.md` | `vantage-fit-wellness-challenges-v1.html` |
| 2 | Health Risk Assessment | Program · data in | `HEALTH-RISK-ASSESSMENT-BRIEF.md` | `vantage-fit-health-risk-assessment-v1.html` |
| 3 | Workforce health insights | Program · data out | `WORKFORCE-HEALTH-INSIGHTS-BRIEF.md` | `vantage-fit-workforce-health-insights-v1.html` |
| 4 | Wellness rewards program | Program · action | `WELLNESS-REWARDS-BRIEF.md` | `vantage-fit-wellness-rewards-v1.html` |
| 5 | Wellness platform | Platform | `WELLNESS-PLATFORM-BRIEF.md` | `vantage-fit-wellness-platform-v1.html` |
| 6 | Solutions hub | Hub / chooser | `SOLUTIONS-HUB-BRIEF.md` | `vantage-fit-solutions-hub-v1.html` |

## Cross-page design principles

1. **One system, six jobs.** Shared tokens (`enterprise.css`), Noto Sans, nav mega-menu, Book a demo CTA. Section architecture varies by archetype (library browser, dual privacy UI, admin score dashboard, effort-receipt rewards, system map, chooser grids).
2. **Participation spine, honest per surface.** Join rates for challenges, voluntary accurate HRA for baseline, action on Org Wellness Score components, redemption tied to completed effort, platform as the system that makes participation measurable.
3. **Data in → data out → action is a chain, not a copy-paste.** HRA, insights, and rewards each own one job and link the others lightly.
4. **Product-real UI over illustration.** Phone assessment, admin aggregate cards, Org Score ring, wallet + catalog, library filter list.
5. **Never invent.** No fabricated KPIs or customers. Customer-result blocks omitted unless an approved story fits. Non-production UI labeled illustrative.
6. **Voice.** Sentence-case, no em-dashes in copy, verb-led CTAs, HR is the reader, lean sections.

## Research anchors

- Help docs (`vantagefit-astro/content/en/help/`) for HRA, workforce health, rewards, reports
- Challenge library data (`wellness-challenges.ts`) for program breadth
- OS specs: HRA, wellness score, points, reports
- Signed-off menu: `menu/vantage-fit-solutions-menu-preview.html`
- Visual peers: `styled-homepage/`, consolidated challenge pages, existing Grok program mocks

## Open product notes (do not block mocks)

- Journey format has no standalone Solutions mock yet (library card only).
- Workforce Health / Org Score activation is account-manager enabled; pages say so.
- Gift-card catalog brands and point expiry are tenant/contract specific.
- Wellness Marketplace (partner offerings) is not the points redemption catalog.
- Admin HRA aggregate UI is illustrative relative to evolving dashboard redesign.

## How to preview

Open any mock under `grok/` in a browser from this worktree root so `../styles/enterprise.css` resolves.
