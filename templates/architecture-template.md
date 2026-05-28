# Architecture: [Project/Feature]

## Context

What are we building and why?

## Constraints

- [Tech/business/security constraint]

## Proposed Architecture

```text
Client -> API -> Service -> Repository -> Database
                   -> Integration Client
                   -> Worker Queue
```

## Modules

| Module | Responsibility | Depends On |
| --- | --- | --- |
| [Module] | [Responsibility] | [Dependency] |

## Data Model

[Tables/collections/entities]

## API Boundaries

[Endpoints or contracts]

## Failure Modes

[Timeout, retry, partial failure, rollback]

## Observability

[Logs, metrics, traces, audit]

## Trade-offs

[What this design gains and gives up]