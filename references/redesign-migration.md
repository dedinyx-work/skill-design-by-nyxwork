# Redesign Migration

Use this reference when replacing inconsistent, generic, or AI-slop UI with a
coherent visual system.

## Objective

Redesign systematically without destabilizing the product.

The goal is not to repaint every screen independently.

The goal is to migrate the product toward one design language.

## Common AI-Slop Signals

Audit for:

- Random gradients
- Purple or blue decorative glow
- Excessive 16–32px radius
- Every section inside a card
- Large floating surfaces
- Excessive shadows
- Oversized headings
- Low information density in operational screens
- Inconsistent spacing
- Inconsistent control heights
- Arbitrary colors
- Too many badges
- Unnecessary charts
- Random icon backgrounds
- Excessive decorative animation
- Duplicate components
- Hardcoded one-off CSS
- Landing-page visual patterns inside app screens

Do not remove a pattern only because it appears on this list.

Remove it when it lacks a product or interaction reason.

## Migration Flow

Use:

Audit → Reference analysis → Design system → Tokens → Component mapping →
Foundation migration → Screen migration → Validation

## Phase 1. Audit

Record:

- Current global styles
- Token system
- Shared components
- Repeated visual inconsistencies
- Most common arbitrary values
- Highest-impact screens
- Accessibility problems
- Responsive problems

Do not start with pixel polishing.

## Phase 2. Define Target Language

If visual references exist, analyze them first.

Define:

- Density
- Typography
- Surface hierarchy
- Color roles
- Spacing
- Radius
- Borders
- Elevation
- Component treatment
- Navigation behavior

## Phase 3. Generate Tokens

Normalize:

- Colors
- Spacing
- Radius
- Shadows
- Typography
- Motion
- Z-index

Map old values to new semantic tokens where practical.

## Phase 4. Component Mapping

Create a migration table.

Example:

| Existing Pattern | Target |
| --- | --- |
| Large rounded card | Standard surface card |
| Gradient CTA | Primary button |
| Random status chip | Semantic badge |
| Custom input | Shared Input |
| Feature-specific modal | Shared Dialog |

Prefer updating shared primitives before updating every screen manually.

## Phase 5. Foundation Migration

Start with high-leverage layers:

1. Global tokens
2. Typography
3. Button
4. Form controls
5. Cards and surfaces
6. Navigation
7. Tables and lists
8. Overlays
9. Status components

This creates visual consistency quickly.

## Phase 6. Screen Migration

Migrate screen-by-screen.

For each screen:

1. Preserve workflow
2. Remove unnecessary visual wrappers
3. Normalize spacing
4. Reuse shared components
5. Improve hierarchy
6. Apply target density
7. Check real content
8. Validate responsive behavior

Do not redesign the information architecture unless required.

## Phase 7. Remove Dead Styling

After migration:

- Delete unused classes
- Remove duplicate tokens
- Remove obsolete components
- Remove abandoned assets
- Remove one-off hacks

Only remove code after confirming it is unused.

## Scope Control

If the user asks to redesign one page:

- Improve that page
- Update shared primitives only when necessary
- Do not silently redesign the whole product

If a shared primitive change affects many pages, explain the impact in the work
plan before making a broad change.

## Progressive Migration

For large products, prefer:

Foundation → High-traffic screens → Repeated patterns → Edge cases

Avoid big-bang redesigns unless the repository and user request justify them.

## Definition of Done

The migration is successful when:

- The UI reads as one product
- Arbitrary styling is reduced
- Existing workflow remains intact
- Shared components are stronger
- Tokens cover normal implementation needs
- Visual references are reflected as system rules
- Accessibility and responsiveness did not regress
