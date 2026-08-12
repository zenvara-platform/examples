# Enrich Records

A small reusable transform/enrich flow invoked as a SUB-FLOW by resilient-ingest-pipeline — demonstrates cross-flow composition (a flow as a building block of a larger pipeline).

**Connectors:** http  
**Capabilities:** sub-flow, flow-invocation, composition  
**Domain:** resilience, data-integration

**What to look for when you run it:** completes with output enriched='records-enriched'; usable standalone or composed via `using: - flow/enrich-records`.

See [`enrich-records.flow.yaml`](./enrich-records.flow.yaml) for the full definition.


> **Demo wiring note.** This sample calls `127.0.0.1:5000` (the local server's always-up `/health` endpoint) and a dead port `:12345` deliberately, so the flow is self-contained and runs end-to-end with zero external setup — the dead port exists purely to force the compensation/recovery path so you can watch it fire. Swap in your own service URLs for a real deployment.
