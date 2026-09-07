# services/

The service catalog, and the root of everything else in this repo. One file per
service.

The filename is the service's ID: `slo/`, `runbooks/`, `incidents/`, and
`reviews/` all reference a service by the name used here. Rename a file and you
break those references, so pick the name carefully once.

**Template:** [../templates/service.md](../templates/service.md) →
`services/<service-name>.md`

## What belongs in an entry

Owner (a team or role, never an individual), tier, dependencies in both
directions, escalation path, where it runs (AWS / GCP / Equinix onprem), and
the operational surface — SLO, runbooks, dashboards, logs.

Write it for the engineer who gets paged for this service for the first time.

## Adding a service

1. Copy the template to `services/<service-name>.md` and fill it in.
2. Create [`slo/<service-name>.md`](../slo), or record in the entry why the
   service has no SLO.
3. Link its runbooks as they are written.

## Rules that apply here

- Owner is a team or role. Individuals move; the catalog should not.
- No real hostnames, internal IPs, or tenant-scoped dashboard URLs. Use
  `<host>`, and name a dashboard rather than linking a scoped one.
- Capacity limits and load numbers are `TODO(metric)` until measured.
