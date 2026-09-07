<!--
TEMPLATE — weekly reliability review.

Copy to:   reviews/weekly/YYYY-MM-DD.md   (Monday of the week under review)

This review links; it does not restate. Numbers come from a query you ran or a
dashboard you read — anything else is TODO(metric). Do not carry a number
forward from last week's review without re-checking it.

Blameless throughout. Describe systems and decisions.
-->

---
review: weekly
week-of: <YYYY-MM-DD>
present: [<name>]
---

# Weekly reliability review — week of <YYYY-MM-DD>

## SLO status

| Service | SLO | Budget consumed | Trend | Policy triggered |
|---|---|---|---|---|
| [<service-name>](../../slo/<service-name>.md) | <target> | <TODO(metric)> | <up / flat / down> | <none / 50% / 75% / 100%> |

## Incidents this week

- [<YYYY-MM-DD-short-slug>](../../incidents/<YYYY-MM-DD-short-slug>/) — <severity>, <one line on impact>

## Page load

| | |
|---|---|
| Pages | <TODO(metric)> |
| Outside working hours | <TODO(metric)> |
| Repeat pages from one alert | <TODO(metric)> |

Source: [oncall/shift-reports/](../../oncall/shift-reports/)

## Action items

| Action | From | Owner | Due | Status |
|---|---|---|---|---|
| <action> | [<incident or review>](<link>) | <name> | <YYYY-MM-DD> | <open / done / dropped> |

Dropped items get a reason, not a silent deletion.

## Decisions needed

<Things blocked on a call the team has to make. If one lands, it becomes an
ADR in decisions/.>
