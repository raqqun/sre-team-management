## What this repo is

The operational source of truth for the <TEAM NAME> at <ORG NAME>:
service catalog, reliability targets, on-call process, incident records,
runbooks, and team practice docs.

Documentation only — nothing here is deployed. Written for <TEAM NAME> members,
the on-call engineer at 3am, new hires, and partner engineering teams.

Team size is 4 engineers. Keep everything proportionate to that. Do not propose
processes, review boards, or document hierarchies built for a large org.

Documents are written in **English**.

## Layout

```
services/     Service catalog. One file per service: owner, tier, dependencies,
              escalation path, where it runs (AWS / GCP / Equinix onprem).
              Everything else keys off this.
slo/          One file per service. SLI definitions, targets, error budget policy.
oncall/       Rotation config, escalation policy, handoff notes, shift reports.
incidents/    One directory per incident: YYYY-MM-DD-short-slug/
runbooks/     One file per alert or failure mode, named after the alert.
practices/    Postmortem process, severity levels, toil policy, onboarding.
reviews/      Weekly reliability reviews, quarterly SLO reports, exec summaries.
decisions/    Short ADRs for reliability decisions. Numbered, immutable.
team/         Charter, roles, ladder expectations.
templates/    Canonical templates. Copy these rather than inventing structure.
scratch/      Gitignored. Throwaway analysis. Paste the output into a doc, not the script.
```

Read `decisions/` before proposing structural changes — several obvious-looking
additions were considered and rejected there.

## Hard rules

**Never invent numbers.** Latency, error rates, budget burn, page counts, MTTR
— if the value isn't in a file I've given you or in command output you can run,
write `TODO(metric)` and say so. A plausible fabricated number in an SLO doc is
worse than a blank.

**Blameless language.** Describe systems and decisions, not people. "The deploy
pipeline allowed an unreviewed config change", never "Alice pushed a bad
config". Never name an individual as a cause. Names are fine for crediting
response work.

**Redact before writing.** No customer names or IDs, real hostnames, internal
IPs, keys, tokens, personal emails, or tenant-scoped dashboard URLs. Use
`<customer-a>`, `<host>`, `<REDACTED>`. Flag anything sensitive you spot in
pasted logs that I forgot to strip.

**Personnel content stays factual.** For workload, performance, or hiring
topics: observable documented facts only. Never infer capability, motivation,
or attitude from on-call metrics.

**Ask when scope is ambiguous.** One clarifying question beats a large
speculative document.

## Vocabulary

- **SLI** — a measurement. **SLO** — a target for an SLI over a window.
  **SLA** — a contractual commitment; we have very few, so never call an SLO one.
- **Error budget** — `1 - SLO` over the window.
- **Toil** — manual, repetitive, automatable work that scales with service size.
  Interrupts and project work are not toil.
- **Incident** — anything that consumed error budget or required unplanned
  human response. Severity levels live in `practices/severity.md`.

## Document expectations

- **SLOs** need an error budget policy stating what the team does at 50% / 75% /
  100% burn. An SLO with no consequence attached isn't one — say so if I write one.
- **Runbooks** lead with mitigation, not diagnosis. Commands must be
  copy-pasteable and marked read-only or state-changing.
- **Incidents** separate what happened (timeline, UTC) from why (contributing
  factors, usually several) from what changes (action items). Every action item
  needs an owner or it's `TODO(owner)`, not an action item.
- **Handoff notes** are short: what's broken, what's degraded-but-known, what's
  likely to page tonight.

Markdown, dates as `YYYY-MM-DD`, times UTC with explicit `Z`. Prefer linking
over duplicating. Keep documents short enough that someone actually reads them.

## Out of scope

Customer-facing material, legal commitments, and individual performance
documentation live elsewhere.
