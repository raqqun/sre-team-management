<!--
TEMPLATE — quarterly SLO report.

Copy to:   reviews/quarterly/YYYY-Qn.md

Audience includes people outside the SRE team. Spell out the vocabulary the
first time: SLI is a measurement, SLO is a target, error budget is 1 - SLO over
the window. These are targets, never SLAs.

Every number is measured or TODO(metric). A fabricated number in a report that
leaves the team is the worst thing in this repo.

No customer names or IDs. Use <customer-a>.
-->

---
review: quarterly
quarter: <YYYY-Qn>
period: <YYYY-MM-DD> to <YYYY-MM-DD>
author: <name>
---

# SLO report <YYYY-Qn>

## Summary

<Four or five sentences for someone who reads nothing else: did the team meet
its targets, what consumed the budget, and what is changing next quarter.>

## Performance against target

| Service | Target | Achieved | Met | Budget consumed |
|---|---|---|---|---|
| [<service-name>](../../slo/<service-name>.md) | <target> | <TODO(metric)> | <yes / no> | <TODO(metric)> |

## Where the budget went

<The incidents and slow burn that account for the consumption above. Link the
incident records rather than retelling them.>

- [<YYYY-MM-DD-short-slug>](../../incidents/<YYYY-MM-DD-short-slug>/) — <TODO(metric)> of budget

## Themes

<Patterns across the quarter that no single incident shows: a dependency that
keeps appearing, a class of change that keeps hurting, alerting that keeps
missing. Systems and decisions, not people.>

## Changes proposed

| Change | Rationale | Becomes |
|---|---|---|
| <target change / new SLO / retire an SLI> | <what the quarter showed> | <ADR in decisions/> |

## What the team needs

<Blockers that are not in the team's control. Concrete asks, each with the
reliability outcome it buys.>
