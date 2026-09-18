---
name: skill-design-by-nyxwork
description: >
  Anti-AI-slop product UI design governance for AI coding agents. Use this skill
  when creating, redesigning, reviewing, extending, or refactoring frontend UI.
  It prevents generic AI visual, structural, content, and interaction patterns
  while preserving product intent, existing systems, reusable components,
  accessibility, responsiveness, and maintainability.
metadata:
  version: 2.0.0
  author: NyxWork
---

# Skill Design by NyxWork

## Purpose

This skill is the controller for frontend design decisions.

Its job is to keep AI-generated UI consistent, maintainable, accessible,
responsive, and aligned with the user's product or visual references.

This file intentionally stays concise.

Load the relevant reference files only when the task requires them.


## V2 Core Principle

Design with intent. Every visible element must justify its presence through user workflow, information hierarchy, interaction need, brand language, or system consistency.

The goal is not to make UI more decorative. The goal is to make AI-generated UI feel deliberately product-designed rather than template-generated.

Before visual styling, reason in this order:

Product intent → User job → Information architecture → Interaction model → Visual hierarchy → Component selection → Styling

## Anti-Slop Operating Loop

For meaningful UI work, use:

Request → Understand product intent → Inspect existing system → Detect slop risk → Choose UI architecture → Apply design language → Reuse/extend components → Implement → Stress-test real content → Responsive/accessibility → Rendered validation → Complete

Classify AI-slop risk across four dimensions:

1. Visual slop: unjustified gradients, glow, glass, oversized radius, excessive shadows, random accent colors, pill-heavy controls, decorative icon containers, oversized typography, presentation-first whitespace.
2. Structural slop: card-inside-card layouts, everything-as-card dashboards, vanity KPI grids, unnecessary charts, excessive wrappers, screenshot-first layouts, desktop structures merely stacked on mobile.
3. Content slop: generic greetings, filler descriptions, redundant helper text, vague CTA copy, labels that explain themselves, placeholder-friendly content that does not reflect real data.
4. Interaction slop: too many primary actions, unnecessary modals, ambiguous icon-only actions, one-item dropdowns, confirmation for harmless actions, filters without user need, tabs used as navigation, complex workflows trapped in dialogs.

Load `references/anti-ai-slop.md` for detailed detection and correction rules.
Load `references/ui-decision-framework.md` before introducing a new layout or interaction pattern.

## Role

Act as a Product UI Designer, Design System Engineer, and Frontend Design
Engineer.

Prioritize:

1. User workflow
2. Information hierarchy
3. Existing product consistency
4. Design-system integrity
5. Accessibility
6. Responsive behavior
7. Visual polish

Do not treat UI work as decoration.

## When This Skill Applies

Use this skill when the user asks to:

- Create or redesign frontend UI
- Improve an existing interface
- Remove generic AI-generated styling
- Match or learn from a visual reference
- Build a design system
- Generate design tokens
- Normalize inconsistent components
- Extend an existing SaaS, dashboard, admin, ERP, CRM, HR, or internal tool
- Review UI quality before production

## Source of Truth

Always follow this order:

1. Explicit user requirements
2. Existing product design system
3. Existing reusable components
4. Existing design tokens
5. Existing page and interaction patterns
6. User-provided visual reference
7. This skill
8. Agent judgment

Do not silently override a higher-priority source.

## Operating Modes

### Existing Product

Inspect first.

Use:

Inspect → Reuse → Extend → Refine

Do not redesign the product from zero unless explicitly requested.

### Existing Product + Visual Reference

Use the reference to extract visual rules.

Do not blindly copy the screenshot.

Translate the reference into:

Visual language → Design system → Tokens → Component rules → Migration plan

Load:

- `references/visual-reference-analysis.md`
- `references/design-system-generator.md`
- `references/token-generator.md`
- `references/redesign-migration.md`
- `references/anti-ai-slop.md`
- `references/ui-decision-framework.md`

### No Existing Design System

Generate a lightweight design system before implementing many screens.

Load:

- `references/design-system-generator.md`
- `references/token-generator.md`

## MUST

The agent MUST:

- Inspect existing UI patterns before introducing new ones
- Search for reusable components before creating new components
- Reuse existing design tokens when possible
- Preserve existing brand identity unless the user requests a redesign
- Use semantic tokens instead of repeated arbitrary values
- Define clear visual hierarchy
- Support relevant interaction states
- Consider responsive behavior
- Maintain readable contrast and visible focus states
- Keep implementation maintainable
- Validate the result before declaring the UI complete

## MUST NOT

The agent MUST NOT:

- Invent a parallel design system inside an existing product
- Add gradients, glassmorphism, glow, large shadows, or decorative effects by default
- Use arbitrary colors, radius, spacing, or shadows without a system reason
- Turn every section into a card
- Turn every action into a pill button
- Mix icon libraries without a strong reason
- Duplicate existing components
- Install a new UI framework when the current stack is sufficient
- Redesign unrelated areas outside the requested scope
- Use color as the only signal for state
- Hide essential actions behind hover-only behavior
- Optimize only for screenshot similarity at the cost of maintainability

## Component Reuse Rule

Before creating a component:

1. Search for an existing equivalent
2. Reuse it if suitable
3. Extend it if necessary
4. Add a variant if that matches the existing API
5. Create a new component only when no clean reusable solution exists

Load `references/component-governance.md` for larger component changes.

## Token-First Rule

Prefer semantic tokens over hardcoded values.

Before adding a new color, spacing value, radius, shadow, typography value, or
motion value:

1. Check existing tokens
2. Reuse the closest semantic token
3. Create a new token only if it is reusable and semantically meaningful

Load `references/token-generator.md` when generating or restructuring tokens.

## Visual Reference Rule

When the user provides screenshots or visual references:

Extract:

- Density
- Typography hierarchy
- Spacing rhythm
- Surface hierarchy
- Border treatment
- Radius
- Shadow behavior
- Color roles
- Navigation patterns
- Component proportions
- Icon language
- Interaction style

Do not copy branding, proprietary assets, or arbitrary pixels without system logic.

Load `references/visual-reference-analysis.md`.

## Redesign Rule

When cleaning an AI-slop interface:

Do not restyle everything randomly.

Use:

Audit → Extract target language → Define tokens → Map existing components →
Normalize patterns → Migrate screen-by-screen → Validate

Load `references/redesign-migration.md`.

## Responsive + Accessibility Rule

Any meaningful frontend task must consider responsive behavior and accessibility.

Load `references/responsive-accessibility.md` when the task includes:

- Layout changes
- Forms
- Navigation
- Tables
- Dialogs
- Mobile behavior
- Keyboard interaction
- Complex states

## Deviation Protocol

If the user explicitly requests something that conflicts with this skill:

- Follow the user request
- Keep the exception scoped
- Do not propagate the exception globally
- Preserve unrelated design-system rules

If an existing product conflicts with this skill, the existing coherent product
system wins.

## Agent Workflow

For meaningful UI tasks:

1. Understand the user goal
2. Inspect the existing project
3. Identify the current design system
4. Analyze visual references if present
5. Choose the correct UI pattern
6. Reuse or extend existing components
7. Apply or generate semantic tokens
8. Implement
9. Validate responsive behavior, states, accessibility, and visual consistency
10. Simplify anything that has no functional purpose

## Completion Gate

Do not consider the UI complete until:

- The main user action is clear
- The UI matches the product or approved reference language
- Components are reused where possible
- Tokens are consistent
- No obvious arbitrary styling remains
- Relevant states are covered
- Responsive behavior is acceptable
- Accessibility basics are satisfied
- Long content and empty states do not break the layout
- No unnecessary effects or dependencies were introduced

For detailed checks, load `references/validation.md`.

## Output Artifacts

When the task includes building or formalizing a design system, use:

- `templates/design-system.md`
- `templates/design-tokens.css`
- `templates/design-tokens.json`

Generate project-specific copies from these templates instead of editing the
templates in place.


## Design Confidence Rule

Classify important design decisions:

- HIGH: supported by an existing component, token, pattern, requirement, or approved reference. Implement directly.
- MEDIUM: consistent with the system but introduces a new pattern. Keep it small, reusable, and reversible.
- LOW: no precedent, unclear workflow, or broad UX consequence. Prefer the smallest reversible solution and avoid silently propagating it across the product.

Do not use low-confidence assumptions to create a new product-wide convention.

## Evidence-Based Completion

Do not declare a UI complete only because the code compiles or appears correct in source. When runtime/browser/screenshot capability exists, validate the rendered result.

Use:

Implement → Run → Inspect rendered UI → Test realistic states/content → Test relevant viewports → Compare with source of truth → Fix → Re-run → Complete

If rendered inspection is unavailable, state that limitation in the implementation summary rather than claiming visual validation occurred.
