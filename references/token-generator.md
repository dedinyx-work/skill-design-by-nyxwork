# Token Generator

Use this reference when generating, restructuring, or normalizing design tokens.

## Objective

Create semantic, reusable tokens that reduce arbitrary styling and make future
AI-generated UI predictable.

## Token Priority

Prefer:

Semantic tokens → Component aliases → Primitive values

Avoid styling directly from primitives inside components when semantic roles are
available.

## Token Categories

Recommended categories:

- color
- typography
- spacing
- size
- radius
- border
- shadow
- motion
- z-index

Only add categories the product needs.

## Color Tokens

Prefer semantic names.

Good:

- color-bg-app
- color-bg-surface
- color-bg-selected
- color-border-default
- color-border-strong
- color-text-primary
- color-text-secondary
- color-brand-primary
- color-status-success
- color-status-warning
- color-status-error

Avoid:

- blue-1
- nice-gray
- card-color
- special-green

Primitive palettes may exist internally, but components should consume semantic
roles when possible.

## Typography Tokens

Define:

- font-family-body
- font-family-heading
- font-size-xs
- font-size-sm
- font-size-md
- font-size-lg
- font-size-xl
- font-weight-regular
- font-weight-medium
- font-weight-semibold
- line-height-tight
- line-height-normal

Do not create excessive size steps.

## Spacing Tokens

Use a predictable scale.

Recommended default:

- space-1: 4px
- space-2: 8px
- space-3: 12px
- space-4: 16px
- space-5: 20px
- space-6: 24px
- space-8: 32px
- space-10: 40px
- space-12: 48px

Adapt to the existing product if a different scale is established.

## Radius Tokens

Recommended:

- radius-xs
- radius-sm
- radius-md
- radius-lg
- radius-pill
- radius-circle

Do not create per-component radius tokens unless the component truly needs a
different semantic behavior.

## Shadow Tokens

Keep the set minimal.

Example:

- shadow-none
- shadow-raised
- shadow-overlay
- shadow-modal

Standard cards often use `shadow-none`.

## Motion Tokens

Define only if motion exists.

Example:

- duration-fast
- duration-normal
- easing-standard

Respect reduced-motion preferences.

## Z-Index Tokens

Use a semantic layer scale.

Example:

- z-base
- z-sticky
- z-dropdown
- z-overlay
- z-modal
- z-toast

Avoid arbitrary values such as 99999.

## Component Aliases

Component-level aliases are useful when the same semantic meaning is reused.

Example:

```css
--button-primary-bg: var(--color-brand-primary);
--button-primary-bg-hover: var(--color-brand-primary-hover);
--button-primary-text: var(--color-text-on-brand);
```

Do not create aliases for every single CSS property.

## Existing Project Rule

If tokens already exist:

1. Audit them
2. Map duplicates
3. Prefer existing naming conventions
4. Deprecate redundant values gradually
5. Avoid a full rename unless explicitly requested

## Reference-Derived Tokens

When a visual reference exists:

1. Extract repeated values
2. Group them by semantic role
3. Remove near-duplicates
4. Normalize spacing and radius
5. Generate missing interaction tokens
6. Preserve the user's brand identity

Do not copy every sampled pixel as a token.

## Output Formats

Use both when useful:

- CSS custom properties
- JSON token structure

Use:

- `templates/design-tokens.css`
- `templates/design-tokens.json`

## Validation

Before finalizing tokens, check:

- Are semantic roles clear?
- Are there near-duplicate colors?
- Are there arbitrary one-off spacing values?
- Are component states covered?
- Can most UI styling be built without new hardcoded values?
- Are token names understandable without opening the design file?

If not, simplify.
