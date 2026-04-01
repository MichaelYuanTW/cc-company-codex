# CC Company Codex

Codex adaptation of [`Shin-sibainu/cc-company`](https://github.com/Shin-sibainu/cc-company).

This repository converts the original Claude Code secretary-office plugin into a Codex-friendly workspace setup.

## What it includes

- A Codex plugin at `plugins/company-secretary/`
- A local marketplace entry at `.agents/plugins/marketplace.json`
- A live office scaffold at `.company/`
- Documentation describing the adaptation in `docs/cc-company-codex-adaptation.md`

## Core idea

The workflow is still:

`user -> secretary -> departments only when needed`

The secretary remains the single front desk. The office starts small and grows only when repeated work patterns justify new departments.

## Main Codex changes

- Replaced Claude-specific plugin structure with `.codex-plugin`
- Replaced `CLAUDE.md` with `OFFICE.md`
- Removed slash-command assumptions
- Kept file-based office memory under `.company/`

## Repository layout

```text
.agents/plugins/marketplace.json
.company/
docs/
plugins/company-secretary/
```

## Usage

After loading this workspace in Codex, you can use natural language requests such as:

- open my secretary office
- show today's tasks
- capture this idea
- help me draft a Japanese client email
- brainstorm my game scenario

## Credits

Original concept and source structure by `Shin-sibainu/cc-company`.
