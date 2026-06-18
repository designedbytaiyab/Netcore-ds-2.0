# Tokens Reference — Netcore DS 2.0

Load this file whenever generating any UI. These are the authoritative values from `design_system_styles.css` (Zeroheight export). Never hardcode hex values in output — always reference the CSS variable name alongside any value you use.

---

## Typography

**Font:** Nunito Sans — all weights and sizes below apply to this family only.
**fontVariationSettings:** `"YTLC" 500, "wdth" 100` — required on every Nunito Sans instance without exception. Omitting this makes the text look visibly different.
**Default text color:** `#17173A` (`--text-charcoal`) — not `#000000`.
**Button text:** always UPPERCASE regardless of style token used.

| Token | Weight | Size | Line-H | Letter-S | Primary use |
|---|---|---|---|---|---|
| header-h1 | 700 | 24px | 32px | 0.4px | Page headings |
| header-h2 | 700 | 20px | 28px | 0.4px | Section headings |
| header-h3 | 700 | 16px | 22px | 0.4px | Card / sub-section titles |
| header-h4 | 700 | 14px | 20px | 0.4px | Table headers, form labels |
| headline-1 | 600 | 18px | 24px | 0.4px | Prominent sub-headlines |
| headline | 600 | 14px | 20px | **0.3px** | Widget labels ⚠️ only exception to 0.4px |
| emphasis | 600 | 14px | 20px | 0.4px | Nav labels, key terms, field labels |
| body-bold | 700 | 14px | 20px | 0.4px | Data values, metric numbers |
| body-regular | 400 | 14px | 20px | 0.4px | Descriptions, table cells, body copy |
| button-default | 600 | 14px | 20px | 0.4px | All buttons (UPPERCASE) |
| small-b | 700 | 12px | 16px | 0.4px | Compact table headers |
| small-sb | 600 | 12px | 16px | 0.4px | Secondary small labels |
| small-xb | 800 | 12px | 16px | 0.4px | Status chips, strong small text |
| caption-c1 | 400 | 12px | 16px | 0.4px | Timestamps, helper text, char count |
| status | 700 | 10px | 16px | 0.4px | Status badge text (ACTIVE, DRAFT…) |

---

## Colors

All values confirmed from `design_system_styles.css`. The CSS variable name is the identifier to use in code.

### Primary
| Token | Hex | CSS Variable |
|---|---|---|
| Cobalt Blue | `#143F93` | `--primary-cobalt-blue` |
| Core Orange | `#FF6B37` | `--primary-core-orange` |
| Ash | `#E8EAF0` | `--primary-ash` |

### Secondary
| Token | Hex | CSS Variable |
|---|---|---|
| Azure | `#0A8FFD` | `--secondary-azure` |
| Green | `#00C48C` | `--secondary-green` |
| Orange | `#FFA26B` | `--secondary-orange` |
| Purple | `#6979F8` | `--secondary-purple` |
| Red | `#F05C5C` | `--secondary-red` |
| Violet | `#BE52F2` | `--secondary-violet` |
| Yellow | `#FFCF5C` | `--secondary-yellow` |

### Tertiary / Surface
| Token | Hex | CSS Variable |
|---|---|---|
| Chalk (surface bg) | `#F6F6F6` | `--tertiary-chalk` |
| Almost Grey (borders) | `#DDE2EE` | `--tertiary-almost-grey` |
| Light Blue BG | `#F4F8FF` | `--tertiary-light-blue-bg` |
| Dark Nav (L1 side nav) | `#17173A` | `--surface-dark-nav` |

### Text
| Token | Hex | CSS Variable |
|---|---|---|
| Charcoal (default) | `#17173A` | `--text-charcoal` |
| Grey (secondary text) | `#6F6F8D` | `--text-grey` |
| White | `#FFFFFF` | `--text-white` |

### Semantic
| Token | Hex | CSS Variable |
|---|---|---|
| Error | `#F05C5C` | `--error-state-red` |
| Warning | `#FFCF5C` | `--warning-state-yellow` |
| Success | `#00C48C` | `--success-state-green` |
| Info | `#0A8FFD` | `--info-state-azure` |

---

## Spacing

Base grid is 8px. Adjust in 4px increments. Micro-adjustments only at 2px.

| Token | Value | Use |
|---|---|---|
| spacing-2 | 2px | Micro gaps (icon to label) |
| spacing-4 | 4px | Tight internal padding |
| spacing-8 | 8px | Default gap between elements |
| spacing-12 | 12px | Medium internal padding |
| spacing-16 | 16px | Standard component padding |
| spacing-20 | 20px | Section gaps (small) |
| spacing-24 | 24px | Section gaps (medium) |
| spacing-32 | 32px | Between sections |
| spacing-40 | 40px | Large layout gaps |
| spacing-48 | 48px | Page-level section spacing |

### Border Radius
| Token | Value | Use |
|---|---|---|
| radius-2 | 2px | Tags, status chips |
| radius-4 | 4px | Buttons, inputs, cards (standard) |
| radius-8 | 8px | Modals, side drawers, larger cards |
| radius-full | 50% | Avatars, circular badges |

---

## Elevation (Shadows)

Use the right shadow for the right context — they're not interchangeable.

| Token | Value | Use |
|---|---|---|
| light-shadow | `0px 5px 12px rgba(23,23,58,0.07)` | Cards, tooltips, dropdowns |
| standard-shadow | `0px 5px 15px rgba(23,23,58,0.15)` | Modals, side drawers, popovers |
| inverted-shadow | `0px -6px 14px rgba(23,23,58,0.05)` | Sticky footer CTA bars |
| tint-shadow | `0px 5px 10px rgba(23,23,58,0.05)` | Top navigation bar |
| azure-horizontal-highlight | `0px 1px 4px rgba(10,143,253,0.5)` | Focus states |
| cobalt-horizontal-highlight | `0px 1px 4px rgba(20,63,147,0.5)` | Active / pressed states |

---

## Layout Grid

Three layout states depending on which navigation is visible.

```
No menu (full width):
┌──────────────────────────────────────────┐
│              TOP NAV (60px)              │
├──────────────────────────────────────────┤
│ 30px │         Content          │ 45px  │
└──────────────────────────────────────────┘

L1 only (60px icon nav):
┌────────────────────────────────────────────┐
│                TOP NAV (60px)              │
├──────┬─────────────────────────────────────┤
│ L1   │ 30px │   Content    │ 45px          │
│ 60px │      │ gutter: 80px │               │
└──────┴─────────────────────────────────────┘

L1 + L2 (60px + 200px nav):
┌──────────────────────────────────────────────┐
│                 TOP NAV (60px)               │
├──────┬────────┬──────────────────────────────┤
│ L1   │  L2   │ 30px │  Content  │ 45px       │
│ 60px │ 200px │      │ gutter:67 │            │
└──────┴────────┴──────────────────────────────┘
```

### Fixed Chrome Heights
| Element | Height |
|---|---|
| Top navigation | 60px |
| L1 side nav width | 60px |
| L2 side nav width | 200px |
| Table row | 48px |
| Button (small) | 28px |
| Button (default) | 32px |
| Button (large) | 40px |
| Input field | 36px (single line) |
| Nav item | 40px |

---

## Channel Colors (for campaign channel icons)

| Channel | Hex | CSS Variable |
|---|---|---|
| Email | `#0078D4` | `--channel-email` |
| SMS | `#00C48C` | `--channel-sms` |
| WhatsApp | `#25D366` | `--channel-whatsapp` |
| App Push | `#6979F8` | `--channel-app-push` |
| Web Push | `#FFA26B` | `--channel-web-push` |
| RCS | `#BE52F2` | `--channel-rcs` |
| In-App | `#0A8FFD` | `--channel-in-app` |
| Web Message | `#FF6B37` | `--channel-web-message` |
