# cc-company -> Codex adaptation

Source repository: [Shin-sibainu/cc-company](https://github.com/Shin-sibainu/cc-company)

## What the original office plugin does

The original plugin is an "AI secretary office" for Claude Code.

Its core design is intentionally simple:

- The secretary is always the single entry point.
- The workspace starts with only a secretary office.
- Departments are created later, only when the work pattern justifies them.
- Files inside `.company/` act as the organization's working memory.

The original flow is:

1. Detect whether `.company/` already exists.
2. If not, ask only two onboarding questions.
3. Generate a secretary office automatically.
4. In normal operation, let the secretary handle common work directly.
5. Route specialized work into departments.
6. Propose new departments after repeated requests in the same domain.

## Original prompt design

The source `SKILL.md` prompt is built around:

- mode detection: bootstrap, migration, or operating mode
- friendly secretary tone
- file-first memory
- routing by keywords and context
- proactive logging of notes, decisions, and learnings
- lightweight expansion instead of heavy upfront setup

This is why the original design feels usable: the user does not need to learn a system first.

## How I adapted it for Codex

I preserved the operating idea but changed the platform assumptions:

- removed Claude-only slash trigger assumptions
- removed `AskUserQuestion` dependence
- replaced `CLAUDE.md` with `OFFICE.md`
- converted the package into a Codex plugin under `.codex-plugin`
- kept `.company/` as the office root so the workflow remains file-based and portable

## Installed items in this workspace

- Repo marketplace entry: `.agents/plugins/marketplace.json`
- Codex plugin: `plugins/company-secretary/.codex-plugin/plugin.json`
- Skill: `plugins/company-secretary/skills/company-secretary/SKILL.md`
- References: `plugins/company-secretary/skills/company-secretary/references/`
- Live office scaffold: `.company/`

## Practical usage

In Codex, this setup is meant to support natural language requests such as:

- open my secretary office
- show today's tasks
- capture this thought
- summarize my office dashboard
- create a research department

The skill should then maintain the office files in `.company/` directly.
