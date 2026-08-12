# Akeneo Channable Export

Cache-served PIM product feed — S3 CSV → stream → rename + bool-coerce → semicolon-delimited CSV ready for channel partners

**Connectors:** s3, filesystem  
**Capabilities:** streaming, cache-served, bool-coercion  
**Domain:** data, io

**What to look for when you run it:** Returns feed-csv (non-empty string); GET /serve returns cached CSV without triggering a rebuild

See [`akeneo-channable-export.flow.yaml`](./akeneo-channable-export.flow.yaml) for the full definition.
