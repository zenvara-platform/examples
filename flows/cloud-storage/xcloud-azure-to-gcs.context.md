# Xcloud Azure To Gcs

Reverse cross-cloud copy — stage a file, upload to Azure, download it back, then upload to GCS, verified with gcs.exists. Proves the download(filepath)→upload(filepath) cache handoff works in BOTH directions across two cloud backends.

**Connectors:** filesystem, azure-blob-storage, gcs  
**Capabilities:** cloud-storage, cross-cloud, multi-backend, cache-handoff  
**Domain:** io

**What to look for when you run it:** status=completed; gcs-found=true (object present on GCS after the cross-cloud copy); bytes equals the staged payload size.

See [`xcloud-azure-to-gcs.flow.yaml`](./xcloud-azure-to-gcs.flow.yaml) for the full definition.
