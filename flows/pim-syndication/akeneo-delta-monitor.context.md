# Akeneo Delta Monitor

Non-destructive incremental delta detection — Redshift UNLOAD → S3 → streaming hash-delta detects changed PIM rows without writing back to Akeneo, proving the delta engine as a standalone observability tool

**Connectors:** redshift, s3  
**Capabilities:** streaming, delta-by-hash, persist  
**Domain:** data, io

**What to look for when you run it:** Returns status='completed' and items-changed count; catalog-hashes persisted for the next run; no Akeneo writes occur

See [`akeneo-delta-monitor.flow.yaml`](./akeneo-delta-monitor.flow.yaml) for the full definition.
