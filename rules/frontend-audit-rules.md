# Frontend Audit Rules

These rules define the review and hardening layer for frontend work. They apply after an initial design or implementation exists, and before claiming that a UI is done.

The purpose is to catch shallow completion, visual drift, broken responsive behavior, inaccessible interactions, and generic AI-looking interfaces.

## Audit Workflow

Use this loop for non-trivial UI work:

```text
Shape -> Build -> Inspect -> Critique -> Polish -> Harden -> Verify
```

### Shape

Define the surface type, user job, visual direction, component boundaries, states, and validation gates before editing.

### Build

Implement with existing design tokens, components, framework patterns, and project conventions. Avoid one-off styling unless the component system deliberately supports it.

### Inspect

Open the UI in a browser when possible. Check desktop and mobile widths, real content length, empty/loading/error states, and interaction states.

### Critique

Review the page like a product designer and a frontend engineer:

- Is the most important action visible without hunting?
- Does the layout match the surface type?
- Does the hierarchy guide the eye in the right order?
- Are controls where a real user would expect them?
- Are repeated elements consistent?
- Does the page feel like this product, or like a generic template?

### Polish

Fix spacing, alignment, typography, visual rhythm, icons, button labels, hover/focus states, motion timing, and responsive details.

### Harden

Check edge cases:

- long titles and labels
- empty data
- failed requests
- loading states
- permission-denied states
- small mobile screens
- high-density desktop screens
- reduced motion preference
- keyboard navigation
- color contrast

### Verify

Run the project-appropriate gates:

```text
format
lint
typecheck
tests
build
browser inspection
responsive inspection
accessibility spot check
```

If a gate cannot run, report it as a validation gap. Do not call the UI complete without matching evidence.

## Deterministic Checks

When the project supports scripts or browser tooling, prefer repeatable checks over subjective claims:

- screenshot desktop and mobile states
- compare key routes after layout changes
- scan for console errors
- run automated accessibility checks if available
- run component tests or visual regression tests when available
- verify text does not overflow buttons, cards, nav items, or modals
- verify interactive canvases or 3D scenes are nonblank and framed correctly

## Frontend Completion Labels

Use status labels strictly:

```text
Modified = files changed, UI not fully checked
Visually inspected = opened and inspected in browser, but automated gates may still be missing
Verified = relevant gates passed and browser inspection supports the claim
Deliverable = verified, risks disclosed, and no required gate is silently missing
```

Do not use "done", "fixed", "ready", or "working" when the evidence only supports `Modified`.

## AI-Looking UI Review

Before finalizing, check for:

- generic copy with no product specificity
- overused gradient or glass effects
- ungrounded metrics, charts, or social proof
- repeated cards where a workflow or table is needed
- large empty visual sections that do not help the user act
- mismatched icon styles
- inconsistent radius, shadows, borders, or spacing
- dramatic hero copy that hides the real offer or product
- decorative animation without interaction value

Fix these before presenting the UI as polished.

## Page-Type Review Rules

### Marketing And Commercial Pages

- The product, offer, or brand must be visible in the first viewport.
- The first viewport should hint at the next section on common desktop and mobile sizes.
- Use real assets, product visuals, diagrams, or generated bitmap visuals when helpful.
- The primary call to action should be specific and tied to the user's next step.

### Product And SaaS Apps

- The first screen should show the working product, not a marketing splash.
- Navigation, filters, status, and primary actions should be stable and predictable.
- Prefer dense but organized information over decorative composition.
- Empty, loading, error, and permission states are required.

### Learning And Agent Training Products

- Break knowledge into progressive modules, lessons, checkpoints, and examples.
- Each concept should include explanation, metaphor, practical task, mistake pattern, and verification.
- The UI should make progress, confidence, and next action obvious.
- Detailed explanations should not crowd the main screen; use lesson pages, drawers, or modals based on flow.

## Handoff Requirements

When reporting frontend work, include:

```text
Status:
Surface type:
What changed:
What was inspected:
Gates run:
Evidence:
Known gaps:
Next action:
```
