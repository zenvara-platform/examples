# Ci Build Test Publish

Zenvara's build connector covers the full build + test + package lifecycle in one flow — compile, test, and publish a deployable artifact only on green, with success-gating at each stage (built / tested / published / outcome)

**Connectors:** build  
**Capabilities:** ci-pipeline, cd-pipeline, build, test, publish, success-gating, nested-conditional  
**Domain:** utility

**What to look for when you run it:** green project: output.built=true, output.tested=true, output.published=true, output.outcome='published'; failing tests: output.outcome='tests-failed', published=false; failing build: output.outcome='build-failed'

See [`ci-build-test-publish.flow.yaml`](./ci-build-test-publish.flow.yaml) for the full definition.
