# UX Writing — Infinity DS 2.0

> Source: Netcore Zeroheight → Communication → UX Writing  
> **Netcorian companion:** Full voice, principles, workflows, and ship gates → `brand-copywriting.md` and `copywriting/SKILL.md`. This file retains DS 2.0-specific rules (UPPERCASE buttons, empty state anatomy).

---

## Core Principle

Write for clarity and action. Every word should help the user understand what to do next or what just happened. Remove friction, not information.

---

## Voice & Tone

| Context | Tone |
|---|---|
| Empty states | Encouraging, action-oriented |
| Error messages | Direct, non-blaming, solution-focused |
| Success states | Brief, affirming |
| Destructive confirmations | Neutral, factual — no fear-mongering |
| Onboarding / nudges | Friendly, instructional |
| Data labels | Precise, no ambiguity |

---

## Writing Rules

### 1. Button Labels
- **Always UPPERCASE** for all button text (Primary, Secondary, Tertiary)
- Use action verbs: CREATE, SAVE, APPLY, CANCEL, DELETE, EXPORT
- Never use "Click here", "Submit", or "OK" alone — be specific
- Single-button nudges: use Primary button config only
- Avoid negative framing — use CANCEL instead of DON'T SAVE

### 2. Page & Section Titles
- Title Case for page headings (H1, H2)
- Sentence case for body copy, helper text, descriptions
- No periods at end of headings
- Keep H1 titles to 3–5 words max

### 3. Labels & Form Fields
- Labels above fields, never inside (placeholder ≠ label)
- Required fields: mark with * and explain "* Required fields" once per form
- Placeholder text: show format hint, not repeated label text
  - Bad: "Enter email address"
  - Good: "name@company.com"
- Error messages: say what went wrong AND how to fix it
  - Bad: "Invalid input"
  - Good: "Enter a valid email address (e.g. name@company.com)"

### 4. Empty States
Every empty state must have:
1. **Illustration** (Netcore brand illustration style)
2. **Headline** — what's missing or what the user can do (H3, Title Case)
3. **Body copy** — 1–2 sentences max, what they'll get by taking action
4. **CTA button** — specific action (+ CREATE CAMPAIGN, + ADD FILTER, etc.)

### 5. Status Labels
Use consistent status vocabulary across the platform:

| Status | Use When |
|---|---|
| DRAFT | Created, not yet published |
| SCHEDULED | Published, waiting to run |
| RUNNING / ACTIVE | Currently executing |
| PAUSED | Manually stopped mid-run |
| COMPLETED | Finished successfully |
| FAILED | Errored out — always show a reason |
| ARCHIVED | Soft-deleted, retrievable |

Status labels: UPPERCASE, status typography (10px/700), inside colored chips

### 6. Numbers & Metrics
- Large numbers: abbreviate K / M / B (1.23M, 450K, 2.1B)
- Percentages: always show % symbol, 1 decimal (3.1%)
- Ratios: use ":" separator (1:5)
- Currency: locale-appropriate format
- Dates: DD Mon YYYY (Apr 03, 2021) or relative ("Today", "Yesterday", "3 days ago")
- Time: 12-hour with AM/PM or 24-hour — be consistent per surface

### 7. Tooltips
- 1–2 sentences max
- Explain the WHY, not just what the field is
- Never repeat the label
- End with a period if it's a full sentence

### 8. Destructive Action Confirmations
Always use a modal with:
- **Title**: What will be deleted / affected (not "Are you sure?")
- **Body**: What will happen (data loss, irreversibility)
- **Primary CTA**: DELETE [ITEM NAME] — specific
- **Secondary CTA**: CANCEL

### 9. Navigation Labels
- Short, noun-based: "Campaigns", "Journeys", "Analytics"
- Not verb phrases: avoid "Manage Campaigns", "View Analytics"
- 1–2 words preferred, 3 max

### 10. Notifications & Toasts
- **Success**: "[Action] was successful." — past tense, brief
- **Error**: "Couldn't [action]. [Reason]. Try again." — explain and offer path
- **Warning**: "This action will [consequence]." — present tense
- **Info**: Use sparingly — only for time-sensitive or non-obvious context
- Toast duration: 4–5 seconds for success/info; errors persist until dismissed

### 11. Charts & Data Labels
- Axis labels: sentence case, include unit in parentheses (Revenue (USD))
- Legend labels: match exactly to data keys — no abbreviations
- Tooltip content: show exact value + label + date/period
- "No data" state: "No data available for this period" — not just "N/A"

### 12. Loading & Processing States
- Use skeleton loaders (wave animation) for data tables — never pulse animation
- Spinner: only for actions < 3 seconds with no predictable end time
- Progress bar: when total steps or % is known ("22 / 46 Fields mapped")
- Never show "Loading..." without context of what's loading

### 13. Segmentation & Filter Language
- Condition language: "who did [event]" / "where [attribute] is [value]"
- Operators: "is", "is not", "contains", "does not contain", "≥", "≤"
- Boolean connectors: "AND", "OR" — uppercase, clearly separated
- Always show count of results when filter is applied ("1,234 contacts match")

### 14. Journey / Flow Terminology
- Triggers: what starts the journey (Event, Schedule, API)
- Actions: what Netcore sends (Email, SMS, Push, WhatsApp)
- Conditions: branching logic (Yes/No, A/B Split)
- Flow Controls: Delay, Wait, Merge, End

---

## Nudge Copy Rules (CEE Platform)

### Nudges Without CTAs
- Background: #191919 (dark)
- Text: #FFFFFF (white)
- Keep to 1 sentence — user is in mid-task

### Nudges With CTAs
- Title: #17173A (charcoal)
- Body: #6F6F8D (grey)
- Primary button always first — only add secondary if absolutely needed
- Both buttons: UPPERCASE text

### Spotlight Nudges
- Full-page overlay opacity: 0.7–0.8
- Button text: #191919 on white button
- Point at the exact element being highlighted

---

## Pre-Publish Checklist

Before any copy goes into production:

- [ ] All button labels are UPPERCASE
- [ ] No "Click here" or vague CTAs
- [ ] All empty states have: illustration + headline + body + CTA
- [ ] Error messages say what went wrong AND how to fix it
- [ ] Status labels use the standard vocabulary
- [ ] Numbers use K/M/B abbreviations at appropriate scale
- [ ] Tooltips are 1–2 sentences and don't repeat the label
- [ ] Destructive confirmations name the item being deleted
- [ ] Loading states use wave skeleton (not pulse, not plain spinner)
