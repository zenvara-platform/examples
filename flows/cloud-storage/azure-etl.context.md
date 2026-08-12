# Azure Etl

A complete cloud ETL round-trip in one flow: stage CSV → upload to Azure → download → convert csv→json → upload the json → head-verify. Proves the download(filepath)→filesystem.read→convert→upload cache-path handoff works for the azure-blob-storage connector.

**Connectors:** filesystem, azure-blob-storage  
**Capabilities:** cloud-storage, etl, format-conversion, cache-handoff, csv-to-json  
**Domain:** io, core

**What to look for when you run it:** status=completed; json-head.Size>0 (the json blob landed); row-count = number of CSV data rows.

See [`azure-etl.flow.yaml`](./azure-etl.flow.yaml) for the full definition.
