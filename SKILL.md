---
name: skill-design-by-nyxwork-v3
description: Design and refine distinctive frontend UI with clear UX hierarchy, anti-slop decisions, brand guidelines, visual reference fidelity, and responsive validation. Use for new screens, landing pages, components, design systems, and redesigns.
metadata:
  version: "3.1.1"
  author: NyxWork
---

# Design by NyxWork V3

## Purpose
Turn a simple user request into intentional, usable, recognizable UI. This file is the controller; references provide operational guidance. Keep the user experience lightweight while doing disciplined design work internally.

## Core contract
Understand → Inspect → Set direction → Build → Inspect the result → Refine.
Start with the user job, then information hierarchy, interaction, composition, typography, assets, and styling. Anti-slop means justified choices, not compulsory minimalism.

## Low-friction operation
- Accept ordinary prompts; users do not need to supply a design brief, select a category, name references, or approve every stage.
- Infer sensible, local, reversible visual decisions. State only assumptions that materially affect the outcome.
- Ask a focused question only when missing information changes the core workflow, mandatory brand interpretation, or requested scope. Continue independent work where possible.
- Do not invent business claims, testimonials, metrics, integrations, or working functionality. Use supplied content or clearly identified sample content when needed.
- Do not require a design-system document or long compliance report for a small edit. Scale artifacts and validation to impact.

## One source-of-truth policy
All references inherit this policy; inspection order never changes authority.
1. Explicit user requirements and approved scoped exceptions.
2. Supplied mandatory brand guidelines and approved brand assets: identity constraints.
3. Approved visual references: only the dimensions they are intended to control.
4. Existing coherent design system, reusable components, semantic tokens, and product patterns.
5. NyxWork principles and local agent judgment.

Assign sources by dimension: brand controls identity; reference controls its agreed composition/treatment; product requirements control behavior. Reference colors do not silently replace mandatory brand colors. An existing component may be extended when the approved target requires it.
For unresolved material conflicts, explain the specific collision and ask once; do not silently average. For nonmaterial gaps, proceed with a reversible interpretation. User overrides stay scoped; do not claim accessibility or brand compliance when an override breaks it.

### Established-system boundary
When a project has an established design system, treat it as the default implementation boundary. Agent assumptions and inspiration references do not authorize departures. Higher-priority sources establish intent, but a conflicting reference alone is not approval to change the system: adapt it within the system unless the user explicitly requests that system-level change. Explain material conflicts and obtain a scoped decision before changing the contract.
New compositions and genuinely missing components are allowed within existing tokens, patterns, accessibility contracts, and architecture. Do not seek approval for routine compliant reuse or composition. If a required capability cannot fit without changing the system, explain the gap and ask a focused question while continuing independent work.

## Adaptive reference loading
Select the closest task internally; no user classification ceremony. Paths below are relative to `references/`. Read applicable files before decisions they govern. Reuse guidance already loaded in the current context.

| Task | Read |
| --- | --- |
| New UI, with or without reference | `ui-decision-framework.md`, `visual-direction.md`, `anti-ai-slop.md`, `responsive-accessibility.md`, `validation.md` |
| Existing UI refinement | `anti-ai-slop.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md` |
| Design system creation | `ui-decision-framework.md`, `design-system-generator.md`, `token-generator.md`, `anti-ai-slop.md`, `responsive-accessibility.md`, `validation.md` |
| Redesign / migration | `ui-decision-framework.md`, `redesign-migration.md`, `visual-direction.md`, `anti-ai-slop.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md` |
| Component-only work | `component-governance.md`, `anti-ai-slop.md`, `responsive-accessibility.md`, `validation.md` |

Cross-cutting triggers for every task:
- Brand guideline or brand assets supplied → `brand-guideline-analysis.md`.
- Visual reference supplied → `visual-reference-analysis.md`.
- Creating/changing typography, color roles, spacing, sizing, radius, elevation, or state tokens → `token-generator.md`.
- Creating/extending reusable components → `component-governance.md`.
- Establishing a shared visual system → `design-system-generator.md`.
- Creating a visual direction from an incomplete brief → `visual-direction.md`.

For a tiny change, apply the relevant sections without expanding into unrelated redesign. Never claim a reference was read if it was not.

## Before implementation
Establish a compact working direction: primary user job and action; screen type; information priority; source responsibilities; brand constraints; reusable patterns; visual anchors; asset availability; responsive transformation; relevant states and accessibility.
Keep this internal for simple tasks. For substantial new UI, give the user a brief direction statement and proceed unless approval was requested. Use `templates/design-brief.md` only when a persistent brief helps collaboration.

## Design execution rules
- Existing product: inspect → reuse → extend → refine. Preserve working behavior unless scope changes it.
- Inspect architecture before component creation: map application entry points, route/layout shells, design-system/theme sources, component layers and public exports, state/data boundaries, and representative consumers across features. Follow conventions and instructions in the repository. Inspect enough breadth to find shared equivalents; do not read every file or use inspection as a reason for unrelated rewrites.
- Hierarchy: make the primary task obvious through order, scale, proximity, alignment, contrast, and progressive disclosure. One dominant action per task context, not an arbitrary one-button rule for the whole screen.
- Distinctiveness: use a coherent composition, type personality, imagery, rhythm, and brand signatures. Do not add novelty to compensate for weak structure. Usable conventions remain valuable.
- Reference fidelity: choose faithful reproduction, brand adaptation, or directional inspiration. Infer from the request and state the mode briefly if ambiguity matters. Preserve the defining anchors for that mode.
- Asset fidelity: exact supplied asset → compatible project asset → intentionally matching created asset → neutral placeholder. Disclose material substitutions; never silently replace distinctive art with emoji or unrelated stock.
- Tokens: inspect existing roles, reuse, then add justified semantic tokens. Templates demonstrate structure, never a mandatory NyxWork palette or type style.
- Components: equivalent existing components must be reused through their intended public API. Check variants and primitive compositions before creation. Do not duplicate by renaming, copying markup, or adding a parallel local wrapper with the same responsibility. Extend coherent APIs only for a real capability gap; create new components only when no suitable equivalent exists and document that gap briefly. Preserve ownership, dependency direction, and state/data boundaries. See `component-governance.md`.
- Expression: gradients, shadows, large type, rounded forms, and rich illustration are valid when supported by brand, reference, or communication purpose. Restraint is a fallback, not a universal aesthetic.
- Responsive: choose Preserve / Reflow / Wrap / Collapse / Scroll / Hide / Reorder per region. Preserve critical tasks, readable content, and reachable controls.
- Content: use meaningful, domain-specific labels; distinguish sample data from factual claims. Cover relevant empty, loading, error, and long-content states without inventing backend behavior.

## Validation and honest completion
Use `validation.md`: check workflow and accessibility, composition, typography/assets, proportions/spacing, then detail. For material visual changes, inspect the rendered result when tools are available, correct important deltas, and inspect again after corrections. Do not perform an extra render ritual when nothing changed.
Run technical checks appropriate to the actual implementation. If runtime, assets, or browser access is unavailable, finish feasible work and report the exact unverified areas. Missing tools are a limitation, not a reason to fabricate evidence or block useful delivery.

Final response scales to the task: summarize changes, meaningful design decisions, checks actually run, and remaining gaps. For substantial brand/reference work, include source interpretation and any deviations. Detailed audit tables are optional unless requested.

Done means the requested scope works, hierarchy is clear, brand constraints are respected or exceptions disclosed, design choices form a coherent language, relevant responsive/accessibility checks are performed, and remaining limitations are explicit. Never claim full compliance or pixel-perfect fidelity without evidence.
