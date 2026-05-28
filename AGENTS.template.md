# Project AGENTS.md Template

This file is the project-level rule blueprint for AI-assisted development. Customize it for each product repository.

## Project Context

**Project name**: [PROJECT_NAME]

**Product direction**: [WHAT_THIS_PROJECT_BUILDS]

**Core workflow**:

```text
Understand goal -> Confirm constraints -> Design -> Implement -> Test -> Review -> Document -> Improve rules
```

## Role Activation

For new features, activate roles in this order when relevant:

1. Product Manager: define user, value, scope, non-goals, and acceptance criteria.
2. Domain Expert: validate domain logic and real-world workflow.
3. UX Architect: define flow, information architecture, and low-friction path.
4. UI Designer: define visual system, components, states, and accessibility.
5. Backend Architect: define API, data model, permissions, integrations, audit logs.
6. AI Agent Engineer: define model calls, structured output, memory, RAG, validation, feedback.
7. Frontend Engineer: implement UI using the design system only.
8. Integration Engineer: verify external APIs locally before feature implementation.
9. Database Engineer: validate schema, indexes, migrations, and query performance.
10. QA Tester: define and run functional, integration, regression, and edge-case tests.
11. Performance Tester: define pressure tests for critical paths.
12. Security Engineer: review auth, permissions, secrets, logs, data isolation, and abuse paths.
13. DevOps Engineer: enforce lint, test, build, CI, deploy, rollback.
14. Code Reviewer: block risky, inconsistent, untested, or spaghetti-code changes.
15. Technical Writer: keep docs and rules current.

## Hard Rules

- Do not blindly implement against unknown external APIs. Verify the API contract or local mock first.
- Do not put route handling, business logic, database queries, third-party calls, and AI prompt logic in one file.
- Do not write page-level random styles. Use the shared design system.
- Do not create features without acceptance criteria.
- Do not call work complete without tests, or an explicit reason why tests could not be run.
- Do not hide uncertainty. State assumptions and validation gaps.
- Do not commit secrets, tokens, credentials, raw private data, or sensitive logs.
- Explain major technical steps: what was done, what technologies were used, why, risks, and validation.

## Required Quality Gates

Before finalizing a change, run the project-appropriate gates:

```text
format
lint
typecheck
unit tests
integration tests
build
security-sensitive review
```

If a gate cannot run, document why and what remains risky.

## Continuous Rule Improvement

When a bug, style inconsistency, integration failure, or repeated correction happens, update this file or the relevant rule document so the same class of issue is less likely to happen again.