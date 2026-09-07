# reviews/

Where the team looks at reliability on a cadence rather than at 3am.

```
weekly/      Weekly reliability review: YYYY-MM-DD.md (Monday of that week)
quarterly/   Quarterly SLO report: YYYY-Qn.md
```

**Templates:**
[../templates/weekly-review.md](../templates/weekly-review.md) →
`reviews/weekly/YYYY-MM-DD.md` ·
[../templates/quarterly-slo-report.md](../templates/quarterly-slo-report.md) →
`reviews/quarterly/YYYY-Qn.md`

## Weekly

Internal. SLO burn, incidents, page load, the state of open action items, and
anything blocked on a decision. It links to [`slo/`](../slo),
[`incidents/`](../incidents), and [`oncall/`](../oncall) rather than restating
them — a review that duplicates its sources goes stale silently.

Dropped action items get a reason, not a silent deletion.

## Quarterly

Read by people outside the SRE team, including the exec summary at the top.
Spell out the vocabulary the first time, and never call an SLO an SLA — we have
very few SLAs and they are contractual.

Target changes proposed here land as an ADR in [`decisions/`](../decisions).

## Rules that apply here

- **Every number is measured or `TODO(metric)`.** A fabricated figure in a
  document that leaves the team is the worst outcome in this repo. Do not carry
  a number forward from last week without re-checking it.
- No customer names or IDs — `<customer-a>`.
- Themes and patterns describe systems and decisions, not people.
