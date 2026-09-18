# Visual Reference Analysis

Use this reference when the user provides screenshots, Figma references,
competitor references, moodboards, or existing interfaces that should guide a
redesign.

## Objective

Convert visual references into reusable design rules.

Do not stop at visual imitation.

The result should explain why the reference looks coherent and how that logic
can scale across a real product.

## Analysis Order

Analyze the reference in this order:

1. Product context
2. Information density
3. Layout structure
4. Typography hierarchy
5. Spacing rhythm
6. Surface hierarchy
7. Color roles
8. Border and radius behavior
9. Shadow and elevation
10. Components
11. Iconography
12. Interaction language
13. Responsive implications

## 1. Product Context

Determine what kind of interface it is:

- SaaS
- Admin
- ERP
- CRM
- HR
- Analytics
- Productivity
- E-commerce operations
- Consumer app
- Marketing page

Do not apply operational UI rules to a marketing reference without adjustment.

## 2. Density

Classify density:

- Low
- Medium
- Medium-high
- High

Look at:

- Row height
- Card padding
- Control height
- Gap size
- Number of visible elements
- Amount of whitespace

Record the density as a system rule, not a feeling.

Example:

> Medium-high density. Controls average 34–38px. Card padding is mostly 12–16px.
> Section gaps are compact. The UI prioritizes scanning over spacious presentation.

## 3. Layout Structure

Identify:

- Sidebar or top navigation
- Fixed vs fluid regions
- Grid columns
- Page max-width
- Common alignment lines
- Repeating section patterns
- Sticky regions
- Scroll behavior

Extract layout logic, not screenshot coordinates.

## 4. Typography

Identify:

- Font family category
- Page title scale
- Section title scale
- Body scale
- Metadata scale
- Weight hierarchy
- Line-height behavior
- Letter spacing
- Numeric styling

Avoid inventing exact font names unless clearly known.

Prefer describing the system semantically.

## 5. Spacing Rhythm

Look for repeated spacing values.

Infer a likely scale such as:

4 / 8 / 12 / 16 / 24 / 32

Avoid reproducing irregular screenshot gaps as hardcoded values.

## 6. Surface Hierarchy

Map surfaces:

- App background
- Sidebar
- Main content
- Card
- Elevated overlay
- Selected surface
- Disabled surface

Determine whether the system is:

- Border-driven
- Shadow-driven
- Contrast-driven
- Mixed

## 7. Color Roles

Do not only collect hex values.

Map color by role:

- Primary
- Primary hover
- Background
- Surface
- Surface subtle
- Border
- Text primary
- Text secondary
- Text muted
- Success
- Warning
- Error
- Info
- Selected
- Focus

If the reference contains brand-specific colors, translate their function
without assuming the user wants the same brand identity.

## 8. Borders and Radius

Identify:

- Border thickness
- Border contrast
- Card radius
- Button radius
- Input radius
- Badge treatment
- Divider usage

Classify the system as:

- Square
- Restrained
- Rounded
- Soft
- Pill-heavy

Do not average unrelated values into one arbitrary token.

## 9. Elevation

Identify where shadows are actually used.

Common patterns:

- No shadow on standard cards
- Shadow only on overlays
- Very subtle card elevation
- Layered floating panels

If shadows are absent, do not add them later "for polish."

## 10. Components

Analyze recurring patterns:

- Buttons
- Inputs
- Selects
- Search
- Cards
- Tables
- Lists
- Tabs
- Sidebar items
- Badges
- Dropdowns
- Modals
- Date pickers
- Pagination
- Tooltips

Describe proportions and hierarchy.

Example:

> Primary buttons are compact, rectangular, medium-weight, and visually stronger
> through fill color rather than large size.

## 11. Iconography

Identify:

- Outline vs filled
- Stroke weight
- Typical size
- Color behavior
- Use of icons with labels
- Icon-only control behavior

Use one compatible icon family in implementation.

## 12. Interaction Language

Infer likely states:

- Hover
- Focus
- Selected
- Active
- Disabled
- Loading
- Expanded
- Error

The reference may not show all states. Generate missing states by extending the
same visual logic.

## 13. Responsive Implications

Do not assume desktop composition should simply shrink.

Identify:

- Which columns can collapse
- Which controls can wrap
- Which navigation can become a drawer
- Which data needs horizontal scroll
- Which actions must remain visible

## Output Format

Produce a compact visual-language summary with:

### Visual Direction

Short description of the overall design language.

### Design Characteristics

- Density
- Typography
- Surface model
- Border model
- Radius
- Shadow
- Color behavior
- Component style
- Navigation style
- Interaction style

### Extracted Rules

List repeatable rules.

### Avoid

List visual patterns that would break the reference language.

### Token Candidates

List semantic token roles that should be generated.

## Important Rule

The visual reference is evidence, not a complete design system.

Always convert the reference into scalable rules before applying it across the
product.
