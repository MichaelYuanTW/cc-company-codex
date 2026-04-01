# Office Templates

Use these templates when creating or updating office files.

## `.company/OFFICE.md`

```md
# Company Office

## Owner Profile
- Business or activity: {{BUSINESS_TYPE}}
- Goals and challenges: {{GOALS_AND_CHALLENGES}}
- Created: {{CREATED_DATE}}

## Structure
```text
.company/
|- OFFICE.md
`- secretary/
   |- OFFICE.md
   |- inbox/
   |- todos/
   `- notes/
```

## Departments
| Department | Folder | Role |
|---|---|---|
| Secretary | secretary | Front desk, planning, capture, notes, and coordination. |
{{DEPARTMENT_ROWS}}

## Rules
- The secretary is always the front desk.
- Prefer capture over delay.
- Append to same-day files instead of creating duplicates.
- Use date-based files for daily work.
- Suggest new departments only when work repeats or the user asks.

## Personalization Notes
{{PERSONALIZATION_NOTES}}
```

## `.company/secretary/OFFICE.md`

```md
# Secretary Office

Role: Front desk, planning, notes, coordination.

## Responsibilities
- Manage today's TODOs
- Capture quick notes and ideas
- Save brainstorming notes
- Maintain decision and learning logs
- Route work into departments only when needed

## Tone
- Warm
- Organized
- Proactive
- Concise

## Working rules
- Read `.company/OFFICE.md` before major office operations.
- Check today's date before updating daily files.
- Append rather than overwrite.
- If unsure where something belongs, capture it in `inbox/` first.
```

## Daily TODO file

Path: `secretary/todos/YYYY-MM-DD.md`

```md
---
date: "{{YYYY-MM-DD}}"
type: daily
---

# {{YYYY-MM-DD}}

## Top priorities
- [ ]

## Standard tasks
- [ ]

## If time allows
- [ ]

## Done
- [x]

## Notes
- 
```

## Inbox file

Path: `secretary/inbox/YYYY-MM-DD.md`

```md
---
date: "{{YYYY-MM-DD}}"
type: inbox
---

# Inbox - {{YYYY-MM-DD}}

## Captures
- {{HH:MM}} |
```

## Brainstorm or note file

Path: `secretary/notes/<topic>.md`

```md
---
created: "{{YYYY-MM-DD}}"
topic: ""
type: note
tags: []
---

# [Topic]

## Background

## Notes

## Next actions
- [ ]
```

## Department starter folders

- `pm/projects/`, `pm/tickets/`
- `research/topics/`
- `marketing/content-plan/`, `marketing/campaigns/`
- `engineering/docs/`, `engineering/debug-log/`
- `finance/invoices/`, `finance/expenses/`
- `sales/clients/`, `sales/proposals/`
- `creative/briefs/`, `creative/assets/`
- `hr/hiring/`
