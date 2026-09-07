# templates/

Canonical templates. Copy one of these rather than inventing structure — if a
document type is missing, add a template here first, then use it.

Templates are written for both people and agents: the usage rules for each one
live in an HTML comment at the top of the file, so they are visible when you
open it and invisible when it renders. Delete that comment when you fill the
template in.

## The templates

| Template | Copy to | For |
|---|---|---|
| [service.md](service.md) | `services/<service-name>.md` | A service catalog entry |
| [slo.md](slo.md) | `slo/<service-name>.md` | SLIs, targets, error budget policy |
| [incident.md](incident.md) | `incidents/YYYY-MM-DD-short-slug/README.md` | An incident record |
| [runbook.md](runbook.md) | `runbooks/<AlertName>.md` | One alert or failure mode |
| [handoff-note.md](handoff-note.md) | `oncall/handoffs/YYYY-MM-DD.md` | Pager handoff between shifts |
| [shift-report.md](shift-report.md) | `oncall/shift-reports/YYYY-MM-DD.md` | End-of-rotation load and toil record |
| [practice.md](practice.md) | `practices/<practice-name>.md` | How the team does something |
| [weekly-review.md](weekly-review.md) | `reviews/weekly/YYYY-MM-DD.md` | Weekly reliability review |
| [quarterly-slo-report.md](quarterly-slo-report.md) | `reviews/quarterly/YYYY-Qn.md` | Quarterly SLO report |
| [adr.md](adr.md) | `decisions/NNNN-short-slug.md` | A reliability decision, immutable |
| [role.md](role.md) | `team/roles/<role-name>.md` | What a role is accountable for |

## How to use one

1. Copy the template to the path in the table. Do not edit the template itself.
2. Delete the HTML comment block at the top.
3. Replace every `<placeholder>`. Every one — a leftover `<service-name>` in a
   committed document is a bug.
4. Leave a `TODO(...)` wherever you do not have the answer. A marked gap is
   correct; an invented value is not.

## Placeholder vocabulary

These mean specific things. Use them exactly.

| Placeholder | Means |
|---|---|
| `TODO(metric)` | A number nobody has measured yet. Never write a plausible one instead. |
| `TODO(owner)` | An action item with no owner — so it is not yet an action item. |
| `TODO(policy)` | A decision the team has not made. Not a sensible default. |
| `<angle-brackets>` | Fill in, or redact: `<customer-a>`, `<host>`, `<REDACTED>`. |

## Conventions every document follows

- Markdown. Dates `YYYY-MM-DD`. Times UTC with an explicit `Z`.
- Front matter is a small block of structured fields at the top, so the corpus
  stays greppable. Keep the fields that are there; do not invent new ones per
  document.
- Link rather than duplicate. A fact lives in one file and is referenced from
  the others.
- Commands in runbooks are copy-pasteable and start with `# read-only` or
  `# STATE-CHANGING — <blast radius>` as the first line inside the fence.
- Describe systems and decisions, not people.
- Redact before writing: no customer names or IDs, real hostnames, internal
  IPs, keys, tokens, personal emails, or tenant-scoped dashboard URLs.

## Changing a template

Templates are shared structure — changing one changes every future document.
Edit freely for wording and clarity. If you are adding or removing a section,
write the reason into [decisions/](../decisions/) as an ADR first.
