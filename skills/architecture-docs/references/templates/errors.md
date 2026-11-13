---
title: Error catalog
owner: TBD
sources:
  - src/**/errors*
verified: TBD
status: draft
---

# Error catalog

| Code | HTTP | Cause | What the user sees | Retryable | Raised in |
|---|---|---|---|---|---|
| `PAYMENT_DECLINED` | 402 | Provider declined | "Your bank declined…" | no | `PaymentsService.authorize` |
