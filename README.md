# NC Design System 2.0

**Product:** Netcore Customer Engagement Platform
**System Name:** Infinity DS 2.0
**Status:** In Progress — Foundations complete, flows to be added per surface

---

## What This Is

The single source of truth for all UI design decisions for the Netcore CE platform. This folder contains design tokens (color, typography, spacing) and component constraints that AI and designers use when generating or reviewing designs.

---

## Product Context

**Platform:** Netcore Customer Engagement — AI-powered growth marketing platform for marketers and admins.

### Core Surfaces
| Surface | Description |
|---|---|
| Campaigns | Create & manage email, SMS, push, WhatsApp, RCS, in-app, Facebook campaigns |
| Journeys | Multi-step automation flows with branching logic |
| Analytics | Funnel, Cohort, RFM, User Path, Actionable Insights |
| Audience | Segments, lists, blocklisting, attributes |
| Content Manager | Template libraries, product catalog |
| Co-Marketer (AI) | Subject line optimizer, send-time optimizer, path optimizer, insights |

---

## Folder Structure

```
NC-design-system-2.0/
├── README.md                          ← this file
│
├── tokens/
│   ├── color-tokens.json              ← brand, semantic, text, surface, border, channel colors
│   ├── typography-tokens.json         ← font family, weights, text scale, headings
│   └── spacing-tokens.json            ← 4px grid, border radius, layout constants
│
├── components/
│   ├── top-navigation.json            ← top nav height, layout, slot definitions
│   ├── side-navigation.json           ← side nav width, item specs, nav sections
│   └── ...                            ← more components added per surface
│
└── screens/                           ← (to be added per flow)
    └── ...
```

---

## Token Format

All tokens follow the W3C Design Token spec — `$value` + `$type`. Tokens can alias other tokens:

```json
{
  "color": {
    "primary": {
      "cobalt-blue": { "$value": "#162F58", "$type": "color" }
    },
    "border": {
      "focus": { "$value": "{color.primary.cobalt-blue}", "$type": "color" }
    }
  }
}
```

Values marked `VERIFY` need to be confirmed against Zeroheight or Figma.

---

## Reference Links
- Product Docs: https://cedocs.netcorecloud.com/docs/overview
- Old DLS (Zeroheight): https://netcore.zeroheight.com/759faf070/p/747aa5-introduction
- Figma File: [add your Figma file link here]
