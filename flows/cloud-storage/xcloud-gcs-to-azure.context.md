# Xcloud Gcs To Azure

A single flow moves an object between two DIFFERENT cloud backends — download from GCS into the run cache, re-upload to Azure Blob Storage — byte-for-byte. Demonstrates that `gcs.download` (a bytes-only read) feeds an Azure upload straight through the run cache, with no intermediate staging step of your own.

**Connectors:** gcs, azure-blob-storage  
**Capabilities:** cloud-storage, cross-cloud, multi-backend, cache-handoff  
**Domain:** io

**What to look for when you run it:** status=completed; bytes equals the source object size; azure-head confirms the blob landed on Azure with the same size.

See [`xcloud-gcs-to-azure.flow.yaml`](./xcloud-gcs-to-azure.flow.yaml) for the full definition.
