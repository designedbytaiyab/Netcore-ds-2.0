---
name: netcore-ds-2
description: Netcore Infinity Design System 2.0 — use this skill whenever building, designing, or modifying any UI for the Netcore Customer Engagement Platform or CDP. Apply whenever someone asks to create a campaign flow, build a dashboard, design navigation, render a data table, create a form or modal, build a settings screen, design an analytics view, or generate any screen that should look and feel like the Netcore product. Even if the request seems simple ("add a button", "show a filter panel") — always load this skill first so the output matches the real Netcore design system exactly.
---

# Netcore DLS 2.0

## What This Skill Is

This skill is the design intelligence layer for the **Netcore Infinity Design System 2.0** — the official design system used across the Netcore Customer Engagement Platform (CEE) and Customer Data Platform (CDP).

It packages everything an AI needs to generate UI that looks and behaves exactly like the real Netcore product: the full token library (colors, typography, spacing, elevation), component rules, UX writing standards, layout grids, and screen-level references for real Netcore flows like the campaign creation wizard.

## How It Helps

Without this skill, asking an AI to "build a campaign creation screen" or "design a data table" produces generic output — arbitrary colors, wrong fonts, made-up layouts. The result looks like a SaaS template, not Netcore.

With this skill loaded, the AI knows:
- **Exact tokens** — Cobalt Blue `#143F93`, Charcoal `#17173A`, Nunito Sans with the correct font variation settings, the full 15-style type scale
- **Real screen specs** — all 10 campaign creation screens documented with exact dimensions and Figma node IDs, so the AI can query the live Figma file for pixel-accurate layout
- **Component rules** — which shadow to use on a card vs a modal, why the L1 nav is dark navy and never chalk, why loading states use wave skeleton not pulse
- **UX writing standards** — buttons are always UPPERCASE, status labels follow a strict vocabulary, empty states always need all four elements
- **A trigger map** — matching common request phrases to the exact reference files and Figma nodes to load before generating anything

The result is UI that a Netcore designer would recognise as correct — not an approximation, but something that could ship.

## What It Covers

- Campaign creation flow (10 screens, 5-step stepper)
- Top navigation, side navigation (L1 dark + L2 chalk)
- Text fields, forms, inputs
- Data tables, status chips, filters
- Modals, overlays, side drawers
- Empty states, loading states
- Buttons, icons, cards, toasts
- Analytics charts (Donut, Line, Bar, Funnel, Cohort, RFM)
- Segmentation and audience targeting patterns
- Nudges and contextual education elements (CEE)

---

---

## Reference Files

| File | What's inside | Load when |
|---|---|---|
| `references/tokens.md` | Full type scale, color palette, spacing grid, elevation shadows, layout grids | Any UI generation |
| `references/components.md` | Component rules for buttons, nav, tables, modals, icons, loading states + pre/post checklists | Picking or building a component |
| `references/campaign-flow.md` | All 10 campaign creation screens, exact dimensions, Figma node IDs, stepper specs | Any campaign-related request |
| `tokens/color-tokens.json` | Full color token definitions with CSS variable names | When you need exact hex values |
| `tokens/typography-tokens.json` | All 15 type styles with exact values | When you need exact font values |
| `tokens/spacing-tokens.json` | Spacing, radius, elevation, layout measurements | When you need exact spacing values |
| `components/text-fields.json` | Input states, sizes (L/M/S), focus ring, Category Labels variant | Building forms |
| `components/top-navigation.json` | Top bar exact specs (60px height, create button, search) | Building top nav |
| `components/side-navigation.json` | L1 dark nav + L2 chalk nav exact specs | Building side nav |
| `screens/campaign-creation.json` | Machine-readable campaign screen specs with node IDs | Campaign flow generation |
| `design_system_styles.css` | Authoritative CSS variable export from Zeroheight | Verifying exact token values |
| `ux-writing.md` | DS 2.0 button case, empty states, status vocabulary | Building UI strings for 2.0 screens |
| `copywriting/SKILL.md` | Netcorian voice, `/copy` trigger, progressive disclosure | Writing or reviewing any Netcore copy |
| `copywriting/spec.md` | Full copywriting spec (companion to `netcore-dls2.md`) | Deep audit or onboarding |

---

## Copywriting

For UI strings beyond DS 2.0 surface rules → `copywriting/SKILL.md` and `copywriting/spec.md`.

Load `ux-writing.md` for 2.0-specific button UPPERCASE and empty state anatomy. Load `copywriting/SKILL.md` for Netcorian voice, jargon rules, and no em dashes.

---

## Figma Sources

Two Figma files back this skill. When a Figma node ID appears in the trigger map, call `get_design_context` on it — the live data is always more accurate than the static JSON.

| File | Key | What it contains |
|---|---|---|
| Infinity Design System 2.0 | `GTAOKrmqHr65sLErXRivA6` | DLS components — Atoms, Molecules, Organisms |
| Netcore MCP — Design | `H2W6ldaO1Py7WW5c3b6YpW` | Campaign creation flow — real Netcore screens |

One quirk: Figma reports letter-spacing as `0.41999…px`. The CSS export rounds it to `0.4px`. Both are correct — use `0.4px` in code, `0.42px` if referencing Figma directly.

---

## How to Handle Any Design Request

Every request goes through this lookup sequence — images first, then text specs, then Figma. Don't skip ahead. The image is the fastest way to ground the output in the real Netcore design before reading anything else.

```
Step 1 — Scan the request for trigger keywords (table below)
Step 2 — Display the reference image(s) for that trigger
Step 3 — Load the text spec file(s) for that trigger  
Step 4 — Call Figma if available and a node ID is listed
Step 5 — Generate using image + specs + tokens as the reference
Step 6 — Run the post-generation checklist before returning output
```

**Step 2 is not optional.** Surface the image before building anything — output it as a markdown image so it's visible in the chat. This grounds the output in the real design and lets the user confirm you're looking at the right thing before any code is written.

If an image file doesn't exist in `assets/` yet, note it and move to the text spec. Images are populated over time — see `assets/HOW-TO-EXPORT.md`.

---

## Trigger Map

Scan the user's request for any of these keywords. When you find a match, follow the full sequence above.

### Campaign Screens

| Keywords that trigger this | Image to display first | Then load these specs | Figma node (if available) |
|---|---|---|---|
| campaign creation flow, new campaign, campaign wizard, create a campaign | `assets/campaign-setup.png` | `references/campaign-flow.md` + `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:1001')` |
| campaign type, how would you like to start, engage analyze create manage | `assets/campaign-type-selection.png` | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:512')` |
| campaign channel, campaign engage, email campaign, sms campaign, whatsapp campaign, push campaign, rcs | `assets/campaign-channel-selection.png` | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:820')` |
| campaign setup, campaign details, campaign name, ga tracking, utm | `assets/campaign-setup.png` | `references/campaign-flow.md` + `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:1001')` |
| campaign audience, audience targeting, segment selection, who to send to | `assets/campaign-audience-step1.png` | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:694')` |
| campaign content, template gallery, email template picker, select template | `assets/campaign-content.png` | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:3804')` |
| campaign schedule, send now, send later, frequency cap, slice and send | `assets/campaign-schedule.png` | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:4435')` |
| campaign preview, campaign review, review before sending, campaign summary | `assets/campaign-preview.png` | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:4154')` |

### Navigation

| Keywords | Image | Specs | Figma |
|---|---|---|---|
| top navigation, top nav, top bar, header bar | `assets/top-navigation.png` | `components/top-navigation.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '299:13696')` |
| side navigation, side nav, left nav, navigation menu, sidebar | `assets/side-nav-l1.png` + `assets/side-nav-l2.png` | `components/side-navigation.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '577:55775')` |

### Forms & Inputs

| Keywords | Image | Specs | Figma |
|---|---|---|---|
| text field, input field, form field, text input, search field | `assets/text-field-states.png` | `components/text-fields.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '6183:17159')` |

### Data & Tables

| Keywords | Image | Specs | Figma |
|---|---|---|---|
| data table, table, listing page, campaign list, results table | `assets/data-table.png` | `references/components.md` → tables section | `get_design_context('GTAOKrmqHr65sLErXRivA6', '144:7737')` |

### Core Components

| Keywords | Image | Specs |
|---|---|---|
| button, CTA, action button, primary button | `assets/buttons.png` | `references/components.md` → buttons section |
| empty state, zero state, no data, nothing here | `assets/empty-state.png` | `references/components.md` → empty states section |
| modal, popup, dialog, confirmation | `assets/modal.png` | `references/components.md` → modals section |
| side drawer, filter panel, filter drawer, side panel | `assets/side-drawer.png` | `references/components.md` → side drawer section |
| status chip, status badge, draft active scheduled | `assets/status-chips.png` | `references/components.md` → status chips section |
| card, widget card, metric card | `assets/cards.png` | `references/components.md` → cards section |
| toast, notification, snackbar, alert | `assets/toast-notifications.png` | `references/components.md` → toasts section |
| accordion, expand collapse, expandable | `assets/accordion.png` | `references/components.md` |
| progress bar, progress indicator, step progress | `assets/progress-bar.png` | `references/components.md` |

### Analytics & Charts

| Keywords | Image | Specs |
|---|---|---|
| donut chart, pie chart, donut | `assets/charts-donut.png` | `references/components.md` |
| line chart, trend chart, line graph | `assets/charts-line.png` | `references/components.md` |
| bar chart, bar graph, column chart | `assets/charts-bar.png` | `references/components.md` |
| funnel, funnel analysis, conversion funnel | `assets/analytics-funnel.png` | `references/components.md` |
| cohort, cohort analysis, retention | `assets/analytics-cohort.png` | `references/components.md` |

### Other Surfaces

| Keywords | Image | Specs |
|---|---|---|
| nudge, tooltip nudge, contextual help, spotlight | `assets/nudge-with-cta.png` | `references/components.md` → nudges section |
| 404, error page, not found page | `assets/404-page.png` | — |
| filters, filter bar, active filters | `assets/filters.png` | `references/components.md` |

### Catch-all

If no trigger keyword matches, load `references/tokens.md` + `references/components.md` and generate using the token values and component rules as the baseline.

---

## Non-Negotiables

These five rules are the ones that most commonly get violated. They're non-negotiable because they're what makes the output look like Netcore and not a generic SaaS tool.

**Font variation settings are mandatory.** Nunito Sans without `fontVariationSettings: "YTLC" 500, "wdth" 100` looks noticeably different. Always include it.

**Text is charcoal, not black.** `#17173A` is the Netcore text color. Pure `#000000` looks out of place against the soft navy brand palette.

**Button labels are always uppercase.** This is a brand-level decision — every button across the entire platform uses uppercase text.

**The L1 side nav is dark navy.** Background color is `#17173A` — not chalk, not white, not grey. This is the primary visual anchor of every Netcore screen.

**Loading states use wave skeleton, not pulse.** Pulse animation is the default in most component libraries. Netcore uses wave. Always override this.

For the full rules including all component details and checklists, read `references/components.md`. For exact token values, read `references/tokens.md`.

---

## Product Context

**Platform:** Netcore Customer Engagement (CEE) + Customer Data Platform (CDP)

| Surface | Description |
|---|---|
| Campaigns | Email, SMS, Push, WhatsApp, In-App, RCS |
| Journeys | Multi-step automation, node-based builder |
| Analytics | Funnel, Cohort, RFM, User Flow, Dashboard |
| Audience | Segmentation, contact lists, filters |
| Content Manager | Templates, product catalog |
| Raman AI | Subject line optimizer, send-time, insights |

**Users:** Marketers (primary), Admins (secondary)

Full DLS reference: `netcore.zeroheight.com/759faf070`
