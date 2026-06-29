# Copywriting skill (`copywriting/`)

Self-contained Netcorian copywriting skill. Install **`copywriting/SKILL.md`** separately from the visual design skill at repo root.

## Folder structure

```
copywriting/
├── SKILL.md           ← Install this file for copywriting (/copy trigger)
├── README.md          ← This file
├── spec.md            ← Full copywriting spec (companion to ../netcore-dls2.md)
└── references/
    ├── voice.md
    ├── rules.md
    ├── patterns.md
    ├── workflows.md
    └── templates.md
```

Also see `../ux-writing.md` for DS 2.0 UPPERCASE button and empty state rules.

## Triggers

| Type | Examples |
|---|---|
| Commands | `/copy` · `/netcorian` · `/ux-writing` |
| User says | "write copy", "UX writing", "button label", "error message", "empty state", "in our voice", "Netcorian", "review this copy" |

## Pair with visual skill

| Task | Load |
|---|---|
| UI layout, colours, components | Root `SKILL.md` (`/ds`) |
| UI strings, voice, microcopy | `copywriting/SKILL.md` (`/copy`) |
| DS 2.0 button case + empty states | `ux-writing.md` |
| Both | Load both skills |
