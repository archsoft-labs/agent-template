<div align="center">

# 🤖 agent-template

**A starter template for repositories that work well with any AI coding agent.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](../../pulls)
[![Template](https://img.shields.io/badge/GitHub-Use%20this%20template-blue?logo=github)](../../generate)

**English** | [🇧🇷 Português (BR)](README.pt-BR.md)

[Features](#-features) •
[Why](#-why-this-template-exists) •
[Getting started](#-getting-started) •
[Structure](#-project-structure) •
[Contributing](#-contributing)

</div>

---

## 📖 About

Modern AI coding agents (Claude Code, GitHub Copilot, Cursor, Codex, Devin…) read persistent context files at the root of your repository to learn its rules, conventions, and reusable workflows. **The problem: each vendor has its own convention** — and none of them read the others' files.

This template solves that by keeping **all conventions in sync** with the same content, so any agent your team uses picks up the same instructions from day one.

| File | Read by | Convention |
|---|---|---|
| `CLAUDE.md` | Claude Code (CLI and IDE extensions) | Anthropic's official convention |
| `AGENTS.md` | Codex, Devin, Cursor, and others | Emerging open standard |
| `.github/copilot-instructions.md` | GitHub Copilot | GitHub's official convention |

## ✨ Features

- 🔓 **Vendor-neutral** — no lock-in. Any agent reads the same conventions.
- 🎯 **Single source of truth** — each rule lives in one place (a skill, command, or agent file); root instruction files only reference them.
- 📦 **Empty by default** — folders ship empty so you add only what your project actually needs.
- 🌍 **Portable** — `.claude/` content is plain Markdown + bash, readable by any agent.
- ⚙️ **Team-ready** — `.gitignore` with agent tooling rules and VS Code settings included.

## 📁 Project structure

```
.
├── CLAUDE.md                          # Instructions for Claude Code
├── AGENTS.md                          # Instructions for AGENTS.md-compatible agents
├── .github/
│   └── copilot-instructions.md        # Instructions for GitHub Copilot
├── .claude/
│   ├── skills/                        # Reusable specialized instructions (SKILL.md per folder)
│   ├── commands/                      # Slash commands (one .md per command)
│   ├── agents/                        # Specialized subagent definitions (one .md per agent)
│   └── settings.json                  # Claude Code settings
├── .vscode/
│   └── settings.json                  # VS Code settings (terminal, auto-save, MCP)
├── .gitignore                         # Python-focused, with agent tooling rules
└── LICENSE                            # MIT
```

### The three instruction files

All three describe the same project structure — skills, commands, and agents — using each vendor's expected location and tone. **When you edit one, edit the others to match.** They are intentionally short: long rules belong in dedicated skill or agent files, not in the root context.

### The `.claude/` folder

A Claude Code convention, but its contents are **portable Markdown + bash**. Other agents can (and should) read from it:

| Folder | What it holds | How it works |
|---|---|---|
| **`skills/`** | Reusable instruction sets (one folder per skill, with a `SKILL.md` inside) | Cover tasks like "browser automation" or "database migrations" — any agent should read the matching skill before executing the task it covers |
| **`commands/`** | Slash commands (in Claude Code, `/name`) | Subfolders become namespaces: `commands/git/squash.md` → `/git:squash`. Other agents treat these as step-by-step playbooks |
| **`agents/`** | Subagent definitions (persona + scope + instructions) | Used when delegating subtasks to focused workers |

All three folders start empty, with a `.gitkeep` placeholder. The instruction files already explain how to add entries — when you create one, list it under the matching "Available X:" heading.

## 🚀 Getting started

### 1. Create a repository from this template

Click **"Use this template"** on GitHub, or via CLI:

```bash
gh repo create my-project --template Archsoft/agent-template
```

### 2. Edit the three instruction files

Update `CLAUDE.md`, `AGENTS.md`, and `.github/copilot-instructions.md` with your project's conventions, stack, and rules. **Keep them in sync.**

### 3. Add skills, commands, and agents

As your project grows, create entries under `.claude/` and list each one in the three instruction files.

### 4. Adjust `.gitignore`

If your project isn't Python, replace the body of `.gitignore` with the appropriate template from [github/gitignore](https://github.com/github/gitignore) and keep the Claude Code / GitHub sections at the bottom.

## 🧭 Design principles

- **Vendor-neutral** — no lock-in. Any agent reads the same conventions.
- **Single source of truth (per concern)** — each rule lives in one place (a skill, command, or agent file); root instruction files only reference them.
- **Empty by default** — folders ship empty so you add only what your project actually needs.
- **English, international** — all files use English to maximize compatibility across teams and tools.

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the project
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

Found a bug or have a suggestion? [Open an issue](../../issues/new).

## ⭐ Support the project

If this template was useful to you, consider giving the repository a **star** — it helps other devs discover it!

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.

---

<div align="center">
Made with ❤️ by <a href="https://github.com/Archsoft">Archsoft®</a>
</div>
