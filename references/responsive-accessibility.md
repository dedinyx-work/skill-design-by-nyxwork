# Responsive and Accessibility

Use this reference for layout changes, forms, navigation, tables, dialogs,
mobile behavior, keyboard interaction, and complex frontend states.

## Objective

Ensure the UI works across realistic viewport sizes and for users with different
interaction needs.

## Responsive Principle

Do not shrink desktop UI until it fits.

Adapt structure.

Use:

Reflow → Wrap → Collapse → Scroll → Hide only low-priority content

## Priority Under Constraint

Preserve in this order:

1. Primary user task
2. Primary action
3. Critical information
4. Navigation access
5. Secondary actions
6. Supporting information
7. Decorative content

## Breakpoints

Use the project's existing breakpoint system.

If none exists, choose a simple set appropriate to the framework.

Do not create many arbitrary breakpoints.

## Layout Patterns

### Grid

Prefer:

4 columns → 2 columns → 1 column

when content permits.

### Sidebar

Prefer:

Full sidebar → compact sidebar → drawer

### Filters

Prefer:

Inline → wrapped → compact toolbar or filter sheet

### Tables

For dense tables:

- Keep critical columns visible
- Allow horizontal scroll when necessary
- Avoid collapsing structured data into unreadable mini-cards by default
- Consider row detail drawers for secondary data

## Content Resilience

Test for:

- Long names
- Long email addresses
- Long labels
- Large numbers
- Missing data
- Multiple languages
- Multi-line content
- Empty states
- Large datasets

Use truncation only when full content remains discoverable.

## Accessibility Baseline

Target WCAG AA where practical.

### Keyboard

Ensure:

- Interactive elements are reachable
- Focus order is logical
- Focus is visible
- Dialogs manage focus correctly
- Escape closes dismissible overlays when appropriate

### Labels

Form controls must have accessible names.

Placeholder text is not a replacement for a label when a persistent label is
needed.

### Color

Do not communicate status with color alone.

Use:

Color + text

or:

Color + icon + text

### Contrast

Use sufficient contrast for:

- Body text
- Muted text
- Controls
- Borders when they communicate structure
- Focus indicators

### Icon-Only Controls

Provide:

- Accessible name
- Tooltip when useful
- Adequate target size

### Touch Targets

Recommended practical target:

- Desktop: at least about 32px
- Touch-oriented UI: about 44px when practical

The visible icon may be smaller than the clickable area.

### Motion

Use motion for:

- State transitions
- Feedback
- Relationship
- Navigation

Avoid decorative motion that interferes with reading.

Respect reduced-motion preferences when possible.

## Forms

Forms should:

- Associate labels with controls
- Show validation near the field
- Preserve entered data after recoverable errors
- Clearly mark required fields
- Avoid validation by color alone

## Dialogs

Dialogs should:

- Have a clear title
- Trap or manage focus appropriately
- Restore focus after closing
- Provide a clear close mechanism
- Avoid hiding essential context when a page or drawer is more appropriate

## Data States

Handle:

- Loading
- Empty
- Error
- Partial data
- Success
- No permission

Do not leave unexplained blank surfaces.

## Definition of Done

Responsive and accessibility work is acceptable when:

- Core tasks work at intended viewport sizes
- No accidental horizontal overflow exists
- Important controls remain reachable
- Focus is visible
- Controls have accessible names
- Status is understandable without color alone
- Long content does not break layout
