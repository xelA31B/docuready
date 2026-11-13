# Docuready — Claude plugin

AI agents give wrong answers when company documents are a mess. Docuready audits your documents, fixes the structure and gives agents the context they need.

## Install

**Claude app (web, desktop):** Plugins → add a marketplace from a GitHub repository → `xelA31B/docuready` → install **Docuready**. Once approved in the Claude directory, search for **Docuready** in Plugins.

**Claude Code (VS Code or terminal):**

```
/plugin marketplace add xelA31B/docuready
/plugin install docuready@docuready
```

## Skills

| Skill | What you get |
|-------|--------------|
| **knowledge-audit** | AI-Readiness Score 0–100: findability, duplicates and conflicts, freshness, ownership, machine readability, gaps, sensitive data to separate. Prioritized cleanup plan. Read-only. |
| **knowledge-structure** | Folder taxonomy, naming convention, source-of-truth map, templates, index and glossary. Applied only after your confirmation; never deletes (archives instead) and logs every change. |
| **agent-context-pack** | A compact `COMPANY_CONTEXT.md` (and `CLAUDE.md` / `AGENTS.md`) that tells AI agents who you are, what you sell, how to talk and what never to do. |

## Commands

Type `/` in Claude and pick a command:

| Command | What it does |
|---|---|
| `/company-context [company or sources]` | Company context file for AI agents (CLAUDE.md / AGENTS.md) |
| `/docs-audit [folder, drive or purpose]` | AI-readiness audit of company documents |
| `/docs-structure [folder or drive]` | Design and apply a clean document structure for AI agents |

## How to use

Works with a folder open in Claude Code or Cowork, uploaded files, or a connected drive (Google Drive, Notion, SharePoint, Confluence).

- "Audit our shared drive — is it ready for an AI support agent?"
- "Наведи порядок в документах компании для ИИ-агента"
- "Create a company context file for our AI assistant"

## Principles

Concise, professional reports in the language of your request. Read-only by default, never deletes, never prints sensitive content.

## Reports

Concise reports in the language of your request, delivered as a branded HTML report where supported.

## License

MIT
