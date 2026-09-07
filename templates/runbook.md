<!--
TEMPLATE — runbook.

Copy to:   runbooks/<AlertName>.md
Filename:  exactly the alert name as it appears in the page, so the on-call
           engineer can find it by pasting the alert title.

Mitigation comes first. An engineer woken at 3am should be able to stop the
bleeding before understanding the cause. Diagnosis goes after.

Every command must be copy-pasteable and marked. The first line inside each
fence is one of:
    # read-only
    # STATE-CHANGING — <what it changes, and the blast radius>
Example:
    ```bash
    # STATE-CHANGING — restarts every pod, drops in-flight requests
    kubectl -n <namespace> rollout restart deploy/<service-name>
    ```
Redact hostnames, IPs, and tenant-scoped URLs: use <host>, <REDACTED>.
-->

---
alert: <AlertName>
service: <service-name>
pages: <yes | no>
severity: <see practices/severity.md>
last-verified: <YYYY-MM-DD>
---

# <AlertName>

## What this means

<One or two sentences: what condition fired, and what a user is experiencing
right now. Not the cause.>

## Mitigate

Do these in order. Stop when the alert clears.

1. **<Action — the fastest thing that restores service.>**

   ```bash
   # STATE-CHANGING — <what it changes, and the blast radius>
   <command>
   ```

2. **<Next action if step 1 did not clear it.>**

   ```bash
   # read-only
   <command>
   ```

3. **If nothing above works** — escalate. See below.

## Confirm it worked

```bash
# read-only
<command that shows the condition has cleared>
```

<What a healthy result looks like. If the alert does not clear within
<duration>, treat it as unmitigated and escalate.>

## Then diagnose

Only after service is restored.

```bash
# read-only
<command>
```

- <Where to look next, and what each signal would mean.>

## Escalate

| When | To |
|---|---|
| <mitigation failed / impact is growing / this is outside the runbook> | <on-call secondary, then the path in the service entry> |

Escalation path: [services/<service-name>.md](../services/<service-name>.md) ·
[oncall/escalation.md](../oncall/escalation.md)

## Related

- Service: [services/<service-name>.md](../services/<service-name>.md)
- SLO: [slo/<service-name>.md](../slo/<service-name>.md)
- Past incidents: <links>
