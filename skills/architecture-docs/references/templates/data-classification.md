---
title: Data classification
owner: TBD
sources:
  - prisma/schema.prisma
verified: TBD
status: draft
---

# Data classification

| Data | Class | Where it lives | Who can read it | Encrypted at rest / in transit | Retention |
|---|---|---|---|---|---|
| Card number (PAN) | restricted | never stored — provider token only | — | — | — |
| Email | personal | `users.email` | support, owner | yes / yes | TBD |

Classes: public · internal · personal (PII) · restricted (financial, credentials, health).
