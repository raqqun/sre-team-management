# runbooks/

One file per alert or failure mode, named exactly after the alert — so the
on-call engineer can find it by pasting the alert title from the page.

**Template:** [../templates/runbook.md](../templates/runbook.md) →
`runbooks/<AlertName>.md`

## Mitigation first

A runbook is read at 3am by someone who needs to stop the bleeding before
understanding the cause. Structure follows that: what the alert means, then how
to mitigate, then how to confirm it worked, then diagnosis, then escalation.

If the top of the file explains the architecture, the runbook is wrong.

## Command marking

Every command is copy-pasteable and marked. The first line inside the fence is
one of:

```bash
# read-only
kubectl -n <namespace> get pods -l app=<service-name>
```

```bash
# STATE-CHANGING — restarts every pod, drops in-flight requests
kubectl -n <namespace> rollout restart deploy/<service-name>
```

An unmarked command is a defect. Someone will run it half-awake.

## Rules that apply here

- No real hostnames, internal IPs, or tenant-scoped dashboard URLs — `<host>`,
  `<REDACTED>`.
- Keep `last-verified` honest. A runbook nobody has run since the last
  migration is worse than none, because it is trusted.
- An alert with no runbook is a finding for the weekly review, not a normal
  state.
