---
name: knowledge-structure
description: >
  This skill should be used when the user asks to "organize our documents for AI", "create a structure
  for our knowledge base", "make an index of our docs", "set naming conventions", "clean up our shared
  drive", "restructure documentation so an AI agent can use it", or after a knowledge-audit when the
  user wants the cleanup plan executed. Also triggers on the same requests in Russian ("структура базы
  знаний", "упорядочить документы") or Hungarian.
metadata:
  version: "0.1.0"
---

# Knowledge Structure

Design and, with confirmation, apply a document structure that people and AI agents can navigate.

## Style and safety rules

- Language of the user's request. Concise, professional, no filler.
- **Plan first, then apply.** Present the full plan and get explicit confirmation before changing anything.
- **Never delete.** Move superseded files to an `_archive/` folder instead. Keep a change log of every move and rename.
- Prefer working on a copy or a new folder when the source is shared and heavily used.
- Do not open, move or expose sensitive documents beyond what the plan requires; propose a separate restricted folder for them.

## Step 1 — Inputs

Use the knowledge-audit findings if available; otherwise run a quick inventory. Confirm the purpose of the agent and who maintains the documents.

## Step 2 — Design

Produce, using `references/structure-guide.md`:

1. **Folder taxonomy** — 5–9 top-level areas by how people look for information (e.g. Company, Products, Sales, Support, Operations, People, Legal), max 3 levels deep.
2. **Naming convention** — one pattern, e.g. `area_topic_YYYY-MM.ext`, no "final/new/v3".
3. **Source-of-truth map** — for each key topic, the one document that wins when others conflict.
4. **Document template** — header block: title, owner, last updated, status (draft/current/archived), audience, summary.
5. **Index** — a `README.md` (or index page) at the root and in each top-level folder listing what is where.
6. **Glossary** — internal terms and abbreviations with one-line definitions.
7. **Restricted area** — where sensitive documents go and who can access them.
8. **Maintenance rule** — owner per area, review cadence (e.g. quarterly), how to archive.

## Step 3 — Present the plan

```
## Proposed structure
(tree, max 3 levels)

## Moves and renames
| Current path | New path | Reason |
(first 30 rows; full list as a file if longer)

## Conflicts to resolve by a human
| Topic | Conflicting documents | Question for the owner |

## New files to create
- README / index, glossary, templates
```

Ask for confirmation: apply all, apply part, or export the plan only.

## Step 4 — Apply (after confirmation)

- Create folders, move and rename files exactly as listed; move superseded files to `_archive/`.
- Create the index, glossary and template files.
- Save `CHANGELOG-docuready.md` with every change (old path → new path, date).
- Report: what was done, what was skipped and why, what needs a human decision.

If the source is a connected cloud drive and the available tools cannot move files, deliver the plan, index, glossary and templates as files and list the moves for the user to perform.

## Branded document

Start the deliverable with a header block, translated into the document language: plugin name with ✦, document title, then subject · version · date · owner · status (draft or current). Follow with a 2–3 line summary and numbered sections; use tables for structured content and code blocks for anything to paste.

If the environment can render HTML artifacts or files, present it as a static HTML page (no scripts) in the house style: header band with a navy #1C1E4E to teal #0E7480 gradient and white text, meta details as small rounded pills, light background #F6F7FB, white rounded cards with a #E3E6EF border, summary card with a gold #FFC448 left accent, dark code blocks. Otherwise deliver the same structure as a document artifact or markdown.
