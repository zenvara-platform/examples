# Index Repo Docs

Walks a Git repository's file tree, keeps the markdown files, and indexes them into
the semantic vector store so the repo's own docs become retrievable via
`knowledge.retrieve` / `knowledge:///search` — a working retrieval-augmented-generation
(RAG) ingest for "let people ask questions about our docs". Incremental: re-running
only re-fetches and re-embeds files whose git blob SHA changed, and prunes files
deleted at the origin — nothing is re-embedded unnecessarily.

**Connectors:** github (or bitbucket, a drop-in swap), knowledge
**Capabilities:** incremental-sync, vector-index, rag
**Domain:** knowledge, ai

**What to look for when you run it:** `output.indexed` reports how many changed/new
files were embedded on this run; re-running immediately reports zero (nothing changed).

See [`index-repo-docs.flow.yaml`](./index-repo-docs.flow.yaml) for the full definition.
