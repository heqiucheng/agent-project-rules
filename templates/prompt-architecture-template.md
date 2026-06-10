# Prompt Architecture Template

Use this template when the user provides only a scenario and intended use, but still expects a complete, reusable prompt.

## Minimal Input

```text
Scenario:
Purpose:
Audience: [optional]
Constraints: [optional]
Preferred model: [optional]
Output language: [optional]
```

## Required Behavior

When generating the prompt, automatically do all of the following:

- complete hidden requirements and success criteria
- add an explicit role definition
- add style constraints suited to the audience and use case
- add an explicit output format
- generate both a concise general version and an advanced premium version
- keep wording portable across mainstream AI models
- remove contradictions, ambiguity, and missing boundaries

## Concise General Version

```text
Role:
[task-appropriate role]

Task:
[what the AI must do]

Context:
[essential background inferred from the scenario and purpose]

Constraints:
- [constraint 1]
- [constraint 2]

Style:
[tone, audience fit, and delivery style]

Output Format:
[clear structure for the final answer]
```

## Advanced Premium Version

```text
Role:
[stronger expert role definition]

Objective:
[clear end goal]

Context:
[useful background and assumptions]

Hidden Requirements Completed:
- [requirement 1]
- [requirement 2]
- [requirement 3]

Execution Rules:
1. [step or behavior 1]
2. [step or behavior 2]
3. [step or behavior 3]

Quality Bar:
- [quality expectation 1]
- [quality expectation 2]

Failure Avoidance:
- [logic or risk guardrail 1]
- [logic or risk guardrail 2]

Style:
[tone, pacing, format constraints]

Output Format:
[explicit final response structure]
```

## Cross-Model Notes

- Prefer plain instructions and visible section headers.
- Avoid vendor-specific features unless the project requires one model.
- Keep required instructions explicit and separate from optional preferences.
- If the target model is weaker at long context, shorten the advanced version before removing the role, constraints, or output format.
