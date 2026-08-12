# Annual Business Analysis

Zenvara streams live data from an ERP (sevDESK) and a project tracker (Jira) in parallel, then drives the script connector to render a Deckungsbeitrag report — no manual export

**Connectors:** sevdesk, jira, filesystem, business-analysis-builder  
**Capabilities:** streaming, multi-source-aggregation, script-connector, deckungsbeitrag  
**Domain:** integration, data, io

**What to look for when you run it:** output.path is a written markdown file; output.deckungsbeitrag is a non-zero float

See [`annual-business-analysis.flow.yaml`](./annual-business-analysis.flow.yaml) for the full definition.
