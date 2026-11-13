# Semantic Token Workflow

Follow `SKILL.md` source authority. Brand values and approved reference roles determine expression; no universal NyxWork palette, font, radius, or shadow is required.

1. Inspect existing variables, theme configuration, typography, and component states.
2. Reuse established semantic roles and naming. Map duplicates before adding a parallel system.
3. Extract needed roles from brand/reference/product: color, typography, spacing, size, radius, border, elevation, focus, motion, layers.
4. Use semantic roles → meaningful component aliases → primitives. Add aliases when they represent a real reusable contract, not every property.
5. Cover relevant hover/focus/selected/disabled/error states and accessible text/surface pairings. Do not alter official brand primitives silently to solve a pairing problem.
6. Apply tokens in components and inspect the rendered result. Document a true one-off instead of inventing a fake reusable role.

## Scale and expression
Choose a compact, useful spacing and type scale appropriate to content density. Preserve reference proportions rather than forcing all designs onto the same scale. Radius/elevation can be square, restrained, rounded, or expressive according to evidence.
Typography roles include family, size, weight, line height, and tracking as needed. Verify font loading and available weights; generic fallback typography is a disclosed limitation when fidelity depends on a missing font.
Use fluid values or responsive overrides where justified, not arbitrary breakpoint proliferation.

## Outputs
Update the project's existing source of truth first. Generate CSS/JSON only when useful for the project; do not mandate both.
`templates/design-tokens.css` and `.json` demonstrate corresponding example roles, not production-ready brand defaults. Keep generated representations consistent; the JSON template is a simple example format, not a claim of standards/schema compliance.
For migration, record `existing value/token → target semantic role → affected components` when impact warrants it.
