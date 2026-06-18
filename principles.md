# Infinity DS 2.0 — Design Principles

Source: netcore.zeroheight.com/759faf070/p/2381cc-principles

> "Our design principles lie at the core of how we approach product design at Netcore."

Design principles help teams make design decisions that reflect their values. This defines the very basic first principle that one should keep in mind while making products for humans.

---

## 1. Jobs to be Done
Each feature or functionality is to be focused on the tasks or jobs that a user would want to achieve with the product. Anything which is not helping the user to achieve their goal and thus does not add enough value to the user, should therefore be removed.

**Design implication:** Every component, screen, and interaction must justify its existence by a user job. Strip anything decorative or redundant.

---

## 2. Modular Design
Repetitive flows and tasks to be designed with a modular approach which can be called in from any other feature of the product.

**Example:** User segmentation can be called from anywhere within Email, APN, BPN etc.

**Design implication:** Never design a flow exclusively for one surface. Components like segmentation, audience picker, date range, and content editor must be reusable across all channels.

---

## 3. Consistency
We choose to display UI elements only when they are needed, rather than make them available at all times.

**Design implication:** Progressive disclosure over feature dumping. Hide controls until the user needs them.

---

## 4. Content is King
*(Partially visible — full content needed from Zeroheight)*

---

## Product Context

**Infinity Design System** is the design language of the products created at Netcore. It is designed by keeping the human (user) at the core, enabling seamless human-software interaction.

### Products covered by this DLS:
| Product | Previously Known As | Description |
|---|---|---|
| Netcore CEE | Smartech | Data-driven marketer platform — Email, SMS, Web, Push, etc. |
| Netcore Email API | Pepipost | Lightning-fast email delivery |
| Netcore PX | Hansel | No-code product experience — walkthroughs, nudges |
| UNBXD | — | AI-driven eCommerce search & recommendations |
| Netcore CDP | — | Customer data unification platform |

---

## Zeroheight DLS Structure (full nav)

```
Overview
├── Introduction
├── Principles
└── Updates

Communication
└── UX Writing

Style
├── Colors          ← documented in color-tokens.json
├── Typography      ← NEEDED: screenshot
├── Layout Guidelines
├── Elevation       ← partially in spacing-tokens.json
├── Iconography
└── Illustrations & Motion

BRAND
└── Raman Mascot

Components
├── Buttons
├── Avatars
└── UI Loaders
```
