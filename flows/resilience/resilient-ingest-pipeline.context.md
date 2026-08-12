# Resilient Ingest Pipeline

A concurrency-gated, retrying, sub-flow-composing multi-stage ingest: extract (with retry/backoff) → enrich (a SUB-FLOW) → load, gated at max:1/on-conflict:skip, with an on-failure recovery block. Demonstrates four resilience features composed in one realistic pipeline (the happy-path companion to order-fulfillment-saga's rollback).

**Connectors:** http  
**Capabilities:** concurrency-gate, retry, sub-flow, flow-invocation, on-failure, marquee-demo  
**Domain:** resilience, data-integration

**What to look for when you run it:** happy path completes with output loaded='ingest-complete', invoking the enrich-records sub-flow between extract and load; a second concurrent fire while one is in flight is skipped (gate); a flaky $extract is retried before failing; any failure runs the on-failure recovery block.

See [`resilient-ingest-pipeline.flow.yaml`](./resilient-ingest-pipeline.flow.yaml) for the full definition.


> **Demo wiring note.** This sample calls `127.0.0.1:5000` (the local server's always-up `/health` endpoint) and a dead port `:12345` deliberately, so the flow is self-contained and runs end-to-end with zero external setup — the dead port exists purely to force the compensation/recovery path so you can watch it fire. Swap in your own service URLs for a real deployment.
