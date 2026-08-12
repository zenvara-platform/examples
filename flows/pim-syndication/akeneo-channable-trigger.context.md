# Akeneo Channable Trigger

Manual orchestration flow that fires all 5 Akeneo export jobs in sequence via REST — proves the akeneo.request action can kick remote PIM jobs with rollback: none semantics

**Connectors:** akeneo  
**Capabilities:** manual-trigger, rollback-none, concurrency-skip  
**Domain:** integration

**What to look for when you run it:** Returns status='all exports triggered'; each log line shows a 200/202 statusCode from the Akeneo API

See [`akeneo-channable-trigger.flow.yaml`](./akeneo-channable-trigger.flow.yaml) for the full definition.
