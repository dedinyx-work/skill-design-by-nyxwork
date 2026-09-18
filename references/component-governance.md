# Component Governance

Use this reference when creating, extending, normalizing, or refactoring UI
components.

## Objective

Prevent duplicate components, visual drift, fragmented APIs, and one-off styling.

## Pattern Before Component

Before searching for a component, confirm the component pattern is appropriate for the user job. Use `ui-decision-framework.md`. Do not reuse a component merely because it exists if its interaction semantics are wrong.

## Reuse Hierarchy

Always follow:

1. Existing component
2. Existing component variant
3. Existing primitive composition
4. New reusable component
5. One-off markup only for truly unique structure

## Search Before Creation

Before creating a component, search for:

- Same purpose
- Same interaction
- Same visual pattern
- Same primitive under another name
- Similar variant in another feature

Do not assume absence.

## Extend vs Create

Extend an existing component when:

- The purpose is the same
- The API can remain understandable
- The visual difference is a legitimate variant
- Reuse improves consistency

Create a new component when:

- The interaction model is different
- The semantic purpose is different
- Adding another variant would make the existing API confusing
- The pattern will be reused

## Variant Discipline

Variants should represent meaningful states or hierarchy.

Good:

- primary
- secondary
- ghost
- destructive
- compact

Bad:

- blueVersion
- page3Button
- slightlyRounded
- dashboardSpecial

## Component Anatomy

For each shared component, define:

- Purpose
- Required props
- Optional props
- Variants
- Sizes
- States
- Accessibility behavior
- Content constraints
- Responsive behavior if relevant

## Core Components

Common shared primitives include:

- Button
- IconButton
- Input
- Textarea
- Select
- Checkbox
- Radio
- Switch
- Badge
- Card
- Table
- Tabs
- Tooltip
- Dropdown
- Dialog
- Drawer
- Toast
- Pagination
- EmptyState
- Skeleton

Do not force all of these into small projects.

## Layout Components

Use reusable layout primitives only when they reduce repetition.

Examples:

- Stack
- Inline
- Grid
- PageShell
- SidebarLayout
- SectionHeader

Avoid abstraction that hides simple CSS without real reuse value.

## State Coverage

Relevant components should consider:

- Default
- Hover
- Focus
- Active
- Selected
- Disabled
- Loading
- Error
- Success

Do not invent states that the component cannot enter.

## Accessibility

Shared components should centralize accessibility where practical.

Examples:

- IconButton requires accessible label
- Form controls support label association
- Dialog manages focus
- Tooltip is not the only source of essential information
- Dropdown supports keyboard navigation

## Styling Rule

Shared components should consume tokens.

Avoid repeated hardcoded:

- Colors
- Radius
- Shadows
- Spacing
- Font sizes

## Anti-Fragmentation Rule

Do not create:

- PrimaryButton
- SecondaryButton
- SmallButton
- BlueButton
- DashboardButton

when one Button component with variants is sufficient.

## Refactor Rule

When multiple duplicate components already exist:

1. Identify shared behavior
2. Choose the strongest existing base
3. Normalize tokens
4. Create a migration path
5. Replace duplicates gradually

Avoid risky full rewrites unless requested.

## Definition of Done

A component change is complete when:

- The API is understandable
- Tokens are used consistently
- Relevant states are covered
- Accessibility behavior is preserved
- No equivalent component was unnecessarily duplicated
- The new pattern fits the existing design system
