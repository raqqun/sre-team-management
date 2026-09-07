# <TEAM NAME> — Operational Source of Truth

The operational documentation for the <TEAM NAME> at <ORG NAME>: what we run,
what we promise it will do, how the pager works, what has broken before, and
how to fix it at 3am.

Documentation only. Nothing here is deployed, and no code here runs in
production.

## Why this repo exists

Small teams keep their operational knowledge in the same three places: a wiki
nobody prunes, a chat history nobody can search, and the head of whoever was on
call last. All three fail the same way — the knowledge is there right up until
the moment someone needs it.

This repo is the fourth place, and the only one that counts. It is a flat set
of Markdown files in version control, reviewed like code, small enough that a
team of five can actually keep it true.

## The problems it solves

**"Who owns this, and who do I call?"** — [`services/`](services/) is the
catalog, and the root of everything else. One file per service: owner, tier,
dependencies in both directions, escalation path, where it runs. Every other
directory keys off the names used there.

**"Is this bad enough to page someone?"** — [`slo/`](slo/) turns a feeling into
a number. Each service gets explicit SLIs, targets, and an error budget policy
that says what the team does at 50% / 75% / 100% burn. A target with no
consequence attached is not an SLO, and the directory says so.

**"It's 3am and I've never seen this alert."** — [`runbooks/`](runbooks/) has
one file per alert, named after the alert so it can be found by pasting the
page title. Mitigation comes first, diagnosis later; every command is
copy-pasteable and marked read-only or state-changing.

**"Did this happen before?"** — [`incidents/`](incidents/) keeps one record per
incident, separating what happened from why from what changes. Blameless by
rule: records describe systems and decisions, never people.

**"What am I picking up with the pager?"** — [`oncall/`](oncall/) holds the
rotation, the escalation policy, and short handoff notes covering what's
broken, what's degraded-but-known, and what's likely to page tonight. Shift
reports surface load and toil patterns across rotations.

**"Are we actually getting more reliable?"** — [`reviews/`](reviews/) is where
that gets looked at on a cadence instead of during an outage: weekly internally,
quarterly for people outside the team.

**"Why is it done this way?"** — [`decisions/`](decisions/) holds short,
numbered, immutable ADRs. Several obvious-looking changes to this repo were
proposed and rejected there, which is what answers the same proposal when it
comes back in six months.

**"How does this team work?"** — [`practices/`](practices/) covers the
postmortem process, severity levels, the toil policy, and onboarding.
[`team/`](team/) covers the charter, roles, and level expectations — roles, not
people.

## Layout

| Directory | Contents |
|---|---|
| [`services/`](services/) | Service catalog. One file per service. |
| [`slo/`](slo/) | SLIs, targets, error budget policy. One file per service. |
| [`oncall/`](oncall/) | Rotation, escalation, handoff notes, shift reports. |
| [`incidents/`](incidents/) | One directory per incident: `YYYY-MM-DD-short-slug/`. |
| [`runbooks/`](runbooks/) | One file per alert or failure mode. |
| [`practices/`](practices/) | How the team works. |
| [`reviews/`](reviews/) | Weekly reviews, quarterly SLO reports. |
| [`decisions/`](decisions/) | Numbered ADRs. Immutable. |
| [`team/`](team/) | Charter, roles, ladder. |
| [`templates/`](templates/) | Canonical templates. Copy these. |
| [`scratch/`](scratch/) | Gitignored. Throwaway analysis. |

Every directory has its own README explaining what belongs in it and the rules
that apply there. Read that one before adding a file.

## Writing anything here

1. **Start from a template.** [`templates/`](templates/) has one per document
   type, with the target path in its table. Copy it; don't invent structure.
2. **Never invent a number.** Latency, error rates, budget burn, page counts,
   MTTR — if it hasn't been measured, write `TODO(metric)`. A plausible
   fabricated figure in an SLO doc is worse than a blank, because someone will
   believe it.
3. **Redact before writing.** No customer names or IDs, real hostnames,
   internal IPs, keys, tokens, personal emails, or tenant-scoped dashboard
   URLs. Use `<customer-a>`, `<host>`, `<REDACTED>` — check pasted log excerpts
   especially.
4. **Describe systems, not people.** This holds in incidents, reviews, shift
   reports, and role docs alike. Names are for crediting response work.
5. **Link rather than duplicate.** A fact lives in one file. Copies go stale
   silently.

Markdown, dates as `YYYY-MM-DD`, times UTC with an explicit `Z`. Keep documents
short enough that someone actually reads them.

## Vocabulary

Used precisely throughout, because the distinctions carry weight:

- **SLI** — a measurement. **SLO** — a target for an SLI over a window.
  **SLA** — a contractual commitment. We have very few; an SLO is never one.
- **Error budget** — `1 - SLO` over the window.
- **Toil** — manual, repetitive, automatable work that scales with service
  size. Interrupts and project work are not toil.
- **Incident** — anything that consumed error budget or required unplanned
  human response. Severity levels live in [`practices/`](practices/).

## Proportion

The team is five engineers. Everything here is sized for that. Process that
needs a larger team to run isn't process, it's a proposal for a larger team —
and it belongs in an ADR, not in a document that implies the team already works
that way.

## Out of scope

Customer-facing material, legal commitments, and individual performance
documentation live elsewhere.
