# Akeneo Channable Export Topn

Runtime-capped PIM product feed — a dynamic `limit: ${max-items}` fuses as a streaming RowLimit, so a top-N channel feed streams end-to-end without materialising the full catalogue

**Connectors:** s3, filesystem  
**Capabilities:** streaming, dynamic-limit, top-n, bool-coercion  
**Domain:** data, io

**What to look for when you run it:** Returns feed-csv (non-empty string) with at most max-items product rows; fused and unfused execution produce identical content

See [`akeneo-channable-export-topn.flow.yaml`](./akeneo-channable-export-topn.flow.yaml) for the full definition.
