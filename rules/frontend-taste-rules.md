# Frontend Taste Rules

These rules define the optional frontend/design enhancement layer for downstream projects. They should activate when a task touches page design, brand expression, commercial presentation, visual polish, interaction quality, animation, or a UI redesign.

The goal is not to make every project look decorative. The goal is to make each interface feel intentional for its audience, product type, and job.

## Activation

Use this layer when the user asks for:

- landing pages, pricing pages, portfolios, product sites, campaigns, or brand pages
- dashboards, SaaS tools, admin panels, editors, builders, or agent workspaces
- frontend redesign, UI polish, visual hierarchy, interaction quality, or motion
- conversion-oriented pages, onboarding flows, course pages, paid training pages, or commercial Agent products

Do not force this layer onto backend-only, CLI-only, data-only, or purely textual work.

## Surface Classification

Before designing or changing UI, classify the surface:

```text
Brand / marketing surface
Product / application surface
Operational / admin surface
Editor / creative tool
Game / interactive experience
Documentation / learning surface
Hybrid surface
```

Then match the visual behavior to that surface:

- Brand and marketing surfaces can use stronger imagery, narrative rhythm, expressive typography, and more distinctive motion.
- Product and application surfaces should prioritize scanning, repeated use, stable layout, clear state, and quiet density.
- Operational and admin surfaces should avoid oversized hero sections and decorative composition.
- Editors and creative tools should make the working object primary, with controls close to the action.
- Games and interactive experiences can be more illustrative, kinetic, and playful.
- Documentation and learning surfaces should optimize reading, sequence, examples, and progressive understanding.

## Design Read

Before implementation, produce a short design read for non-trivial UI work:

```text
Audience:
Primary job:
Surface type:
Emotional target:
Trust signals:
Interaction density:
Content density:
Motion role:
Visual references:
Non-goals:
```

If a local `DESIGN.md` exists, the design read must align with it. If it conflicts with the user's new request, state the conflict and choose the lowest-risk interpretation before editing.

## Three Dials

Use these dials to avoid default, template-like UI.

### DESIGN_VARIANCE

How far the interface can move away from conventional layouts.

```text
1 = standard, conservative, familiar
2 = slightly distinctive within known patterns
3 = clearly branded and memorable
4 = bold layout, strong point of view
5 = experimental, only when the audience and task support it
```

Default:

- product/admin tools: `1-2`
- learning products and commercial Agent training: `2-3`
- brand/marketing pages: `3-4`
- games/interactive experiences: `3-5`

### MOTION_INTENSITY

How much animation should guide attention.

```text
0 = no animation except required state changes
1 = subtle transitions and feedback
2 = scroll, reveal, and small interaction motion
3 = expressive branded motion
4 = highly kinetic experience
```

Default:

- admin/product tools: `0-1`
- learning products: `1-2`
- marketing pages: `2-3`
- games/interactive experiences: `3-4`

Motion must clarify hierarchy, feedback, or progression. Do not add motion as decoration when it makes the interface harder to use.

### VISUAL_DENSITY

How much information appears on screen at once.

```text
1 = spacious, editorial, low density
2 = balanced narrative sections
3 = compact but readable product UI
4 = dense operational UI
5 = expert UI with heavy data density
```

Default:

- landing pages: `1-2`
- course/training products: `2-3`
- SaaS dashboards: `3-4`
- admin/data tools: `4-5`

## Anti-Slop Rules

Avoid these common low-quality AI UI patterns:

- generic purple-blue gradient identity without product reason
- oversized cards stacked inside other cards
- fake dashboard widgets that do not map to real user decisions
- decorative blobs, floating orbs, or bokeh-style backgrounds
- repeated feature cards when the workflow needs an actual usable tool
- hero sections that hide the real product or next action
- buttons with vague labels such as "Get Started" when the user needs a specific action
- motion that distracts from task completion
- page text explaining basic UI usage instead of making the UI obvious
- one-note palettes that are only variations of one hue

## Motion And Libraries

Use the project's existing animation stack first. If the project already uses Framer Motion, Motion One, GSAP, anime.js, Lenis, or a similar library, follow the existing pattern.

Do not add a new animation library unless:

- the requested interaction is hard to implement cleanly with the current stack
- the bundle and maintenance cost are acceptable
- the project owner has implicitly or explicitly allowed dependency additions
- the effect improves comprehension, conversion, or interaction quality

For simple UI feedback, CSS transitions are usually enough.

## Visual Asset Rule

Websites, games, product pages, and commercial learning pages should use relevant visual assets when the subject benefits from being seen. Prefer real product screenshots, generated bitmap assets, diagrams, or interactive scenes over generic abstract decoration.

Do not use dark, blurred, cropped, stock-like imagery when the user needs to inspect the product, workflow, or offer.

## Required Output For UI Planning

For meaningful UI work, the AI should state:

```text
Surface type:
Design dials:
Layout strategy:
Component system:
Motion strategy:
Responsive strategy:
Validation plan:
```

This can be brief, but it must exist before major UI implementation.
