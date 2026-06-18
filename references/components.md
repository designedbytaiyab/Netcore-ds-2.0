# Components Reference — Netcore DS 2.0

Load this file when building or choosing any component. The rules here exist to enforce consistency across the platform — each one reflects a deliberate product decision, not an arbitrary style choice.

---

## Buttons

Primary buttons use cobalt blue (`#143F93`) fill with white uppercase text. Secondary buttons use white fill with an `#DDE2EE` border and cobalt text. There should only ever be one Primary button per screen section — it's the signal for what the most important action is.

| Property | Value |
|---|---|
| Heights | 28px (sm) / 32px (default) / 40px (lg) |
| Horizontal padding | 16px |
| Border radius | 4px |
| Text style | button-default (600/14px) — always UPPERCASE |
| Primary fill | `#143F93` (`--primary-cobalt-blue`) |
| Secondary border | `1px solid #DDE2EE` |
| Disabled state | `#F6F6F6` bg, `#DDE2EE` text |
| Icon buttons | 16px icon, centered, 32×32px hit area minimum |

---

## Navigation

### L1 Side Nav
The dark navy background (`#17173A`) is the primary visual identity of the Netcore product. Using chalk or white here would make it look like a different product entirely.

| Property | Value |
|---|---|
| Width | 60px |
| Background | `#17173A` (`--surface-dark-nav`) |
| Icons | 20px, white outline |
| Active icon | cobalt blue `#143F93` |
| Nav item height | 40px |

### L2 Side Nav
| Property | Value |
|---|---|
| Width | 200px |
| Background | `#F6F6F6` (`--tertiary-chalk`) |
| Text style | emphasis (600/14px) |
| Active item | 3px left cobalt border + `#F4F8FF` row fill |
| Nav item height | 40px |

### Top Navigation
| Property | Value |
|---|---|
| Height | 60px (not 56px — confirmed from Figma) |
| Background | `#FFFFFF` |
| Shadow | `tint-shadow: 0px 5px 10px rgba(23,23,58,0.05)` |
| CREATE button | Primary button, right side |
| Search | center-aligned, 400px wide |

---

## Text Fields

Full spec in `components/text-fields.json`. Key values:

| Property | Value |
|---|---|
| Sizes | L: 620px / M: 300px / S: 140px |
| Padding | px: 15px, py: 11px |
| Border (default) | `1px solid #DDE2EE` |
| Border (focus) | `1px solid #143F93` |
| Focus ring | `box-shadow: 0px 0px 0px 4px #DBE7FF` |
| Border radius | 4px |
| Disabled bg | `#F6F6F6` (chalk) |
| Error border | `1px solid #F05C5C` |
| Label style | emphasis (600/14px) — above the field, never inside |
| Placeholder color | `#6F6F8D` |

---

## Data Tables

Tables are the most common surface in Netcore. Row height is fixed so tables feel consistent across the entire product.

| Property | Value |
|---|---|
| Row height | 48px |
| Header style | small-b (700/12px) or header-h4 (700/14px) |
| First column | sticky on horizontally scrollable tables |
| Loading state | wave skeleton — never pulse |
| Hover state | `#F4F8FF` row fill |
| Selected row | `#F4F8FF` fill + cobalt left border 3px |
| Status chips | UPPERCASE text, status style (700/10px), colored background |

---

## Loading States

Wave skeleton is the Netcore standard. Pulse is the default in most component libraries, so this almost always needs an explicit override.

| Context | Loader |
|---|---|
| Data tables, card lists, any content that takes >1s | Wave skeleton |
| Short actions with no predictable end (<3s) | Spinner (cobalt, 20px) |
| Known progress (file import, field mapping) | Progress bar with count label ("22 / 46 fields") |

Never show a plain "Loading…" text without context of what's loading.

---

## Icons

The outline/filled rule exists because Segmentation is visually distinct from the rest of the product — it uses filled icons to signal that you're in a different mode.

| Context | Style |
|---|---|
| All product icons | Outline only |
| Segmentation component only | Filled |
| Inline (text + icon) | 16px |
| Navigation | 20px |
| Hero / empty state | 24px |
| Icon color (default) | `#6F6F8D` (grey) |
| Icon color (active) | `#143F93` (cobalt) |

---

## Empty States

An empty state with just an illustration and no CTA leaves the user stranded. All four elements are required because each one serves a different job — illustration draws attention, headline names the state, body explains the value, CTA gives the next step.

Every empty state must have:
1. **Brand illustration** — flat, character-based, Netcore palette
2. **H3 headline** — Title Case, 3–6 words, names what's missing or what can be done
3. **Body copy** — 1–2 sentences, explains what the user gets by taking action
4. **UPPERCASE CTA button** — specific action (e.g. `+ CREATE CAMPAIGN`, `+ ADD FILTER`)

---

## Modals / Overlays

Modal = Overlay + PopUp together. Never render one without the other — a popup without a dim overlay doesn't clearly separate the user from the background context.

| Property | Value |
|---|---|
| Overlay background | `#17173A` at 0.5 opacity |
| PopUp shadow | `standard-shadow: 0px 5px 15px rgba(23,23,58,0.15)` |
| Border radius | 8px |
| Destructive confirmations | Name the specific item in the Primary CTA (e.g. `DELETE CAMPAIGN TITLE`, not just `DELETE`) |

### Campaign-specific modals
- Campaign type selection: 840px wide, right-side panel, full viewport height
- Campaign channel selection: 1136px wide, right-side panel, full viewport height

---

## Cards

| Property | Value |
|---|---|
| Shadow | `light-shadow: 0px 5px 12px rgba(23,23,58,0.07)` |
| Border radius | 8px |
| Background | `#FFFFFF` |
| Hover shadow | `standard-shadow` |

### Campaign Channel Cards (230×72px)
Used in the campaign engage screen. Icon (24×24px) sits in a 60×60px decorative container on the right. Label uses emphasis style (600/14px).

---

## Status Chips

| Status | Color | Background |
|---|---|---|
| ACTIVE / RUNNING | `#00C48C` | `#E6FBF5` |
| DRAFT | `#6F6F8D` | `#F6F6F6` |
| SCHEDULED | `#0A8FFD` | `#E8F5FF` |
| PAUSED | `#FFA26B` | `#FFF4EC` |
| COMPLETED | `#143F93` | `#EEF3FF` |
| FAILED | `#F05C5C` | `#FFF0F0` |
| ARCHIVED | `#6F6F8D` | `#F6F6F6` |

Text style: `status` (700/10px), always UPPERCASE, border-radius 2px.

---

## Toasts & Notifications

| Type | Duration | Behavior |
|---|---|---|
| Success | 4–5 seconds | Auto-dismiss |
| Info | 4–5 seconds | Auto-dismiss |
| Warning | 5–7 seconds | Auto-dismiss |
| Error | Persistent | User must dismiss |

Copy pattern: Success → "Campaign saved." / Error → "Couldn't save. Check your connection and try again."

---

## Pre-Generation Checklist

Before producing any design output, confirm:

- [ ] Token files loaded — color, typography, spacing values available
- [ ] Platform surface identified (CEE / CDP / Email API)
- [ ] Layout state identified (no menu / L1 only / L1+L2)
- [ ] Figma node queried if this is a named screen
- [ ] Primary action identified — what should the user do first?
- [ ] Empty and loading states considered

---

## Post-Generation Checklist

Before returning output to the user, verify:

**Tokens**
- [ ] All colors reference CSS variable names, not raw hex
- [ ] Every Nunito Sans instance has `fontVariationSettings: "YTLC" 500, "wdth" 100`
- [ ] Default text color is `#17173A`, not `#000000`
- [ ] Spacing values are on the 4px/8px grid

**Typography**
- [ ] All button labels are UPPERCASE
- [ ] `headline` style uses `0.3px` letter-spacing (the only exception to 0.4px)
- [ ] Status badge text uses `status` style (700/10px)

**Layout**
- [ ] Top nav height is 60px
- [ ] L1 side nav has dark navy (`#17173A`) background
- [ ] Correct layout grid for nav state applied

**Components**
- [ ] Loading states use wave skeleton (not pulse) for tables
- [ ] Icons are outline except in Segmentation
- [ ] Modals include overlay + popup together
- [ ] Empty states have all 4 required elements
- [ ] Elevation token matches the use case

**UX Writing**
- [ ] No vague CTAs ("Click here", "Submit", "OK")
- [ ] Error messages say what went wrong + how to fix it
- [ ] Status labels use the standard vocabulary
- [ ] Numbers at scale use K/M/B (1.2M, not 1,234,567)
