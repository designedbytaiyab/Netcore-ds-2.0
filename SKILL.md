---
name: Netcore DS 2.0
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

---

## Figma Sources

Two Figma files back this skill. When a Figma node ID appears in the trigger map, call `get_design_context` on it — the live data is always more accurate than the static JSON.

| File | Key | What it contains |
|---|---|---|
| Infinity Design System 2.0 | `GTAOKrmqHr65sLErXRivA6` | DLS components — Atoms, Molecules, Organisms |
| Netcore MCP — Design | `H2W6ldaO1Py7WW5c3b6YpW` | Campaign creation flow — real Netcore screens |

One quirk: Figma reports letter-spacing as `0.41999…px`. The CSS export rounds it to `0.4px`. Both are correct — use `0.4px` in code, `0.42px` if referencing Figma directly.

---

## Trigger Map

Match the request to a row, load the files listed, call the Figma node if one is shown.

| When the request is about… | Load | Call Figma |
|---|---|---|
| Campaign creation flow / new campaign / campaign wizard | `references/campaign-flow.md` + `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:1001')` |
| Campaign type selection ("how would you like to start") | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:512')` |
| Campaign channel / email / SMS / WhatsApp / push campaign | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:820')` |
| Audience targeting / segment selection | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:694')` |
| Campaign content / template gallery | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:3804')` |
| Campaign schedule / send now / frequency cap | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:4435')` |
| Campaign preview / campaign review | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:4154')` |
| Top navigation / top bar / header | `components/top-navigation.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '299:13696')` |
| Side navigation / left nav / navigation menu | `components/side-navigation.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '577:55775')` |
| Text field / input / form | `components/text-fields.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '6183:17159')` |
| Data table / listing page / campaign list | `references/components.md` (tables section) | `get_design_context('GTAOKrmqHr65sLErXRivA6', '144:7737')` |
| Empty state / zero state / no data | `references/components.md` (empty states section) | — |
| Modal / popup / confirmation dialog | `references/components.md` (modals section) | — |
| Any UI generation (catch-all) | `references/tokens.md` + `references/components.md` | — |

---

## Workflow for Screen-Level Requests

When someone asks for a named screen (campaign setup, audience page, etc.), the order matters:

1. Find the screen's Figma node ID from `screens/campaign-creation.json`
2. Call `get_design_context` on that node — this is your layout source of truth
3. Load `references/tokens.md` for colors, type, spacing
4. Use the Figma output as the exact structural reference — don't invent layout
5. Run the post-generation checklist from `references/components.md` before returning output

Generating a campaign screen from memory produces a generic result. The Figma call is what makes it look like the real product.

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
