# Orchestration Rules

## Purpose

Reduce unnecessary user interruptions by giving the AI development team a default coordination mechanism.

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

## Role Coordination

The orchestrator should select only the roles needed for the task, not every role every time.

Examples:

```text
UI feature -> Product Manager + UX Architect + UI Designer + Frontend Engineer + QA + Code Reviewer
API integration -> Integration Engineer + Backend Architect + QA + Security + Code Reviewer
AI memory/RAG -> AI Agent Engineer + Database Engineer + Backend Architect + QA + Security
Bug fix -> Relevant Engineer + QA + Code Reviewer
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