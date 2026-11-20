---
type: note
title: "What is a folio?"
status: stable
---

# What is a folio?

A **folio** is a piece of living documentation that lives inside Zenvara's library alongside your flows, connections, and environments. This page is itself a folio — you are reading one right now.

Folios are meant for the kind of knowledge that a team keeps rewriting in chat, email, and whiteboards: onboarding notes, runbooks, glossaries, "how we do X here" guides, meeting decisions, postmortems. Anything a human benefits from having at their fingertips.

## What goes inside

A folio is a single Markdown file: a short YAML frontmatter block for the metadata, then the document you are reading.

```
knowledge/folios/{name}.folio.md         # frontmatter + body, one file
knowledge/folios/{name}.context.md       # optional sidecar — what it demonstrates
```

The frontmatter is tiny:

```yaml
---
type: note
title: "What is a folio?"
status: stable
---
```

Everything after the closing `---` is the document, and it is whatever you want — headings, lists, tables, code blocks, links. Regular GitHub-flavored Markdown, nothing exotic.

## Why folios instead of a wiki

Folios live in the same store as the rest of your Zenvara project. That means they:

- Travel with your environment — backups, branches, and deployments move them along with your flows.
- Are versioned through the same git-backed storage layer as your definitions, so you get history, diffs, and branch-based staging for free.
- Can be searched and retrieved by tools, agents, and connectors in the same way flows can.

You still get a wiki-like editing experience, but the content lives next to the code it documents rather than drifting away in a separate system.

## Editing this folio

Try it. Open this document, add a section under the one you are reading, save it. The change is recorded by the knowledge store and shows up immediately the next time someone opens the folio.

If you want to start fresh, delete this folio and create your own. A minimal folio is one file:

```
knowledge/folios/hello-team.folio.md
```

That is the entire feature.

## Ideas to try

- A team handbook: onboarding steps, conventions, who to ask about what.
- A runbook: "what to do when the nightly export fails", step by step.
- A glossary of domain terms the team keeps tripping over.
- Meeting notes that outlive the meeting.
- A decisions log: why we picked X over Y, so the next person does not have to re-litigate it.

None of these are about Zenvara itself. Folios are for **your** knowledge — this one is just an example of the shape they take.
