<!--
TEMPLATE — service level objectives.

Copy to:   slo/<service-name>.md   (same filename as the services/ entry)

An SLO needs an error budget policy stating what the team does at 50% / 75% /
100% burn. An SLO with no consequence attached is not an SLO — do not commit
this file with the policy table unfilled.

These are targets, not SLAs. Never call them SLAs.
Never write a measured number you have not measured: use TODO(metric).
A policy the team has not agreed yet is TODO(policy), not a plausible default.
-->

---
service: <service-name>
window: <28d | 30d | 90d — rolling unless stated>
owner: <team or role>
last-reviewed: <YYYY-MM-DD>
---

# SLOs — <service-name>

Service entry: [services/<service-name>.md](../services/<service-name>.md)

## SLIs and targets

| SLI | How it is measured | Target | Window |
|---|---|---|---|
| <Availability — e.g. share of requests not returning 5xx> | <exact query or metric source> | <TODO(metric)> | <28d> |
| <Latency — e.g. share of requests served under N ms> | <exact query or metric source> | <TODO(metric)> | <28d> |

Each SLI must name the exact measurement, not the idea of one. If the
measurement does not exist yet, say so here and leave the target as
TODO(metric).

## Error budget

Error budget is `1 - SLO` over the window.

| | |
|---|---|
| Budget | <TODO(metric)> |
| Consumed this window | <TODO(metric)> |
| As of | <YYYY-MM-DD> |

## Error budget policy

What the team does as the budget burns. This is the part that makes it an SLO.

| Burn | The team does |
|---|---|
| 50% | <TODO(policy)> |
| 75% | <TODO(policy)> |
| 100% | <TODO(policy)> |

## Excluded

<Traffic, endpoints, or windows deliberately outside these SLIs — synthetic
checks, known-bad clients, announced maintenance — and why. If nothing is
excluded, write "Nothing excluded.">

## Review

Reviewed <cadence>. Target changes are proposed in
[reviews/quarterly/](../reviews/quarterly/) and recorded as an ADR in
[decisions/](../decisions/).
