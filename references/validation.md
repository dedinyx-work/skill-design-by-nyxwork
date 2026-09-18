# Validation

Use this reference before declaring a meaningful UI task complete.

## Objective

Catch visual drift, AI-slop patterns, responsive failures, accessibility issues,
and maintainability problems before completion.

## 1. Product Fit

Check:

- Does the result look like the same product?
- Does it respect the existing brand?
- Does it follow the approved visual reference?
- Did the agent introduce an unrelated style?

Fail if the new UI looks like a separate template.

## 2. Hierarchy

Check:

- Is the primary task obvious?
- Is the primary action visually clear?
- Are secondary actions quieter?
- Can critical information be scanned quickly?
- Is color being used to compensate for weak hierarchy?

## 3. Tokens

Check:

- Are semantic tokens used?
- Are new arbitrary colors present?
- Are near-duplicate values present?
- Are spacing values consistent?
- Are radius values consistent?
- Are shadows controlled?

## 4. Components

Check:

- Were existing components reused?
- Were unnecessary duplicates created?
- Are variants semantically named?
- Are component APIs consistent?
- Are shared patterns actually reusable?

## 5. Layout

Check:

- Are alignment lines consistent?
- Are gaps consistent?
- Are control heights consistent?
- Are card widths intentional?
- Is there unnecessary nesting?
- Is there accidental horizontal scroll?

## 6. AI-Slop Detection

Validate four dimensions: visual, structural, content, and interaction. Load `anti-ai-slop.md` when any risk is present.

Look for unnecessary:

- Gradients
- Glow
- Glass effects
- Decorative blobs
- Huge headings
- Excessive radius
- Floating cards
- Strong shadows
- Too many badges
- Random accent colors
- Oversized metrics
- Unnecessary charts
- Decorative motion

Keep any of these only when they support the approved visual language or a real
interaction need.

## 7. Interaction States

Check relevant:

- Default
- Hover
- Focus
- Active
- Selected
- Disabled
- Loading
- Error
- Success

Do not require every state for every component.

## 8. Data States

Check:

- Loading
- Empty
- Error
- Partial data
- No permission
- Long content
- Missing content

## 9. Responsive

Check:

- Large desktop
- Desktop
- Tablet
- Mobile when relevant
- Wrapping
- Overflow
- Sticky elements
- Navigation access
- Table behavior
- Modal behavior

## 10. Accessibility

Check:

- Visible focus
- Meaningful labels
- Accessible icon buttons
- Sufficient contrast
- Keyboard access
- Form label association
- Color-independent state communication

## 11. Engineering Quality

Check:

- No unnecessary dependency
- No repeated magic values
- No avoidable inline styles
- No duplicate CSS patterns
- No unnecessary absolute positioning
- No arbitrary z-index escalation
- Code matches project conventions

## 12. Scope

Check:

- Did the work stay within requested scope?
- Were shared changes justified?
- Were unrelated screens left untouched?
- Were broad changes explained when unavoidable?

## Final Decision

Mark the UI complete only if critical checks pass.

If a critical issue remains, refine before completion.

Prefer fixing:

1. Workflow problems
2. Accessibility failures
3. Broken responsive behavior
4. Design-system inconsistency
5. Visual polish


## Rendered Evidence Gate

When runtime or screenshot inspection is available, completion requires checking the rendered UI rather than source code alone. Re-run after fixes. Never claim visual validation if the rendered interface was not inspected.
