---
title: System context (C4 level 1)
owner: TBD
sources:
  - TBD
verified: TBD
status: draft
---

# System context

One paragraph: what the system does and for whom.

```mermaid
flowchart LR
    user(["Customer<br/>Uses the web and mobile app"])
    admin(["Back-office operator"])
    system["<b>System name</b><br/>What it does"]
    bank["Bank / payment provider<br/>(external)"]
    mail["Email provider<br/>(external)"]
    user -->|"Pays, checks balance"| system
    admin -->|"Reviews disputes"| system
    system -->|"Charges cards (HTTPS, REST)"| bank
    system -->|"Sends receipts"| mail
```

| Actor or system | Role | Integration | Owner |
|---|---|---|---|
| Customer | … | Web, mobile | — |
| Bank | … | REST over mTLS, webhooks | TBD |

## Open questions

- …
