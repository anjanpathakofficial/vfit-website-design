# Wellness rewards program page brief

## Page job

Show enterprise HR buyers how Vantage Fit connects verified wellness effort to usable rewards through a concrete points, wallet, redemption, and reporting system. The page should make the reinforcement loop tangible without presenting points as a substitute for program design.

Intended URL: `/solutions/wellness-rewards-program/`

Primary audience: Benefits, Total Rewards, Wellbeing, and program leaders

Primary CTA: **Book a demo**

Secondary CTA: **See pricing**

## Product truth used

- HR can configure point values for challenge tasks during challenge creation.
- Employees earn points from challenge task completion, milestones, challenge completion, and admin awards. The code-verified wallet spec is the authority for the redemption story.
- Employees can view their points balance and statement, browse a gift-card or voucher catalog, choose a denomination, confirm redemption, and receive gift-card details in app and by email.
- Admins can upload points by CSV. Current help documentation describes OTP verification for the upload flow.
- Transaction reports show earned, awarded, and deducted points with source and timestamp. Redemption reports show what was redeemed, denomination, category, and date.
- Wallet labels, value visibility, conversion display, multi-country setup, catalog configuration, and multi-wallet setup require coordination with the Vantage Fit account manager.
- The standard setup uses one wallet. Where multiple wallets are configured, a wellness wallet can remain separate from a Rewards & Recognition wallet, each with its own balance, catalog, and history. Points cannot move between wallets.
- The Vantage Fit Lifestyle Spending Account is gift-card only. The page therefore does not promise merchandise in the wellness wallet.

## Narrative and architecture

The page uses the reward loop as its organizing device. This gives buyers a direct answer to three questions: what earns value, where the value goes, and whether the program can be governed.

1. **Hero: Reward the effort you want repeated.** A product-real loop shows a completed challenge task becoming points, appearing in a wallet, and ending in a gift-card redemption.
2. **Earn, see, redeem.** Three steps explain the employee experience in plain language.
3. **Design the behavior, not just the prize.** An HR control panel demonstrates configurable challenge points and targeted admin awards.
4. **A wallet employees can understand.** A statement and redemption catalog section emphasizes balance, transaction history, denomination selection, and confirmation.
5. **Govern the program after launch.** Transaction and redemption reports make allocation and spend auditable.
6. **Enterprise setup options.** A compact table separates self-serve controls from account-manager configuration, preventing overstatement.
7. **Connection, FAQ, and CTA.** The page links back to insights as the preceding action trigger, then resolves rollout questions.

This architecture is intentionally transactional and sequential. It does not reuse the insights page's analytical rail or the challenge library's browsing system. Its signature is the continuous effort-to-value receipt that runs through the hero.

## Full copy deck

### Hero

Eyebrow: Wellness rewards program

Headline: **Reward the effort you want repeated.**

Body: Connect challenge tasks and wellness milestones to points employees can see, understand, and redeem for gift cards. Give HR the controls and reports to run the program responsibly.

Primary CTA: Book a demo

Secondary CTA: See pricing

Reward loop:

- Effort: Complete a configured wellness task.
- Earn: Points are credited to the employee wallet.
- Redeem: Choose an available gift card and denomination.
- Reinforce: The reward makes progress feel tangible.

### Employee experience

Headline: **From completed task to usable reward.**

- **Earn through real participation.** Attach point values to challenge tasks, milestones, and completion.
- **See every movement.** Employees can check their balance and review earned and redeemed transactions in their wallet statement.
- **Redeem with a clear finish.** Browse available gift cards, select a denomination, confirm, and receive the gift-card details.

### HR control section

Eyebrow: Program design

Headline: **Put the incentive behind the behavior that matters.**

Body: Set point values while creating challenge tasks, then use admin awards when a program needs a separate recognition moment.

UI labels: Challenge task; Point value; Completion rule; Reward preview; Upload points; CSV; OTP verified.

### Wallet section

Headline: **Make earned value easy to follow.**

Body: The wallet keeps the employee experience coherent from balance to statement to redemption.

Wallet labels: Available points; Wallet statement; Earned; Redeemed; Redeem points; Gift cards; Choose denomination; Confirm redemption.

### Reporting section

Eyebrow: Reward governance

Headline: **See where points came from and where they went.**

- Transaction report: Audit earned, awarded, and deducted points with their source and timestamp.
- Redemption report: Review gift-card redemptions by item, denomination, category, and date.
- Filtered CSV exports: Carry the relevant view into reconciliation and internal reporting workflows.

### Setup options

Headline: **Know what HR controls and what is configured with you.**

Self-serve:

- Set challenge task point values.
- Upload points by CSV with OTP verification.
- Review transaction and redemption reports.

Configured with your account manager:

- Wallet availability and employee-facing points label.
- Points value and conversion-rate display.
- Multi-country setup and catalog configuration.
- Separate wallet setup where required.

### Connected chain

Eyebrow: From insight to action

Headline: **Use the signal to choose what you reinforce.**

Body: Workforce health insights shows where participation or behavior needs attention. Rewards gives the next program a tangible reinforcement layer.

CTA: Explore workforce health insights

### FAQ

**What can employees redeem wellness points for?** The Vantage Fit wellness wallet supports gift cards and vouchers available in the configured catalog.

**Can we award points outside a challenge?** Yes. Admins can upload awards by CSV, with OTP verification in the current admin flow.

**Can wellness rewards stay separate from our recognition program?** A separate wellness wallet can be configured. Each wallet keeps its own balance, catalog, and history, and points do not move between wallets.

**How can HR audit rewards?** Transaction and redemption reports show point movements and redemptions, with filters and CSV export.

### Final CTA

Headline: **Make healthy effort feel worth repeating.**

Body: See how points, wallets, gift-card redemption, and reporting work together in Vantage Fit.

Buttons: Book a demo · See pricing

## Visual direction

- Shared system: `styles/enterprise.css`, Noto Sans, Vantage Fit coral, mint, amber, ink, canvas, shared navigation, button, card, and footer behavior.
- Page-specific palette: reward coral `#F15162`, wallet ink `#29294C`, confirmation mint `#41D8B4`, value amber `#F6B93B`, paper `#FFFFFF`, cloud `#F1F1F6`.
- Signature: a horizontal effort-to-value receipt that visually carries one task through points, wallet, and redemption.
- Aesthetic risk: the hero uses the visual language of a transparent transaction receipt instead of celebratory confetti. This fits an enterprise rewards buyer who needs motivation and governance in the same system.
- Responsive behavior: the receipt becomes a vertical timeline; catalog cards become a horizontal snap strip; admin tables become stacked labeled rows.
- Accessibility: semantic landmarks and headings, visible focus states, color-independent statuses, reduced-motion support, and sufficiently large interactive targets.

## Sources

No external statistics, redemption counts, catalog sizes, or customer outcome claims are used. Product UI content is illustrative and does not use fake employee identities or balances.

- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-wellness-rewards-work.md`, admin rewards overview.
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-upload-points.md`, CSV and OTP point awards.
- `../../../vantagefit-astro/content/en/help/admin/challenges/admin-how-do-i-view-redemption-reports.md`, redemption reporting.
- `../../../vantagefit-astro/content/en/help/admin/reports/admin-what-reports-are-available.md`, transaction and redemption report fields and export behavior.
- `../../../vantagefit-astro/content/en/help/employee/rewards/how-do-i-earn-points.md`, employee earning paths.
- `../../../vantagefit-astro/content/en/help/employee/rewards/how-do-i-view-my-wallet-statement.md`, wallet statement behavior.
- `../../../vantagefit-astro/content/en/help/employee/rewards/how-do-i-redeem-points.md`, redemption flow.
- `../../../vc-os/vfit-os/specs/product/08-rewards-marketplace/rewards-wallet.md`, code-verified points, wallet, gift-card, and configuration truth.
- `../../../vc-os/vfit-os/specs/product/08-rewards-marketplace/multi-wallet.md`, multi-wallet and Lifestyle Spending Account boundaries.
- `../../../vc-os/vfit-os/specs/08-rewards-marketplace/points-rewards.md`, challenge point configuration.

## Metadata draft

Meta title: **Employee Wellness Rewards Program | Vantage Fit**

Meta description: **Connect wellness effort to points, employee wallets, gift-card redemption, and auditable HR reporting with Vantage Fit.**

## Solutions IA fit

This page owns **Action** in the Workforce health & rewards column. It follows Health Risk Assessment as Data in and Workforce health insights as Data out. The connection appears as a single insight-to-action handoff, while the rest of the page stays focused on behavior reinforcement and reward operations.
