# Akeneo Product Sync Test

Test-environment mirror of the live sync pipeline — identical architecture targeting sandbox Akeneo, proving the delta sync pattern is environment-portable without a cron trigger

**Connectors:** redshift, s3, akeneo, filesystem  
**Capabilities:** streaming, delta-by-hash, persist, failure-reporting, concurrency-skip  
**Domain:** data, io, integration

**What to look for when you run it:** Returns status='completed', items-synced count, per-type created/updated/failed counters; failures-uri populated only when failures exist

See [`akeneo-product-sync-test.flow.yaml`](./akeneo-product-sync-test.flow.yaml) for the full definition.
