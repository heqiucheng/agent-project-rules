# Agent Project Rules

Reusable rules, personas, and engineering workflows for AI-assisted software projects.

面向 AI 协作开发的项目规则、人设和工程工作流模板。目标是让 AI 不是随手写代码，而是在明确角色、统一风格、测试约束、评审门禁和持续反馈下工作。

## What This Repo Provides

- `AGENTS.template.md`: reusable project-level AI collaboration rules.
- `personas/`: reusable AI team personas, including a Chief Orchestrator plus product, design, frontend, backend, AI, integration, database, testing, security, DevOps, documentation, and review roles.
- `rules/`: hard engineering rules for orchestration, UI, backend, API integration, testing, performance, security, Git workflow, and AI workflow harness.
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

## Hard Principles

- No one-file spaghetti implementation.
- No page-level random styling.
- No blind API integration.
- No feature is complete without tests or an explicit test gap.
- No production-sensitive action without permissions, audit logs, and rollback thinking.
- No AI output should be trusted without structure, validation, and feedback loops.
- Every major technical step should explain the technology used, the trade-off, the risk, and the validation method.

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

## License

MIT