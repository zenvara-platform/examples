# Website Deploy

Zenvara delivers a full CI/CD pipeline for a static site — webhook-triggered download → Vite build → SFTP declarative sync with pruning → smoke-test HTTP check, all in one flow

**Connectors:** http, archive, build, filesystem, sftp  
**Capabilities:** git-webhook-trigger, auto-provision, declarative-sync, sftp-prune, smoke-test  
**Domain:** io, integration

**What to look for when you run it:** output.smoke-status = 200; output.uploaded + output.updated > 0; output.deleted reflects pruned stale files

See [`website-deploy.flow.yaml`](./website-deploy.flow.yaml) for the full definition.
