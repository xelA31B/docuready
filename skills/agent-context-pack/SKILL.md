---
name: agent-context-pack
description: >
  This skill should be used when the user asks to "create a company context file for AI agents",
  "write CLAUDE.md / AGENTS.md for our company", "give the AI assistant background about our business",
  "make a company brief for AI", "prepare a system prompt about our company", or wants a compact,
  structured summary of a company that AI agents can load as context. Also triggers on the same requests
  in Russian ("контекст компании для ИИ", "файл для агента о компании") or Hungarian.
metadata:
  version: "0.1.0"
---

# Agent Context Pack

Produce a compact, accurate context file that tells AI agents what they need to know about the company.

## Style rules

- Language of the user's request (or the language the agent will work in, if the user says so).
- Concise and factual. Every statement must come from the company's documents or the user; mark anything inferred as **to confirm**.
- No personal data beyond role titles and public contact channels. No credentials, prices or terms that are not meant to be shared with the agent's audience.

## Steps

1. **Sources.** Use audited/structured documents if available; otherwise ask for the key documents (about, products, pricing, policies, FAQ) or a website URL.
2. **Audience of the agent.** Internal team, customers or partners — this decides what may be included.
3. **Draft the pack** in the format below, max ~1,500 words.
4. **Validate.** List open questions and every **to confirm** item for the user.
5. **Deliver** as `COMPANY_CONTEXT.md` (and, if the user works with Claude Code or other agents, also as `CLAUDE.md` / `AGENTS.md` with the same content).

## Format

```
# [Company] — context for AI agents
Last updated: YYYY-MM-DD · Owner: [role]

## Who we are
2–3 sentences: what, for whom, where.

## Products and services
| Name | What it does | For whom | Key facts |

## How we talk
Tone, words to use/avoid, languages.

## Rules for the agent
- What it may do / must never do (promises, discounts, legal or medical advice, sharing internal data)
- When to hand over to a human, and how

## Key policies
Pricing principles, refunds, SLAs, privacy — summary plus link to the source document.

## Glossary
| Term | Meaning |

## Where to find more
| Topic | Source of truth (document / link) |

## Open questions
- items marked to confirm
```
