# AGENTS.md

Instructions for AI coding agents (Codex, Devin, Cursor, and other AGENTS.md-compatible tools) in this repository.

## Project skills

Skills are reusable specialized instructions, one per folder, defined in `SKILL.md` files with YAML frontmatter (`name`, `description`). This project uses the `.claude/skills/` folder — a Claude Code convention, but the content is portable Markdown + bash: **any agent should read the matching skill before executing the task it covers**:

Available skills:

- _No skills defined yet._ When you create one, list it here with a summary of when to use it.

## Project commands

Commands are reusable slash commands, one `.md` file per command in the `.claude/commands/` folder, with YAML frontmatter (`description`, `allowed-tools`). In Claude Code they are invoked as `/<name>` (subfolders become namespaces: `commands/<group>/<name>.md` → `/<group>:<name>`); other agents should read the file and follow its steps:

Available commands:

- _No commands defined yet._ When you create one, list it here with a summary of when to use it.

## Project agents

Agents are specialized subagent definitions (a persona + scope + instructions), one `.md` file per agent in the `.claude/agents/` folder. Before delegating a subtask to a specialized agent, read the corresponding definition:

Available agents:

- _No agents defined yet._ When you create one, list it here with a summary of when to use it.
