# Prompt Architecture Rules

## Purpose

Make prompt generation a default, reusable discipline across downstream repositories. Prompt work should be structured with the same rigor used for product, engineering, and testing work.

## Default Operating Mode

When the user provides only a scenario, task, or intended use, the AI should not wait for a perfectly specified request. It should complete the prompt with the missing pieces required for a reliable answer, while keeping assumptions reasonable and visible only when they matter.

Preserve the user's language by default.

## Hidden Requirement Completion

The system should infer or define the following when they are missing:

- target audience or user level
- desired outcome and success criteria
- scope boundaries and non-goals
- tone and delivery style
- output format and level of detail
- practical constraints such as time, channel, platform, or context window sensitivity
- common failure cases, contradictions, and ambiguity

Ask follow-up questions only when the missing information materially changes safety, legality, cost, or the outcome quality.

## Role, Style, And Output Injection

Every reusable prompt should explicitly define:

- a role suited to the task
- the core objective
- the operating constraints
- the style or tone requirements
- the expected output format

If the user does not specify these, the system should add them automatically.

## Dual-Version Standard

Unless the user explicitly asks for one version only, every prompt-generation response should include:

1. `Concise General Version`
2. `Advanced Premium Version`

The concise general version should:

- be short, reusable, and broadly portable
- contain only the essential role, task, constraints, and output contract

The advanced premium version should:

- add deeper structure, stronger guardrails, and better failure handling
- include workflow guidance, quality bar, and clearer evaluation expectations
- be stronger than the concise version, not merely longer

## Cross-Model Compatibility

Prompts should be written to work well across ChatGPT, Claude, DeepSeek, Kimi, Doubao, Wenxin, Xunfei, and similar assistants.

Compatibility rules:

- prefer plain language and explicit section headers
- avoid vendor-specific syntax unless requested
- separate must-have instructions from optional preferences
- use deterministic output schemas when consistency matters
- tell the model what to do when information is incomplete
- avoid requesting hidden chain-of-thought; request concise reasoning or decision criteria instead

## Logic-Gap Prevention

Before finalizing a prompt, scan for:

- conflicting instructions
- undefined audience
- vague success criteria
- missing output format
- unconstrained scope
- role-task mismatch
- missing failure boundaries
- hidden assumptions that should be explicit

If a gap is found, fix it before returning the prompt.

## Escalation Boundary

Do not ask clarifying questions for ordinary low-risk omissions.

Ask the user before assuming details that affect:

- legal or safety exposure
- pricing, payment, or budget commitments
- public branding or market claims
- medical, financial, or compliance-sensitive outcomes
- irreversible architecture or workflow lock-in

## Default Output Contract

For prompt-generation tasks, the preferred response shape is:

```text
Concise General Version
Advanced Premium Version
Assumptions or risk notes only when needed
```

Do not pad the response with long meta commentary.

## Minimal Input Contract

The user should be able to provide as little as:

```text
Scenario:
Purpose:
```

Optional fields:

```text
Audience:
Constraints:
Preferred model:
Output language:
```

The system should still produce a complete result when the optional fields are missing.
