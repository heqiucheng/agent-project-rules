# Backend Engineering Rules

## Hard Rules

- Do not put route handling, request parsing, permissions, business logic, database queries, third-party calls, and AI prompt logic in one file.
- Use layered architecture: controller, service/usecase, domain, repository/store, integration/client, worker/job, dto/schema.
- Keep module boundaries explicit.
- Define consistent response, error, pagination, logging, and ID conventions.
- Add necessary comments for complex rules, permissions, idempotency, AI fallback, and performance decisions.
- Paginate list APIs.
- Avoid N+1 queries and unbounded scans.
- Prefer async jobs for slow tasks: uploads, sync, AI generation, vectorization, report aggregation.

## Review Blockers

- Missing permission checks.
- Mixed responsibilities in one large file.
- Inconsistent response or error format.
- Missing tests for core paths.
- Sensitive data in logs.
- Missing structured validation for AI output.