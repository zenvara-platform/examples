# Azure Roundtrip

The azure-blob-storage connector's COMPLETE object lifecycle (upload → exists → head → list → copy → cross-container move → delete) runs clean end-to-end against Azure Blob Storage, AND the move is atomic with NO data loss / NO partial (source gone, dest present) — pins the StartCopy+WaitForCompletion-before-delete correctness.

**Connectors:** filesystem, azure-blob-storage  
**Capabilities:** cloud-storage, object-lifecycle, head-metadata, list, server-side-copy, cross-container-move  
**Domain:** io

**What to look for when you run it:** status=completed; exists-after-upload=true; head-data has all 7 fields (Key/Container/Size/LastModified/ETag/ContentType/Tier); list-keycount>=1; move-status='success'; exists-src-after-move=false AND exists-dest-after-move=true (the no-data-loss assertion).

See [`azure-roundtrip.flow.yaml`](./azure-roundtrip.flow.yaml) for the full definition.
