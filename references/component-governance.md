# Component Governance
Objective: prevent duplicate components, visual drift, fragmented APIs, and one-off styling.
Reuse hierarchy: existing component → existing variant → existing primitive composition → new reusable component → one-off markup only for truly unique structure.
Search before creation by purpose, interaction, visual pattern, primitive, and nearby variants.
Extend when purpose is the same and API stays understandable; create when semantic purpose/interaction differs or variants would damage the API.
Shared components consider purpose, props, variants, sizes, real states, accessibility, content constraints, responsive behavior.
Consume semantic tokens; avoid repeated hardcoded colors, radii, shadows, spacing, type sizes.
Definition of done: understandable API, consistent tokens, relevant states, accessibility preserved, no unnecessary duplicate, fits system.
