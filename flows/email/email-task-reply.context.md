# Email Task Reply

Zenvara bridges email replies into Jira — AI extracts the issue key and posts the reply as a comment automatically

**Connectors:** imap, ai, jira  
**Capabilities:** mail-trigger, ai-extraction, conditional, for-each  
**Domain:** mail, ai, integration

**What to look for when you run it:** output.status = 'completed'; each reply email with a parseable issue key produces a jira.comment create

See [`email-task-reply.flow.yaml`](./email-task-reply.flow.yaml) for the full definition.
