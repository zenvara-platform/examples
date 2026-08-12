# Demo Report

The "click it and it works" flow: zero connectors, zero configuration. It assigns a
small set of inline invoice line items, filters them, and renders the already-seeded
`example-report` Liquid template into an HTML invoice — nothing to wire up first. Run
this one first if you want to see Zenvara produce a real result before touching any
connection or environment.

**Connectors:** none — self-contained
**Capabilities:** render, filter, zero-configuration
**Domain:** reporting

**What to look for when you run it:** `output.report` is a non-empty HTML string (the
rendered invoice); `output.line-count` matches the number of line items that passed
the filter.

See [`demo-report.flow.yaml`](./demo-report.flow.yaml) for the full definition.
