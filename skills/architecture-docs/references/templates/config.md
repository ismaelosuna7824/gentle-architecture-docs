---
title: Configuration
owner: TBD
sources:
  - .env.example
  - src/config/**
verified: TBD
status: draft
---

# Configuration

| Variable / flag | Default | Effect | Required in | Secret? | Read in |
|---|---|---|---|---|---|
| `DATABASE_URL` | — | Primary database | all | yes | `src/config/database.ts` |
