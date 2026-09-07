# practices/

How the team works: postmortem process, severity levels, toil policy,
onboarding. One file per practice.

**Template:** [../templates/practice.md](../templates/practice.md) →
`practices/<practice-name>.md`

A practice doc says what the team actually does, in enough detail that a new
hire can follow it without asking. If the team does not do it yet, the document
says `status: proposed`.

Several other directories point here for definitions, so these files are load
bearing:

| Document | Referenced by |
|---|---|
| `severity.md` | [`incidents/`](../incidents), [`runbooks/`](../runbooks) |
| `service-tiers.md` | [`services/`](../services) |
| `postmortem.md` | [`incidents/`](../incidents) |
| `toil.md` | [`oncall/`](../oncall), [`reviews/`](../reviews) |

## Vocabulary this directory owns

**Toil** — manual, repetitive, automatable work that scales with service size.
Interrupts and project work are not toil. The distinction matters because the
toil policy commits the team to reducing toil, and it cannot commit to
eliminating interrupts.

## Proportion

Team size is 5 engineers. A practice that needs more people than that to run is
not a practice, it is a proposal for a larger team. If a step exists only to
produce a document nobody reads, cut the step.
