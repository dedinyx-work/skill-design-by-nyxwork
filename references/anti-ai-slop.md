# Anti AI-Slop Design Rules

## Objective
Prevent UI that looks template-generated, decoration-first, or structurally generic. Anti-slop does not mean minimalism. It means every design choice has a reason.

## Decision Test
For every visible element ask: Does this improve workflow, hierarchy, comprehension, interaction feedback, brand recognition, or system consistency? If none apply, remove or simplify it.

## Visual Slop
Reject by default when unsupported by product language: decorative gradients, glow, glassmorphism, large floating shadows, excessive radius, pill-everything, colored icon tiles everywhere, random accent colors, giant headings, decorative blobs, ornamental charts, excessive whitespace.

Do not ban a treatment merely because it appears here. Keep it when an approved reference, brand system, or interaction purpose supports it.

## Structural Slop
Audit for card-inside-card, every section becoming a card, default KPI-card plus chart dashboard composition, repeated title-description-card blocks, unnecessary containers, duplicate section headers, presentation-first whitespace, modals for persistent or complex workflows, desktop layouts merely stacked into cards on mobile.

Prefer the simplest structure that communicates hierarchy. Use alignment, spacing, typography, dividers, and surface changes before adding another container.

## Content Slop
Remove generic filler such as greetings or descriptions that do not change a decision. Helper text must prevent error, explain unfamiliar concepts, communicate constraints, or provide useful context. Do not repeat a visible label in helper text. Use realistic domain content when available.

UI copy must earn its space.

## Interaction Slop
Audit for multiple competing primary CTAs, unnecessary confirmation dialogs, one-item dropdowns, ambiguous icon-only controls, hover-only essential actions, filters without a real filtering need, tabs used for unrelated navigation, complex workflows forced into dialogs, and status communicated only by color.

## Dashboard Rule
Do not assume dashboard means KPI cards plus charts. Determine the decisions and actions users need first. Operational products often benefit more from queues, exceptions, recent changes, approvals, searchable records, and actionable status than vanity metrics.

## Card Rule
Use a card when content is a meaningful independent group or surface. Do not use cards merely to create separation. Prefer whitespace, dividers, grid alignment, or section hierarchy when sufficient.

## Decoration Budget
A strong visual effect increases the burden of justification. The more prominent the gradient, shadow, animation, color, radius, or illustration, the clearer its brand or interaction purpose must be.

## Real Content Test
Test meaningful screens with normal, long, missing, empty, loading, error, permission-limited, and high-volume data where relevant. A layout that works only with short placeholder content is not complete.

## Anti-Slop Completion Gate
Before completion verify: primary task is obvious, hierarchy works without decorative effects, no component exists only to fill space, no filler copy remains, actions have clear priority, cards and charts are justified, real content survives, and the result still belongs to the product's design language.
