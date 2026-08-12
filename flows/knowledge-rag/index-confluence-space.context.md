# Index Confluence Space

Indexes a Confluence space into the semantic vector store so its pages are
retrievable via `knowledge.retrieve` / `knowledge:///search`. Incremental: a cheap
CQL list (version numbers only, no page bodies) builds a manifest, which is diffed
against what is already indexed — only new or changed pages have their body fetched
and re-embedded, and pages deleted from the space are pruned automatically. The same
reconcile shape backs `index-repo-docs`, keyed on a git blob SHA instead of a page
version number.

**Connectors:** confluence, knowledge
**Capabilities:** incremental-sync, vector-index, rag
**Domain:** knowledge, ai

**What to look for when you run it:** `output.indexed` reports the number of
new/changed pages embedded on this run.

See [`index-confluence-space.flow.yaml`](./index-confluence-space.flow.yaml) for the
full definition.
