# gentle-architecture-docs

A [Pi](https://pi.dev) / Gentle Shell skill that writes and maintains a project's architecture documentation as code, in `docs/`, with Mermaid diagrams: ADRs, C4 (context, containers, components), data model and dictionary, state and sequence diagrams, API contracts, deployment, security and threat model, runbooks, non-functional requirements and a domain glossary.

Every document lists the code it describes and the commit it was last checked at, so the agent (and CI) can tell when it went stale.

## Install

```bash
gentle-shell install git:github.com/ismaelosuna7824/gentle-architecture-docs   # personal
gentle-shell install -l git:github.com/ismaelosuna7824/gentle-architecture-docs # this project only
# or try it once without installing:
gentle-shell --skill ./skills/architecture-docs
```

## Use

| Command | Does |
|---|---|
| `/skill:architecture-docs init` | Map the repo; create the structure, index and every document it can ground in code |
| `/skill:architecture-docs adr <title>` | Record a decision from the current conversation |
| `/skill:architecture-docs feature <name>` | Document one feature: components, data, states, flows |
| `/skill:architecture-docs update` | Update the docs for what changed in the code |
| `/skill:architecture-docs check` | Report stale docs, broken links, invalid diagrams |

The agent also picks the skill on its own when you ask it to document something or record a decision.

## In CI

```bash
node skills/architecture-docs/scripts/docs-check.mjs --base origin/main --strict
```

Fails when a document's sources changed without the document being re-verified, a link is broken or a Mermaid block is malformed.
