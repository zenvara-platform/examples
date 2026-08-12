# Email Knowledge Ingestion

Zenvara can ingest email at scale — AI-extracting structured knowledge from each message and persisting it across runs

**Connectors:** imap, ai  
**Capabilities:** mail-trigger, ai-extraction, persist, for-each  
**Domain:** mail, ai

**What to look for when you run it:** output.status = 'completed'; output.processed equals the number of unread messages fetched

See [`email-knowledge-ingestion.flow.yaml`](./email-knowledge-ingestion.flow.yaml) for the full definition.
