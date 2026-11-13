---
name: knowledge-audit
description: >
  This skill should be used when the user asks to "audit our documents", "is our knowledge base ready
  for AI", "check our Google Drive / Notion / SharePoint for AI agents", "find duplicate or outdated
  docs", "why does the AI agent give wrong answers from our docs", "prepare company documents for an
  AI assistant", or wants an assessment of how usable a company's documents are for AI agents.
  Also triggers on the same requests in Russian ("аудит документов", "готовы ли документы для ИИ",
  "навести порядок в документах") or Hungarian.
metadata:
  version: "0.1.0"
---

# Knowledge Audit

Assess how ready a company's documents are for AI agents and produce a prioritized cleanup plan.

## Style and safety rules

- Language of the user's request. Concise, professional, no filler. Tables over paragraphs.
- **Read-only.** Do not move, rename, edit or delete anything during the audit.
- **Sensitive data:** flag documents that appear to contain personal data, credentials, financial or health information — by file name and type of data only. Never quote or print the sensitive content.
- Report only what you actually opened or listed. Mark sampled areas as **sampled** and unopened areas as **not checked**.

## Step 1 — Scope

Ask only for what is missing:

- Source: a folder open in Claude Code / Cowork, uploaded files, or a connected drive (Google Drive, Notion, SharePoint, Confluence). If none is available, suggest connecting one or uploading a sample.
- Purpose: what the AI agent should do with these documents (e.g. answer customer questions, onboard employees, support sales).
- Size: if more than ~200 files, audit the structure fully and sample content (at least 20 files across folders).

## Step 2 — Inventory

Build a short inventory: folders, file count by type, date range, largest areas, files with no clear owner or date.

## Step 3 — Check against AI-readiness criteria

| Criterion | What to look for |
|---|---|
| Findability | Clear folder structure, meaningful file names, an index or README |
| Single source of truth | Duplicates, conflicting versions ("final_v3_NEW"), contradictory facts across docs |
| Freshness | Outdated documents still in active folders, no "last updated" date |
| Ownership | No owner or responsible team stated |
| Machine readability | Scanned PDFs without text, images of tables, slides without notes, locked formats |
| Self-contained content | Undefined internal jargon or abbreviations, missing context, links to inaccessible places |
| Structure inside docs | Headings, consistent templates, Q&A or step formats vs. long unstructured text |
| Coverage | Gaps relative to the stated purpose (e.g. no pricing, no refund policy, no product specs) |
| Sensitive data | Documents an agent should not access (personal data, credentials, HR, finance) mixed with general content |

## Step 4 — Score and report

Score each criterion 0–10 and compute an overall **AI-Readiness Score (0–100)** (equal weights unless the purpose makes one criterion critical — state it).

```
# Knowledge Audit — [Company/Source] · [date]

**AI-Readiness Score:** X/100 — one-line verdict

## Key findings
- 3–5 bullets, most important first

## Scorecard
| Criterion | Score | Finding | Example (file) |

## Sensitive data to separate
| File / folder | Type of data | Recommendation |
(names only, no content)

## Cleanup plan
| # | Action | Why | Effort | Impact |
Group: Quick wins (this week) · Next 30 days · Ongoing

## Not checked
- areas and what is needed to check them
```

Close with one line offering: build the new structure and index (`knowledge-structure`) or a company context file for agents (`agent-context-pack`).

## Branded report

If the environment can render HTML artifacts or files, deliver the full report using `references/report-template.html` (fill the placeholders, keep the design and colours; use the score ring for the main score and status chips for pass / warn / fail / not checked). Otherwise use the markdown format above. Keep the chat reply to a short summary either way.

## Recurring run

At the end of the report, offer a recurring run. Recommended cadence: a light re-audit monthly (new, duplicate and outdated documents) and a full audit quarterly.

Let the user choose their own schedule. Ask in one short message, with the recommendation pre-filled:

- **Frequency:** daily · weekly · every 2 weeks · monthly · quarterly · custom
- **Day:** e.g. Monday, Friday, 1st of the month
- **Time and time zone:** e.g. 09:00 Europe/Budapest (use the user's time zone if known)
- **Delivery:** in this chat, a new chat, or a document

If the environment offers scheduled tasks (a scheduling tool is available), create the task only after the user confirms these choices. Write the scheduled prompt so it is self-contained: what to check (project, repository or company), which skill to run, the report language, and where to deliver the result. Confirm what was scheduled in one line. The user can change or cancel the schedule at any time; when asked, update or remove it.

If no scheduling tool is available, state the chosen or recommended cadence and suggest a calendar reminder.
