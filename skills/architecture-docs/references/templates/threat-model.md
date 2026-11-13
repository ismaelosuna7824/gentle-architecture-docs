---
title: Threat model (STRIDE)
owner: TBD
sources:
  - TBD
verified: TBD
status: draft
---

# Threat model

Trust boundaries (from [containers](../architecture/c4-containers.md)) and, for each, STRIDE:

| Boundary | Threat (STRIDE) | Example | Mitigation in place (code) | Gap / action |
|---|---|---|---|---|
| Internet → API | Spoofing | Stolen token reused | Short-lived tokens, `auth.guard.ts` | … |
| API → DB | Tampering | … | … | … |

S Spoofing · T Tampering · R Repudiation · I Information disclosure · D Denial of service · E Elevation of privilege.
