<div align="center">

# 🤖 agent-template

**Um template inicial para repositórios que funcionam bem com qualquer agente de código de IA.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](../../pulls)
[![Template](https://img.shields.io/badge/GitHub-Use%20this%20template-blue?logo=github)](../../generate)

[🇺🇸 English](README.md) | **Português (BR)**

[Recursos](#-recursos) •
[Por que usar](#-por-que-este-template-existe) •
[Começando](#-começando) •
[Estrutura](#-estrutura-do-projeto) •
[Como contribuir](#-contribuindo)

</div>

---

## 📖 Sobre

Agentes modernos de código com IA (Claude Code, GitHub Copilot, Cursor, Codex, Devin…) leem arquivos de contexto na raiz do repositório para aprender as regras, convenções e fluxos de trabalho do seu projeto. **O problema: cada fornecedor tem sua própria convenção** — e nenhum lê os arquivos dos outros.

Este template resolve isso mantendo **todas as convenções sincronizadas** com o mesmo conteúdo, para que qualquer agente que seu time use receba as mesmas instruções desde o primeiro dia.

| Arquivo | Lido por | Convenção |
|---|---|---|
| `CLAUDE.md` | Claude Code (CLI e extensões de IDE) | Convenção oficial da Anthropic |
| `AGENTS.md` | Codex, Devin, Cursor e outros | Padrão aberto emergente |
| `.github/copilot-instructions.md` | GitHub Copilot | Convenção oficial do GitHub |

## ✨ Recursos

- 🔓 **Vendor-neutral** — sem lock-in. Qualquer agente lê as mesmas convenções.
- 🎯 **Fonte única de verdade** — cada regra vive em um só lugar (skill, command ou agent); os arquivos raiz apenas referenciam.
- 📦 **Vazio por padrão** — as pastas vêm vazias para você adicionar apenas o que seu projeto realmente precisa.
- 🌍 **Portável** — o conteúdo de `.claude/` é Markdown + bash puro, legível por qualquer agente.
- ⚙️ **Pronto para o time** — `.gitignore` com regras de ferramentas de agente e configurações de VS Code incluídas.

## 📁 Estrutura do projeto

```
.
├── CLAUDE.md                          # Instruções para o Claude Code
├── AGENTS.md                          # Instruções para agentes compatíveis com AGENTS.md
├── .github/
│   └── copilot-instructions.md        # Instruções para o GitHub Copilot
├── .claude/
│   ├── skills/                        # Instruções especializadas reutilizáveis (SKILL.md por pasta)
│   ├── commands/                      # Slash commands (um .md por comando)
│   ├── agents/                        # Definições de subagentes especializados (um .md por agente)
│   └── settings.json                  # Configurações do Claude Code
├── .vscode/
│   └── settings.json                  # Configurações do VS Code (terminal, auto-save, MCP)
├── .gitignore                         # Focado em Python, com regras para ferramentas de agente
└── LICENSE                            # MIT
```

### Os três arquivos de instrução

Os três descrevem a mesma estrutura do projeto — skills, commands e agents — usando o local e o tom esperados por cada fornecedor. **Quando editar um, edite os outros para manter sincronia.** Eles são intencionalmente curtos: regras longas pertencem a arquivos dedicados de skill ou agent, não ao contexto raiz.

### A pasta `.claude/`

É uma convenção do Claude Code, mas seu conteúdo é **Markdown + bash portável**. Outros agentes podem (e devem) ler dela:

| Pasta | O que contém | Como funciona |
|---|---|---|
| **`skills/`** | Conjuntos de instruções reutilizáveis (uma pasta por skill, com um `SKILL.md` dentro) | Cobrem tarefas como "automação de browser" ou "migrações de banco" — qualquer agente deve ler a skill correspondente antes de executar a tarefa |
| **`commands/`** | Slash commands (no Claude Code, `/nome`) | Subpastas viram namespaces: `commands/git/squash.md` → `/git:squash`. Outros agentes os tratam como playbooks passo a passo |
| **`agents/`** | Definições de subagentes (persona + escopo + instruções) | Usadas ao delegar subtarefas para workers focados |

As três pastas começam vazias, com um placeholder `.gitkeep`. Os arquivos de instrução já explicam como adicionar entradas — ao criar uma, liste-a sob o cabeçalho "Available X:" correspondente.

## 🚀 Começando

### 1. Crie um repositório a partir do template

Clique em **"Use this template"** no GitHub, ou via CLI:

```bash
gh repo create meu-projeto --template Archsoft/agent-template
```

### 2. Edite os três arquivos de instrução

Atualize `CLAUDE.md`, `AGENTS.md` e `.github/copilot-instructions.md` com as convenções, stack e regras do seu projeto. **Mantenha-os em sincronia.**

### 3. Adicione skills, commands e agents

Conforme o projeto cresce, crie entradas em `.claude/` e liste cada uma nos três arquivos de instrução.

### 4. Ajuste o `.gitignore`

Se seu projeto não for Python, substitua o corpo do `.gitignore` pelo template apropriado do [github/gitignore](https://github.com/github/gitignore) e mantenha as seções Claude Code / GitHub no final.

## 🧭 Princípios de design

- **Vendor-neutral** — sem lock-in. Qualquer agente lê as mesmas convenções.
- **Fonte única de verdade (por preocupação)** — cada regra vive em um lugar (skill, command ou agent); os arquivos de instrução raiz apenas referenciam.
- **Vazio por padrão** — as pastas vêm vazias para você adicionar só o necessário.
- **Inglês, internacional** — todos os arquivos usam inglês para maximizar a compatibilidade entre times e ferramentas.

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para:

1. Fazer um fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/minha-feature`)
3. Commitar suas mudanças (`git commit -m 'Adiciona minha feature'`)
4. Enviar para a branch (`git push origin feature/minha-feature`)
5. Abrir um Pull Request

Encontrou um bug ou tem uma sugestão? [Abra uma issue](../../issues/new).

## ⭐ Apoie o projeto

Se este template foi útil para você, considere dar uma **estrela** no repositório — isso ajuda outros devs a descobri-lo!

## 📄 Licença

Distribuído sob a licença MIT. Veja [LICENSE](LICENSE) para mais informações.

---

<div align="center">
Feito com ❤️ por <a href="https://github.com/Archsoft">Archsoft®</a>
</div>
