# Codex Office Adaptation Notes

This reference summarizes the operating design extracted from `Shin-sibainu/cc-company` and the changes made for Codex.

## Original operating model

The original plugin is built around a simple routing concept:

`user -> secretary -> department(s) when needed`

Key ideas:

- The secretary is the permanent entry point.
- The organization starts with only a secretary office.
- Departments are created only when the pattern of work repeats or the user asks for them.
- The workspace itself acts as memory through files.
- The assistant should proactively log decisions, ideas, and learnings.

## Original prompt design

The original `company` skill prompt emphasizes:

- detect whether the company workspace already exists
- onboard in only two questions
- auto-generate a secretary office
- operate in management mode once the office exists
- route work by keyword and context
- suggest department creation after repeated requests
- keep the tone friendly, secretary-like, and proactive
- rely on templates for consistent file generation

## Why adaptation is needed for Codex

The source plugin assumes Claude-specific mechanics such as:

- slash-triggered invocation
- `AskUserQuestion`
- `CLAUDE.md` file naming conventions

Codex works better with:

- normal conversation triggers
- file-backed skills and plugin manifests under `.codex-plugin`
- regular workspace edits instead of tool-specific interactive steps

## Codex adaptation choices

We preserve the model, but change the interface:

- Secretary remains the single conversational front desk.
- The office still lives under `.company/`.
- The main rule file becomes `.company/OFFICE.md`.
- Department instruction files become `.company/<department>/OFFICE.md`.
- The skill triggers from natural language intent instead of a slash command.
- Onboarding becomes a minimal bootstrap, with assumptions allowed when harmless.

## Expected usage in Codex

The user can now say things like:

- "Open my secretary office."
- "What should I do today?"
- "Capture this idea."
- "Summarize the office dashboard."
- "Create a research department."

The skill should then read or update the `.company/` files directly.
