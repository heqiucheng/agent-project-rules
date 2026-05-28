# Git Workflow Rules

## Hard Rules

- Commit related changes together with clear messages.
- Do not mix unrelated refactors with feature work.
- Do not commit secrets or environment files.
- Run quality gates before pushing when practical.
- Document any gate that could not run.
- Keep generated or bulky artifacts out unless they are required.

## Suggested Commit Prefixes

```text
feat:
fix:
docs:
style:
refactor:
test:
chore:
ci:
perf:
security:
```