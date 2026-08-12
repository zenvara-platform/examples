# Gcs Roundtrip

The gcs connector's core object lifecycle (upload → exists → server-side copy → delete) runs clean end-to-end against Google Cloud Storage; every output field matches the documented shape (upload→response, exists→exists:bool, copy→status, delete-object→response).

**Connectors:** filesystem, gcs  
**Capabilities:** cloud-storage, object-lifecycle, server-side-copy, cache-staging  
**Domain:** io

**What to look for when you run it:** status=completed; exists-after-upload=true; copy-status='success'; exists-copy-dst=true; delete responses present. (Scoped to the byte-level lifecycle — see `azure-roundtrip` for list and head-metadata coverage.)

See [`gcs-roundtrip.flow.yaml`](./gcs-roundtrip.flow.yaml) for the full definition.
