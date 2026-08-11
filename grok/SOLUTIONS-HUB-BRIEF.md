# Solutions hub brief

**Page:** Solutions hub (index / chooser)  
**Intended URL:** `/solutions/`  
**Mock:** `vantage-fit-solutions-hub-v1.html`  
**Archetype:** Directory chooser (not a program page, not a second homepage)

---

## Research takeaways

### Job of this page
Buyers land here from mega-menu “Solutions,” SEO for “employee wellness solutions,” or internal links. They need to **pick a next click** within two signed-off columns plus the platform feature. They do not need feature encyclopedia copy.

### Signed-off IA (source of truth)
From `menu/vantage-fit-solutions-menu-preview.html` + `_SHARED-RESEARCH-AND-SYSTEM.md`:

| Zone | Pages |
|---|---|
| **① Wellness challenges** | Library (flagship) · Step · Multi-activity · Remote & hybrid team · Virtual marathon |
| **② Workforce health & rewards** | HRA (data in) · Insights (data out) · Rewards (action) |
| **Featured** | Wellness platform (~850 search demand) |
| **This page** | Hub at `/solutions/` |

Challenge program mocks already shipped in this folder. Health/rewards/platform/library mocks are sibling filenames from shared research (may ship in parallel).

### What not to do
- Do not dump every capability equally.
- Do not force challenge-page sections (formats explorer, integrity deep-dive, long FAQ).
- Do not invent customers, metrics, or product claims.
- Do not use em-dashes.

### Spine
Participation remains the north star, but the hub only **routes** to pages that own participation stories (join challenges, complete HRA, act on insights, redeem rewards, run the platform).

---

## Why this structure

1. **Compact hero** with jump chips: orient in one screen, no product mock wall.
2. **Two path cards** mirror the mega-menu columns so the hub and nav feel like one system.
3. **Challenges block:** library is larger (flagship), then four program cards for already-shipped pages.
4. **Health & rewards block:** three equal cards ordered as data in → data out → action, with a short chain label (not a third full page of copy).
5. **Platform featured band:** earns the high-demand “wellness platform” intent without becoming a homepage clone.
6. **Closing CTA:** Book a demo primary; secondary explores the library (chooser-friendly).

Density stays light: one-line descriptions, verb-led card CTAs, scannable tags.

---

## Full copy deck

### Meta
- **Title:** Employee Wellness Solutions | Vantage Fit  
- **Description:** Choose wellness challenges, health risk assessment, workforce insights, rewards, or the full platform. Built for enterprise HR participation programs.

### Nav (Solutions mega, current-state on hub)
- Wellness challenges (Library)  
- Step challenges · Multi-activity · Remote & hybrid team · Virtual marathon  
- Health Risk Assessment · Workforce health insights · Wellness rewards program  
- Banner: Explore the wellness platform  

### Hero
- **Eyebrow:** Solutions  
- **H1:** Find the wellness solution that fits how you run the program.  
- **Lead:** Challenges people join, health data that stays useful, rewards tied to real effort, and one platform that ties it together. Pick a path below.  
- **Primary CTA:** Book a demo  
- **Secondary CTA:** Explore challenges  
- **Jump chips:** Wellness challenges · Health & rewards · Wellness platform  

### Path overview (2 cards)
1. **Wellness challenges**  
   Run company-wide programs people choose to join, from step races to multi-activity calendars.  
   CTA: Browse challenges  

2. **Workforce health & rewards**  
   Baseline health (HRA), board-ready insights, and points people redeem for real effort.  
   CTA: See the data chain  

### Section ① Wellness challenges
- **Eyebrow / H2:** Wellness challenges  
- **Lead:** Start with the full library, or jump into a format your teams already ask for.

**Library card (featured in section)**  
- Title: Wellness challenges library  
- Tag: Flagship  
- Body: Ready-to-run programs across physical, mental, nutrition, sleep, team, and holistic themes. Pick a template, set audience rules, launch.  
- CTA: Open the library →  

**Program cards**
| Title | One-liner | Link |
|---|---|---|
| Step challenges | Company-wide step goals with phone-first tracking and live leaderboards. | steps mock |
| Multi-activity challenges | Any mix of activities, solo or in teams, over themed weeks. | multi-activity mock |
| Remote & hybrid team challenges | Squads and average scoring so hybrid teams compete fairly. | team mock |
| Virtual marathon | Distance events powered by steps that unite a distributed workforce. | virtual marathon mock |

### Section ② Workforce health & rewards
- **Eyebrow / H2:** Workforce health & rewards  
- **Lead:** Data in, data out, then action. Each page owns one job in the chain.

**Chain strip:** Health Risk Assessment → Workforce health insights → Wellness rewards  

| Tag | Title | One-liner | Link |
|---|---|---|---|
| Data in | Health Risk Assessment | Voluntary baseline questionnaire that feeds aggregate risk views and Wellness Score baseline. | HRA mock |
| Data out | Workforce health insights | Org Wellness Score, AI insights, and participation/challenge/activity in one console. | Insights mock |
| Action | Wellness rewards program | Points for completed tasks, wallet balance, and gift-card redemption tied to real effort. | Rewards mock |

### Featured platform
- **Eyebrow:** Featured · Product  
- **H2:** The wellness platform employees use every day.  
- **Body:** Challenges, tracking, HRA and scores, rewards, and HR analytics in one system. Built for participation, not clinical surveillance.  
- **Micro:** Wearables · HRIS / SSO · HIPAA · SOC 2 · GDPR · ISO  
- **Primary:** Explore the platform  
- **Secondary:** Book a demo  

### Final CTA
- **H2:** Not sure where to start?  
- **Lead:** We will map a 90-day path from your first challenge to measurable participation.  
- **Primary:** Book a demo  
- **Secondary:** See pricing  

### Footer Solutions links
Hub (current), library, steps, HRA, platform (relative mocks where available).

---

## Mega-menu fit

Hub is the index under Solutions. Mega-menu columns match page sections ① and ②. Platform is featured on the hub (and can sit as mega banner), not a third equal column of links. No extra top-level Solutions items invented.

---

## Data-chain role

Hub **labels** the chain (in → out → action) and routes. It does not explain HRA fields, score math, or wallet config. Those live on the three program pages.

---

## Visual / component decisions

- Link `../styles/enterprise.css` + page-scoped hub styles only.
- Card grid, not long prose sections.
- Product-feel cards with small icons/tags (no stock illustration dump).
- Jump chips as in-page anchors for scanability.
- Mobile: single-column stacks; nav reuses enterprise mobile mega pattern.

---

## Assumptions & gaps

1. Sibling mocks for library, HRA, insights, rewards, and platform may not all exist yet in `grok/`; hub still links the **signed-off filenames** so the set wires up as pages land.  
2. No customer proof section on hub (optional and not needed for a chooser).  
3. Secondary hero CTA goes to challenges library (chooser intent) rather than pricing; pricing appears in final band and nav.  
4. Menu descriptions adapted lightly for card body length; product claims stay within shared research product truth.  
5. Mental health remains off the Solutions top-level set per signed-off menu (moved out of Solutions IA).

---

## Sources

- `menu/vantage-fit-solutions-menu-preview.html` (IA, labels, demand notes)  
- `grok/_SHARED-RESEARCH-AND-SYSTEM.md` (product truth, filenames, CTAs, guardrails)  
- `styles/enterprise.css` + `styled-homepage/index.html` (visual system)  
- Existing Grok challenge mocks for chrome and shipped program links  
- Condensed product truth (challenges library, HRA, insights, rewards, platform) from shared research only; no new stats invented
