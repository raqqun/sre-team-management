# slo/

One file per service, sharing the filename with its
[`services/`](../services) entry.

**Template:** [../templates/slo.md](../templates/slo.md) →
`slo/<service-name>.md`

## What an SLO document must have

An **error budget policy** — what the team does at 50% / 75% / 100% burn. An
SLO with no consequence attached is not an SLO, it is a wish. If a document
here has targets and no policy, that is a defect worth fixing before the next
review.

Each SLI must name its exact measurement — the query or metric source, not the
idea of one. "Availability" is not an SLI; "share of requests not returning
5xx, measured at the load balancer" is.

## Vocabulary

- **SLI** — a measurement.
- **SLO** — a target for an SLI over a window.
- **Error budget** — `1 - SLO` over that window.
- **SLA** — a contractual commitment. We have very few. Never call an SLO one,
  in this directory or anywhere else.

## Rules that apply here

- Never write a number you have not measured. `TODO(metric)` is correct;
  a plausible figure is not.
- A burn policy the team has not agreed on is `TODO(policy)`.
- Target changes are proposed in [`reviews/quarterly/`](../reviews/quarterly)
  and recorded as an ADR in [`decisions/`](../decisions).
