# Project Bootstrap Checklist

Use this checklist when starting a new product repository from zero.

## Goal

Turn a blank repository into a project that an AI coding agent can enter and run with a Chief Orchestrator by default, without re-explaining the same rules every time.

## Phase 1: Create The Rule Entry

1. Copy `AGENTS.template.md` into the new repository as `AGENTS.md`.
2. Fill in project name, product direction, tech stack, required commands, domain-specific hard rules, and prompt architecture expectations.
3. Keep the Chief Orchestrator enabled by default unless the project truly needs a different control model.
4. Keep prompt architecture enabled by default if the project will generate prompts, agent instructions, research requests, AI workflows, or reusable output templates.
5. Add the coding-agent reliability rules when the project will use autonomous or semi-autonomous coding tools.
6. Add the Karpathy coding behavior layer when the project will use agents for implementation, review, debugging, or refactoring.
7. Add the frontend/design enhancement layer when the project has pages, dashboards, commercial surfaces, learning flows, editors, games, or meaningful UI.

Exit check:

```text
The repo has one clear AI rule entry file: AGENTS.md
```

## Phase 2: Create The Minimum Docs Spine

Create these folders and starter files before feature work starts:

```text
docs/agents/
docs/specs/
docs/architecture/
docs/design/
docs/testing/
.agents/rules/
DESIGN.md
```

Copy only the personas and rules the project actually needs. Start lean, but include the orchestration entry first.

Recommended baseline:

```text
docs/agents/chief-orchestrator.md
docs/agents/product-manager.md
docs/agents/prompt-architect.md
docs/agents/frontend-engineer.md
docs/agents/backend-architect.md
docs/agents/qa-tester.md
docs/agents/code-reviewer.md
```

Recommended baseline rules:

```text
docs/rules/orchestration-rules.md
docs/rules/backend-engineering-rules.md
docs/rules/frontend-style-rules.md
docs/rules/frontend-taste-rules.md
docs/rules/frontend-audit-rules.md
docs/rules/design-md-rules.md
docs/rules/testing-rules.md
docs/rules/documentation-rules.md
docs/rules/git-workflow-rules.md
docs/rules/karpathy-coding-rules.md
docs/rules/prompt-architecture-rules.md
docs/rules/verification-truthfulness-rules.md
docs/rules/agent-reliability-rules.md
docs/rules/instruction-chain-rules.md
docs/rules/untrusted-input-rules.md
```

Exit check:

```text
The repo has a stable docs structure before code sprawl starts
```

## Phase 3: Define The First Product Boundaries

Before implementation, create the first version of:

1. PRD
2. architecture note
3. `DESIGN.md` or frontend brief if meaningful UI is involved
4. API contract if frontend/backend or integration is involved
5. test plan if the workflow has shared or risky behavior

Use the templates in `templates/` as the starting point.

Exit check:

```text
The AI can answer: what are we building, what is out of scope, how will we validate it
```

## Phase 4: Enable The Orchestrator Workflow

The Chief Orchestrator should now run this default loop:

```text
understand goal
classify task type
route personas
inspect local context
choose reversible validated path
implement
test
review
document
continue if next step is still low-risk
```

Use `rules/orchestration-rules.md` plus the status and implementation templates in this repo.

If the project uses coding agents, also install:

```text
rules/agent-reliability-rules.md
rules/karpathy-coding-rules.md
rules/instruction-chain-rules.md
rules/untrusted-input-rules.md
templates/work-log-template.md
```

Exit check:

```text
The AI no longer stops after every small step to ask for routine confirmation
```

## Phase 5: Install Quality Gates Early

Define the actual commands for:

```text
format
lint
typecheck
unit tests
integration tests
build
```

Write them into `AGENTS.md` and optionally the project README.

If a gate cannot run yet, write the current gap explicitly instead of pretending the gate exists.

Add one startup audit note for:

```text
instruction chain
runtime capability state
scope lock / diff budget
```

Exit check:

```text
Every meaningful implementation phase has a validation path
```

## Phase 6: Add Domain Hard Rules

This is where the generic starter becomes a real project rule system.

Examples:

- regulated data handling
- destructive migration approval rules
- UI design constraints
- AI output safety boundaries
- prompt structure and output contract rules
- verification truthfulness and anti-fake-completion rules
- instruction chain and directory-scoped rule rules
- untrusted-input and prompt-injection handling rules
- governance file protection and scope-lock rules
- mandatory audit trail rules
- external API verification requirements

Exit check:

```text
Project-specific risk is documented in rules, not repeated ad hoc in chat
```

## Phase 7: First Working Loop

Before scale-up, make sure the repository can complete one real vertical slice:

```text
spec
implementation
verification
commit
push
rule update
```

Do not expand the system until one slice can complete cleanly.

## Common Failure Modes

- Copying every persona and rule even when the repo is small.
- Starting implementation before AGENTS.md and docs spine exist.
- Treating the orchestrator as a passive advisor instead of the default execution controller.
- Writing quality gates as aspirations without runnable commands.
- Leaving domain-specific constraints only in chat history.
- Assuming a coding agent will follow rules that were never audited at startup.
- Letting `.agents/rules/` and `AGENTS.md` drift apart.

## Recommended First Commit

```text
chore: bootstrap ai project rules
```
