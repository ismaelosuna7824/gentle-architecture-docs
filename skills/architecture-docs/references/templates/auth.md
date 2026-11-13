---
title: Authentication and authorization
owner: TBD
sources:
  - src/auth/**
verified: TBD
status: draft
---

# Authentication and authorization

```mermaid
sequenceDiagram
    actor U as User
    participant App
    participant IdP as Identity provider
    participant API
    U->>App: sign in
    App->>IdP: authorization code + PKCE
    IdP-->>App: tokens
    App->>API: request + access token
    API->>API: verify signature, audience, expiry, role
```

## Roles × permissions

| Permission | admin | operator | customer |
|---|---|---|---|
| View own transactions | ✓ | ✓ | ✓ |
| Refund | ✓ | ✓ | — |

Where each check is enforced: `file:symbol`.

## Secrets

Where secrets live, who can read them, how they rotate.
