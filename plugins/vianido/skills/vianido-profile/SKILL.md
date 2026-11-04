---
name: vianido-profile
description: Update the Vianido profile of an organization the user manages with the Vianido MCP tools, from a single field change or a new metric value to a first full fill of an empty profile.
---

# Managing a profile

Changes go live as soon as they are written. For writing profile content, also follow `vianido-writing`; for the About page, follow `vianido-about-page`.

## Start

1. `list_my_organizations`; ask which one if there are several.
2. `get_organization`, and tell the user briefly what it shows, what came from the organization versus public data (`overrides`, `inherited`), and what is empty.

No write tools listed: the connection lacks edit access. Ask the user to reconnect and approve it.

## First fill

When the profile is mostly empty or inherited, ask for sources before writing anything:

- the website, and pages about programs or history;
- an annual or impact report, brochure or grant proposal, in whatever form you can read;
- what they want said or left out;
- current contact, donation and volunteer details, and social profiles;
- the figures they track themselves, with the period each covers;
- photos they own and want shown.

Then propose every field at once, with the source of each, and write once the user approves. Small later edits skip this.

## Every write

Show the exact values, dry-run with `validate_only: true`, write, then re-read and report.

## Metrics

- Only figures the organization tracks and the user confirms. Never derive one from a report's prose or fill in missing periods.
- Use a template from `list_metric_templates` when one measures the same thing; create a custom metric only when none fits.
- One metric per thing measured. A new year or quarter is a new value on the same metric, not a new metric.
- Before recording a value for a date that already has one, show the user the value it replaces.

## Logo and images

Uploading needs you to read the file and send it over HTTP yourself. Without a shell or HTTP access, as in most hosted chats, ask the user to upload it on the Vianido website instead. Use only images the user provides or confirms the organization owns.

## Accuracy

- Only facts from the user or the organization's own website and documents. Leave a field empty rather than guess.
- When sources disagree, ask which is current.

## Not available here

Causes, updates, answers to questions, replies to reviews and voices are edited on the Vianido website. Videos are uploaded there too. Say so rather than using another field.

## Keep it current

Donors and funders read profiles year-round, and outdated contact, donation or program details cost the organization trust. After a first fill or a large update, and if you can schedule reminders or recurring tasks, offer to remind the user to review the profile and record new metric values. Ask how often their information changes: monthly for an organization with frequent events or programs, every three months otherwise. Set it only if the user agrees.
