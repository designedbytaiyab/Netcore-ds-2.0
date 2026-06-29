# Changelog — Netcore DS 2.0 Skill

All notable changes to this skill are documented here.
Format: `[version] — date` · Added / Changed / Fixed

---

## [1.5.0] — 17 Jun 2026

### Added
- `copywriting/spec.md` — full Netcorian copywriting spec inside `copywriting/` folder
- `copywriting/README.md` — folder map and trigger phrase table for AI discovery
- `copywriting/SKILL.md` — installable copywriting skill with `/copy`, `/netcorian`, `/ux-writing` triggers
- `copywriting/references/` — voice, rules, patterns, workflows, templates (progressive disclosure)

### Changed
- `netcore-dls2.md` — copywriting companion link in header
- `SKILL.md` — copywriting reference routing and cross-links
- `ux-writing.md` — points to Netcorian companion docs; retains DS 2.0 UPPERCASE button rules

---

## [1.4.0] — 24 Jun 2026

### Added
- `assets/` — 13 Figma screenshots: 10 campaign creation screens + top nav, side nav, text fields
- `.github/PULL_REQUEST_TEMPLATE.md` — standard PR format for tracking changes
- `CHANGELOG.md` — this file

### Changed
- `SKILL.md` — trigger map updated to image-first lookup sequence. AI now surfaces reference image before reading text specs. Triggers split into named sections (Campaign, Nav, Forms, Components, Analytics).

---

## [1.3.0] — 24 Jun 2026

### Added
- `references/tokens.md` — full type scale, color palette, spacing grid, elevation, layout grids
- `references/components.md` — all component rules + pre/post generation checklists
- `references/campaign-flow.md` — all 10 campaign screens with exact dimensions and Figma node map

### Changed
- `SKILL.md` — restructured following Anthropic progressive disclosure pattern. Trimmed to ~180 lines lean orchestrator. Description made pushy for better triggering.

---

## [1.2.0] — 18 Jun 2026

### Added
- `netcore-dls2.md` — full skill file with trigger map, Figma node IDs, component rules, checklists
- `design_system_styles.css` — authoritative CSS token export from Zeroheight

---

## [1.1.0] — 18 Jun 2026

### Added
- `tokens/color-tokens.json` — full color token library with CSS variable names
- `tokens/typography-tokens.json` — 15-style type scale
- `tokens/spacing-tokens.json` — spacing, radius, elevation, layout grid tokens
- `components/top-navigation.json` — top bar exact specs
- `components/side-navigation.json` — L1 dark nav + L2 chalk nav specs
- `components/text-fields.json` — input states, sizes, focus ring, Category Labels variant
- `screens/campaign-creation.json` — all 10 campaign screens with Figma node IDs
- `component-inventory.json` — full component list with Figma nodes
- `ux-writing.md` — 14 UX writing rules + pre-publish checklist
- `principles.md` — design principles 1–4

---

## [1.0.0] — Initial release

### Added
- Repository initialised with README

---

## How to add an entry

When you open a PR, add a new section at the top of this file:

```
## [X.Y.Z] — DD Mon YYYY

### Added
- what was added

### Changed
- what was updated

### Fixed
- what was corrected
```

Version numbering:
- `X` — major (full redesign, breaking change)
- `Y` — minor (new flow, new component set, new screenshots)
- `Z` — patch (typo fix, token correction, small update)
