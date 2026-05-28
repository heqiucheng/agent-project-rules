# Performance Testing Rules

## When Required

Run or plan performance testing for:

- List queries and filtering.
- Detail pages with large child data.
- File upload and parsing.
- Batch AI generation.
- Vectorization and retrieval.
- Report aggregation.
- Third-party sync jobs.

## Required Metrics

```text
Data volume
Concurrency
P50/P95/P99 latency
Error rate
CPU/memory
Database slow queries
Queue backlog
External API latency
```

## Hard Rule

Performance claims must be backed by measurement or explicitly marked as assumptions.