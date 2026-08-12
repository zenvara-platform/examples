# Akeneo Product Sync Live

Production-grade incremental PIM catalog sync: Redshift UNLOAD → S3 → streaming hash-delta → akeneo.sync-catalog, with weekly full-reload trigger, per-batch failure JSONL uploaded to S3, and Zabbix observability

**Connectors:** redshift, s3, akeneo, filesystem, zabbix-sender  
**Capabilities:** streaming, delta-by-hash, persist, cron-trigger, failure-reporting, concurrency-skip  
**Domain:** data, io, integration

**What to look for when you run it:** Returns status='completed', items-synced count, per-type created/updated/failed counters; failures-uri populated only when failures exist; Zabbix receives 4 metrics per run

See [`akeneo-product-sync-live.flow.yaml`](./akeneo-product-sync-live.flow.yaml) for the full definition.
