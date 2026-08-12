# Akeneo Channable Export Fr

FR locale variant of the enriched PIM feed pipeline — mirrors DE architecture, proving the same output-guard and SQS-trigger pattern works per-locale with independent persist state

**Connectors:** s3, filesystem, zabbix-sender  
**Capabilities:** streaming, cache-served, event-trigger, delta-by-size, output-guards, bool-coercion, persist, lookup-by-join  
**Domain:** data, io, integration

**What to look for when you run it:** Returns feed-csv (non-empty); FR-suffixed column names present; output guards block empty or >20% deviant feeds; Zabbix receives [fr]-keyed metrics

See [`akeneo-channable-export-fr.flow.yaml`](./akeneo-channable-export-fr.flow.yaml) for the full definition.
