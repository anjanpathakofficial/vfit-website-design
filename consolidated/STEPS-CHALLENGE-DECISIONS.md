# Steps Challenge solutions page — consolidated structure + decisions
_Best-of synthesis from the 4-model bake-off (Claude Fable, Kimi K3, GPT Sol, Grok) + our own solution-page template. Decided 2026-08-04. This is the information flow all Steps Challenge page versions should follow; the same skeleton generalizes to other solution pages._

## Where each idea came from
| Element | Source | Why we took it |
|---|---|---|
| Visual system (iPhone journey mock, participation-pulse card, formats tab-explorer, admin dashboard mock, testimonial band) | **GPT Sol** | Strongest, most product-real visuals; the look the team liked |
| Recognition opener ("A leaderboard is not participation") | **Ours** | GPT Sol jumps straight to product; the problem beat earns the promise |
| "Familiar story" problem→fix framing | **Kimi K3** | Expands recognition into 3–4 named problems typical challenges have |
| **Five formats incl. Custom / Multi-activity (27 task types)** | **Claude Fable / Kimi** | GPT Sol and Grok MISSED Custom — the most-used format. Fix. |
| **Data integrity / anti-fraud section** (trusted sources, one device, anomaly+GPS, 3-day buffer, manual-off) + flagged "source rejected" leaderboard visual | **Claude Fable** | The standout section; a real enterprise objection answered with proof |
| Auto-enrollment ("no signup drive"; audience rules; new hires auto-added) | **Claude Fable** | Removes the biggest participation-killer: manual sign-up |
| Recognition beyond the top 3 (badges from first 3,000 steps, certificates) | **Claude / Kimi** | Rewards the non-athletes — the whole participation thesis |
| "Private by choice" (leaderboard opt-out, wheelchair mode) + data residency | **Claude Fable** | Inclusion + privacy; strong for enterprise + accessibility |
| Dedicated trust/governance block + Measure-impact cross-link | **Ours** | Keeps privacy in one repeatable block; ties to the participation spine |
| Concise FAQ | **Kimi/Grok/GPT Sol (consensus)** | DECISION: keep FAQ on solution pages (objection handling + SEO). Homepage cut FAQ; solution pages are a different context. |
| Real proof numbers (Brazosport 86%, Tata 59%, Wipro 3x) | **Ours (approved)** | Only use approved figures; everything else labeled illustrative |

## Decision for THIS page (2026-08-04): GPT-Sol as the core
For the Steps Challenge specifically, the team preferred **GPT-Sol's version**, so the shipped page (`~/VFIT WORK/Vantage-Fit-Steps-Challenge-Consolidated.html`) uses **GPT-Sol's structure and verbatim copy as the core** (copy lifted from the live GPT-Sol page; em-dashes softened to commas to fit our voice). We add **only two things**: the **Custom multi-week 5th format** (GPT-Sol had 4) and **Claude Fable's Data-integrity section**. For this page, don't reintroduce the earlier restructured flow (familiar-story grid, separate trust section, Measure-impact cross-link) unless asked.

> **This is an example, not a hard-and-fast rule.** GPT-Sol won *here*; on another page a different model's structure or copy may be the strongest. The durable method is: run the variants, pick the best base **for that page**, keep the winning source's own copy verbatim where it's good, and graft in the best sections the others added. Do not treat GPT-Sol as the automatic default core for every page — re-evaluate per page.

## The consolidated information flow (the structure to follow — GPT-Sol core)
1. **Hero** — "A step challenge built to move the whole workforce." + iPhone journey mock + participation-pulse card.
2. **Rollout confidence** band — "Easy to join. Fair to run. Clear about data." 4 cards: Phone-first access · Local days, global program · Leaderboard privacy · Bounded HR visibility.
3. **Formats** — tab-explorer, "Choose the behavior you want to create." All five: Race, Streak, Journey, E-Marathon, **Custom multi-week** (ADDED).
4. **Designed for follow-through** — "Make the first step easy, and the next one visible." Sync radial (one primary source) + 4 numbered points + "Prefer progress without the pressure?" note.
5. **Data integrity** (ADDED — Claude Fable) — "A leaderboard your skeptics can audit." Trusted sources · one device · anomaly + GPS · 3-day buffer · manual off by default. Visual: leaderboard with a flagged "Source rejected" entry.
6. **Control for HR** — "Launch in minutes. Keep momentum. Leave with proof." 4-step workflow + admin dashboard mock (with a "Next action" nudge).
7. **FAQ** ("Questions before rollout") — ~4 concise questions.
8. **Closer** — "See the step challenge your workforce would actually join." + CTAs + 4 demo callouts.

> **Boss feedback (2026-08-04):** removed the **Customer-result section** (we won't have that much data for every solution), trimmed copy throughout, and cut the page length. Principles going forward: keep pages **lean, not text-heavy** — short one-line card/step descriptions, drop redundant intro ledes; a full **customer-result section is OPTIONAL**, include only where a real, approved story exists.

---
_Superseded earlier draft flow (do not use): familiar-story problem grid → built-to-join → for-HR → enterprise trust → where-it-leads cross-link → testimonial → FAQ. Kept here only for history._

## Guardrails (unchanged)
5 self-serve formats named correctly (Race/Streak/Journey/E-Marathon/Custom); ops-only formats (GPS Marathon, Level, Weight Burn, training plans) = AM-configured; only HIPAA-alignment + GDPR asserted; aggregate-only + count-only privacy; no wearable required; average scoring; sentence-case, no em-dashes, verb-led CTAs, HR is the reader; all non-approved figures labeled illustrative.

## How this generalizes
This flow = the solution-page template (`solution-page-structure.md`) with two program-page additions proven here: a **formats explorer** (§3) and, where trust is a buying objection, a **data-integrity section** (§5). Other "by program" pages reuse §1–4 + §7–11; §5 applies wherever fairness/fraud is a concern.
