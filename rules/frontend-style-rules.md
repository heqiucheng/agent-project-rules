# Frontend Style Rules

## Hard Rules

- Do not write inline styles or page-level hardcoded colors, font sizes, spacing, radius, or shadows.
- Use shared design tokens and reusable components.
- Pages compose components; components own styling.
- Buttons, badges, cards, empty states, loading states, risk notices, and AI insight panels must be reusable.
- UI states must be centralized and consistent.
- Accessibility and responsive behavior are required.

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