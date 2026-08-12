# Index Jira Project

Searches a Jira project by JQL and indexes each matching issue's summary and
description into the semantic vector store, so past issues become retrievable via
`knowledge.retrieve` / `knowledge:///search` with citations back to the issue key.
Draining every page uses `stream: from: list:` rather than a bare `list:` call, so
large projects are indexed in full rather than silently capped at the connector's
first page.

**Connectors:** jira, knowledge
**Capabilities:** streaming, vector-index, rag
**Domain:** knowledge, ai

**What to look for when you run it:** `output.indexed` equals the number of issues
your JQL matched.

See [`index-jira-project.flow.yaml`](./index-jira-project.flow.yaml) for the full
definition.
