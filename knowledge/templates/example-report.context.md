# Example Invoice Report

A Liquid template (`template.liquid` + a `sample.json` preview payload) rendering a
simple HTML invoice — the template `demo-report.flow.yaml` renders via the `render:`
step. Templates are Zenvara's Liquid-based reporting layer: bind any flow's data to
one and render HTML, and it works standalone (`preview-template`) or wired into a
flow.

See [`example-report.template.yaml`](./example-report.template.yaml),
[`example-report/template.liquid`](./example-report/template.liquid), and
[`example-report/sample.json`](./example-report/sample.json).
