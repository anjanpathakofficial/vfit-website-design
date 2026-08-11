# Wellness Rewards Program: Solutions Page Brief

**Page:** Wellness rewards program (Section ② Action)  
**Intended URL:** `/solutions/wellness-rewards-program/`  
**Mock file:** `vantage-fit-wellness-rewards-v1.html`  
**Audience:** US enterprise HR / CHRO / Benefits / Total Rewards / Wellbeing leaders; secondary program managers  
**North star (honest for this page):** **Redemption habits**, points employees earn only when real effort completes, so incentives reinforce participation rather than vanity  
**Visual baseline:** `styles/enterprise.css` + peer Grok program pages + `styled-homepage/`  
**Primary CTA:** Book a demo · **Secondary:** See pricing  

---

## 1. Research takeaways (product truth)

Sources prioritized: help docs (`admin-how-wellness-rewards-work`, earn/redeem/wallet statement, upload points, redemption reports), OS product specs (`rewards-wallet.md`, `multi-wallet.md`, `points-rewards.md`). **Wellness Marketplace** is a separate partner-offerings catalog and is **not** gift-card redemption. Live marketing was not used as the product blueprint.

### 1.1 What the product actually is

Vantage Fit rewards employees with **points** for completing challenge tasks and related wellness effort. Points land in an employee **Wallet**, show optional monetary value, and redeem for **gift cards** from a curated in-app catalog (delivered in-app and by email).

| Layer | Product behavior | Source |
|-------|------------------|--------|
| **Earn** | Challenge task completion is the primary path; admin bulk awards via Reward Hub CSV | Help: earn points; upload points |
| **Credit timing** | Single-event / milestones: real-time; daily targets: end-of-day after sync; leaderboard bonuses: after 3-day buffer; admin upload: on OTP approval | Help: admin-how-wellness-rewards-work |
| **Configure** | Per-task point value set in USD at challenge create/edit; display converts to employee local currency | Help: wellness rewards work |
| **Wallet** | Balance, statement (earned / redeemed / gifted), redeem flow, My Gift Cards | Help: wallet statement; redeem |
| **Unified balance** | Standard setup shares balance with **VantageCircle R&R** wallet (one pool) | Help + rewards-wallet.md |
| **Multi-wallet (optional)** | AM-configured separate pots (e.g. Wellness LSA vs R&R); VFit LSA is gift-cards only | multi-wallet.md |
| **HR audit** | Transaction Report, Redemption Report (CSV), Incentivization KPI (reward spend) | Help: reports; wellness rewards work |
| **Tenant config (AM)** | Point label, show monetary value, conversion rate, wallet on/off, redemption on/off, multi-country balances | Help: wellness rewards work |

### 1.2 What this page must not claim

| Avoid | Why |
|-------|-----|
| Marketplace partner offerings = gift-card catalog | Separate product surface (`wellness-marketplace.md`) |
| Merchandise in the Vantage Fit wellness wallet | LSA is gift-cards only; merchandise may exist on other wallets |
| Budget-pool cap at challenge level | Product allocates per-task; spend scales with completion |
| Fabricated redemption rates or catalog size | No approved rewards-specific customer metrics for this bake-off |
| Challenge-page patterns (formats explorer, fraud LB) | Wrong archetype |

### 1.3 Buyer job

Help Benefits / Total Rewards / Wellbeing answer:

1. Do points come from **completed effort**, or from show-up vanity?  
2. Can employees **see and redeem** value without a second system?  
3. Does this **unify** (or cleanly separate) with our R&R balance?  
4. Can HR **configure incentives** and **audit spend**?  
→ Book a demo.

### 1.4 Positioning line

> Wellness rewards that stick because points only land when effort is complete: configurable task values, a real wallet and gift-card catalog, unified VantageCircle balance by default, and reports Finance can reconcile.

### 1.5 Data-chain role (Section ② Action)

| Step | Page | Role |
|------|------|------|
| Data in | Health Risk Assessment | Baseline health signal |
| Data out | Workforce health insights | Where participation needs attention |
| **Action** | **Wellness rewards** | Reinforce the habits you want repeated |

This page owns **incentive design + wallet + redemption + audit**. It links the chain lightly; it does not re-teach HRA or analytics.

---

## 2. Page strategy & structure

### Job of this page

Conversion page for rewards as **behavior reinforcement**, not a gift-card storefront and not a challenge format page.

### Narrative arc (rewards archetype, not challenge clone)

| # | Section | Intent |
|---|---------|--------|
| 1 | **Hero** | Effort → points → wallet → gift card; product-real wallet + catalog mock; dual CTAs |
| 2 | **Value strip** | Three buyer promises (effort-tied · wallet/gift cards · audit) without fake KPIs |
| 3 | **How it works** | Earn · See · Redeem (employee loop, lean) |
| 4 | **When points land** | Credit-timing table as product trust (real-time / EOD / buffer / OTP) |
| 5 | **Wallet + catalog** | Product-real dual mock: statement + gift-card categories |
| 6 | **Unified R&R balance** | Platform advantage; optional multi-wallet note |
| 7 | **HR controls** | Per-task values, Reward Hub upload + OTP, transaction/redemption reports |
| 8 | **Chain strip** | Light Data in → Data out → Action |
| 9 | **FAQ** | ~5 rollout objections |
| 10 | **Trust + final CTA** | Security strip + Book a demo |

**Deliberately omitted:** customer-result section (no approved rewards-specific outcomes), formats explorer, marketplace deep-dive, encyclopedic config matrix.

### Visual signature (distinct from challenge pages)

- **Amber accent** on value/money moments (alongside coral/mint system tokens).  
- Hero signature = **wallet phone + catalog card**, not leaderboard.  
- Admin signature = **Reward Hub / report table**, not challenge builder.  
- Optional **effort receipt** strip (task complete → +pts → redeem).  

---

## 3. Full copy deck

### Meta

- **Title:** Employee Wellness Rewards Program for HR | Vantage Fit  
- **Description:** Points tied to completed wellness effort, employee wallet and gift-card redemption, unified VantageCircle balance, and HR audit reports. Book a demo.

### Hero

- **Eyebrow:** Solutions · Workforce health & rewards · Action  
- **H1:** Rewards that reinforce effort, not vanity.  
- **Lead:** Attach points to completed challenge tasks. Employees earn into a real wallet, redeem gift cards in-app, and share a unified balance with VantageCircle R&R when you run both.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** See pricing  
- **Micro:** Effort-tied points · Wallet + gift cards · Transaction & redemption reports  

### Value strip (no fake metrics)

1. **Points for completed work.** Daily targets, single-event tasks, milestones, and leaderboard bonuses when you configure them.  
2. **A wallet employees open.** Balance, statement, and gift-card catalog in one place.  
3. **Spend you can audit.** Transaction and redemption reports plus an Incentivization KPI for reward spend.

### How it works

- **Earn.** Complete challenge tasks (or receive an admin award).  
- **See.** Points land in the Wallet with optional monetary value.  
- **Redeem.** Choose a gift card and denomination; delivery in-app and by email.

### When points land

| Action | When points appear |
|--------|-------------------|
| Single-event tasks & milestones | Real-time |
| Daily activity targets | End of day after source sync |
| Final leaderboard bonuses | After challenge end + 3-day buffer |
| Admin bulk upload | After OTP approval |

### Wallet + catalog

- Balance front and center; statement for earned / redeemed.  
- Catalog by category (shopping, food, entertainment, illustrative).  
- Denominations gated by balance; redemptions final.  
- Caption: Illustrative UI · gift-card catalog, not partner marketplace.

### Unified balance

- Default: Vantage Fit and VantageCircle R&R points share **one** balance and catalog path.  
- Optional: multi-wallet setup via account manager (separate Wellness LSA vs R&R). Vantage Fit LSA redeems gift cards only.

### HR controls

- Set USD point values per task when creating challenges.  
- Reward Hub → Upload Points (CSV) with OTP verification.  
- Reports: Transaction Report, Redemption Report, CSV export.  
- Incentivization KPI: total reward spend in local currency.  
- AM-configured: point label, monetary display, wallet/redemption toggles, multi-country balances.

### Chain

- Health Risk Assessment (Data in) → Workforce health insights (Data out) → **Wellness rewards (Action)**  
- Line: Use insights to decide what to reinforce. Use rewards so that effort pays out.

### FAQ

1. **What can employees redeem points for?** Gift cards from the configured catalog, delivered in-app and by email. The wellness partner marketplace is separate.  
2. **When do points appear?** Real-time for single-event tasks; end of day for daily targets; leaderboard bonuses after a 3-day buffer; admin awards after OTP.  
3. **Are Vantage Fit points separate from VantageCircle R&R?** By default they share one unified wallet. Multi-wallet separation is available via your account manager.  
4. **Can HR award points outside a challenge?** Yes. Reward Hub CSV upload with OTP verification.  
5. **How do we audit spend?** Transaction and Redemption reports with filters and CSV export; Incentivization KPI on Overview.

### Final CTA

- **H2:** Make healthy effort worth repeating.  
- **Body:** See task-level incentives, wallet redemption, and audit reports in a walkthrough for your benefits stack.  
- **Checks:** Effort-tied points · Gift-card wallet · Unified R&R balance · HR reports  

---

## 4. Mega-menu fit

Signed-off Solutions IA:

**② Workforce health & rewards**  
- Health Risk Assessment (Data in)  
- Workforce health insights (Data out)  
- **Wellness rewards program (Action)** ← this page  

Nav mega uses two columns: Wellness challenges | Workforce health & rewards + featured platform/hub links. Current page marked on Wellness rewards.

---

## 5. Sources

- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-wellness-rewards-work.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-upload-points.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-view-redemption-reports.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/employee/rewards/how-do-i-earn-points.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/employee/rewards/how-do-i-redeem-points.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/employee/rewards/how-do-i-view-my-wallet-statement.md`  
- `/Users/anjanpathak/work/gitcode/vantagefit-astro/content/en/help/employee/rewards/where-do-i-see-my-points.md`  
- `/Users/anjanpathak/work/gitcode/vc-os/vfit-os/specs/product/08-rewards-marketplace/rewards-wallet.md`  
- `/Users/anjanpathak/work/gitcode/vc-os/vfit-os/specs/product/08-rewards-marketplace/multi-wallet.md`  
- `/Users/anjanpathak/work/gitcode/vc-os/vfit-os/specs/08-rewards-marketplace/points-rewards.md`  
- `/Users/anjanpathak/work/gitcode/vc-os/vfit-os/specs/08-rewards-marketplace/wellness-marketplace.md` (boundary only)  
- Shared system: `grok/_SHARED-RESEARCH-AND-SYSTEM.md`

---

## 6. Decisions (summary for bake-off)

1. **Effort-receipt narrative** over prize-catalog marketing: credit timing + task values are the differentiator.  
2. **Default unified VantageCircle balance** is the platform story; multi-wallet is FAQ/config depth, not the hero.  
3. **No customer-result block** (no approved rewards-only metrics); value strip replaces vanity KPIs.

## 7. Gaps / watch items

- Exact gift-card vendor set and regional catalog composition are AM-configured; mocks stay brand-generic.  
- Points validity/expiry is contract-gated and not always visible in wallet UI; page does not oversell expiry rules.  
- Monetary challenges (explicit monetary-redemption semantics) are limited availability; page stays on standard points configuration.  
- Web wallet is backlog for pure VFit web; mobile + VC host cover redemption in product truth.  
- Sibling HRA/insights HTML may not exist yet in this folder; chain links use planned relative filenames.
