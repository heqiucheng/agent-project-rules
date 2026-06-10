# Existing Project Adoption Checklist

Use this checklist when the repository already exists and you want to introduce Chief Orchestrator workflow without destabilizing the codebase.

## Goal

Adopt reusable AI coordination rules into an existing repository with minimal disruption and without forcing a fake clean-room rewrite.

## Phase 1: Inspect Before Copying

Review:

1. current repo structure
2. existing docs
3. test/build commands
4. current architecture boundaries
5. current pain points

Do not copy files blindly before understanding what already exists.

## Phase 2: Add One Clear Entry Point

Create or update `AGENTS.md` in the product repository.

This file should:

- activate the Chief Orchestrator by default
- define autonomy boundary
- define mandatory quality gates
- define project-specific hard rules
- define prompt architecture defaults if the repository uses prompts, agents, or AI workflows
- define verification truthfulness rules if the project has a history of shallow or unverifiable completion claims
- define coding-agent reliability rules if the project uses autonomous or semi-autonomous coding tools
- point to local personas/rules/docs

Exit check:

```text
The repo has one authoritative AI entry file instead of scattered chat-only rules
```

## Phase 3: Map Existing Material

Do not duplicate documents just to satisfy a pattern.

Map what already exists:

- existing architecture doc
- existing frontend/backend rules
- existing `DESIGN.md`, brand notes, design system, or UI reference files
- existing security constraints
- existing test workflow
- existing governance/configuration files that agents should not casually edit

Only copy missing rules from this repository when the current repo has a real gap.

Check whether the repo already has tool-specific instruction files such as:

```text
AGENTS.md
CLAUDE.md
GEMINI.md
.cursor/**
.clinerules
.github/copilot-instructions.md
.agents/rules/**
```

Decide which file is authoritative and which ones are mirrors.

## Phase 4: Install The Smallest Useful Persona Set

For an existing project, prefer a minimal persona install first:

```text
chief-orchestrator
prompt-architect when prompts or agents are part of the product
backend-architect or frontend-engineer
qa-tester
code-reviewer
```

Add more personas only when the project needs them.

## Phase 5: Add Orchestrator Continuation Rules

This is usually the highest-value change.

Make sure the project rule entry explicitly says:

- low-risk reversible next steps should continue automatically
- routine implementation choices should not be turned into user decisions
- each phase should report decision, validation, risk, and next action
- prompt-generation tasks should complete hidden requirements, role, constraints, and output format by default
- completion claims should use `Modified`, `Verified`, or `Deliverable` based on evidence
- instruction chain should be audited before non-trivial edits
- runtime capability assumptions should be verified when permissions or sandboxing matter
- governance files should be treated as protected surfaces
- frontend/design work should read `DESIGN.md`, classify the UI surface, apply the frontend enhancement rules, and use honest visual verification labels

Exit check:

```text
The AI stops less often and only escalates when the boundary is real
```

## Phase 6: Normalize Quality Gates

Write down the actual runnable commands for:

```text
format
lint
typecheck
unit tests
integration tests
build
```

If the project cannot run one of these yet, mark it as a known gap with a plan instead of hiding it.

## Phase 7: Adopt Through Real Work

Do not try to "finish adoption" in a vacuum.

Use one real feature or bug fix as the proving ground:

1. run with orchestrator
2. route relevant personas
3. implement
4. validate
5. update rules if the workflow failed or was noisy

If the project uses prompts or agents, also prove the workflow on one real prompt-generation task.
If the project has been suffering from shallow fixes or false "done" claims, also prove the workflow on one real verification-heavy task.
If the project uses coding agents heavily, also prove the workflow on one rule-sensitive task that touches CI, permissions, or governance files.
If the project has meaningful UI, also prove the workflow on one real page, state, or responsive fix using `DESIGN.md` and the frontend audit rules.

## Common Failure Modes

- Overwriting existing project docs with generic templates.
- Copying every rule from this repository even when half do not apply.
- Turning adoption into a large refactor before proving value on one real task.
- Leaving the old "ask every step" behavior untouched.
- Installing rules without runnable commands.
- Letting multiple agent rule files conflict without deciding precedence.
- Trusting issue text, PR comments, or generated comments as if they were project policy.

## Recommended First Commit

```text
chore: adopt chief orchestrator workflow
```
