# API Integration Rules

## Principle

Do not build blindly against unknown APIs. First verify the contract, then implement the feature.

## Required Workflow

```text
1. Read official docs or existing contract.
2. Identify auth, endpoint, method, params, response, errors, rate limits.
3. Create a minimal local smoke test or mock.
4. Capture a sanitized real or expected response sample.
5. Define typed request/response schema.
6. Implement client wrapper.
7. Write integration tests against mock/fake client.
8. Only then build product behavior on top.
```

## Hard Rules

- Third-party API calls must be wrapped in an integration client.
- Domain logic must not depend directly on SDK objects.
- Timeouts, retries, rate limits, auth errors, schema changes, and partial failures must be handled.
- API credentials must never be logged or committed.
- Local verification must pass before dependent feature code is considered complete.

## Required Artifacts

```text
Verified contract notes
Local smoke test or mock
Sanitized request/response examples
Error mapping
Retry/rate-limit strategy
Integration tests
```