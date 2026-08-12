# Order Fulfillment Saga

A transactional order-fulfillment saga: reserve-inventory → charge-payment → create-shipment, each with retry + an explicit `compensate:` block. When create-shipment fails after the first two committed, the engine drains the compensation stack in LIFO order (refund payment, then release inventory) and exits with a typed error — a clean, complete rollback.

**Connectors:** http  
**Capabilities:** saga, compensation, rollback, transactional, retry, on-failure, marquee-demo  
**Domain:** resilience, commerce

**What to look for when you run it:** flow fails at $create-shipment (connection refused); the compensation drain runs $charge-payment's then $reserve-inventory's compensate blocks (LIFO) and logs 'All compensation steps completed successfully'; terminal error is the typed shipment error, not a crash; the return step is never reached.

See [`order-fulfillment-saga.flow.yaml`](./order-fulfillment-saga.flow.yaml) for the full definition.


> **Demo wiring note.** This sample calls `127.0.0.1:5000` (the local server's always-up `/health` endpoint) and a dead port `:12345` deliberately, so the flow is self-contained and runs end-to-end with zero external setup — the dead port exists purely to force the compensation/recovery path so you can watch it fire. Swap in your own service URLs for a real deployment.
