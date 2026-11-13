# Documentation structure

System-wide documents live by type; anything that belongs to one feature lives in `docs/features/<feature>/`. A decision usually crosses features, so ADRs are global and say which features they affect.

```text
docs/
├── README.md                    # the map: what this is, run it locally, where everything is
├── glossary.md                  # domain terms and their exact meaning
├── architecture/
│   ├── c4-context.md            # C4 level 1: the system, its users and external systems
│   ├── c4-containers.md         # C4 level 2: deployables (apps, APIs, workers, DBs, queues)
│   ├── deployment.md            # where each container runs, environments, CI/CD flow
│   └── nfr.md                   # SLOs, performance, scale limits, retention, backups
├── adr/
│   └── NNNN-title.md            # one decision each, numbered globally
├── security/
│   ├── auth.md                  # authentication flow, roles × permissions matrix
│   ├── data-classification.md   # sensitive data: what, where it lives, who can read it
│   └── threat-model.md          # STRIDE per trust boundary
├── operations/
│   ├── local-setup.md           # running it locally in under 15 minutes
│   ├── deploy-and-rollback.md
│   ├── config.md                # env vars and feature flags: default, effect, who changes it
│   ├── errors.md                # error catalog: code, cause, what the user sees, retryable?
│   └── runbooks/<incident>.md   # "X is down": symptoms, checks, fixes, escalation
├── api/                         # generated contracts (OpenAPI, AsyncAPI); never hand-edited
└── features/<feature>/
    ├── README.md                # purpose, C4 level 3 (components), dependencies
    ├── data.md                  # ERD + data dictionary for its entities
    ├── states.md                # lifecycle diagrams for entities with a status
    └── flows.md                 # sequence diagrams of critical flows, failures included
```

## Who reads what

| Reader | Starts at |
|---|---|
| Business, product | `c4-context.md`, `glossary.md`, feature READMEs |
| New developer | `docs/README.md` → `local-setup.md` → `c4-containers.md` → their feature |
| Feature team | `features/<feature>/` and the ADRs that list it |
| On-call | `operations/runbooks/`, `deploy-and-rollback.md`, `errors.md` |
| Security review | `security/`, `data-classification.md`, `auth.md` |

## What a feature is

A business capability with its own code area (usually a top-level module, package or bounded context): `payments`, `subscriptions`, `ledger`. Not a technical layer (`controllers`, `utils`). If the code is organized by layer, group by the domain words its routes, entities and services share, and say so in `docs/README.md`.

## Small projects

Skip what has no content rather than leaving empty files: a single-deployable app needs no `c4-containers.md` beyond one paragraph in `c4-context.md`; a project without an API has no `api/`. `docs/README.md` lists what exists.
