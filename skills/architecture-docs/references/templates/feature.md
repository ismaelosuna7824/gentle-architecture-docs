---
title: Feature — name
owner: TBD
sources:
  - src/feature/**
verified: TBD
status: draft
---

# Feature name

What it does, for whom, and the main use cases (one line each).

## Components (C4 level 3)

```mermaid
flowchart TB
    subgraph api["API container"]
        ctrl["PaymentsController"]
        svc["PaymentsService"]
        repo["PaymentsRepository"]
        gw["ProviderGateway"]
    end
    ctrl --> svc --> repo
    svc --> gw -->|"HTTPS"| provider["Payment provider (external)"]
```

| Component | Responsibility | Code |
|---|---|---|
| PaymentsService | … | `src/payments/payments.service.ts` |

## Depends on / used by

- Uses: …
- Used by: …

## See also

[Data](data.md) · [States](states.md) · [Flows](flows.md) · ADRs: [NNNN](../../adr/NNNN-title.md)
