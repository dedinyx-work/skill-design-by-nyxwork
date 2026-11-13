# Architecture-Aware Component Governance

Prevent duplicate implementations, fragmented APIs, and visual drift. Inherit source authority and the established-system boundary from `SKILL.md`. Equivalent existing components must be reused; a different name or folder does not make a duplicate justified.

## Inspect the architecture before creating
Build a proportionate map of the UI architecture, not only the requested screen:
- Repository instructions, framework entry points, routes, page/layout shells.
- Theme providers, design-system packages, semantic token sources, styling conventions.
- Component layers: primitives, shared UI, domain components, feature-local compositions.
- Public exports/import conventions, ownership, dependency direction, state/data boundaries.
- Representative consumers across features, available variants, examples/stories, and relevant tests when present.

Search by purpose, behavior, accessible role, labels, visual pattern, primitive, and related variants. Trace actual usages and exports; do not conclude a component is missing from a single filename search. Inspect broadly enough to find shared equivalents, then focus on the affected paths. Exhaustive reading of every file is not required.

## Decide in this order
| Finding | Required action |
| --- | --- |
| Existing component meets the semantic purpose and behavior | Reuse its public API. |
| Existing variant/props provide the needed treatment | Use them; do not recreate the variant locally. |
| Existing primitives can form the required unique composition | Compose them within established architecture. |
| Same component purpose, but a genuine capability is missing | Extend its API coherently if compatible with the system; inspect affected consumers. |
| No suitable equivalent, or purpose/interaction is genuinely different | Create at the appropriate ownership layer using existing tokens and conventions. |
| Requirement would break the established design-system contract | Explain the conflict and obtain a scoped user decision before departing. |

Semantic and behavioral equivalence matters more than superficial resemblance. A navigation link and a destructive action may look similar but have different contracts. Reuse the correct primitive rather than forcing unrelated responsibilities into one component.

## Guardrails
- Do not copy an existing component into a feature, rename a duplicate, deep-import private internals, or bypass its API with ad hoc styling.
- Do not wrap a component solely to reproduce the same API under another name. A wrapper is justified by a real domain contract, orchestration, or intentional adaptation.
- Do not create a parallel theme, token system, UI library, or component registry to satisfy an inspiration screenshot.
- Keep shared primitives free of feature-specific data fetching and business state unless established architecture explicitly assigns that responsibility.
- New components belong at the lowest appropriate ownership scope. Do not promote one-off compositions into a speculative shared kit.
- Existing duplicates are not permission to add more. Choose the canonical supported component; flag material ambiguity without launching an unrelated consolidation.
- A reference or agent preference cannot override system contracts. Explicit system changes stay scoped and account for affected consumers.

## Verify and communicate
For creation or extension, record a short justification: candidates inspected → missing capability → reuse/compose/extend/create decision. This may be a sentence in the work summary; no mandatory user-facing inventory for routine reuse.
Check relevant consumers, variants, semantic tokens, content limits, responsive behavior, focus/keyboard contracts, and state ownership. Run meaningful project checks for the affected scope.
Done: no avoidable equivalent duplicate, correct public API and layer, consistent system styling, relevant behavior preserved, and any approved system departure explicit.
