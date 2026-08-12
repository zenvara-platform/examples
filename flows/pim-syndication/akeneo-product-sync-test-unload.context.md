# Akeneo Product Sync Test Unload

Minimal Redshift UNLOAD → S3 → streaming delta → akeneo.sync-catalog pipeline — the earliest proof-of-concept for the hash-delta sync pattern, without failure reporting or observability overhead

**Connectors:** redshift, s3, akeneo  
**Capabilities:** streaming, delta-by-hash, persist  
**Domain:** data, io, integration

**What to look for when you run it:** Returns status='completed' and items-synced count; catalog-hashes persisted; models and products created/updated/failed counters present

See [`akeneo-product-sync-test-unload.flow.yaml`](./akeneo-product-sync-test-unload.flow.yaml) for the full definition.
