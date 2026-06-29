# Netcore DLS 2.0 — Design Skill

> Infinity Design System 2.0 for the Netcore Customer Engagement Platform.
> Every UI generation using this skill MUST follow these rules exactly. No exceptions.
> **Copywriting companion:** UI strings, voice, and Netcorian rules live in `copywriting/spec.md` and `copywriting/SKILL.md`. This file governs visual tokens and components only.

---

## Reference Files (Load Before Any Design Task)

### Live Figma Source (Primary Reference)
| Resource | Details |
|---|---|
| **Figma File** | https://www.figma.com/design/GTAOKrmqHr65sLErXRivA6 |
| **File Key** | `GTAOKrmqHr65sLErXRivA6` |
| **Pages** | 48:2941 Cover · 5:72 Icons · 33:2896 Atoms · 60:2987 Molecules · 144:7737 Organisms |
| **How to query** | Use `get_design_context(fileKey, nodeId)` for exact component specs + code · `get_variable_defs(fileKey, nodeId)` for live token values · `get_metadata(fileKey)` for page/node structure |
| **Letter-spacing note** | Figma raw value = 0.41999… ≈ **0.42px**. CSS export rounds to **0.4px**. Both are correct — use 0.4px in CSS variables, 0.42px when referencing Figma directly. |

### Authoritative Token Sources
| File | Contents | When to Load |
|---|---|---|
| `/Users/taiyabafsar/Downloads/design_system_styles.css` | CSS token export from Zeroheight — authoritative hex values + CSS variable names | Always |
| `NC-design-system-2.0/tokens/color-tokens.json` | All color tokens with descriptions | Always |
| `NC-design-system-2.0/tokens/typography-tokens.json` | Full type scale (15 styles) + font rules | Always |
| `NC-design-system-2.0/tokens/spacing-tokens.json` | Spacing, radius, elevation, layout grid | Always |

### Component & Pattern References
| File | Contents | When to Load |
|---|---|---|
| `NC-design-system-2.0/component-inventory.json` | Full component list with Figma nodes + Zeroheight refs | When choosing which component to use |
| `NC-design-system-2.0/ux-writing.md` | UX writing rules + copy checklist | When writing any UI copy |
| `NC-design-system-2.0/principles.md` | Design principles 1–4 | When making layout/hierarchy decisions |
| `NC-design-system-2.0/components/top-navigation.json` | Top nav exact specs | When generating top nav |
| `NC-design-system-2.0/components/side-navigation.json` | Side nav exact specs | When generating side nav |
| `NC-design-system-2.0/components/text-fields.json` | Input sizes (L:620/M:300/S:140), focus ring spec (#DBE7FF), states, Category Labels variant | When generating forms or inputs |

### Screen-Level References (Real Netcore Designs)
| File | Contents | When to Load |
|---|---|---|
| `NC-design-system-2.0/screens/campaign-creation.json` | All 10 campaign creation screens — exact sizes, layout structure, node IDs | **ALWAYS** when generating any campaign UI |

### Second Figma File — Campaign Creation Reference Designs
| Resource | Details |
|---|---|
| **Figma File** | `H2W6ldaO1Py7WW5c3b6YpW` (Netcore MCP — Design) |
| **Screenshots section** | node `31:4752` — 10 full campaign screens as reference images |
| **Assets section** | node `31:4753` — exact component specs for all campaign screens |
| **Per-screen lookup** | Call `get_design_context(fileKey='H2W6ldaO1Py7WW5c3b6YpW', nodeId='<id>')` for any screen — see `screens/campaign-creation.json` for node IDs |

### Brand Assets
| File | Contents |
|---|---|
| `/Users/taiyabafsar/Downloads/Logo___Brand_Assets.zip` | Netcore logo, wordmark, icon variants — use for all logo placement |
| `/Users/taiyabafsar/Downloads/design_system_styles.css` | All CSS variables — use these names in code output |

---

## TRIGGER MAP — What to Load for Each Request

When a prompt matches a trigger below, load the listed files BEFORE generating anything.

| Trigger phrases | Load these files | Figma lookup |
|---|---|---|
| "campaign creation flow", "create a campaign", "new campaign", "campaign setup", "campaign wizard" | `screens/campaign-creation.json` + all 3 token files | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:1001')` for Setup screen |
| "campaign type", "how would you like to start", "engage / analyze / create / manage" | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:512')` |
| "campaign channel", "campaign engage", "email campaign", "sms campaign", "whatsapp campaign", "push campaign" | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '23:820')` |
| "campaign audience", "audience targeting", "segment selection" | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:694')` |
| "campaign content", "template gallery", "email template picker" | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:3804')` |
| "campaign schedule", "send now / send later", "frequency cap" | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:4435')` |
| "campaign preview", "campaign review", "campaign summary" | `screens/campaign-creation.json` | `get_design_context('H2W6ldaO1Py7WW5c3b6YpW', '31:4154')` |
| "top navigation", "top bar", "top nav", "header" | `components/top-navigation.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '299:13696')` |
| "side navigation", "side nav", "left nav", "navigation menu" | `components/side-navigation.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '577:55775')` |
| "text field", "input", "form", "text input" | `components/text-fields.json` | `get_design_context('GTAOKrmqHr65sLErXRivA6', '6183:17159')` |
| "data table", "table", "listing page", "campaign list" | `component-inventory.json` (data-tables section) | `get_design_context('GTAOKrmqHr65sLErXRivA6', '144:7737')` for Organisms page |
| "empty state", "no data", "zero state" | `component-inventory.json` (empty-states section) + `ux-writing.md` | — |
| "modal", "popup", "dialog", "confirmation" | `component-inventory.json` (modals-popups section) | — |
| "button", "CTA", "action button" | `component-inventory.json` (atoms.buttons section) | — |
| "any UI generation" (catch-all) | All 3 token files + `component-inventory.json` | — |

### MANDATORY WORKFLOW for Screen-Level Requests

When the trigger is a **named screen** (campaign creation, audience page, etc.):

```
1. Load screens/campaign-creation.json → find the screen's figma-node ID
2. Call get_design_context(fileKey='H2W6ldaO1Py7WW5c3b6YpW', nodeId='<id>')
3. Load all 3 token files
4. Use Figma output as the EXACT layout reference — do NOT invent structure
5. Apply DLS tokens for all colors, typography, spacing
6. Run POST-GENERATION CHECKLIST before returning output
```

**Never generate a campaign screen from memory or guesswork. Always pull from Figma first.**

---

## PRE-GENERATION CHECKLIST

**Run through every item before producing any design output.**

### 1. Files Loaded
- [ ] Loaded `color-tokens.json` — have all color tokens available
- [ ] Loaded `typography-tokens.json` — have full type scale available
- [ ] Loaded `spacing-tokens.json` — have layout, spacing, elevation values
- [ ] Loaded component inventory if choosing components
- [ ] Loaded UX writing rules if writing any labels, CTAs, or copy

### 2. Context Established
- [ ] I know which platform surface this is for (CEE / CDP / Email API / etc.)
- [ ] I know which layout state applies (no menu / L1 only / L1+L2)
- [ ] I know if this is a new screen or extending an existing pattern
- [ ] I've identified which existing components to reuse (not reinvent)

### 3. Design Direction Clear
- [ ] The primary action is identified (what should the user do first?)
- [ ] The data hierarchy is clear (what's most important on screen?)
- [ ] Empty states and loading states are considered
- [ ] Error/edge cases are accounted for

---

## CORE DESIGN RULES (Non-Negotiable)

### Typography
- **Font:** Nunito Sans for ALL UI text
- **fontVariationSettings:** `"YTLC" 500, "wdth" 100` — MANDATORY on every Nunito Sans instance
- **Default text color:** `#17173A` (charcoal) — never pure black `#000000`
- **Button text:** ALWAYS UPPERCASE — no exceptions
- **Headline letter-spacing exception:** `headline` style uses `0.3px`, not `0.4px`

Full type scale:
| Token | Weight | Size | Line-H | Letter-S | Use |
|---|---|---|---|---|---|
| header-h1 | 700 | 24px | 32px | 0.4px | Page headings |
| header-h2 | 700 | 20px | 28px | 0.4px | Section headings |
| header-h3 | 700 | 16px | 22px | 0.4px | Card/sub-section titles |
| header-h4 | 700 | 14px | 20px | 0.4px | Table headers, form labels |
| headline-1 | 600 | 18px | 24px | 0.4px | Prominent sub-headlines |
| headline | 600 | 14px | 20px | **0.3px** | Widget labels (⚠️ 0.3px) |
| emphasis | 600 | 14px | 20px | 0.4px | Nav labels, key terms |
| body-bold | 700 | 14px | 20px | 0.4px | Data values, metric numbers |
| body-regular | 400 | 14px | 20px | 0.4px | Descriptions, table cells |
| button-default | 600 | 14px | 20px | 0.4px | ALL BUTTONS (UPPERCASE) |
| small-b | 700 | 12px | 16px | 0.4px | Compact table headers |
| small-sb | 600 | 12px | 16px | 0.4px | Secondary small labels |
| small-xb | 800 | 12px | 16px | 0.4px | Status chips, strong small |
| caption-c1 | 400 | 12px | 16px | 0.4px | Timestamps, helper text |
| status | 700 | 10px | 16px | 0.4px | Status badge text (ACTIVE, DRAFT…) |

### Colors
Key values from `design_system_styles.css`:
```
Primary:    Cobalt Blue #143F93   (--primary-cobalt-blue)
Text:       Charcoal    #17173A   (--text-charcoal)
Secondary:  Grey        #6F6F8D   (--tertiary-grey / --text-grey)
Surface:    Chalk       #F6F6F6   (--tertiary-chalk)
Border:     Almost Grey #DDE2EE   (--tertiary-almost-grey)
Tinted BG:  Light Blue  #F4F8FF   (--tertiary-light-blue-bg)
Azure:               #0A8FFD   (--secondary-azure)
Green:               #00C48C   (--secondary-green)
Orange:              #FFA26B   (--secondary-orange)
Purple:              #6979F8   (--secondary-purple)
Red/Error:           #F05C5C   (--secondary-red / --error-state-red)
Violet:              #BE52F2   (--secondary-violet)
Yellow/Warning:      #FFCF5C   (--secondary-yellow / --warning-state-yellow)
```
- Never hardcode hex values in designs/code — always reference a CSS variable or token name
- Dark nav background (L1 side nav): `#17173A` — NOT chalk

### Spacing & Grid
- Base grid: **8px**. Adjust in 4px increments. Micro: 2px.
- Layout grid states:
  - **No menu:** left 30px / gutter 30px / right 45px
  - **L1 only (60px nav):** 30px gap / right 45px / inner gutter 80px
  - **L1+L2 (60+200px):** 30px gap / right 45px / content gutter 67px
- Top nav height: **60px** (confirmed — not 56px)
- Side nav L1: **60px wide** (dark navy `#17173A`)
- Side nav L2: **200px wide** (chalk `#F6F6F6`)

### Elevation (which shadow to use)
| Use case | Token |
|---|---|
| Cards, tooltips, dropdowns | `light-shadow: 0px 5px 12px rgba(23,23,58,0.07)` |
| Modals, side drawers, popovers | `standard-shadow: 0px 5px 15px rgba(23,23,58,0.15)` |
| Sticky footer CTA bars | `inverted-shadow: 0px -6px 14px rgba(23,23,58,0.05)` |
| Top nav | `tint-shadow: 0px 5px 10px rgba(23,23,58,0.05)` |
| Focus states (azure) | `azure-horizontal-highlight: 0px 1px 4px rgba(10,143,253,0.5)` |
| Active/pressed (cobalt) | `cobalt-horizontal-highlight: 0px 1px 4px rgba(20,63,147,0.5)` |

---

## COMPONENT RULES (Enforced)

### Buttons
- Primary: cobalt blue fill, white UPPERCASE text, 4px radius
- Secondary: white fill, `#DDE2EE` border, cobalt text, UPPERCASE
- Never more than one Primary per screen section
- Height: 28px (sm) / 32px (default) / 40px (lg)
- Horizontal padding: 16px

### Navigation
- L1 side nav: **dark navy `#17173A` background** — not chalk, not white
- L2 side nav: chalk `#F6F6F6` background — text labels + outline icons
- Active item in L2: 3px cobalt left border + `#F4F8FF` row fill
- Top nav height: **60px** exactly

### Loading States
- **Tables & cards:** skeleton wave loader — **NOT pulse, NOT spinner**
- **Short actions (< 3s):** spinner (cobalt blue)
- **Known progress:** progress bar with count / total label

### Iconography
- Default: **outline style only**
- **Exception:** Segmentation component uses **filled** icons
- Sizes: 16px (inline), 20px (nav), 24px (hero/empty state)

### Empty States
Every empty state needs ALL FOUR:
1. Brand illustration
2. H3 headline (Title Case)
3. 1–2 sentence body copy
4. UPPERCASE CTA button

### Modal / Overlay pattern
- Modal = **Overlay + PopUp together** — never one without the other
- Overlay: `#17173A` at 0.5 opacity
- Destructive confirmations: name the specific item in the CTA button

### Data Tables
- Row height: 48px
- 1st column sticky on scrollable tables
- Status chips: UPPERCASE text, status (10px/700) typography

### Segmentation
- Uses filled icons (exception rule)
- CEE: Include/Exclude blocks with condition rows
- CDP: attribute/value row pairs with AND ▼ connectors

---

## POST-GENERATION CHECKLIST

**Verify every item before returning output to user.**

### Tokens & Styles
- [ ] Every color references a CSS variable name (`--primary-cobalt-blue`) or token path, not a raw hex
- [ ] Every font instance specifies `fontVariationSettings: "YTLC" 500, "wdth" 100`
- [ ] Default text uses `#17173A` (charcoal) — not `#000000`
- [ ] Spacing values fall on the 4px/8px grid
- [ ] Border radius matches token values (4px standard, 8px cards/modals)

### Typography
- [ ] All button labels are UPPERCASE
- [ ] `headline` style uses 0.3px letter-spacing (not 0.4px)
- [ ] Status badge text uses `status` style (10px/700)
- [ ] Caption/helper text uses `caption-c1` (12px/400)

### Layout
- [ ] Top nav height is 60px
- [ ] Correct layout grid applied for nav state (no menu / L1 / L1+L2)
- [ ] L1 side nav has dark navy (`#17173A`) background
- [ ] Content respects appropriate gutter/padding values

### Components
- [ ] Loading states use wave skeleton (not pulse/spinner) for tables
- [ ] Icons are outline (unless in Segmentation — then filled)
- [ ] Modals use the Overlay + PopUp combined pattern
- [ ] Empty states have all 4 required elements
- [ ] Elevation tokens match the use case (cards vs modals vs sticky bars)

### UX Writing
- [ ] No vague CTAs ("Click here", "Submit", "OK")
- [ ] Error messages explain what went wrong + how to fix
- [ ] Status labels use standard vocabulary (DRAFT/ACTIVE/SCHEDULED/PAUSED/COMPLETED/FAILED)
- [ ] Numbers at scale use K/M/B abbreviations
- [ ] Tooltips are ≤ 2 sentences and don't repeat the label

### Brand
- [ ] Netcore logo used from `/Users/taiyabafsar/Downloads/Logo___Brand_Assets.zip`
- [ ] Illustration style matches Netcore brand (flat, character-based, brand palette)

---

## LAYOUT GRID DIAGRAM

```
No menu:
┌──────────────────────────────────────────┐
│              TOP NAV (60px)              │
├──────────────────────────────────────────┤
│ 30px │        Content        │ 45px      │
└──────────────────────────────────────────┘

L1 only (60px icon nav):
┌────────────────────────────────────────────────┐
│                  TOP NAV (60px)                │
├──────┬─────────────────────────────────────────┤
│ L1   │  30px gap │    Content      │ 45px      │
│ 60px │           │  gutter: 80px   │           │
└──────┴─────────────────────────────────────────┘

L1 + L2 (60 + 200px):
┌────────────────────────────────────────────────────┐
│                    TOP NAV (60px)                  │
├──────┬────────┬───────────────────────────────────┤
│ L1   │  L2   │  30px │  Content  │ 45px           │
│ 60px │ 200px │       │ gutter:67 │                │
└──────┴────────┴───────────────────────────────────┘
```

---

## PRODUCT CONTEXT

**Platform:** Netcore Customer Engagement — AI-powered growth marketing (CEE) + Customer Data Platform (CDP)

**Core Surfaces:**
| Surface | Description |
|---|---|
| Campaigns | Email, SMS, Push, WhatsApp, In-App, RCS |
| Journeys | Multi-step automation with node-based builder |
| Analytics | Funnel, Cohort, RFM, User Flow, Dashboard |
| Audience / Segmentation | CEE filter, CDP filter, contact lists |
| Content Manager | Templates, product catalog |
| Raman AI | Subject line optimizer, send-time, insights |

**Users:** Marketers (primary), Admins (secondary)

---

## ZEROHEIGHT REFERENCE

Full DLS documented at: `netcore.zeroheight.com/759faf070`

Navigation structure:
- **Overview:** Introduction, Principles, Updates
- **Communication:** UX Writing
- **Style:** Colors, Typography, Layout Guidelines, Elevation, Iconography, Illustrations & Motion
- **Components:** Buttons → UI Loaders → Overlays → Text Fields → Dropdowns → Tags → Slider Selectors → Toasts & Flags → Drop Zone → Tooltips → Cards → Side Drawers → PopUps → Left Navigation → Calendar → Progress Indicator → Top Bar → Modals → Tabs & Menu → Segmentation → Journey → Charts & Analysis → Accordion → Filters & Side Drawers → Miscellaneous → Progress Bar
- **Templates:** Data Tables, Empty States
- **Pages:** 404 Page
- **Resources:** Downloads, Nudges on CEE, Design tokens, (OLD) UX Writing Guide

---

## FILE SIZE NOTE

This skill file is the enforcer — it references data, it doesn't duplicate it.
Always load the JSON token files for exact values before generating anything.
Component-specific details live in `NC-design-system-2.0/components/<name>.json`.
