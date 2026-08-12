# Ci Build Test

Zenvara's build connector delivers a CI pipeline in one flow — compile a project, run its test suite, branch on build success, and return structured pass/fail counts (built / outcome / total-tests / passed / failed)

**Connectors:** build  
**Capabilities:** ci-pipeline, build, test, structured-test-results, success-gating  
**Domain:** utility

**What to look for when you run it:** for a green project: output.built=true, output.outcome='green', output.passed>0, output.failed=0; for a failing build: output.built=false, output.outcome='build-failed'

See [`ci-build-test.flow.yaml`](./ci-build-test.flow.yaml) for the full definition.
