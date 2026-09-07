# decisions/

Short ADRs for reliability decisions. Numbered `NNNN-short-slug.md`, and
immutable once merged.

**Read this directory before proposing a structural change** — several
obvious-looking additions to this repo were considered and rejected here, and
the `Rejected` section of an ADR is what answers the same proposal when it
comes back in six months.

**Template:** [../templates/adr.md](../templates/adr.md) →
`decisions/NNNN-short-slug.md`

## What earns an ADR

A decision that constrains future work and would otherwise be re-litigated:
an SLO target change, a change to repo structure or a template's sections, a
platform choice, a deliberate acceptance of risk. Not routine changes — those
are just commits.

## Immutability

Once merged, do not edit the Context, Decision, or Consequences of a record.
Context is a snapshot of what was true on its date; editing it destroys the
only reason the record is useful.

When a decision changes, write a new ADR, set the old one's status to
`superseded by [NNNN](NNNN-slug.md)`, and link forward from the old and back
from the new.

Numbers are never reused, including for abandoned proposals.
