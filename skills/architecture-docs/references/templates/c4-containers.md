---
title: Containers (C4 level 2)
owner: TBD
sources:
  - TBD
verified: TBD
status: draft
---

# Containers

Every deployable unit and data store, and how they talk.

```mermaid
flowchart LR
    user(["Customer"])
    subgraph system["System name"]
        web["Web app<br/><i>Angular</i>"]
        api["API<br/><i>NestJS</i>"]
        worker["Worker<br/><i>Node, BullMQ</i>"]
        db[("Database<br/><i>PostgreSQL</i>")]
        queue[["Queue<br/><i>Redis</i>"]]
    end
    user --> web -->|"JSON/HTTPS"| api
    api --> db
    api -->|"enqueue"| queue --> worker --> db
```

| Container | Technology | Responsibility | Code | Deployed as |
|---|---|---|---|---|
| API | NestJS | … | `apps/api/` | … |

## Open questions

- …
