---
title: Feature — states
owner: TBD
sources:
  - src/feature/**/status*
verified: TBD
status: draft
---

# States

## Entity name

```mermaid
stateDiagram-v2
    [*] --> pending
    pending --> authorized: provider approves
    pending --> failed: provider declines / timeout
    authorized --> captured: capture() within 7 days
    authorized --> voided: void()
    captured --> refunded: refund() [amount ≤ captured]
    failed --> [*]
    voided --> [*]
    refunded --> [*]
```

| From | To | Trigger | Guard | Code |
|---|---|---|---|---|
| pending | authorized | provider webhook `payment.approved` | — | `WebhookHandler.onApproved` |

## Findings

Transitions the code allows but should not (or should allow but does not), states never reached, terminal states that can still change.
