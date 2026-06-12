# Frontend Style Rules

These rules cover baseline frontend structure. For meaningful UI design, also use:

```text
rules/frontend-taste-rules.md
rules/frontend-audit-rules.md
rules/design-md-rules.md
templates/frontend-brief-template.md
templates/design-md-template.md
```

## Hard Rules

- Do not write inline styles or page-level hardcoded colors, font sizes, spacing, radius, or shadows.
- Use shared design tokens and reusable components.
- Pages compose components; components own styling.
- Buttons, badges, cards, empty states, loading states, risk notices, and AI insight panels must be reusable.
- UI states must be centralized and consistent.
- Accessibility and responsive behavior are required.
- Read `DESIGN.md` when it exists before changing visual language, layout, motion, icons, typography, or color.
- Classify the UI surface before design changes: marketing, product app, admin, editor, game, learning, or hybrid.
- Do not present generic AI-looking UI as polished product work.
- Do not add animation libraries or visual effects unless they serve comprehension, feedback, conversion, or interaction quality.

## Required Style Structure

```text
src/styles/tokens.css
src/styles/base.css
src/styles/layout.css
src/styles/components.css
src/styles/states.css
src/styles/themes.css
```

Adapt this structure to the chosen framework, but keep the same principle.

## Required Frontend Planning

This is the structure layer. Surface classification, design dials, and the UI planning block live in one place:

```text
rules/frontend-taste-rules.md
```

State that planning block before meaningful UI work. Do not duplicate it here.

## Completion Rule

Frontend completion labels (`Modified`, `Visually inspected`, `Verified`, `Deliverable`) are defined in one place:

```text
rules/frontend-audit-rules.md
```

Use them strictly. If the UI was not opened in a browser or otherwise inspected, do not imply visual verification.
