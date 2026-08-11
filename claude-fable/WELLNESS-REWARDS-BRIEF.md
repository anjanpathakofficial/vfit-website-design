# Vantage Fit: Wellness rewards program, page brief (v1)

**Page:** 4 of 6 in the Solutions set
**URL:** `/solutions/wellness-rewards-program/`
**Archetype:** Program page, Section ② "action" step
**Mock to build:** `claude-fable/vantage-fit-wellness-rewards-v1.html`
**Stylesheet:** `../styles/enterprise.css` plus one page-local `<style>` block. Nothing else.
**Chrome:** paste head, nav, trust band, related band, closer and footer from
`scratchpad/research/chrome.html`. Do not re-author them.

The builder should be able to produce the page from sections 5, 6 and 7 of this document without
writing a single new sentence. Every string that appears on the page is in here.

---

## 1. Research takeaways that decided the page

Each takeaway is the reason a section exists. Source paths use these prefixes:

- `help/` = `vantagefit-astro/content/en/help/`
- `product/` = `vc-os/vfit-os/specs/product/` (code-verified, Jun 2026)
- `sources/` = `vc-os/vfit-os/sources/`
- `rules/` = `vc-os/vfit-os/.claude/rules/`
- `dash/` = `vc-dashboard-design/` (design intent, never publishable)

### T1. There are two kinds of "points" and merging them breaks the page at sentence one

Leaderboard points are a per-challenge score. Vantage Points are the redeemable wallet balance.
Both are set in the same per-task **Points** field, and the wallet side is gated per tenant.
[`help/admin/challenges/admin-how-do-i-create-custom-challenge.md`,
`help/admin/challenges/admin-how-wellness-rewards-work.md`,
`product/08-rewards-marketplace/rewards-wallet.md`]

**Decision:** this page says **Vantage Points, wallet, redemption**. The word "leaderboard" appears
only twice on the page, both times about a **ranking bonus** or about **opting out**, never as a
reward mechanism.

### T2. Exactly five things emit wallet points, and the list is closed

Challenge task completion, Journey milestone, challenge completion, final leaderboard ranking
bonus, admin award. The code-verified spec names four; the help docs add the ranking bonus.
Nothing else emits wallet points.
[`product/08-rewards-marketplace/rewards-wallet.md` §02,
`help/employee/rewards/how-do-i-earn-points.md`,
`help/admin/challenges/admin-how-wellness-rewards-work.md` "When Points Are Credited"]

**Decision:** section S2 is a closed list of five, each carrying its real credit timing. This is
the most under-used honesty asset in the whole dossier, because every competitor page says
"employees earn points for being active" and that sentence is false here.

### T3. The things that look like earning sources and are not, are the anti-gaming argument

- Badges: *"Badges themselves do not award VFit points... Badges are recognition-only."*
  [`help/admin/challenges/admin-how-do-badges-work.md`]
- Marketplace: *"You cannot use your wellness points to buy Marketplace offerings."*
  [`help/employee/programs/what-is-the-marketplace.md`]
- Raw daily activity outside a challenge task: no earning event exists for it.
  [`product/08-rewards-marketplace/rewards-wallet.md`, by omission across all five events]
- HRA completion on its own: zero hits in any repo.
- Wellness Leagues, social feed, streaks as a standalone faucet: no documented emission.

**Decision:** S2 carries a visible "what does not earn points" strip. Naming the boundary is worth
more to a sceptical buyer than another benefit sentence.

### T4. The one number that cannot be published is the per-task rate

Three sources give three shapes for the same field: `0.50` USD in the rewards help article,
"multiples of 5" in the stale Draft specs, and a plain integer score in the challenge-creation
help article. Code-verified `product/**` does not restate the multiples-of-5 rule.
[`help/admin/challenges/admin-how-wellness-rewards-work.md`,
`vc-os/vfit-os/specs/08-rewards-marketplace/points-rewards.md` (Draft),
`help/admin/challenges/admin-how-do-i-create-custom-challenge.md`]

**Decision, followed under the precedence rule:** describe per-task values as admin-set. Never
state a rate, a currency unit on a per-task value, or a validation rule. This shapes the budget
mock: **currency symbols are allowed only on the three surfaces that really carry them** (the
Incentivization KPI, gift card denominations, and the Redemption Report), and never on a per-task
Points field. See §6.0.

### T5. USD-value monetary challenges are contract-gated to almost nobody

`product/02-challenges-gamification/challenges.md` says the toggle is available "via your Vantage
Fit account manager (**currently only 1 company**)". The help article calls it "Monetary Challenges
(Limited Availability)... a contract-gated feature available on a small number of accounts today".

**Decision:** never present USD-per-task configuration as the standard path. The page says point
values, not dollar values.

### T6. There is no budget pool, and saying so is the strongest thing on the page

Verbatim, from the dedicated rewards article:
*"Vantage Fit does not enforce a 'budget pool' cap at the challenge level. You allocate per-task;
total spend depends on how many employees complete each task. Use the leaderboard during the
challenge to monitor uptake."* [`help/admin/challenges/admin-how-wellness-rewards-work.md`]

Against that, three real controls exist:
1. Non-step tasks pay up to **100% of the target** and no further, so per-employee exposure per
   task is fixed at design time. [`help/admin/challenges/admin-how-do-i-create-custom-challenge.md`,
   `help/employee/challenges/how-does-the-leaderboard-work.md`]
2. The **Incentivization** KPI on the Overview shows reward spend to date in the logged-in admin's
   currency, converted via SOLI, filtered by date range and country.
   [`product/09-admin-platform/admin-dashboard.md`, `product/08-rewards-marketplace/soli-currency.md`]
3. The **Transaction Report** and **Redemption Report** are full ledgers, filterable, CSV
   exportable, and the docs' own advice is to archive them monthly "for budget reconciliation and
   audit purposes" and to "use historical redemption data to forecast future spending".
   [`help/admin/challenges/admin-how-do-i-view-redemption-reports.md`,
   `help/admin/reports/admin-what-reports-are-available.md`]

**Decision:** the budget section leads with the absence, then answers it. "Spend you design, then
reconcile" beats a fake cap. The word **cap** is never used about money on this page; it is used
only about task targets.

### T7. A budget module exists only as design intent, and must not be drawn

`dash/vc-data.js` proposes a Reward module with Fund / Supply / Catalog / Report, "Rewards Hub >
Budgets", "Rewards Hub > Quotas", a "Wellness budget left" tile, and seeded fiction (Acme, Priya
Sharma, 68% participation, Rs 4.2L budget left, 340 catalog items).

**Decision:** the "budget console" on this page is assembled **only** from shipped surfaces: the
challenge wizard's Certificates & Rewards step, the Overview KPI row, and the Redemption Report.
No invented tile, no budget gauge, no spend-remaining bar, no approval workflow.

### T8. The redemption flow is fully documented step by step, which is rare

Wallet icon, Redeem Points, catalogue by category, select card, choose denomination, Confirm,
points deducted immediately, delivered in-app and by email, then **My Gift Cards** with an
**Activate** button for vendors that need it. Redemption is instant, redemptions are final, and
the app blocks a denomination above the balance.
[`help/employee/rewards/how-do-i-redeem-points.md`,
`help/employee/rewards/how-do-i-view-my-wallet-statement.md`]

**Decision:** this is the page signature. Eight documented steps is enough to draw the whole
earn-to-redeem chain as connected product UI rather than four icons.

### T9. The wallet is a Lifestyle Spending Account, gift cards only by design

*"Vantage Fit's own wallet is a dedicated Lifestyle Spending Account (LSA)... the Vantage Fit
Lifestyle Spending Account is gift-cards only."* Merchandise in the VFit wallet is
`Roadmap: Not planned`. [`product/08-rewards-marketplace/multi-wallet.md`]

The legacy live page says "Gift Cards, Merchandise, or memorable Experiences". That is wrong and
gets rewritten. Category examples appearing in the Redemption Report UI (Merchandise, Experience
Vouchers) come from the shared report engine across the whole Vantage Circle economy, not from the
VFit wallet.

**Decision:** the catalogue section leads with gift cards, names the LSA, and states the boundary
out loud. Sourced catalogue breadth is **20+ categories**
[`sources/VFit-Marketing-Content-Compacted.md`, an approved source per `rules/data-accuracy.md`].

### T10. One wallet by default, ring-fenced if you want it

Vantage Fit points and Vantage Circle R&R points share one balance and one catalogue by default,
and deductions are symmetric. A company can instead run more than one named wallet, each with its
own catalogue, balance, history and reporting, set up through the account manager. Points cannot
move between wallets. [`product/08-rewards-marketplace/rewards-wallet.md`,
`product/08-rewards-marketplace/multi-wallet.md`,
`help/employee/rewards/how-do-i-earn-points.md`]

**Decision:** this is a budget-governance answer, not a features answer, so it sits in S5 as a
two-card row, not in the catalogue section.

### T11. SOLI is the global-equity answer, with one exact allowed phrasing

*"Our SOLI (Standard of Living Index) system ensures equivalent purchasing power across 190+
countries."* and *"Points have equivalent purchasing power, not equal numbers."*
[`product/08-rewards-marketplace/soli-currency.md`]

**Decision:** "190+ countries" appears exactly once on the page, attached to currency conversion.
Never as availability, never as catalogue reach, never as a customer footprint. Rates per company
per country are set with the account manager, not self-serve.

### T12. Tax has zero coverage in every repo

A grep for tax, taxable, fringe and payroll across `product/**` and all help docs returns nothing.

**Decision:** the FAQ answers the tax question **procedurally** (here is the record your payroll
team needs) and refers the reader to their own advisors. No tax statement of any kind.

### T13. Real controls exist against gaming, and one of them protects the payout specifically

Trusted step sources, one primary device at a time, GPS pace and vehicle checks, source tracking,
the 100%-of-target rule, and the **3-day buffer** before ranking bonuses pay out so backdated
syncs settle. Bulk point uploads require an **OTP to the initiating admin's email**, and *"only
the admin who initiated the upload can verify it."*
[`product/10-integrations/device-integrations.md`, `product/02-challenges-gamification/challenges.md`,
`help/admin/challenges/admin-how-do-i-upload-points.md`]

**Decision:** the fairness band uses only these. The step-cap number is never quoted (three sources,
three answers), and the Draft anti-cheat caps are never used.

### T14. Opting out of the leaderboard does not stop earning

*"You still earn points. Challenge completion rewards, milestone rewards, and task-based points
continue to accumulate in your wallet as normal."*
[`help/employee/challenges/can-i-opt-out-of-leaderboard.md`]

**Decision:** this is the participation north-star line for a rewards page. It answers "does this
only pay the already-fit" with a shipped product behaviour instead of a promise. It appears in the
FAQ and as a supporting line in S2.

### T15. The HRA can itself be a point-earning task

**Health Vitals (HRA)** is one of the 27 Custom Challenge task types, classed as event-based
("cannot be self-logged"), with the documented use "risk stratification, baseline profiling at
program launch". Lab Report Upload sits next to it.
[`help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md`]

**Decision:** this is how the page links back to the Health Risk Assessment page without claiming
that completing an HRA earns points on its own. The wording is always "when you set it as a
challenge task".

### T16. Employees are auto-enrolled, so earning starts without a hunt

*"Employees do not self-join challenges."* Audience rules enroll them.
[`product/02-challenges-gamification/challenges.md`, `help/employee/challenges/how-do-i-join-a-challenge.md`]

**Decision:** one sentence in S2. Required by the claims gate and it happens to be a real benefit
on a rewards page: the reward does not depend on the employee finding the program.

### Conflicts encountered, and which side this page took

| # | Conflict | Sources | Ruling applied here |
|---|---|---|---|
| C1 | Per-task value: `0.50` USD vs "multiples of 5" vs plain integer | help rewards article vs Draft specs vs help challenge-creation article | Publish neither. Values are admin-set. No currency unit on a per-task field. |
| C2 | Monetary challenges: standard path vs "currently only 1 company" | help article's own step list vs `product/02-.../challenges.md` | Contract-gated and rare. Never presented as standard. |
| C3 | Merchandise and experiences in the catalogue | Redemption Report category examples and legacy YAML vs `multi-wallet.md` | Gift cards only from the Vantage Fit wallet. The report categories belong to the shared engine. |
| C4 | OTP on employee redemption | `sources/VFit-Marketing-Content-Compacted.md` vs the dedicated redemption help article | Help docs win. No MFA claim on employee redemption. OTP is claimed only on admin points upload. |
| C5 | Inter-country transfer | wallet statement help article lists it as a transaction type vs `soli-currency.md` "there is no transfer screen" | Not featured at all. No transfer claim. |
| C6 | Lite Mode and the wallet | two help docs say rewards work vs `rewards-wallet.md` says hidden | Avoided entirely. Lite Mode is not mentioned on this page. |
| C7 | Overview KPI cards: 5-card help list vs 4-card code-verified row | `help/admin/workforce-health/admin-dashboard-overview.md` vs `product/09-admin-platform/admin-dashboard.md` | Code-verified four: Enrolled Users, Active Users, Incentivization, Participation Rate. Settled ruling, `ia-claims-proof.md` G3. |
| C8 | "Reward Hub" vs "Rewards Hub" | both spellings in help docs | Use **Rewards Hub** everywhere on this page and in every mock. |
| C9 | Step cap number | 25,000 (help) vs disabled (code-verified) vs 50,000 (Draft) | No number. The mechanism is not even named on this page; the 100%-of-target rule carries the fairness argument instead. |
| C10 | Wellness Score range | 0 to 100 vs ~108 in three dossier files | 0 to 100. Not referenced on this page anyway. |

---

## 2. Strategy

### 2.1 The buyer

Two readers, and this is the only page in the set where the second one is real.

- **Primary: the HR or total-rewards lead** who owns the wellness program and has been burned by a
  points program that either nobody redeemed or that quietly overspent.
- **Secondary, and decisive: whoever signs the reward budget.** Finance partner, CFO on an
  enterprise deal, or the total-rewards director. This reader does not care about badges. They care
  about a number they can forecast, a ledger they can reconcile, and evidence that the money is
  buying real behaviour.

No other page in this set has a finance reader. That is why this page shows money and the other
five do not.

### 2.2 The one thing this page must land

**Every point is bought by a task somebody actually completed, and you can price that before you
publish and reconcile it after.**

If a reader leaves believing only that "Vantage Fit has gift cards", the page failed. Gift cards
are table stakes. The differentiators are the closed earning list, the 100%-of-target rule, and the
two exportable ledgers.

### 2.3 Why this section order

The page runs as a money argument, not a feature tour:

1. **Hero** puts the wallet and the spend KPI side by side, so both readers see themselves.
2. **Where points come from** closes the list. Five events, and an explicit "not these". Credibility
   first, because the rest of the page is asking to be trusted with a budget.
3. **The flow** (signature) proves the promise end to end in product UI. Earning is worthless if
   redemption is a maze, and redemption is the best-evidenced part of the product.
4. **What points become** answers "is the catalogue any good, and is it fair in Manila and Munich".
5. **Budget** (signature) is the finance section. It leads with the honest absence of a budget pool,
   then gives three real surfaces, one per phase.
6. **Fairness** answers "will they game it" with mechanisms and a ledger, not with reassurance.
7. **Proof** is two approved quotes and nothing more, because no rewards metric is approved.
8. **Security** carries the standard trust band, re-pointed at money controls.
9. **FAQ** takes the five objections that survive.
10. **Related, closer.**

The economic argument is deliberately sequenced **after** the product proof. A CFO who has not seen
the flow will not believe the ledger.

### 2.4 What is deliberately left out, and why

| Left out | Why |
|---|---|
| A `.results-grid` stat strip | No approved rewards metric exists. Brazosport's 86% is an engagement rate for a challenge, not a rewards outcome. Padding it here would be a causal-attribution violation. |
| Any per-task rate, USD example, or points-to-currency ratio | T4. Three sources disagree, and the register forbids it. |
| Badges | They earn nothing. Putting a badge ladder on a rewards page is the exact legacy mistake being corrected. |
| Wellness Leagues, Wellness Score | No documented point emission, both account-manager gated. |
| The Marketplace | Explicitly cannot be paid for with points. It appears once, in the "does not earn" strip, so nobody assumes it is the store. |
| Inter-country transfer, send-a-gift-card-to-a-colleague | Transfer is not in VFit at all (C5). Sending cards is real but iOS and Android only, and it is a small delight next to a budget argument. Cut for focus. |
| Lite Mode | C6. |
| MFA on employee redemption | C4. |
| A formats explorer or a leaderboard mock | Those belong to the challenge pages. This page links to them. |
| A vendor or brand count, and a wall of retailer logos | No sourced figure. Ruling E2 in `rewards.md`: render the catalogue by its sourced category axis. |
| Points expiry as a feature | Contract-level only, and employee-facing expiry visibility is Backlog. It appears once, as an honest FAQ-adjacent line in S3's trailing note. |

### 2.5 The signature, stated plainly for the builder

Two things make this page structurally unlike its five siblings. If either is missing, rebuild.

- **S3, the flow rail.** Four connected product screens in one horizontal run: a task completing in
  the app, the point landing in the wallet statement, the catalogue, the confirmation and the
  delivered card. Not four icons. Not a `.steps` band. Each stage carries the shipped rule that
  governs it.
- **S5, the spend console.** One console frame, three tabs, three genuinely different real screens:
  the wizard step where money is allocated, the Overview KPI row where it is watched, the Redemption
  Report where it is reconciled.

---

## 3. Section map and band alternation

| # | id | Section | Class | Ground | Dark? |
|---|---|---|---|---|---|
| S1 | `hero` | Hero plus logo band | `hero rewards-hero` | cream radial gradient | no |
| S2 | `earn` | Where points come from | `hub-section earn-screen` | `#fff` | no |
| S3 | `flow` | Earn to redeem, end to end | `hub-section flow-screen` | `var(--canvas)` | no |
| S4 | `catalog` | What points become | `hub-section catalog-screen` | `#fff` | no |
| S5 | `budget` | Spend you design, then reconcile | `hub-section budget-screen` | `var(--canvas)` | no |
| S6 | `fairness` | Rewards that pay effort | `hub-section fairness-screen` | `#fff` with dark `.fairband` inset | inset |
| S7 | `proof` | What it sounds like on the ground | `hub-section proof-hub` | `#f6f7f4` | no |
| S8 | `security` | Controls around the money | `screen trust-screen solutions-trust` | dark gradient | **yes** |
| S9 | `faq` | Questions HR and finance ask | `hub-section faq-screen` | `#fff` | no |
| S10 | `related` | Where teams go next | `related-screen` | `var(--canvas)` | no |
| S11 | `demo` | Closer | `final` | dark gradient | **yes** |

Three dark moments (fairband inset, trust screen, closer), none adjacent, S7 separates the inset
from the trust band. No two identical grounds touch. `#f6f7f4` is used once, for proof, as the
system reserves it.

---

## 4. Voice rules binding on this page

- No em-dashes anywhere. Not in copy, not in mocks, not in the meta description, not in `aria-label`
  strings. Commas, colons, periods.
- Banned words: robust, seamless, comprehensive, user-friendly, holistic, empower, leverage,
  game-changer, best-in-class, all-in-one. Also avoid: simply, just, intuitive, optimize, utilize.
  Prefer "set" and "set up" over "configure".
- Sentence case for H1, H2, H3, buttons, card titles, table headers. Title Case only for product
  nouns: Vantage Fit, Vantage Points, Vantage Circle, Rewards Hub, Transaction Report, Redemption
  Report, Redeem Points, My Gift Cards, Statement, Health Risk Assessment, Lifestyle Spending
  Account, Incentivization.
- Every H2 on this page ends with a period. Hold that choice across the page.
- Verb-led CTAs. Primary "Book a demo" to `https://www.vantagefit.io/request-demo/`. Secondary
  "See pricing" to `https://www.vantagefit.io/pricing/`.
- Numerals for every measurable quantity. Thousands separators. `tabular-nums` on every column of
  digits in a mock.
- Oxford comma always. US spelling in new copy.

---

## 5. Copy deck

Everything below is final copy. Do not rewrite, do not add. Bracketed notes in `[ ]` are build
instructions, not copy.

### S1. Hero

`<header class="hero rewards-hero" id="hero" aria-labelledby="hero-heading">`

**Eyebrow:** `Wellness rewards program`

**H1:** `Rewards worth coming back for, on effort you can verify.`
[Wrap `coming back for` in the single `<em>`, which takes the coral gradient text fill. Include the
`@media (forced-colors: active)` fallback.]

**Lead:**
`Employees earn Vantage Points for challenge tasks they actually complete, then redeem them for real gift cards. You set the value on every task, and every credit lands on an exportable ledger.`
[31 words. The house budget is 20 to 30 for a hero subhead; do not lengthen it further.]

**Buttons:**
- `Book a demo` (`.btn .btn-primary`, `https://www.vantagefit.io/request-demo/`)
- `See pricing` (`.btn .btn-outline`, `https://www.vantagefit.io/pricing/`)

**Hero note** (`.hero-note`, lime dot):
`Five ways to earn. A catalogue spanning 20+ categories. One exportable ledger.`

**Hero visual:** `.dash` (admin Overview KPI row) plus `.phone` (employee wallet). Full spec in
§6.1 and §6.2.

**Logo band** (last child of `<header class="hero">`, verbatim from `chrome.html`):
`Trusted by 100+ organizations worldwide` then the word marks
`TATA MOTORS · WIPRO · TEVA · GODREJ · TEXAS INSTRUMENTS · HEIDRICK & STRUGGLES · BRAZOSPORT ISD`.

---

### S2. Where points come from

`<section class="hub-section earn-screen" id="earn" aria-labelledby="earn-heading">`

**Eyebrow:** `The earning model`

**H2:** `Five ways to earn, and nothing outside them.`

**Lead:**
`Vantage Points are bought by completed work inside a challenge you designed, plus the awards you make yourself. Here is the whole list, with when each one lands.`
[The trailing clause is load-bearing: card 5, Admin award, is issued from Rewards Hub and is not
inside a challenge. Without it the lead contradicts the fifth card on the same screen.]

**Five cards** (`.format-grid` at `repeat(6,1fr)`, cards 1 to 3 `span 2`, cards 4 and 5 `span 3`,
each `.format-card` carrying a 74x44 `.format-glyph` and a `.best-for` footer):

| # | H3 | Body (one line) | `.best-for` label | `.best-for` value |
|---|---|---|---|---|
| 1 | `Challenge task completion` | `An employee hits the target on a task in a live challenge.` | `LANDS` | `Real time for single-event tasks. End of day for daily targets, once the source data syncs.` |
| 2 | `Journey milestone` | `A checkpoint on a Journey route is reached.` | `LANDS` | `Real time` |
| 3 | `Challenge completion` | `The challenge they were enrolled in finishes.` | `LANDS` | `On completion` |
| 4 | `Final ranking bonus` | `Top finishers take a bonus, if you set one.` | `LANDS` | `After the end date, once a 3-day buffer lets backdated syncs settle` |
| 5 | `Admin award` | `You award points to one person or a whole list from Rewards Hub.` | `LANDS` | `After OTP verification` |

**Exclusions strip** (`.earn-exclusions`, three chips, each with a small "no" glyph):

- `Badges earn nothing. They are recognition only.`
- `Steps outside a challenge task earn nothing.`
- `Points cannot be spent in the Marketplace.`

**Trailing note** (`.format-note`, `.8rem`, muted, two sentences, contains one internal link):
`Point values are set task by task while you build the challenge, in the same Certificates & Rewards step as certificates. Employees are enrolled by your audience rules, so earning starts without anyone hunting for a program to join. `
then the inline link: `See the challenge library` to `https://www.vantagefit.io/solutions/wellness-challenges/`

**Supporting line** (`.earn-inclusive`, one sentence, sits under the note, ink not muted):
`Opting out of the leaderboard hides an employee from the rankings and does not stop their points: task rewards, milestone rewards and completion rewards keep accruing.`

---

### S3. Earn to redeem, end to end  [SIGNATURE SECTION]

`<section class="hub-section flow-screen" id="flow" aria-labelledby="flow-heading">`

**Eyebrow:** `The flow`

**H2:** `From a completed task to a gift card in hand.`

**Lead:**
`Four screens, no forms to chase, no HR ticket in the middle. This is the whole path a point takes.`

**Flow rail** (`.flow-rail`, four `.flow-stage` panels with chevron connectors, full spec §6.3):

**Stage 01, label `Earn`, screen title `Spring Steps Race`**
Caption under the screen (`.flow-rule`):
`Single-event tasks credit in real time with a confirmation popup. Daily targets settle at end of day, once the source data syncs.`

**Stage 02, label `Wallet`, screen title `Wallet`**
Caption:
`Points land in one balance with a statement line naming what earned them.`

**Stage 03, label `Choose`, screen title `Redeem Points`**
Caption:
`The catalogue is organized by category. Denominations show in the employee's local currency, and the app blocks any denomination above their balance.`

**Stage 04, label `Receive`, screen title `Confirm`**
Caption:
`Points are deducted immediately. The card arrives in-app and by email, and lives in My Gift Cards.`

**Trailing note** (`.flow-note`, `.8rem`, muted, three sentences):
`Redemptions are final once confirmed. On iOS and Android the whole flow happens in the app; on the web, employees reach the wallet and the catalogue through the Vantage Circle header. If your contract sets a validity period on points, tell employees to redeem promptly, because the wallet does not show expiry dates inline.`

---

### S4. What points become

`<section class="hub-section catalog-screen" id="catalog" aria-labelledby="catalog-heading">`

**Eyebrow:** `The catalogue`

**H2:** `Real gift cards, in the currency they live in.`

**Lead:**
`The Vantage Fit wallet is a Lifestyle Spending Account: gift cards by design, not a company store and not merchandise.`

**Category grid** (`.cat-grid`, 12 tiles, each a `.cat-tile` with a small line glyph and a label;
labels are exactly these, in this order):

`Online and in-store shopping` · `Food and dining` · `Travel and leisure` · `Entertainment` ·
`Health and wellness products` · `Sports and fitness gear` · `Apparel and fashion` ·
`Electronics and appliances` · `Groceries` · `Gaming` · `Baby products` · `Charity donations`

**Grid caption** (`.cat-note`, sits directly under the grid, `.8rem`, muted):
`20+ categories in the redemption catalogue. Availability varies by region.`

**SOLI strip** (`.soli-strip`, three `.soli-point` items in a row, each `<b>` title plus one line):

| `<b>` | Line |
|---|---|
| `Local currency, not a conversion exercise` | `Balances and gift card denominations both display in the employee's own currency.` |
| `Equivalent purchasing power` | `Cost-of-living adjusted conversion covers 190+ countries, so a reward carries the same weight wherever someone sits.` |
| `Rates set for your company` | `Points-per-unit rates are set per company, per country, with your account manager before launch.` |

**Pull line** (`.soli-quote`, one sentence, larger, coral left rule):
`Points have equivalent purchasing power, not equal numbers.`

**Trailing note** (`.catalog-fine`, `.8rem`, muted):
`Merchandise sits on other Vantage Circle wallets, not on the Vantage Fit Lifestyle Spending Account.`

---

### S5. Spend you design, then reconcile  [SIGNATURE SECTION]

`<section class="hub-section budget-screen" id="budget" aria-labelledby="budget-heading">`

**Eyebrow:** `For HR and finance`

**H2:** `Spend you design, then reconcile.`

**Lead:**
`Vantage Fit does not hold a pot that stops at zero. It gives you the numbers to set your own ceiling before you publish, watch it while the program runs, and reconcile it to the last gift card.`

**Console** (`.tour-tabs` shell, three-tab `.seg` segmented control, three `.tabpane`. Each pane is
a `.tour-copy` checklist plus a `.tour-media` mock. Full mock specs in §6.4, §6.5, §6.6.)

**Tab labels:** `Before you publish` · `While it runs` · `After it ends`

**Pane 1, `Before you publish`** (`.tour-checks`, four `li`, each `<b>` plus one line):

| `<b>` | Line |
|---|---|
| `You see the audience before you commit` | `Set the audience rule and the wizard shows how many employees match.` |
| `You set the value on each task` | `Point values are set per task, so the mix is yours: cheap daily habits, richer one-off milestones.` |
| `Nothing above the target earns` | `Non-step tasks pay up to 100% of the target and no further. Log five yoga sessions against a target of three and three are paid.` |
| `So the ceiling is arithmetic, not a surprise` | `Matching employees, multiplied by tasks, multiplied by the value you set. You can price the worst case before you publish it.` |

Media: **Certificates & Rewards wizard mock** (§6.4).

**Pane 2, `While it runs`** (`.tour-checks`, four `li`):

| `<b>` | Line |
|---|---|
| `Incentivization is a KPI, not a hunt` | `The Overview shows reward spend to date in your own currency, converted through SOLI.` |
| `Filter it the way finance asks for it` | `By date range, and by country.` |
| `Drill straight into the ledger` | `Incentivization opens the Transaction Report, every credit and debit with its source.` |
| `The leaderboard is your leading indicator` | `Uptake during the challenge tells you where spend is heading before the ledger does.` |

Media: **Overview KPI row mock** (§6.5).

**Pane 3, `After it ends`** (`.tour-checks`, four `li`):

| `<b>` | Line |
|---|---|
| `See what was actually chosen` | `The Redemption Report lists employee, reward, denomination, category and date.` |
| `Size earned against redeemed` | `Cross-reference the Transaction Report to find the gap between points earned and points spent.` |
| `Filter, then export` | `Both reports filter and download as CSV. Archive them monthly for reconciliation.` |
| `Plan for the spike` | `Redemptions cluster right after a challenge ends. Expect it and it stops being a surprise.` |

Media: **Redemption Report mock** (§6.6).

**Wallet fencing row** (`.fence-duo`, two cards side by side, directly under the console):

| Card | H3 | Body |
|---|---|---|
| 1 | `One balance by default` | `Vantage Fit points and Vantage Circle recognition points share one wallet and one catalogue, and redemptions in either place draw on the same pool.` |
| 2 | `Ring-fenced if you need it` | `A company can run a named Wellness wallet with its own catalogue, balance, history and reporting, set up through your account manager. Points do not move between wallets.` |

**Trailing note** (`.budget-fine`, `.8rem`, muted, contains one internal link):
`Reward budgets can be organized per country, as India plus rest of world, or as one global pool. Spend sits on the same Overview as participation, so the two numbers are read together. `
then the inline link: `See workforce health insights` to
`https://www.vantagefit.io/solutions/workforce-health-insights/`

---

### S6. Rewards that pay effort

`<section class="hub-section fairness-screen" id="fairness" aria-labelledby="fairness-heading">`
[Section ground `#fff`. The dark `.fairband` sits inside it as an inset.]

**Inside `.fairband`, left column:**

**Eyebrow:** `Fairness` (renders in `--lime` on the dark inset)

**H2:** `Rewards that pay effort, not exploits.`

**Lead:**
`The controls that keep a leaderboard honest are the same ones that keep the wallet honest.`

**`.fair-list`, four `.fair-item`:**

| `<b>` | Line |
|---|---|
| `Effort has to come from a trusted source` | `Steps count from Apple Health and Google Fit and other approved sources, on one primary device at a time, so nothing gets counted twice.` |
| `Over-completion earns nothing` | `Non-step tasks pay up to 100% of the target. The person who does five times the target is paid the same as the person who did it once.` |
| `Ranking bonuses wait for the data` | `They pay out after the end date with a 3-day buffer, so backdated syncs settle before anyone is paid for a position.` |
| `Every credit names its source` | `The Transaction Report logs each credit and debit with the challenge, action or admin operation that triggered it.` |

**`.fair-fine`** (one sentence above the top hairline of the fine print):
`Bulk point awards need an OTP sent to the initiating admin's email, and only the admin who started the upload can verify it.`

**Right column:** the **ledger board mock** (§6.7).

---

### S7. What it sounds like on the ground

`<section class="hub-section proof-hub" id="proof" aria-labelledby="proof-heading">`

**Eyebrow:** `Proof`

**H2:** `Points people actually notice.`

**`.quote-duo`, two `.quote-band.text-only` cards** (no video, no photo, coral left rule):

**Quote 1**
`It's a great way to log activities. Employees are also rewarded with points, recognition and prizes.`
`.quote-who`: `Rachel Arthur, Director of Benefits & Wellness, Brazosport ISD`

**Quote 2**
`It is engaging and has features that keep everyone motivated. From tracking activity levels to earning rewards, the app has made wellness accessible and fun for all our employees.`
`.quote-who`: `Tara Shore, Niche Technology`

**`.proof-fine`:**
left `small`: `Quotes from named customer programs. Outcomes vary by workforce and program design.`
right `.text-link`: `Read customer stories` to `https://www.vantagefit.io/casestudy/`

[No `.results-grid` on this page. No stat tiles. See §2.4.]

---

### S8. Controls around the money

`<section class="screen trust-screen solutions-trust" id="security" aria-labelledby="security-heading">`

[Structure verbatim from `chrome.html`. Swap the H2, the lead and the four card bodies only. Keep
the compliance strings and the `.mark-strip` exactly as they are. Do not restore the Cloudinary
certification raster.]

**Eyebrow:** `Enterprise security & compliance`

**H2:** `Controls around the money, and around the data.`

**Lead:**
`Every point movement is logged and exportable, manual awards need a verification step, and the health data behind the activity never reaches an admin screen.`

**Trust actions:** `Book a demo` plus text link `Explore security & compliance →` to
`https://www.vantagefit.io/features/security-and-compliance/`

**Four `.trust-card`:**

| Glyph | H3 | Body |
|---|---|---|
| `&#9673;` | `Every movement on the ledger` | `The Transaction Report carries each credit and debit with its source, and the Redemption Report carries each reward, denomination and category. Both export to CSV.` |
| `&#8644;` | `Manual awards are verified` | `A bulk points upload previews the recipients and the total, then requires an OTP sent to the initiating admin's email before anything is credited.` |
| `&#9737;` | `Regional data residency` | `Employee data stays in your assigned region: India, US, EU, or UAE instances.` |
| `&#10003;` | `Independently audited` | `SOC 2 Type II audited; operates under HIPAA guidelines. Security documentation available during evaluation.` |

**`.trust-plaque`:** the typeset `.mark-strip` from `chrome.html`, three strings only:
`Follows HIPAA guidelines` · `SOC 2 Type II` · `Secured regional data hosting`.
`.trust-support`: `Security documentation is available during evaluation.`

---

### S9. Questions HR and finance ask

`<section class="hub-section faq-screen" id="faq" aria-labelledby="faq-heading">`

**Eyebrow:** `FAQ`

**H2:** `Questions HR and finance ask.`

Five `<details class="faq-item">`, first one `open`.

**Q1 (open):** `What does a wellness rewards program actually cost us?`
**A:** `You set the point value on each task, so cost is a design decision rather than a discovery. Non-step tasks pay up to 100% of the target and no further, so the maximum a single employee can earn from a task is fixed before you publish. Vantage Fit does not enforce a budget pool that stops at zero, which is why the Overview carries an Incentivization KPI showing spend to date in your currency, and why the Transaction Report and Redemption Report both export to CSV for reconciliation.`

**Q2:** `Can employees game the points?`
**A:** `Steps have to arrive from a trusted source, on one primary device at a time, so the same day cannot be counted twice. Non-step tasks stop paying at 100% of the target. Final ranking bonuses wait for a 3-day buffer so backdated syncs settle before anyone is paid for a position. Every credit is logged with the challenge, action or admin operation that produced it, and bulk awards require an OTP sent to the admin who started the upload.`

**Q3:** `How are these rewards treated for tax?`
**A:** `That is a question for your payroll and tax advisors, and the treatment differs by country. What Vantage Fit gives you is the record they will ask for: the Transaction Report lists every credit and debit with the employee, the amount, the date and the source, and the Redemption Report lists every reward with its denomination, category and date. Both filter and export to CSV.`

**Q4:** `Is the reward fair for employees in different countries?`
**A:** `Points have equivalent purchasing power, not equal numbers. Balances and gift card denominations display in the employee's local currency, and cost-of-living adjusted conversion covers 190+ countries. Points-per-unit rates are set per company, per country, and your account manager confirms them with you before launch. Catalogue depth does vary by region, so it is worth reviewing the local catalogue during evaluation.`

**Q5:** `Do employees have to compete to earn anything?`
**A:** `No. Four of the five earning events have nothing to do with ranking: task completion, Journey milestones, challenge completion and admin awards. Ranking bonuses are optional and are the only place position matters. An employee can even opt out of the individual leaderboard entirely and keep earning, because task, milestone and completion rewards continue as normal.`

---

### S10. Where teams go next

`<section class="related-screen" id="related" aria-labelledby="related-heading">`

**Eyebrow:** `Keep exploring`
**H2:** `Where teams go next`

Exactly three `.related-row`:

| H3 | One line | href |
|---|---|---|
| `Wellness challenges` | `The library of programs that create the effort points are paying for.` | `https://www.vantagefit.io/solutions/wellness-challenges/` |
| `Health Risk Assessment` | `Baseline screening you can set as a challenge task, so a first step counts.` | `https://www.vantagefit.io/solutions/health-risk-assessment/` |
| `Workforce health insights` | `Read participation and reward spend on the same page.` | `https://www.vantagefit.io/solutions/workforce-health-insights/` |

---

### S11. Closer

`<section class="final" id="demo" aria-labelledby="demo-heading">`

**H2:** `See what this costs on your headcount.`

**Body:**
`In a 30-minute demo we will price a program against your workforce, walk the employee wallet and redemption flow, and show the two reports your finance team will reconcile against.`

**Buttons:** `Book a demo` (primary) and `See pricing` (outline).

**`.final-checks`:** `Point values you set` · `Gift cards, not gimmicks` · `Ledger exports to CSV`

**`.final-note`:** `Turn participation into progress.`

---

## 6. Product-real UI spec

### 6.0 Rules that bind every mock on this page

1. Wrap each mock in `role="img"` with a full `aria-label` describing what it shows, ending with
   the exact sentence `Figures shown are illustrative.` No em-dashes inside `aria-label`.
2. Every decorative child gets `aria-hidden="true"`.
3. Every mock carries a visible `<span class="mock-tag">Illustrative data</span>`.
4. Every column of digits gets `font-variant-numeric: tabular-nums`.
5. **Currency rule, specific to this page.** A currency symbol may appear on exactly three
   surfaces, because those are the three that really carry one: the **Incentivization KPI** (admin
   currency), a **gift card denomination** (employee local currency), and the **Redemption Report
   Denomination column**. A per-task **Points** field never carries a currency symbol, never says
   USD, and never implies a validation rule. Put this HTML comment above the wizard mock:
   `<!-- CLAIMS: per-task point values are set by the admin and vary by contract. The numbers here are illustrative and must keep the mock-tag. Never print a currency unit on a per-task Points field. -->`
6. Product nouns only. Approved strings for this page:
   `Rewards Hub` · `Rewards Hub > Upload Points` · `Reports > Transaction Report` ·
   `Reports > Redemption Report` · `Certificates & Rewards` · `Target Audience` · `Points` ·
   `Wallet` · `Points Balance` · `Statement` · `Redeem Points` · `My Gift Cards` · `Activate` ·
   `Confirm` · `Export CSV` · `Enrolled Users` · `Active Users` · `Incentivization` ·
   `Participation Rate` · `View more →` · `vs Prev Quarter` · `Date` · `Description` · `Points +/-`.
   Use **Rewards Hub**, never "Reward Hub" (C8).
7. No retailer logos and no brand wall. The catalogue is rendered on its sourced **category** axis.
   If a single brand tile is ever unavoidable, `Amazon Gift Card` is the only sourced example, and
   the surrounding mock still needs its `mock-tag`.

---

### 6.1 Hero mock A: `.dash`, admin Overview

Standard `.dash` shell: `.dash-top` with three grey dots and a URL pill, then `.dash-body`.

- `.dash-title` small: `Admin · Overview`  strong: `Rewards this quarter`
  plus `<span class="mock-tag">Illustrative data</span>` on the right.
- **KPI row, exactly four cards** (code-verified row, ruling C7). Render as a 2x2 grid of compact
  cards inside the dash. Each card: label, value, delta pill, and a 3px sparkline.

| Card label | Value | Delta pill | Delta label |
|---|---|---|---|
| `Enrolled Users` | `1,284` | `+96` | `vs Prev Quarter` |
| `Active Users` | `1,046` | `+11%` | `vs Prev Quarter` |
| `Incentivization` | `$18,240` | `+12%` | `vs Prev Quarter` |
| `Participation Rate` | `81%` | `+6 pts` | `vs Prev Quarter` |

- Promote **Incentivization** to `.metric-card.metric-main` styling (the `#e8f7f1` tint) so the
  money card reads first.
- Under the Incentivization card, one micro row: `View more →` in coral, `.62rem`.
- `aria-label`: `Admin dashboard overview showing four KPI cards: enrolled users, active users, incentivization spend, and participation rate, with the rewards spend card highlighted. Figures shown are illustrative.`

### 6.2 Hero mock B: `.phone`, employee wallet

Standard `.phone` shell, `-3deg`, `194px`, positioned `right:-16px; bottom:2px`.

- `.phone-head`: `Vantage Fit` plus the `.avatar` dot.
- **Balance block** (replaces the `.challenge` card used on the challenge pages):
  - small caps label: `Points Balance`
  - big number: `2,480`
  - sub-line: `Vantage Points`
- **Statement rows**, three, each `Date · Description · Points +/-` with the sign colored
  (`--mint-dark` for credits, `--coral-deep` for the debit):

| Date | Description | Points |
|---|---|---|
| `May 14` | `Steps challenge task completed` | `+12` |
| `May 13` | `Admin award` | `+120` |
| `May 09` | `Gift card redeemed` | `-1,000` |

- `.phone-cta`: `Redeem Points`
- `<span class="mock-tag">Illustrative data</span>` at the bottom of the screen.
- `aria-label`: `Employee wallet in the Vantage Fit app showing a points balance, three recent statement lines, and a redeem points button. Figures shown are illustrative.`

### 6.3 The flow rail (`.flow-rail`)  [signature]

**Layout.** `display:grid; grid-template-columns: repeat(4, 1fr); gap: 14px;` on a light
`var(--canvas)` ground. Between stages, a chevron connector drawn with a `::after` on stages 1 to
3: a 22px right-pointing chevron in `rgba(41,41,76,.22)`, absolutely positioned at the vertical
centre of the gap, `aria-hidden`. Below 1100px the grid becomes `repeat(2,1fr)` and the connectors
rotate to point down between rows; below 640px it becomes one column with down chevrons.

**Each `.flow-stage` is:**
```
.flow-step      -> a small pill: "01" plus the stage label ("Earn"), .6rem/800, uppercase
.flow-screen    -> the drawn mini-screen, white, radius 16px, 1px var(--line),
                   box-shadow 0 10px 28px rgba(41,41,76,.07), min-height 232px
.flow-rule      -> the caption, .78rem, muted, line-height 1.5, margin-top 12px
```
**Do not put `role="img"` on `.flow-rail`.** That role makes its whole subtree presentational, and
the rail contains the four `.flow-rule` captions, which are page copy carrying the shipped rule for
each stage, plus the `mock-tag`. A rail-level role deletes all of them from the accessibility tree.
Instead: `.flow-rail` is a plain container, each `.flow-panel` carries its own `role="img"` and
`aria-label`, and the `.flow-step` pills stay readable so the order is announced. One `mock-tag` on
the rail, top right of stage 01.

Per-panel `aria-label`, each ending with the required illustrative sentence:

| Stage | `aria-label` |
|---|---|
| 01 | `Challenge screen for the Spring Steps Race on day 12 of 28, showing a steps task at 8,412 of 10,000, a completed water task, and a popup crediting 12 Vantage Points. Figures shown are illustrative.` |
| 02 | `Wallet screen showing a points balance of 2,480, tabs for Redeem Points, Statement and My Gift Cards, and three statement lines. Figures shown are illustrative.` |
| 03 | `Redeem Points catalogue screen with category chips, two gift card tiles, and four denominations where the two above the balance are struck out as unavailable. Figures shown are illustrative.` |
| 04 | `Confirmation screen summarizing the reward, the denomination of 1,000 points, and the balance after redemption, with the delivered card in My Gift Cards. Figures shown are illustrative.` |

**Stage 01, `Earn`.** A challenge screen fragment.
- Header row: `Spring Steps Race` with a right-aligned muted `Day 12 of 28`.
- Task row A: icon tile, `Steps`, target line `8,412 / 10,000`, a `.progress` bar at 84%.
- Task row B: icon tile, `Water`, `8 / 8 glasses`, a mint check, row tinted `rgba(65,216,180,.08)`.
- Floating toast overlaid on the lower third: mint left rule, bold `+12 Vantage Points`, second
  line muted `Water daily target completed`.

**Stage 02, `Wallet`.**
- Header: `Wallet`.
- Balance block: label `Points Balance`, value `2,480`.
- Segmented row of three inert chips: `Redeem Points` (active, coral tint) · `Statement` ·
  `My Gift Cards`.
- Statement table with a header row `Date` / `Description` / `Points +/-` and three rows, the same
  three used in §6.2. Give the `+12` row a faint mint left edge so the eye connects it back to
  stage 01.

**Stage 03, `Choose`.**
- Header: `Redeem Points`.
- Category chip row, four chips, first active: `Shopping` · `Food and dining` · `Entertainment` ·
  `Travel`.
- Two card tiles side by side, brandless: each a rounded rectangle with a subtle gradient, a small
  card glyph, and a label. Tile 1 label `Shopping gift card`. Tile 2 label `Dining gift card`.
- Denomination row under tile 1, four chips: `500` (selected, coral ring) · `1,000` ·
  `2,500` (dimmed, struck) · `5,000` (dimmed, struck), followed by a `.72rem` muted line
  `Amounts above your balance are unavailable.`
  [Denominations here are point amounts, not currency. Do not print a currency symbol in this
  stage. The local-currency fact is carried by the caption copy, not by the tile.]

**Stage 04, `Receive`.**
- Header: `Confirm`.
- Summary rows: `Reward` / `Shopping gift card` · `Denomination` / `1,000 points` ·
  `Balance after` / `1,480`.
- A full-width coral `Confirm` button (inert).
- Below a hairline, a delivered-card strip: a mini card tile, label `My Gift Cards`, sub-line
  `Delivered in-app and by email`, and a small outlined `Activate` button on the right.

### 6.4 Budget console, pane 1 media: Certificates & Rewards wizard (`.launch-mock`)

White 460px card, radius 18px, `box-shadow: 0 22px 54px rgba(41,41,76,.12)`, inside `.tour-media`.

- `.lm-head`: `<b>Create challenge</b>` and `<span>Step 6 of 7 · Certificates &amp; Rewards</span>`
- `.lm-row`: `Audience` with `<span class="lm-chip">All US offices · 1,284 match</span>`
- Section label row: `Point rewards`
- Three task rows, each a `.lm-task`: task name on the left, a small inert numeric field on the
  right showing the points value, and a `.lm-help` micro line under the first one.

| Task | Mode | Points field |
|---|---|---|
| `Steps · daily target` | `Daily` | `12` |
| `Water · daily target` | `Daily` | `8` |
| `Yoga · 3 sessions` | `Weekly` | `30` |

- `.lm-help` under the Yoga row: `Non-step tasks pay up to 100% of the target.`
- `.lm-cta` (inert): `Review & publish`
- `.lm-note`: `Point values are set per task. Values shown are illustrative.`
- `<span class="mock-tag">Illustrative data</span>`
- `aria-label`: `Challenge creation wizard on the certificates and rewards step, showing an audience of 1,284 matching employees and a point value set on each of three tasks. Figures shown are illustrative.`
- The claims comment from §6.0 rule 5 goes immediately above this block.

### 6.5 Budget console, pane 2 media: Overview KPI row

A wider, flatter variant of the hero `.dash`, without the browser chrome bar.

- Header strip: `Admin · Overview` on the left; on the right two inert filter chips
  `Date range: This quarter` and `Country: All`.
- The same four KPI cards as §6.1, laid out `repeat(4,1fr)` at this width, with
  **Incentivization** carrying the mint tint plus a `View more →` link and, under the value, the
  micro line `Opens the Transaction Report`.
- Under the row, one hairline-separated note: `Spend is shown in your own currency, converted through SOLI.`
- `mock-tag` top right.
- `aria-label`: `Admin overview with a date range and country filter and four KPI cards, where the incentivization card shows rewards spend to date and links through to the transaction report. Figures shown are illustrative.`

### 6.6 Budget console, pane 3 media: Redemption Report (`.report-mock`)

Same shell as `.launch-mock`, wider. Reuse the `.rm-*` pattern from the team-challenge page.

- `.rm-head`: `<b>Reports</b>` `<span>Redemption Report</span>`
- `.rm-controls`: two `.rm-field` chips, `Date range: Apr 1 to Jun 30` and `Category: All`, and a
  coral `.rm-export` button reading `Export CSV`.
- `.rm-cols` header row, exactly the shipped columns:
  `Employee` · `Reward` · `Denomination` · `Category` · `Date`
  [The Email column exists in the product but is dropped from the mock for width. Say so nowhere;
  simply do not imply the list is complete.]
- Four `.rm-row`:

| Employee | Reward | Denomination | Category | Date |
|---|---|---|---|---|
| `A. Rivera` | `Shopping gift card` | `$25` | `Gift Cards` | `Jun 12` |
| `P. Sharma` | `Dining gift card` | `INR 500` | `Gift Cards` | `Jun 12` |
| `D. Osei` | `Wellness gift card` | `$50` | `Gift Cards` | `Jun 09` |
| `J. Kim` | `Entertainment gift card` | `$25` | `Gift Cards` | `Jun 04` |

- `.rm-callout` bubble anchored to the export button:
  `Cross-reference the Transaction Report to size points earned against points redeemed.`
- `mock-tag`.
- `aria-label`: `Redemption report table filtered by date range and category, listing four redemptions with employee, reward, denomination, category and date, and an export to CSV button. Figures shown are illustrative.`

### 6.7 Fairness ledger board (`.ledger-board`)

Same shell as the `.audit-board` used on the challenge pages: a white 380px panel floating on the
dark `.fairband`, `box-shadow: 0 26px 60px rgba(0,0,0,.32)`, radius 18px.

- `.ledger-head`: `<b>Reports · Transaction Report</b>` and a right chip
  `<span class="audit-live"><i></i> Live</span>`
- Column header row: `Employee` · `Source` · `Points` (grid `1fr 1.3fr auto`).
- Four rows:

| Employee | Source | Points | Row treatment |
|---|---|---|---|
| `A. Rivera` | `Spring Steps Race · Steps daily target` | `+12` | normal |
| `P. Sharma` | `Spring Steps Race · Water daily target` | `+8` | normal |
| `D. Osei` | `Spring Steps Race · Yoga 3 sessions` | `+30` | carries a small amber-neutral chip reading `Capped at target · 5 logged, 3 paid` |
| `J. Kim` | `Rewards Hub · Upload Points` | `+120` | carries a small mint chip reading `OTP verified` |

- `.ledger-caption` (`.audit-caption` styling): `Every credit carries the challenge, action or admin operation that produced it.`
- `mock-tag`.
- `aria-label`: `Transaction report panel listing four point credits, each naming its source, including one credit capped at the task target and one bulk admin award marked as verified by one time password. Figures shown are illustrative.`

### 6.8 Page-local components the builder must write

These are not in `enterprise.css`. Copy the base patterns from the named v1 page, then add the new
ones.

| Component | Source | New for this page? |
|---|---|---|
| `.hub-section`, `.hub-head`, `.reveal`, `.skip-link`, contrast lifts, `.btn-primary` fix, forced-colors fallback, `.mock-tag` | `chrome.html` | no |
| `.format-grid`, `.format-card`, `.format-glyph`, `.best-for` | `vantage-fit-steps-challenge-v1.html` | no |
| `.fairband`, `.fair-list`, `.fair-item`, `.fair-fine` | `vantage-fit-steps-challenge-v1.html` | no |
| `.audit-board` shell, restyled as `.ledger-board` | `vantage-fit-steps-challenge-v1.html` §5.4 | restyle |
| `.launch-mock` and `.lm-*` | `vantage-fit-team-challenge-v1.html` | add `.lm-task` |
| `.report-mock` and `.rm-*` | `vantage-fit-team-challenge-v1.html` | no |
| `.quote-duo`, `.quote-band.text-only`, `.quote-who`, `.proof-fine` | `vantage-fit-steps-challenge-v1.html` | no |
| `.faq-list`, `.faq-item` | `design-system.md` addendum F3 | no |
| `.tour-tabs`, `.seg`, `.seg-btn`, `.seg-thumb`, `.tabpane`, `.tour-checks`, `.tour-media` | `enterprise.css` | **three-tab thumb math needed** |
| `.flow-rail`, `.flow-stage`, `.flow-step`, `.flow-screen`, `.flow-rule` | none | **new** |
| `.earn-exclusions` chips | none | **new** |
| `.cat-grid`, `.cat-tile`, `.cat-note` | none | **new** |
| `.soli-strip`, `.soli-point`, `.soli-quote` | none | **new** |
| `.fence-duo` | none | **new**, two-card variant of `.trust-grid` |
| `.ledger-*` rows and chips | none | **new** |

**Three-tab segmented control.** The `chrome.html` handler only toggles a two-tab thumb
(`seg.classList.toggle('hr', i === 1)`). Replace it with a real transform on the thumb:
`thumb.style.transform = 'translateX(' + (i * 100) + '%)'` with `.seg-btn` and `.seg-thumb` each at
`calc(100% / 3)`. Keep `role="tablist"` / `role="tab"` with `aria-selected` and `aria-controls`,
panes as `role="tabpanel"` with the `hidden` attribute, and the `:focus-visible` override
`3px solid var(--coral-dark)` with `outline-offset:2px`. Below 600px the `.seg` stacks to full
width and the thumb width follows.

### 6.9 Accessibility checklist for this page

- One `h1`, in the hero, `id="hero-heading"`, referenced by the header's `aria-labelledby`.
- Every section has an `id` and an `aria-labelledby` pointing at its own `h2`.
- Sub-item titles inside `.fair-list`, `.tour-checks`, `.soli-strip` and `.flow-step` are `<b>`,
  not headings. Card titles in `.format-card`, `.cat-tile`, `.fence-duo`, `.trust-card` and FAQ
  summaries are `h3`.
- `.skip-link` is the first child of `<body>`.
- The nav self-locates: `is-current` on the Solutions trigger, and `is-page` plus
  `aria-current="page"` on the Wellness rewards program `.mega-link`, whose `href` becomes `#top`.
  The footer Solutions column gives the same link `aria-current="page"` and
  `style="color:#fff;font-weight:700"`.
- Escape closes an open mega and returns focus to the trigger; `aria-expanded` stays in sync on the
  pointer, focus and mobile paths.
- Gradient-clipped text (`h1 em`) has the `@media (forced-colors: active)` fallback.
- `?gray` grayscale review hook at the end of the script.
- Reduced-motion: the connectors, the reveal observer and the `.seg-thumb` all respect it.

---

## 7. Claims table

Every factual assertion on the page, with its source and status. Anything not on this list does not
go on the page.

| # | Claim as it appears | Where | Source | Status |
|---|---|---|---|---|
| 1 | Employees earn Vantage Points for completing challenge tasks | Hero, S2 | `help/employee/rewards/how-do-i-earn-points.md`, `product/08-.../rewards-wallet.md` | SHIPPED |
| 2 | Points redeem for real gift cards | Hero, S3, S4 | `help/employee/rewards/how-do-i-redeem-points.md` | SHIPPED |
| 3 | You set the point value on every task | Hero, S2, S5 | `help/admin/challenges/admin-how-do-i-create-custom-challenge.md`, `help/admin/challenges/admin-how-wellness-rewards-work.md` | SHIPPED |
| 4 | Five earning events: task completion, Journey milestone, challenge completion, final ranking bonus, admin award | S2 | `product/08-.../rewards-wallet.md` §02 (four) plus `help/admin/challenges/admin-how-wellness-rewards-work.md` (ranking bonus) | SHIPPED |
| 5 | Single-event tasks credit in real time with a confirmation popup | S2, S3 | `help/admin/challenges/admin-how-wellness-rewards-work.md`, `help/employee/rewards/how-do-i-earn-points.md` | SHIPPED |
| 6 | Daily targets settle at end of day once the source data syncs | S2, S3 | `help/admin/challenges/admin-how-wellness-rewards-work.md` | SHIPPED |
| 7 | Journey milestone points credit in real time | S2 | same, plus `help/admin/challenges/admin-how-do-i-create-journey-challenge.md` | SHIPPED |
| 8 | Points on challenge completion | S2 | `product/08-.../rewards-wallet.md` | SHIPPED |
| 9 | Ranking bonuses pay after the end date with a 3-day buffer for backdated syncs | S2, S6, S9 Q2 | `help/admin/challenges/admin-how-wellness-rewards-work.md`, `product/02-.../challenges.md` | SHIPPED |
| 10 | Admin award lands after OTP verification | S2, S6, S8, S9 Q2 | `help/admin/challenges/admin-how-do-i-upload-points.md` | SHIPPED |
| 11 | Badges earn nothing, they are recognition only | S2 strip | `help/admin/challenges/admin-how-do-badges-work.md` | SHIPPED |
| 12 | Steps outside a challenge task earn nothing | S2 strip | `product/08-.../rewards-wallet.md`, by omission across all five events | SHIPPED (by exclusion) |
| 13 | Points cannot be spent in the Marketplace | S2 strip | `help/employee/programs/what-is-the-marketplace.md`, `help/admin/programs/admin-how-does-marketplace-work.md` | SHIPPED (as excluded) |
| 14 | Point values are set in the Certificates & Rewards step | S2 note, S5 pane 1 | `help/admin/challenges/admin-how-do-i-create-a-challenge.md` | SHIPPED |
| 15 | Employees are enrolled by audience rules, not by browsing and joining | S2 note | `product/02-.../challenges.md`, `help/employee/challenges/how-do-i-join-a-challenge.md` | SHIPPED |
| 16 | Opting out of the leaderboard does not stop earning | S2, S9 Q5 | `help/employee/challenges/can-i-opt-out-of-leaderboard.md` | SHIPPED |
| 17 | Redemption path: Wallet, Redeem Points, catalogue by category, select card, choose denomination, Confirm | S3 | `help/employee/rewards/how-do-i-redeem-points.md` | SHIPPED |
| 18 | Points are deducted immediately | S3, S9 | same | SHIPPED |
| 19 | Gift card delivered in-app and by email | S3 | same | SHIPPED |
| 20 | Cards live in My Gift Cards, some vendors need an Activate step | S3 | `help/employee/rewards/how-do-i-view-my-wallet-statement.md` | SHIPPED |
| 21 | The app blocks a denomination above the balance | S3 | `help/employee/rewards/how-do-i-redeem-points.md` | SHIPPED |
| 22 | Redemptions are final once confirmed | S3 note | same | SHIPPED |
| 23 | Denominations display in the employee's local currency | S3, S4 | `product/08-.../soli-currency.md` | SHIPPED |
| 24 | Statement lines carry Date, Description and Points +/- | S3, mock §6.2 | `help/employee/rewards/how-do-i-view-my-wallet-statement.md` | SHIPPED |
| 25 | Web users reach the wallet and catalogue through the Vantage Circle header | S3 note | `product/00-platform/navigation-ia.md`, `product/08-.../rewards-wallet.md` §06 | SHIPPED |
| 26 | Points may carry a contract validity period, and the wallet does not show expiry inline | S3 note | `help/admin/challenges/admin-how-wellness-rewards-work.md`, `product/08-.../rewards-wallet.md` | SHIPPED |
| 27 | The Vantage Fit wallet is a Lifestyle Spending Account, gift cards by design | S4, S4 fine | `product/08-.../multi-wallet.md` | SHIPPED |
| 28 | Merchandise sits on other wallets, not the VFit LSA | S4 fine | same, Roadmap row "Not planned" | SHIPPED (as excluded) |
| 29 | The catalogue spans 20+ categories | S4, hero note | `sources/VFit-Marketing-Content-Compacted.md`, approved by `rules/data-accuracy.md` | SHIPPED |
| 30 | The 12 named categories | S4 grid | same source, verbatim list | SHIPPED |
| 31 | Cost-of-living adjusted conversion covers 190+ countries | S4, S9 Q4 | `product/08-.../soli-currency.md` | SHIPPED, product capability only |
| 32 | Points have equivalent purchasing power, not equal numbers | S4 pull line, S9 Q4 | same, verbatim | SHIPPED |
| 33 | Points-per-unit rates are set per company, per country, with the account manager | S4, S9 Q4 | same | SHIPPED |
| 34 | Catalogue availability varies by region | S4 caption, S9 Q4 | `product/08-.../rewards-wallet.md` Roadmap, "more gift card vendors per region", Ongoing | HONEST LIMIT (roadmap-derived, stated as a limit, never as a promise) |
| 35 | Vantage Fit does not enforce a budget pool at the challenge level | S5 lead, S9 Q1 | `help/admin/challenges/admin-how-wellness-rewards-work.md`, verbatim tip | SHIPPED |
| 36 | The wizard shows how many employees match the audience rule | S5 pane 1 | `help/admin/challenges/admin-how-do-i-set-target-audience.md` | SHIPPED |
| 37 | Non-step tasks pay up to 100% of the target, five sessions against three earns for three | S5, S6, S9 Q1 | `help/admin/challenges/admin-how-do-i-create-custom-challenge.md`, `help/employee/challenges/how-does-the-leaderboard-work.md` | SHIPPED |
| 38 | Incentivization KPI shows reward spend in the admin's currency, converted via SOLI | S5 pane 2, S9 Q1 | `product/09-admin-platform/admin-dashboard.md`, `product/08-.../soli-currency.md` | SHIPPED |
| 39 | Incentivization filters by date range and country | S5 pane 2 | `product/08-.../soli-currency.md` FAQ | SHIPPED |
| 40 | Incentivization drills into the Transaction Report | S5 pane 2 | `product/09-admin-platform/admin-dashboard.md`; drill destination corroborated in `insights-reports.md` §Story A | SHIPPED |
| 41 | The Overview KPI row is Enrolled Users, Active Users, Incentivization, Participation Rate | mocks §6.1, §6.5 | `product/09-admin-platform/admin-dashboard.md` | SHIPPED, settled ruling C7 |
| 42 | The leaderboard shows uptake during the challenge | S5 pane 2 | `help/admin/challenges/admin-how-wellness-rewards-work.md` | SHIPPED |
| 43 | Redemption Report columns: employee, email, reward, denomination, category, date | S5 pane 3, S8, S9 Q3 | `help/admin/challenges/admin-how-do-i-view-redemption-reports.md` | SHIPPED |
| 44 | Transaction Report logs every credit and debit with its source | S5, S6, S8, S9 | `help/admin/reports/admin-what-reports-are-available.md`, `product/09-admin-platform/admin-dashboard.md` | SHIPPED |
| 45 | Both reports filter and export to CSV | S5, S8, S9 Q3 | `help/admin/challenges/admin-how-do-i-view-redemption-reports.md`, `help/admin/reports/admin-how-do-i-export-reports.md` | SHIPPED |
| 46 | Archive the export monthly for reconciliation | S5 pane 3 | `help/admin/challenges/admin-how-do-i-view-redemption-reports.md`, verbatim tip | SHIPPED |
| 47 | Cross-reference redemption against transactions to size earned vs redeemed | S5 pane 3, mock §6.6 | same | SHIPPED |
| 48 | Redemptions spike right after a challenge ends | S5 pane 3 | same | SHIPPED |
| 49 | Budgets can be per country, India plus rest of world, or one global pool | S5 fine | `product/08-.../soli-currency.md` | SHIPPED, account-manager set |
| 50 | One wallet by default, shared with Vantage Circle recognition, symmetric deductions | S5 fence card 1 | `product/08-.../rewards-wallet.md`, `help/employee/rewards/how-do-i-earn-points.md`, `help/employee/rewards/how-do-i-view-my-wallet-statement.md` | SHIPPED |
| 51 | A named Wellness wallet with its own catalogue, balance, history and reporting; points do not move between wallets | S5 fence card 2 | `product/08-.../multi-wallet.md` | SHIPPED, account-manager set |
| 52 | Steps count from Apple Health and Google Fit and other approved sources | S6 | `product/10-integrations/device-integrations.md`, `product/01-core-tracking/activity-tracking.md` | SHIPPED |
| 53 | One primary device at a time, to avoid double counting | S6 | `product/10-integrations/device-integrations.md`, verbatim | SHIPPED |
| 54 | Bulk upload previews recipients and the total, then requires an OTP to the initiating admin | S6 fine, S8 | `help/admin/challenges/admin-how-do-i-upload-points.md` | SHIPPED |
| 55 | Regional data residency: India, US, EU, UAE | S8 | `product/03-health-wellness/onboarding-health-profile.md` | SHIPPED |
| 56 | SOC 2 Type II audited; operates under HIPAA guidelines | S8, mark strip | `rules/data-accuracy.md`, `chrome.html` cleared strings | APPROVED-CLAIM |
| 57 | Trusted by 100+ organizations worldwide | logo band | `rules/data-accuracy.md` | APPROVED-CLAIM, the only aggregate |
| 58 | Rachel Arthur quote | S7 | `rules/data-accuracy.md`, Brazosport ISD block | APPROVED-CLAIM, verbatim |
| 59 | Tara Shore quote | S7 | `rules/data-accuracy.md` Tier A, Niche Technology, Apr 2025 | APPROVED-CLAIM, verbatim |
| 60 | Health Risk Assessment can be set as a challenge task | S10 related row | `help/admin/challenges/admin-what-tasks-can-i-include-in-a-custom-challenge.md`, "Health Vitals (HRA)" | SHIPPED |

### 7.1 Cut, not softened

Claims considered and removed because no source supports them at the strength the page would need:

| Considered | Why cut |
|---|---|
| A per-task rate, a USD example, "multiples of 5" | T4, C1 |
| "USD value per task" as the normal setup | T5, C2. Contract-gated to roughly one account |
| Any redemption rate, adoption rate or reward ROI figure | Nothing in the approved register. "3X ROI" and "12X the platform cost" are on the banned list |
| A vendor count or brand count | No sourced figure. The 400+ in the design repo is fiction |
| A minimum redemption threshold | Not documented |
| Employee-visible points expiry | Backlog, and the wallet does not show it inline |
| MFA on employee redemption | C4 |
| Employees transferring points to each other or between countries | C5 |
| A budget cap, spend ceiling, quota, auto-stop, or approval workflow | T6, T7. The product does not do this |
| Any tax, gross-up or payroll-treatment statement | T12 |
| A completion rate for any program | None approved anywhere |
| Slack or Microsoft Teams | Zero spec coverage |
| "Start free trial" | No trial exists |
| Lite Mode behaviour | C6 |

---

## 8. Meta

**Meta title** (47 characters, matches the observed convention and the recommended title in the IA
dossier §6.2, no em-dash):

```
Employee Wellness Rewards Program | Vantage Fit
```

**Meta description** (154 characters, capability plus differentiator plus CTA):

```
Reward wellness with Vantage Points employees redeem for real gift cards. Set the value on every task, watch spend, export the ledger. Book a demo.
```

**Other head requirements**
- `<meta name="robots" content="noindex, nofollow">` because this is an unshipped mock on a preview
  host.
- `theme-color` `#18262b`, Noto Sans at weights 400 to 800, `../styles/enterprise.css`, then one
  page-local `<style>` block.
- Primary keyword: **employee rewards for wellness** (200/mo). Adjacent phrases to keep in H2s and
  body without stuffing: employee wellness rewards program, wellness incentive program, points and
  gift cards for employees.
- If the builder adds JSON-LD, it must be `FAQPage` matching the five S9 questions **verbatim**,
  plus `SoftwareApplication` and `BreadcrumbList`. Schema that drifts from visible copy is a known
  defect on the live site; do not repeat it. No banned stat may appear in schema.

---

## 9. Menu fit and the section ② chain

**Placement:** Solutions mega-menu, **column ②, row 3**, the last row of the column.

| Field | Exact string |
|---|---|
| Menu label | `Wellness rewards program` |
| Description line | `Points and gift cards tied to real effort` |
| Badge in the sign-off gallery | `Action` |
| URL | `/solutions/wellness-rewards-program/` |
| Footer Solutions column | row 9, last, label `Wellness rewards program` |

Column ② header, verbatim from the signed-off preview:
`Workforce health & rewards — measure and motivate`. That string is nav markup reproduced verbatim
and is the only place an em-dash may appear on this page. If the build uses `chrome.html`'s colon
variant instead, keep that choice consistent across all six pages.

**Chain position: data in, data out, action.**

```
Health Risk Assessment   ->   Workforce health insights   ->   Wellness rewards program
     (data in)                       (data out)                        (action)
     baseline                    participation proof              what moves behaviour
                                                                          |
                                                     closes the loop back into challenges
```

How this page plays its role:

- **It receives from insights.** Spend and participation live on the same Overview, so the reader
  arriving from the insights page finds the Incentivization KPI they were just shown, in context.
  S5's trailing note links back.
- **It receives from the HRA page.** The HRA is a task type, so the baseline screening the HRA page
  sells can itself be the first thing an employee is paid for. The related row carries that.
- **It closes the loop into challenges.** Points are only ever bought by challenge tasks, so the
  page routes back to the library. S2's trailing note and the first related row both do it.
- **It stands alone.** A reader landing cold on "employee rewards for wellness" gets the earning
  model, the flow, the catalogue and the budget answer without needing either sibling.

**Nav self-location.** The Solutions trigger takes `is-current`; the Wellness rewards program
`.mega-link` takes `is-page`, `aria-current="page"` and `href="#top"`.

---

## 10. Cross-links

Body links, three, which matches the 2 to 3 internal links per page convention. Related rows are in
addition and are the standard three.

| From | Anchor text | To | Why |
|---|---|---|---|
| S2 trailing note | `See the challenge library` | `/solutions/wellness-challenges/` | Points exist only because a challenge task exists. This is the honest upstream. |
| S5 trailing note | `See workforce health insights` | `/solutions/workforce-health-insights/` | Spend and participation are read on the same Overview. |
| S8 trust actions | `Explore security & compliance →` | `/features/security-and-compliance/` | Standard trust-band link from `chrome.html`. |
| S7 proof fine print | `Read customer stories` | `/casestudy/` | Standard proof-band link. |

Related rows (S10): `/solutions/wellness-challenges/`, `/solutions/health-risk-assessment/`,
`/solutions/workforce-health-insights/`.

**Inbound links this page should receive** (for whoever builds the other five):

- Wellness challenges library: from its rewards or recognition beat.
- Health Risk Assessment: where it mentions running the HRA as a challenge task.
- Workforce health insights: from the Incentivization KPI explanation.
- Wellness platform: from the incentives module in the platform map.
- Solutions hub: column ② card 3.

---

## 11. Assumptions and gaps

### 11.1 Assumptions made

| # | Assumption | Basis | Risk if wrong |
|---|---|---|---|
| A1 | The `/solutions/` URL prefix is correct for this page | The signed-off menu and the shipping brief both use it | `seo-conventions.md` says solution pages are root-level with no prefix. Flagged, not resolved. See 11.3. |
| A2 | An illustrative per-task Points value in a wizard mock does not read as a published rate | The mock-tag plus the caption "Point values are set per task. Values shown are illustrative." plus the no-currency rule | A reviewer could still read `12` as a rate. If so, replace the numeric fields with a masked field showing three dots and keep the row labels. That fallback preserves the section. |
| A3 | Currency symbols on the Incentivization KPI, gift card denominations, and the Redemption Report Denomination column are safe | All three surfaces genuinely carry a currency in the product, and `$25` / `INR 500` are the help doc's own examples | Low. |
| A4 | Showing an illustrative `$18,240` spend figure is acceptable | It is labelled illustrative, and the KPI is a real surface | Low, but keep the figure modest and unremarkable so nobody quotes it. |
| A5 | Dropping the Email column from the Redemption Report mock is fine for width | Column set is documented; the mock is a partial view, not a claim of completeness | Low. |
| A6 | The Niche Technology quote is attributable to Tara Shore by name | `rules/data-accuracy.md` Tier A lists the quote under Tara Shore, Apr 2025, with no title given | Do not invent a title. Company plus name only, exactly as written. |
| A7 | "Rewards Hub" is the right spelling for every mock | The code-verified admin spec uses it more often; the dossier recommends it | Cosmetic. Just stay consistent. |

### 11.2 Gaps where no source exists, designed around

| Gap | How the page copes |
|---|---|
| No per-task rate can be published | The exposure argument is expressed as a shape (matching employees x tasks x the value you set), never as a worked dollar figure. |
| No budget module exists | The console is assembled from three shipped screens and the section leads with the absence. |
| No tax coverage anywhere | FAQ Q3 answers procedurally and defers to the reader's advisors. |
| No approved rewards metric | S7 is two quotes and no stat tiles. No `.results-grid`. |
| No sourced vendor or brand count | The catalogue is rendered on its category axis, with "20+ categories" as the only number. |
| No minimum redemption threshold documented | Never mentioned. The balance guard carries the "can I actually spend this" answer instead. |
| Catalogue depth per region is a roadmap item | Stated once as an honest limit ("availability varies by region"), never as a promise of parity. |

### 11.3 A human must verify before this page ships

1. **URL prefix.** `/solutions/wellness-rewards-program/` versus the root-level rule in
   `vfit-os/.claude/rules/seo-conventions.md`. The menu is the newer decision and is followed here,
   but the conflict is unresolved. This is the same open question flagged on every page in the set.
2. **The legacy page at `/wellness-rewards-program/`.** It carries "Fit points", "1 Fit Point = 1
   Rupee", and "Gift Cards, Merchandise, or memorable Experiences". Decide whether this page
   replaces it with a redirect or sits above it. All three legacy strings are banned and must not
   survive either way.
3. **Whether an illustrative per-task Points value is acceptable to the claims reviewer.** See A2
   and its fallback.
4. **The Incentivization currency shown in the mocks.** The page is USD-priced and global, so `$` is
   used. Confirm that is the right default for the target audience rather than a mixed-currency
   render.
5. **Niche Technology usage cap.** `content-standards.md` requires checking the usage-caps ledger in
   `content-marketing/plans/phase-1-blog-update-guide.md` before reusing a testimonial. Both quotes
   in S7 need that check.
6. **Whether the trust band's four cards may be re-pointed at money controls.** Two of the four
   cards here differ from the `chrome.html` defaults. The compliance wording is untouched, but the
   swap should be confirmed by whoever owns the shared chrome so all six pages stay consistent.

### 11.4 Known risks in the build

- The flow rail is the most likely thing to break at 640px. Four drawn screens in a row must
  collapse to one column with the connectors rotating, and each screen must stay legible at 320px.
  If a stage cannot stay legible, drop its least important row (the second task row in stage 01, the
  second card tile in stage 03), never the caption.
- The three-tab segmented control needs new thumb math. The inherited handler is two-tab only.
- The `.fairband` inset and the dark `.trust-screen` must stay separated by S7. If S7 is ever cut,
  the two dark moments become adjacent and the band rhythm breaks.
