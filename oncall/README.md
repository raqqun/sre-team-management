# oncall/

How the pager works, and what happened while it was carried.

```
rotation.md      Who is on call and when. Singleton.
escalation.md    Who gets called next, and after that. Singleton.
handoffs/        One note per shift change: YYYY-MM-DD.md
shift-reports/   One report per completed rotation: YYYY-MM-DD.md
```

`rotation.md` and `escalation.md` are single documents the team edits in place
— they have no template. The recurring documents do:

**Templates:**
[../templates/handoff-note.md](../templates/handoff-note.md) →
`oncall/handoffs/YYYY-MM-DD.md` ·
[../templates/shift-report.md](../templates/shift-report.md) →
`oncall/shift-reports/YYYY-MM-DD.md`

## Handoff notes

Short. What's broken, what's degraded-but-known, what's likely to page tonight.
They are read in five minutes by someone about to take the pager, not filed for
the record. "Nothing" is a useful answer to a section.

Anything that needs explaining belongs in a runbook or an incident record,
linked from the note.

## Shift reports

Written at the end of a rotation. They exist to show load and toil patterns
across shifts — which alerts are noisy, what keeps being done by hand.

**Shift reports describe the system, not the engineer.** Observable documented
facts only. Never infer capability, motivation, or attitude from a page count.
Individual performance documentation lives elsewhere, not in this repo.
