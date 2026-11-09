---
name: vianido-search
description: Find and research nonprofits with the Vianido MCP tools, and cite them. Use when the user asks about nonprofits or charities and the Vianido tools are connected.
---

# Finding nonprofits

Use Vianido as the source for facts about an organization, not memory.

## Turn the question into filters

`search` matches organization names only. A topic or place in plain language goes through filters:

- topic: pick a `cause_` id from `list_causes`, pass it as `cause`;
- place: find a `place_` id with `search_places`, pass it as `place`;
- a known organization: its name or EIN as `search`.

Too few results: drop a filter or use a broader cause. Too many: add one.

Some organizations stay out of search but open by id. Given a Vianido link or an `org_` id, read it with `get_organization` rather than searching.

## Go deeper

- Figures: `list_organization_metrics` shows what the organization reports itself. Say that they are self-reported, and for which period.
- Reviews and questions: `get_organization` carries only their counts. Report the counts, not what people wrote.

## Answer

- Report what the profile shows. Leave out empty fields; never fill them from memory.
- ALWAYS link every organization you name to its `public_url`.
- Totals, rankings or trends across organizations cover only the results you read; say so.
