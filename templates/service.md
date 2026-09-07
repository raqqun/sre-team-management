<!--
TEMPLATE — service catalog entry.

Copy to:   services/<service-name>.md
Filename:  lowercase, hyphenated. This filename is the service's ID everywhere
           else in the repo (slo/, runbooks/, incidents/ all reference it).
Then:      create slo/<service-name>.md, or state below why there is no SLO.

Before committing: delete every HTML comment, replace every <placeholder>, and
resolve or keep every TODO(...) honestly. Do not guess a value.
Tier definitions live in practices/service-tiers.md — write that doc before an
entry claims a tier.
-->

---
service: <service-name>
tier: <1 | 2 | 3>
owner: <team or role — never an individual>
platform: <aws | gcp | equinix-onprem>
slo: <slo/<service-name>.md | none — reason below>
status: <production | beta | deprecated>
---

# <service-name>

<One or two sentences: what it does, and what breaks for whom when it stops.>

## Where it runs

| | |
|---|---|
| Platform | <aws / gcp / equinix-onprem> |
| Region or site | <region-or-site> |
| Deploy unit | <cluster / host group — use `<host>`, never a real hostname> |
| Deploy mechanism | <pipeline or process, linked if documented> |

## Dependencies

Depends on — losing these degrades or breaks this service:

| Service | Type | What breaks without it |
|---|---|---|
| [<service>](<service>.md) | <hard / soft> | <effect> |

Depended on by — these break when this service does:

| Service | Type | Effect |
|---|---|---|
| [<service>](<service>.md) | <hard / soft> | <effect> |

## Escalation

| Step | Who |
|---|---|
| 1 | On-call primary — see [rotation](../oncall/rotation.md) |
| 2 | <secondary or owning team> |
| 3 | <service owner / vendor, with the documented contact route> |

Full policy: [oncall/escalation.md](../oncall/escalation.md)

## Operational surface

- **SLO** — [slo/<service-name>.md](../slo/<service-name>.md)
- **Runbooks** — [<AlertName>](../runbooks/<AlertName>.md)
- **Dashboards** — <name and how to find it. No tenant-scoped URLs.>
- **Logs** — <where, and how to reach them>

## Known constraints

<Load limits, single points of failure, manual steps, planned deprecation.
The things a new on-call engineer would otherwise learn at 3am. TODO(metric)
for any limit that hasn't been measured.>
