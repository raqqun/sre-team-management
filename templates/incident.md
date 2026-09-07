<!--
TEMPLATE — incident record.

Copy to:   incidents/YYYY-MM-DD-short-slug/README.md
           Date is the day the incident started, UTC. Slug is 2-4 words on what
           broke, not on the cause: "checkout-5xx", not "bad-redis-config".
           Supporting material (graphs, log excerpts, queries) goes in the same
           directory and is linked from the record.

Blameless: describe systems and decisions, never people. "The deploy pipeline
allowed an unreviewed config change", never "<name> pushed a bad config".
Never name an individual as a cause. Names are fine for crediting response work.

Redact: no customer names or IDs, real hostnames, internal IPs, keys, tokens,
personal emails, or tenant-scoped dashboard URLs. Use <customer-a>, <host>,
<REDACTED>.

Times are UTC with an explicit Z. Numbers you have not measured are
TODO(metric). Action items without an owner are TODO(owner).
-->

---
incident: <YYYY-MM-DD-short-slug>
severity: <see practices/severity.md>
services: [<service-name>]
started: <YYYY-MM-DDTHH:MMZ>
resolved: <YYYY-MM-DDTHH:MMZ>
status: <under-investigation | draft | final>
---

# <YYYY-MM-DD> <short description of what broke>

## Summary

<Three sentences at most: what was affected, for how long, and what ended it.
Someone should be able to read only this and know whether to read on.>

## Impact

| | |
|---|---|
| User-visible effect | <what someone outside the team experienced> |
| Duration | <TODO(metric)> |
| Error budget consumed | <TODO(metric)> — [slo/<service-name>.md](../../slo/<service-name>.md) |
| Detected by | <alert name / customer report / engineer noticed> |

## What happened

Timeline. Facts and observations only — no analysis, that goes below.

| Time (UTC) | Event |
|---|---|
| <YYYY-MM-DDTHH:MMZ> | <what happened or was observed> |
| <YYYY-MM-DDTHH:MMZ> | <alert fired / mitigation applied / recovery confirmed> |

## Why it happened

Contributing factors — there are usually several. Include what made the
incident possible, not only what triggered it.

- <Factor: a system, a default, a gap in a check, an absent signal.>
- <Factor.>

## What made the response harder or easier

- <Missing runbook, misleading dashboard, unclear ownership, good alerting.>

## What changes

Every action item has an owner, or it is TODO(owner) and not yet an action item.

| Action | Owner | Due | Tracking |
|---|---|---|---|
| <specific, verifiable change> | <name> | <YYYY-MM-DD> | <ticket> |

## Supporting material

- <file in this directory, and what it shows>
