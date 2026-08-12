# Akeneo Channable Export De

S3-event-triggered locale-enriched PIM feed with output guards that refuse to publish if the feed is empty or deviates >20% from the prior run — cache poisoning protection in production

**Connectors:** s3, filesystem, zabbix-sender  
**Capabilities:** streaming, cache-served, event-trigger, delta-by-size, output-guards, bool-coercion, persist, lookup-by-join  
**Domain:** data, io, integration

**What to look for when you run it:** Returns feed-csv (non-empty); output guards block on empty or outlier delta; Zabbix receives status/rows/bytes metrics and delta_pct on subsequent runs

See [`akeneo-channable-export-de.flow.yaml`](./akeneo-channable-export-de.flow.yaml) for the full definition.
