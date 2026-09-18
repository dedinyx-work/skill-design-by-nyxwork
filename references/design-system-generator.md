# Design System Generator

Use this reference when the project has no coherent design system, when the user
asks to formalize one, or when a redesign needs a stable system before
implementation.

## Objective

Generate the smallest complete design system needed to keep the product
consistent.

Do not create a huge theoretical system for a small product.

## Inputs

Use available inputs in this order:

1. Existing product patterns
2. Existing brand assets
3. User-provided visual references
4. Product context
5. Default production UI principles

## Required Sections

A generated design system should define:

1. Design direction
2. Principles
3. Density
4. Color roles
5. Typography
6. Spacing
7. Sizing
8. Radius
9. Borders
10. Elevation
11. Iconography
12. Core component rules
13. Interaction states
14. Responsive behavior
15. Accessibility baseline
16. Anti-patterns
17. Anti-AI-slop constraints

## Design Direction

Describe the product in practical terms.

Example:

> Structured enterprise SaaS interface with medium-high information density,
> neutral surfaces, restrained radius, border-driven separation, and a single
> strong brand accent.

Avoid vague language such as:

- Beautiful
- Premium
- Futuristic
- Stunning
- Cutting-edge

unless the product context genuinely requires it.

## Principles

Keep principles actionable.

Recommended categories:

- Clarity before decoration
- Reuse before invention
- Tokens before arbitrary values
- Hierarchy before color
- Accessibility by default
- Responsive structure, not shrinkage
- Real-content resilience

## Density

Choose one:

- Low
- Medium
- Medium-high
- High

Then define implications for:

- Control height
- Table row height
- Card padding
- Section gaps
- Typography scale

## Color System

Use semantic roles.

Minimum:

- Brand primary
- Brand primary hover
- Background
- Surface
- Surface subtle
- Surface selected
- Border
- Border strong
- Text primary
- Text secondary
- Text muted
- Success
- Warning
- Error
- Info
- Focus

Avoid creating many decorative colors.

## Typography

Define:

- Font family
- Heading family if different
- Page title
- Section title
- Card title
- Body
- Label
- Metadata
- Metric
- Button text

Use typography hierarchy consistently across pages.

## Spacing

Prefer a small predictable scale.

Example:

4 / 8 / 12 / 16 / 20 / 24 / 32 / 40 / 48

Do not generate dozens of spacing tokens unless the product needs them.

## Sizing

Define reusable dimensions for:

- Control heights
- Icon sizes
- Sidebar width if relevant
- Header height if relevant
- Touch target minimum
- Content max-width if relevant

## Radius

Define a restrained set.

Example:

- xs
- sm
- md
- lg
- pill
- circle

Avoid one-off radius values per component.

## Borders

Define:

- Default border
- Subtle divider
- Strong border
- Focus border

Prefer borders and surface contrast over unnecessary shadows.

## Elevation

Keep elevation levels minimal.

Typical:

- Surface
- Raised
- Overlay
- Modal

Many enterprise interfaces only need overlay and modal shadows.

## Iconography

Define:

- Preferred icon family
- Stroke style
- Standard sizes
- Color behavior
- Icon-only accessibility rule

## Component Rules

At minimum define:

- Button
- Input
- Select
- Card
- Table
- List row
- Badge
- Tabs
- Dropdown
- Modal
- Navigation item

For each component, define:

- Purpose
- Visual hierarchy
- Size
- Radius
- States
- When not to use

## Interaction States

Define visual behavior for relevant states:

- Hover
- Focus
- Active
- Selected
- Disabled
- Loading
- Error
- Success

## Responsive Behavior

Define structural rules, not only breakpoints.

Example:

- 4 columns → 2 columns → 1 column
- Full sidebar → compact sidebar → drawer
- Inline filters → wrapped filters → filter sheet

## Accessibility Baseline

Include:

- Visible keyboard focus
- Labels for controls
- Meaningful contrast
- Color-independent state communication
- Semantic elements
- Accessible icon-only controls
- Reasonable touch targets

## Anti-Patterns

Define what the system rejects.

Typical:

- Random gradients
- Glassmorphism without purpose
- Excessive shadows
- Arbitrary colors
- Excessive radius
- Nested cards
- Giant marketing typography
- Too many badges
- Unnecessary charts
- Decorative motion

## Output Rule

Generate the design system using `templates/design-system.md`.

Keep it project-specific.

Do not leave placeholder sections that are irrelevant to the product.
