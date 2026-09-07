# incidents/

One directory per incident, named `YYYY-MM-DD-short-slug/`. The date is when it
started, UTC. The slug says what broke, not what caused it — `checkout-5xx`,
not `bad-redis-config`, because the cause is often wrong on day one.

The record itself is `README.md` inside that directory. Graphs, log excerpts,
and queries live alongside it and are linked from the record.

**Template:** [../templates/incident.md](../templates/incident.md) →
`incidents/YYYY-MM-DD-short-slug/README.md`

An **incident** is anything that consumed error budget or required unplanned
human response. Severity levels live in
[`practices/severity.md`](../practices).

## The three separations

A record keeps these apart, because mixing them is how postmortems turn into
arguments:

- **What happened** — the timeline. Facts and observations, UTC with an
  explicit `Z`. No analysis.
- **Why** — contributing factors. Usually several. What made the incident
  possible, not only what triggered it.
- **What changes** — action items. Every one has an owner, or it is
  `TODO(owner)` and not yet an action item.

## Rules that apply here

- **Blameless.** Describe systems and decisions, never people. "The deploy
  pipeline allowed an unreviewed config change" — never "<name> pushed a bad
  config". Never name an individual as a cause. Names are fine for crediting
  response work.
- **Redact before writing.** No customer names or IDs, real hostnames, internal
  IPs, keys, tokens, personal emails, or tenant-scoped dashboard URLs. Use
  `<customer-a>`, `<host>`, `<REDACTED>`. Check pasted log excerpts especially.
- Duration and error budget consumed are `TODO(metric)` until measured.
