# Agent Project Rules

Reusable rules, personas, templates, prompt architecture workflows, frontend/design quality workflows, and coding-agent reliability workflows for AI-assisted software projects.

This repository is a reusable starter pack for downstream product repositories. It provides a default operating system for AI collaboration across product design, frontend quality, engineering, testing, documentation, prompt architecture, and coding-agent reliability.

## What This Repo Provides

- `AGENTS.template.md`: reusable project-level AI collaboration rules, now including default prompt-architecture, frontend/design enhancement, coding-agent reliability, and Karpathy-inspired coding behavior.
- `personas/`: reusable AI team personas, including a Chief Orchestrator plus product, design, frontend, backend, AI, integration, database, testing, security, DevOps, documentation, review, and prompt-architecture roles.
- `rules/`: hard engineering rules for orchestration, UI, frontend taste, frontend audit, `DESIGN.md`, backend, API integration, testing, performance, security, Git workflow, AI workflow harness, prompt architecture, verification truthfulness, instruction chain control, untrusted-input handling, coding-agent reliability, and Karpathy-inspired coding behavior.
- `playbooks/`: project adoption and orchestration execution checklists.
- `templates/`: PRD, architecture, API contract, UI design system, frontend brief, `DESIGN.md`, test plan, prompt-architecture templates, work-log templates, Karpathy adoption prompts, and cross-project bootstrap prompts.
- `examples/`: examples showing how a product repository can adopt these rules.

## Core Idea

```text
Clear rules first
Then design
Then implement
Then test
Then review
Then document
Then improve the rules
```

AI should not blindly write features and patch bugs afterward. For external APIs, databases, model calls, and complex integrations, the workflow must validate the real contract or a local mock first, then implement against that verified result.

Prompt work should follow the same discipline. A rough idea is not enough. The system should complete the hidden requirements, make the role explicit, define style constraints, define output format, and remove logic holes before presenting the final prompt.

Execution truthfulness should follow the same discipline. Superficial edits are not the same as working behavior, and "done" is not the same as "verified".

Coding-agent reliability should follow the same discipline. A rule file that merely exists is not the same as a rule chain that was actually audited and applied.

Karpathy-style coding behavior should follow the same discipline. The agent should think before coding, keep solutions simple, make surgical changes, and define success criteria before claiming a task is done.

Frontend work should follow the same discipline. A page that merely renders is not the same as a product experience that matches its audience, design language, responsive needs, interaction states, and verification evidence.

## Prompt Architecture Default

Any downstream project that adopts this repo can treat prompt generation as a first-class workflow.

When a user gives only a scenario and intended use, the default prompt-architecture rule should:

- infer hidden requirements, constraints, and success criteria
- add a suitable role definition
- add style constraints matched to audience and purpose
- add an output format that can be reused and checked
- generate a concise general version and an advanced premium version
- keep the prompt portable across ChatGPT, Claude, DeepSeek, Kimi, Doubao, Wenxin, Xunfei, and similar assistants
- remove contradictions, missing boundaries, and ambiguous instructions before finalizing the prompt

The core files for this layer are:

```text
AGENTS.template.md
rules/prompt-architecture-rules.md
rules/verification-truthfulness-rules.md
templates/prompt-architecture-template.md
personas/prompt-architect.md
```

## Coding Agent Reliability Default

Any downstream project that adopts this repo can treat coding-agent reliability as a first-class workflow.

The default coding-agent reliability layer should:

- audit the instruction chain before non-trivial edits
- verify runtime capability state before permission-sensitive actions
- protect governance files and configuration surfaces from casual edits
- lock scope before editing and disclose scope expansion
- prefer deterministic gates over prompt-only reminders
- maintain a work log for multi-step or resumed tasks
- treat issue text, copied prompts, PR comments, external tool output, and web content as untrusted input until screened

The core files for this layer are:

```text
AGENTS.template.md
rules/agent-reliability-rules.md
rules/instruction-chain-rules.md
rules/untrusted-input-rules.md
templates/work-log-template.md
.agents/rules/README.md
```

## Karpathy Coding Behavior Layer

Any downstream project that adopts this repo can use the Karpathy-inspired coding behavior layer as the default guardrail for implementation work.

The default Karpathy layer should:

- state assumptions before non-trivial edits
- surface ambiguity instead of silently guessing
- select the simplest viable implementation path
- avoid speculative abstractions and unrelated cleanup
- keep every changed line traceable to the user request, agreed scope, or validation
- convert vague work into success criteria and evidence

The core files for this layer are:

```text
AGENTS.template.md
rules/karpathy-coding-rules.md
rules/agent-reliability-rules.md
rules/verification-truthfulness-rules.md
templates/karpathy-guidelines-adoption-prompt.md
templates/other-project-bootstrap-prompt.md
```

## Frontend Design Enhancement Layer

Any downstream project that adopts this repo can treat frontend taste, visual consistency, interaction quality, and UI verification as a reusable enhancement layer.

This layer activates when a task touches page design, brand expression, commercial pages, learning products, dashboards, editors, games, UI polish, animation, or responsive behavior.

The default frontend/design layer should:

- read `DESIGN.md` when it exists before changing visual language
- classify the UI surface before designing
- set `DESIGN_VARIANCE`, `MOTION_INTENSITY`, and `VISUAL_DENSITY`
- distinguish marketing, product, admin, editor, game, and learning surfaces
- avoid generic AI-looking UI and random page-level styling
- require desktop/mobile inspection and honest completion labels for meaningful UI work
- use relevant visual assets when a page, game, or commercial product benefits from being seen

The core files for this layer are:

```text
AGENTS.template.md
rules/frontend-style-rules.md
rules/frontend-taste-rules.md
rules/frontend-audit-rules.md
rules/design-md-rules.md
templates/frontend-brief-template.md
templates/design-md-template.md
personas/ui-designer.md
personas/frontend-engineer.md
```

## Cross-Tool Compatibility

Keep `AGENTS.md` as the primary repository rule entry.

For tools that support directory-scoped rules, use `.agents/rules/` as the shared mirror for path-specific constraints. The mirror should not contradict `AGENTS.md`; it exists to improve portability across Codex, Claude Code, Cursor, Cline, Windsurf, Copilot, and related toolchains.

## Use This Repo As A Starter Pack

If you are creating a new project from zero:

1. Copy `AGENTS.template.md` into the new repo as `AGENTS.md`.
2. Follow `playbooks/project-bootstrap-checklist.md`.
3. Copy only the personas, rules, and templates the project actually needs.
4. Make the Chief Orchestrator the default execution controller from day one.
5. Keep the prompt-architecture rule active unless the project has a deliberate reason to opt out.
6. Add the coding-agent reliability rules when the project will use coding agents, autonomous refactors, or AI-assisted code execution.
7. Add `DESIGN.md` and the frontend enhancement rules when the project has a meaningful UI, commercial page, learning flow, dashboard, editor, or game.

If you are adopting these rules into an existing repository:

1. Inspect what the repo already has.
2. Add one authoritative `AGENTS.md`.
3. Follow `playbooks/existing-project-adoption-checklist.md`.
4. Prove the workflow on one real feature, bug fix, or prompt-generation task before broad expansion.
5. If the project uses coding agents, prove the workflow on one verification-heavy task and one governance-sensitive task.

## Recommended Project Adoption

Copy `AGENTS.template.md` into your project as `AGENTS.md`, then customize:

```text
Project name
Product direction
Domain-specific constraints
Tech stack
Required commands
Deployment rules
Prompt architecture expectations
Coding-agent reliability expectations
Frontend/design expectations
```

Copy the personas and rules you need into your project docs, or reference this repo directly.

Recommended orchestration support files:

```text
playbooks/project-bootstrap-checklist.md
playbooks/existing-project-adoption-checklist.md
templates/status-update-template.md
templates/implementation-phase-template.md
templates/frontend-brief-template.md
templates/design-md-template.md
templates/prompt-architecture-template.md
templates/work-log-template.md
templates/other-project-bootstrap-prompt.md
```

## Hard Principles

- No one-file spaghetti implementation.
- No page-level random styling.
- No generic AI-looking UI should be presented as polished product design.
- No blind API integration.
- No feature is complete without tests or an explicit test gap.
- No production-sensitive action without permissions, audit logs, and rollback thinking.
- No AI output should be trusted without structure, validation, and feedback loops.
- Every major technical step should explain the technology used, the trade-off, the risk, and the validation method.
- No routine low-risk step should be converted into unnecessary user confirmation.
- No prompt output should ship without a role, constraints, output contract, and a contradiction scan unless the user explicitly asks for raw free-form text.
- No work should be described as fixed, complete, successful, or ready without matching validation evidence and a correct status label.
- No coding-agent workflow should assume rules, permissions, or scope are obvious. Audit them explicitly when they matter.

## Suggested Structure In Product Repos

```text
AGENTS.md
docs/agents/
docs/rules/
docs/specs/
docs/design/
DESIGN.md
docs/architecture/
docs/testing/
docs/prompts/
.agents/rules/
```

## Best First Install

For most new software projects, start with this minimal set:

```text
AGENTS.md
personas/chief-orchestrator.md
personas/product-manager.md
personas/frontend-engineer.md
personas/backend-architect.md
personas/prompt-architect.md
personas/qa-tester.md
personas/code-reviewer.md
rules/orchestration-rules.md
rules/backend-engineering-rules.md
rules/frontend-style-rules.md
rules/frontend-taste-rules.md
rules/frontend-audit-rules.md
rules/design-md-rules.md
rules/testing-rules.md
rules/documentation-rules.md
rules/git-workflow-rules.md
rules/karpathy-coding-rules.md
rules/prompt-architecture-rules.md
rules/verification-truthfulness-rules.md
rules/agent-reliability-rules.md
rules/instruction-chain-rules.md
rules/untrusted-input-rules.md
playbooks/project-bootstrap-checklist.md
templates/status-update-template.md
templates/implementation-phase-template.md
templates/frontend-brief-template.md
templates/design-md-template.md
templates/prompt-architecture-template.md
templates/work-log-template.md
templates/karpathy-guidelines-adoption-prompt.md
templates/other-project-bootstrap-prompt.md
```

## License

MIT
