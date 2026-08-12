# Index Folder

Walks a directory under the filesystem connector's sandbox root, reads each matching
text file, and indexes it into the semantic vector store — a RAG ingest for local
files (a docs folder, a notes tree) with no external system involved at all.
Re-running replaces a file's chunks in place rather than duplicating them.

**Connectors:** filesystem, knowledge
**Capabilities:** vector-index, rag, filesystem-sandbox
**Domain:** knowledge, ai

**What to look for when you run it:** `output.indexed` reports the number of files
embedded; `knowledge.retrieve` against the same collection then surfaces their
content.

See [`index-folder.flow.yaml`](./index-folder.flow.yaml) for the full definition.
