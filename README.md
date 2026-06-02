# Agent Project Rules

Reusable rules, personas, and engineering workflows for AI-assisted software projects.

面向 AI 协作开发的项目规则、人设和工程工作流模板。目标是让 AI 不是随手写代码，而是在明确角色、统一风格、测试约束、评审门禁和持续反馈下工作。

This repository is intended to act as a reusable Chief Orchestrator starter pack for new product repositories.

## What This Repo Provides

- `AGENTS.template.md`: reusable project-level AI collaboration rules.
- `personas/`: reusable AI team personas, including a Chief Orchestrator plus product, design, frontend, backend, AI, integration, database, testing, security, DevOps, documentation, and review roles.
- `rules/`: hard engineering rules for orchestration, UI, backend, API integration, testing, performance, security, Git workflow, and AI workflow harness.
- `playbooks/`: project adoption and orchestration execution checklists.
- `templates/`: PRD, architecture, API contract, UI design system, and test plan templates.
- `examples/`: examples showing how a product repository can adopt these rules.

## Core Idea

```text
Chief Orchestrator coordinates roles within clear autonomy boundaries
Clear rules first
Then design
Then implement
Then test
Then review
Then improve the rules
```

AI should not blindly write features and patch bugs afterward. For external APIs, databases, model calls, and complex integrations, the workflow must validate the real contract or a local mock first, then implement against that verified result.

## Use This Repo As A Starter Pack

If you are creating a new project from zero:

1. Copy `AGENTS.template.md` into the new repo as `AGENTS.md`.
2. Follow [project-bootstrap-checklist.md](/d:/项目git/agent-project-rules/playbooks/project-bootstrap-checklist.md).
3. Copy only the personas, rules, and templates the project actually needs.
4. Make the Chief Orchestrator the default execution controller from day one.

If you are adopting these rules into an existing repository:

1. Inspect what the repo already has.
2. Add one authoritative `AGENTS.md`.
3. Follow [existing-project-adoption-checklist.md](/d:/项目git/agent-project-rules/playbooks/existing-project-adoption-checklist.md).
4. Prove the workflow on one real feature or bug fix before broad expansion.

## Recommended Project Adoption

Copy `AGENTS.template.md` into your project as `AGENTS.md`, then customize:

```text
Project name
Product direction
Domain-specific constraints
Tech stack
Required commands
Deployment rules
```

Copy the personas and rules you need into your project docs, or reference this repo directly.

Recommended orchestration support files:

```text
playbooks/project-bootstrap-checklist.md
playbooks/existing-project-adoption-checklist.md
templates/status-update-template.md
templates/implementation-phase-template.md
```

## Hard Principles

- No one-file spaghetti implementation.
- No page-level random styling.
- No blind API integration.
- No feature is complete without tests or an explicit test gap.
- No production-sensitive action without permissions, audit logs, and rollback thinking.
- No AI output should be trusted without structure, validation, and feedback loops.
- Every major technical step should explain the technology used, the trade-off, the risk, and the validation method.
- No routine low-risk step should be converted into unnecessary user confirmation.

## Suggested Structure In Product Repos

```text
AGENTS.md
docs/agents/
docs/rules/
docs/specs/
docs/design/
docs/architecture/
docs/testing/
```

## Best First Install

For most new software projects, start with this minimal set:

```text
AGENTS.md
personas/chief-orchestrator.md
personas/product-manager.md
personas/frontend-engineer.md
personas/backend-architect.md
personas/qa-tester.md
personas/code-reviewer.md
rules/orchestration-rules.md
rules/backend-engineering-rules.md
rules/frontend-style-rules.md
rules/testing-rules.md
rules/documentation-rules.md
rules/git-workflow-rules.md
playbooks/project-bootstrap-checklist.md
templates/status-update-template.md
templates/implementation-phase-template.md
```

## License

MIT
