# DESIGN.md Rules

`DESIGN.md` is the first-class design-language file for a product repository. It describes how the product should look, feel, move, and communicate.

Use it as a durable design reference, not as a one-time mockup note.

## When To Use

Read `DESIGN.md` before:

- creating or redesigning pages
- changing brand, layout, typography, color, motion, icons, or component style
- building landing pages, commercial pages, dashboards, editors, games, or learning experiences
- evaluating whether a UI feels consistent with the product

If `DESIGN.md` is absent and the task is meaningful frontend or brand work, create or propose one using `templates/design-md-template.md`.

## Lookup Order

Check these locations:

```text
DESIGN.md
docs/design/DESIGN.md
docs/DESIGN.md
design/DESIGN.md
```

If multiple files exist, prefer the most local file for the edited area and reconcile it with the root `AGENTS.md`.

## Relationship To AGENTS.md

`AGENTS.md` controls engineering behavior, safety, workflow, and role activation.

`DESIGN.md` controls product design language:

```text
brand personality
visual direction
layout principles
component feel
motion behavior
content tone
accessibility expectations
visual references
```

If they conflict, `AGENTS.md` wins for engineering/safety/workflow rules, and `DESIGN.md` wins for design-language choices unless the user gives a newer explicit instruction.

## Required Contents

A useful `DESIGN.md` should include:

```text
Product identity
Audience
Primary surfaces
Design principles
Visual language
Color and typography direction
Layout rules
Component rules
Interaction and motion rules
Content tone
Accessibility requirements
Responsive behavior
Anti-patterns
Reference examples
```

It does not need to be long. It needs to be specific enough to prevent random styling.

## Design Reference Safety

Use references to understand patterns, not to copy protected designs wholesale.

Allowed:

- describe what works in a reference
- adapt a layout principle to the current product
- borrow broad interaction ideas
- use public design-language notes as inspiration

Avoid:

- copying exact page structure, copy, assets, or visual identity
- cloning a competitor's distinctive design
- mixing many references into an incoherent style
- treating inspiration files as higher priority than the user's product goal

## Update Rule

Update `DESIGN.md` when:

- the product's visual direction changes
- a new page type appears
- repeated UI review comments show a missing rule
- the team chooses a new motion, icon, typography, or component convention
- frontend work exposes a recurring style problem

Do not rewrite `DESIGN.md` casually during unrelated implementation work.

## Required AI Behavior

For UI work, the AI should report:

```text
DESIGN.md found:
Relevant design rules:
Conflicts:
Applied interpretation:
Validation:
```

If no `DESIGN.md` exists:

```text
DESIGN.md found: no
Fallback:
Needed later:
```

The fallback should be the existing design system, the user's explicit request, and the frontend taste rules.
