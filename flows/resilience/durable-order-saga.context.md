# Durable Order Saga

A DURABLE (event-sourced) order-fulfillment saga: reserve-inventory → charge-payment → create-shipment, each with retry + an explicit `compensate:` block, running on the PersistentFlowActor via `durable: true`. The engine journals a `RunEvent` per step (so a crashed saga can resume by replay). When create-shipment fails after the first two committed, it drains the compensation stack in LIFO order (refund payment, then release inventory) and exits with a typed error. Uses only the non-streaming step kinds the durable engine supports, so it compiles clean (no V1322).

**Connectors:** http  
**Capabilities:** durable, event-sourced, saga, compensation, rollback, on-failure, retry, marquee-demo  
**Domain:** resilience, commerce

**What to look for when you run it:** Compiles clean (durable + operation/return kinds only, no V1322). The flow's own `durable: true` routes it to the event-sourced engine; it fails at $create-shipment (connection refused); the drain runs $charge-payment's then $reserve-inventory's compensate blocks (LIFO), journaling CompensationStarted → CompensationStepCompleted (×2) → CompensationCompleted; the terminal journal event is `RunFailed` (event↔status both failed); the return step is never reached.

See [`durable-order-saga.flow.yaml`](./durable-order-saga.flow.yaml) for the full definition.


> **Demo wiring note.** This sample calls `127.0.0.1:5000` (the local server's always-up `/health` endpoint) and a dead port `:12345` deliberately, so the flow is self-contained and runs end-to-end with zero external setup — the dead port exists purely to force the compensation/recovery path so you can watch it fire. Swap in your own service URLs for a real deployment.
