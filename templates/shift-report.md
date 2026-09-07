<!--
TEMPLATE — end-of-rotation shift report.

Copy to:   oncall/shift-reports/YYYY-MM-DD.md   (date the shift ended)

This is a record of what the rotation was like, used to find load and toil
patterns across shifts. It is not a record of how an engineer performed.

Personnel rule: observable documented facts only. Never infer capability,
motivation, or attitude from on-call metrics. Page counts describe the
system, not the person who carried the pager.

Counts you have not actually counted are TODO(metric).
-->

---
shift: <YYYY-MM-DD> to <YYYY-MM-DD>
engineer: <name>
---

# Shift report <YYYY-MM-DD> to <YYYY-MM-DD>

## Load

| | |
|---|---|
| Pages | <TODO(metric)> |
| Pages outside working hours | <TODO(metric)> |
| Actionable | <TODO(metric)> |
| Incidents opened | <TODO(metric)> |

## Incidents

- [<YYYY-MM-DD-short-slug>](../../incidents/<YYYY-MM-DD-short-slug>/) — <one line>

## Noisy or unactionable alerts

| Alert | Times fired | Why it was not actionable | Proposed change |
|---|---|---|---|
| <AlertName> | <TODO(metric)> | <reason> | <tune / delete / write runbook> |

## Toil observed

<Manual, repetitive, automatable work that scales with the service. Interrupts
and project work are not toil — leave them out.>

## What should change

| Change | Owner | Where it goes |
|---|---|---|
| <specific> | <name or TODO(owner)> | <runbook / backlog / ADR> |
