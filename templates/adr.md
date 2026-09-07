<!--
TEMPLATE — architecture decision record.

Copy to:   decisions/NNNN-short-slug.md
           NNNN is the next unused number, zero-padded. Never reuse one.

ADRs are immutable. Once merged, do not edit the Context, Decision, or
Consequences of a record — if the decision changes, write a new ADR and set
this one's status to superseded, with a link both ways.

The "Rejected" section is the point of this directory. Someone will propose the
rejected option again in six months; this is what answers them.
-->

---
adr: <NNNN>
title: <short imperative title>
status: <proposed | accepted | superseded by [NNNN](NNNN-slug.md)>
date: <YYYY-MM-DD>
deciders: [<name>]
---

# <NNNN>. <Title>

## Context

<The situation forcing a decision, and the constraints that narrow it — team
size, existing platforms, on-call load. Facts as they were on the date above.
Do not update this section later.>

## Decision

<What was decided, in the active voice and one paragraph. "We will ...">

## Consequences

<What this makes easier, what it makes harder, and what the team now has to
live with. Include the costs — an ADR listing only benefits is a pitch, not a
record.>

## Rejected

| Option | Why not |
|---|---|
| <alternative that was seriously considered> | <the reason, specific to our constraints> |
