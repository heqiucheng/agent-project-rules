# Testing Rules

## Hard Rules

- A feature is not complete until relevant tests pass or test gaps are explicitly documented.
- `Modified` means changed but not yet proven.
- `Verified` requires relevant validation evidence for the claimed scope.
- `Deliverable` requires verified behavior plus explicit disclosure of any residual risk or skipped gate.
- Cover normal, empty, invalid, unauthorized, duplicate, timeout, third-party failure, and rollback paths.
- Bugs should add regression tests when practical.
- AI features must test structured output validation and bad-output handling.
- API integrations need mocks/fakes and local smoke tests.
- If a test could not run, do not summarize the work as fully done.

## Minimum Test Types

```text
Unit tests
API tests
Integration tests with mocks/fakes
Regression tests for bug fixes
Build/type/lint checks
```

## Completion Note

Every completed task should state:

```text
Status
Tests run
Results
Tests not run and why
Evidence
Residual risk
```
