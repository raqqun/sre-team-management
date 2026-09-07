<!--
TEMPLATE — on-call handoff note.

Copy to:   oncall/handoffs/YYYY-MM-DD.md   (date the shift starts)

Keep it short. This is read in five minutes by someone about to carry the
pager, not filed for the record. If a section is empty, write "Nothing" and
move on — an empty section is useful information.

Anything long enough to need explaining belongs in a runbook or an incident
record, linked from here.
-->

---
handoff: <YYYY-MM-DD>
from: <name>
to: <name>
---

# Handoff <YYYY-MM-DD>

## Broken now

<What is actively failing, what has been tried, and what the next step is.
Link the incident record if one is open. "Nothing" is a valid answer.>

## Degraded but known

<Working but not right. Why it is not being fixed right now, and the condition
under which it becomes urgent.>

## Likely to page tonight

<Known-flaky alerts, a deploy landing, a batch job, a dependency in a bad
state. For each: what to do, or the runbook that says.>

## In flight

<Changes, freezes, maintenance windows, anything a page might be related to.>
