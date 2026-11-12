# Structure guide

## Principles for AI-readable documents

- One topic per document; one source of truth per topic.
- Put the answer first: a 2–3 sentence summary at the top of every document.
- Use headings, numbered steps, tables and Q&A blocks; avoid long unbroken text.
- State dates, owners and status explicitly; agents cannot infer them.
- Define internal jargon once in the glossary and link to it.
- Prefer text formats (Markdown, Google Docs, DOCX with real text) over scans and images of text.
- Keep sensitive content in a separate restricted area so agents can be given the general area safely.

## Example taxonomy (adapt to the company)

```
/00_Index            README, glossary, how to use this knowledge base
/01_Company          mission, org chart (roles, not personal data), policies
/02_Products         specs, pricing, release notes, FAQs
/03_Sales            pitch, objection handling, case studies, proposals templates
/04_Support          troubleshooting, refund and SLA policies, macros
/05_Operations       processes (SOPs), vendors, tools
/06_People           onboarding, handbook (restricted: contracts, salaries → /99_Restricted)
/07_Legal            terms, privacy policy, contract templates
/99_Restricted       sensitive documents, limited access
/_archive            superseded documents
```

## Document header template

```
Title:
Owner (role/team):
Last updated: YYYY-MM-DD
Status: draft | current | archived
Audience: internal | customers | partners
Summary: 2–3 sentences
```

## Naming convention examples

- `products_pricing_2026-11.md`
- `support_refund-policy_2026-09.docx`
- `sales_case-study_acme_2026-06.pdf`

Avoid: spaces, "final", "new", "copy", version numbers in names (use the status field and archive instead).
