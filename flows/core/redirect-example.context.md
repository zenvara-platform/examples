# Redirect Example

Flows can emit HTTP redirect responses — serving a 302 Location header via the /serve endpoint

**Connectors:** none — self-contained  
**Capabilities:** redirect-mode, serve-endpoint  
**Domain:** core

**What to look for when you run it:** GET /serve?target=https://example.com/x returns HTTP 302 with Location: https://example.com/x

See [`redirect-example.flow.yaml`](./redirect-example.flow.yaml) for the full definition.
