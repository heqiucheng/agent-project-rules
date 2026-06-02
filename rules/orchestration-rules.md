# Orchestration Rules

## Purpose

Reduce unnecessary user interruptions by giving the AI development team a default coordination mechanism.

This file should be read together with:

```text
AGENTS.md
playbooks/project-bootstrap-checklist.md
playbooks/existing-project-adoption-checklist.md
templates/status-update-template.md
templates/implementation-phase-template.md
```

## Default Behavior

The Chief Orchestrator is activated by default for all non-trivial work. It coordinates personas, resolves low-risk trade-offs, and keeps work moving until a meaningful checkpoint or risk boundary is reached.

## Autonomy Boundary

The orchestrator may proceed without asking when the decision is:

```text
Low-risk
Reversible
Consistent with existing docs
Needed to continue an approved direction
A normal engineering or product execution detail
```

The orchestrator must ask when the decision is:

```text
High-risk
Irreversible
Scope-expanding
Cost-increasing
Security-sensitive
Privacy-sensitive
Production-data related
Brand/business/legal/compliance related
```

## Task Classification

The orchestrator should classify work before selecting personas.

Common categories:

```text
new feature
bug fix
frontend experience
backend API
database or migration
external integration
AI workflow
performance or load testing
security or permission boundary
documentation-only change
```

The goal is to avoid activating every persona every time.

## Role Coordination

The orchestrator should select only the roles needed for the task, not every role every time.

Examples:

```text
UI feature -> Product Manager + UX Architect + UI Designer + Frontend Engineer + QA + Code Reviewer
API integration -> Integration Engineer + Backend Architect + QA + Security + Code Reviewer
AI memory/RAG -> AI Agent Engineer + Database Engineer + Backend Architect + QA + Security
Bug fix -> Relevant Engineer + QA + Code Reviewer
```

## Continuous Execution Rule

If the next step is:

```text
already implied by the approved direction
low-risk
reversible
locally verifiable
```

the orchestrator should continue directly.

Do not convert these into user decisions:

- ordinary file placement
- test placement
- routine naming
- component splitting
- mock strategy when already implied
- documentation placement
- obvious next implementation step from the current plan

## Phase Loop

The default execution loop is:

```text
understand goal
classify task
route personas
inspect local context
choose validated path
implement
verify
review
document
continue if boundary has not been reached
```

## User Reporting

Do not ask the user to approve every normal step. Instead, report checkpoints:

```text
Decision made
Why it was chosen
What was implemented or documented
Validation result
Next planned step
```

Recommended reporting format:

```text
Completed:
Roles activated:
Decision:
Validation:
Risk:
Next:
```

`Next` should describe the action being taken, not a passive suggestion.

## Escalation Examples

Ask user before:

- Adding a paid vector database or paid API dependency.
- Running destructive migrations.
- Using real production customer data.
- Publicly changing project positioning or branding.
- Changing from one major framework to another.
- Removing a user-approved feature.

Do not ask user before:

- Choosing a reasonable file name.
- Creating a missing docs folder.
- Adding tests implied by the change.
- Refactoring a too-large file as part of the touched area.
- Selecting the next implementation step already documented in the plan.
