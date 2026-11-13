---
title: Deployment
owner: TBD
sources:
  - .github/workflows/**
  - infra/**
verified: TBD
status: draft
---

# Deployment

```mermaid
flowchart TB
    subgraph prod["Production — region"]
        lb["Load balancer"] --> api["API (n replicas)"]
        api --> db[("Managed PostgreSQL")]
    end
    dev["Developer"] -->|"push"| ci["CI"] -->|"build, test, deploy"| prod
```

| Environment | URL | Where it runs | Deployed by | Data |
|---|---|---|---|---|
| dev | … | … | … | synthetic |
| staging | … | … | … | … |
| prod | … | … | … | real |

## Deploy flow

Steps from merge to production, with the workflow file for each.

## Open questions

- …
