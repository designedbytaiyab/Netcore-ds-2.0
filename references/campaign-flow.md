# Campaign Creation Flow — Netcore DS 2.0

Load this file whenever building anything related to creating a campaign. It documents all 10 screens of the campaign creation flow with exact dimensions and Figma node IDs.

Always call `get_design_context(fileKey='H2W6ldaO1Py7WW5c3b6YpW', nodeId='<id>')` for the specific screen you're building — the Figma data is the ground truth for exact measurements.

---

## Flow Overview

**Figma file:** `H2W6ldaO1Py7WW5c3b6YpW` (Netcore MCP — Design)
**Screenshots node:** `31:4752` — all 10 screens as reference images
**Assets node:** `31:4753` — component-level specs for all screens
**Canvas width:** 1440px

Entry point: Campaign Home → click CREATE → Campaign Type modal (screen 2)

**Stepper steps:** Setup → Audience → Content → Schedule → Preview

---

## Shared Chrome (Appears on All Flow Screens)

### Top Bar
- Component: `organism/Top Bar/CDP Header`
- Height: 97px
- Contents: Back arrow (←) · Campaign title · Stepper · SAVE DRAFT (125×34px) · SCHEDULE (106×34px)
- Both action buttons right-aligned at x:1149

### Stepper
- 5 steps: Setup / Audience / Content / Schedule / Preview
- Each step: 24×24px icon + text label below
- Connector between steps: 62px wide line
- Active: filled cobalt icon
- Completed: checkmark icon
- Upcoming: grey outline icon

### Summary Panel
- Width: 350px, fixed right side
- 4 sections: Setup / Audience / Content / Schedule
- Each field: label (header-h4 bold) + value (body-regular grey)
- Fields: Campaign Name · Tags · Conversion Goal · GA Tracking

---

## Screens

### Screen 1 — Campaign Home
| Property | Value |
|---|---|
| Figma node | `31:4585` |
| Size | 1440×900 |
| Description | Landing page listing all campaigns. CREATE button in top nav opens the type-selection modal. |

---

### Screen 2 — Campaign Type Selection
| Property | Value |
|---|---|
| Figma node | `23:512` |
| Size | 1440×900 |

Right-side panel modal sliding over the Campaign Home page.

**Modal specs:**
- Width: 840px
- Offset from left edge: 600px
- Height: 900px (full viewport)
- Header title: "How would you like to start?"
- Close button: 40×40px × icon, top-right at x:704

**Options grid:**
- Container: 744×498px at x:48, y:128
- Layout: 2×2 grid
- Each option: 360×237px
- Icon: 48×48px, centered horizontally, y:40
- Title: SemiBold 20px, charcoal
- Description: Regular 14px, grey, 2–3 lines

| Option | Icon | Description |
|---|---|---|
| Engage with users | megaphone-off | Create personalized campaigns and user journeys |
| Analyze user behaviour | bar-chart | Create funnels, cohorts, and RFM to measure performance |
| Create template | layout-dashboard | Customize reusable templates for your campaigns |
| Manage contacts | circle-x | Add contacts, import list or create segment |

---

### Screen 3 — Campaign Channel Selection (Engage)
| Property | Value |
|---|---|
| Figma node | `23:820` |
| Size | 1440×900 |

Wider panel modal, replaces the type selection modal.

**Modal specs:**
- Width: 1136px
- Offset from left: 304px
- Height: 900px
- Header title: "How do you want to engage with your users?"
- Close button: 40×40px at x:1000

**Content container:** 1040×706px at x:48, y:128

**Sections:**

*Journey (y:48)*
- 1 card: Journey (chart-network icon 24×24)

*Campaigns (y:160)*
- Section header: megaphone icon 18×18 + "Campaigns" label
- Row 1 (4 cards): Email · SMS · App push · Web push
- Row 2 (2 cards): WhatsApp · RCS (RCS has "New" badge — 47×20px, right of card)
- Gap between cards: 16px

*Onsite (y:398)*
- Section header: computer icon 18×18 + "Onsite" label
- Cards: In-app message · Web message

*Personalized Content (y:548)*
- Section header: user-star icon 18×18 + "Personalized Content" label
- Cards: Web · App

**Card anatomy (230×72px):**
- Decorative icon bg: 60×60px at x:180, y:6 (right side)
- Content row: 190×24px at x:20, y:24
- Icon in row: 24×24px
- Label: 154×20px at x:36, emphasis style (600/14px)

---

### Screen 4 — Campaign Setup
| Property | Value |
|---|---|
| Figma node | `23:1001` |
| Size | 1440×1324 |

Full page with top bar + form + right summary panel.

**Form sections:**

*Campaign Details*
- Title: "Campaign details"
- Subtitle: "Provide basic details about your campaign"
- Fields: Campaign Name · Tags · Category Labels · Conversion Goal (toggle) · GA Tracking (toggle)

*GA Tracking (expanded)*
- Title: "GA Tracking"
- Subtitle: "Track your campaign performance. Set default values for Google Analytics."
- Fields: UTM Campaign · UTM Content · URL parameters

---

### Screen 5 — Campaign Audience (Step 1)
| Property | Value |
|---|---|
| Figma node | `31:694` |
| Size | 1440×689 |
| Description | Audience targeting — segment selection and filtering |

---

### Screen 6 — Campaign Audience (Step 2)
| Property | Value |
|---|---|
| Figma node | `31:4595` |
| Size | 1440×1315 |
| Description | Expanded audience page with segmentation filters applied |

---

### Screen 7 — Campaign Content
| Property | Value |
|---|---|
| Figma node | `31:3804` |
| Size | 1440×1411 |

Two stacked sections:

*Sender Details (node 31:3805)*
- Height: 512px
- Contents: top-bar (52px) + main form (460px)

*Email Template Gallery (node 31:3845)*
- Height: 899px
- Container node: `31:3846`
- Template picker grid — select from pre-built email templates

---

### Screen 8 — Campaign Content (Template Selected)
| Property | Value |
|---|---|
| Figma node | `31:4599` |
| Size | 1440×1644 |
| Description | Template selected state — shows preview + edit options |

---

### Screen 9 — Campaign Schedule
| Property | Value |
|---|---|
| Figma node | `31:4435` |
| Size | 1440×734 |

**Schedule container:** 988×464px at x:30, y:127

*Frequency Cap section (y:92)*
- Toggle: 40×22px
- Warning box: 860px wide, triangle-alert 18×18 icon + warning text

*When to Send section*
- Radio options: Send now · Send later · Slice & send · Optimize with co-marketer
- Radio size: 16×16px
- "Optimize with co-marketer" has a circle-help 14×14 icon after the label

**Header row:** 908×28px — title (181×28px) left · metadata (293×18px) right-aligned

---

### Screen 10 — Campaign Preview
| Property | Value |
|---|---|
| Figma node | `31:4154` |
| Size | 1440×1115 |
| Description | Final review screen — campaign preview before publishing |

---

## Figma Node Quick Reference

| Screen | Node ID |
|---|---|
| Campaign Home | `31:4585` |
| Campaign Type | `23:512` |
| Campaign Engage (channels) | `23:820` |
| Campaign Setup | `23:1001` |
| Audience Step 1 | `31:694` |
| Audience Step 2 | `31:4595` |
| Content (template gallery) | `31:3804` |
| Content (selected) | `31:4599` |
| Schedule | `31:4435` |
| Preview | `31:4154` |
