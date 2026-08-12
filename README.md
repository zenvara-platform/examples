# Zenvara Samples

Real, working Zenvara flows, folios, skills, templates, environments, and
connections — the same shapes you'd write for your own automation, each with a
short `.context.md` sidecar explaining what it demonstrates and what to look for
when you run it.

This directory *is* [`zenvara-platform/examples`](https://github.com/zenvara-platform/examples)
byte-for-byte — vendored out from `zenvara-platform/server-source`, the canonical
source, by a release job. See that repo's `docs/decisions/` for why the canonical
copy lives there rather than in this public repo itself.

## Layout

```
samples/
  flows/
    pim-syndication/   Akeneo → Channable product-feed exports and sync/monitor flows
    reporting/          zero-config and multi-source reports
    cloud-storage/       S3 / Azure Blob / GCS round-trips and cross-cloud moves
    ci-cd/                build, test, and deploy pipelines
    resilience/           durable sagas, retries, compensation, sub-flow composition
    core/                 minimal building-block flows (echo, redirect)
    email/                IMAP + AI knowledge ingestion and auto-reply
    knowledge-rag/         retrieval-augmented-generation ingest flows (repo docs,
                           Confluence, Jira, local folders)
  knowledge/
    folios/                knowledge-base entities (title + document.md)
    folio-documents/       the folio bodies
    skills/                guided-methodology entities (the kaizen-cycle PDCA skill)
    templates/              Liquid report templates
  config/
    environments/           named connection compositions a flow runs against
    connections/             one-per-backend typed connection definitions
```

Each entity is a pair: `<name>.<kind>.yaml` (the definition) + `<name>.context.md`
(what it shows, in plain language) sitting right beside it.

## How to use these

- **Browse.** Every `.context.md` is written to be read standalone.
- **Load into a live instance.** Point git-backed storage at a clone of this repo,
  or load individual files with `create-entity … content=<yaml>`.
- **Run one.** `demo-report` needs zero configuration — clone, point Zenvara's
  storage at it, and run `run-flow(name="demo-report")` for an immediate result.
  Most others need a bound environment/connection (see each flow's `.context.md`
  and the `config/` samples for the shape).

## What's *not* here

This is a curated sample set, not the full product surface — no third-party
credentials, no customer data, no internal engineering history. Everything here
validates clean against Zenvara's own `validate-flow` oracle and passed an
explicit scrub pass for internal identifiers before publication.

## License

MIT — see [`LICENSE.md`](./LICENSE.md).
