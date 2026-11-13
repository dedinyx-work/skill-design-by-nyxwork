---
name: skill-design-by-nyxwork-v3
description: Intent-first anti-AI-slop product UI governance for AI coding agents.
metadata:
  version: 3.0.0
  author: NyxWork
---

# Design by NyxWork V3

## Purpose
Controller for frontend design decisions. V3 is an execution contract, router, and completion gate; detailed rules live in `references/`.

## Core Principle
Every visible element must justify its presence through workflow, hierarchy, interaction need, brand language, or system consistency.

Product intent → User job → Information architecture → Interaction model → Visual hierarchy → Component selection → Styling → Rendered validation.

## Mandatory Execution Contract
INTENT → REFERENCE ANALYSIS → UI DECISION → ANTI-SLOP → TOKENS → COMPONENT GOVERNANCE → RESPONSIVE/ACCESSIBILITY → IMPLEMENTATION → RENDER VALIDATION → COMPLIANCE REPORT.

Never claim NyxWork compliance if a required stage/reference was skipped.

## Source of Truth
1. Explicit user requirements and approved decisions
2. Approved visual reference for the requested screen
3. Existing coherent product design system
4. Existing reusable components and semantic tokens
5. Existing product/page/interaction patterns
6. NyxWork governance
7. Simplest intentional solution
8. Agent judgment

Identify material conflicts; never silently average them.

## Mandatory Reference Loading Gate
### A — New UI from visual reference
MUST load: `visual-reference-analysis.md`, `ui-decision-framework.md`, `anti-ai-slop.md`, `token-generator.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md`.
Load `design-system-generator.md` if no coherent system exists or one must be formalized.

### B — Existing UI refinement
MUST load: `visual-reference-analysis.md` when a reference exists, `anti-ai-slop.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md`.
Also load `token-generator.md` whenever tokens/typography/spacing/radius/elevation/color roles change.

### C — Design system creation
MUST load: `ui-decision-framework.md`, `token-generator.md`, `design-system-generator.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md`.

### D — Redesign / migration
MUST load: `visual-reference-analysis.md` when references exist, `ui-decision-framework.md`, `redesign-migration.md`, `anti-ai-slop.md`, `token-generator.md`, `component-governance.md`, `responsive-accessibility.md`, `validation.md`.

### E — Component-only work
MUST load: `component-governance.md`, `anti-ai-slop.md`, `responsive-accessibility.md`, `validation.md`.

Mandatory references may not be silently skipped.

## Pre-Implementation Gate
Before editing UI code establish internally: task classification; product intent/user job; source of truth; information hierarchy; extracted visual characteristics; design-system status; reusable components; token impact; responsive strategy; accessibility; unsupported assumptions; asset fidelity limitations.

## Inspect Before Create
Existing products: Inspect → Reuse → Extend → Refine.

## Anti-Invention Rule
Do not invent unsupported sections, navigation, filters, badges, dashboards, cards, gradients, shadows, glass, decorative containers, illustrations, icons, interactions, mobile navigation, footer structures, or product behavior. A new element needs support from requirement, approved reference, established pattern, or necessary accessibility/interaction constraint.

## Asset Fidelity Rule
Distinctive photography/illustration/iconography/texture/hand lettering:
Exact supplied asset → close project asset → intentionally created matching asset → neutral placeholder.
Never silently downgrade to emoji, generic icons, crude SVGs, or unrelated stock assets.

## Token-First Rule
Consume semantic tokens when roles exist. Avoid repeated raw hex, arbitrary spacing/radii/type/shadows. Inspect → reuse → create justified semantic token → document true one-off exception.

## Typography Governance
Evaluate personality, hierarchy, role, weight, scale, line height, and letter spacing. Do not default to generic geometric sans when the approved reference communicates another personality.

## Component Governance
Create/extend based on repeated visual pattern, behavior, or semantic product role. Avoid monoliths and premature generic UI kits.

## Responsive Transformation
Never desktop → shrink → stack. For each region choose Preserve / Reflow / Wrap / Collapse / Scroll / Hide / Reorder. Validate touch targets, overflow, safe areas, typography, image crop, and scroll boundaries.

## Anti-AI-Slop Gate
Audit unsupported excessive cards, nested cards, floating shadows, glass, gradients, pills, radius, decorative icon containers, filler copy, badges, generic dashboard patterns, fake metrics, presentation-first whitespace, and filters/interactions without need.

## Visual Validation Loop
IMPLEMENT → RENDER → COMPARE → IDENTIFY DELTAS → FIX → RENDER AGAIN.
Compare composition, alignment, density, whitespace, typography, color, image/component proportions, hierarchy, assets, and responsive behavior. Technical checks alone are insufficient.

## Self-Correction
If output diverges materially, return to reference analysis and fix the underlying decision before adding patch CSS.

## Compliance Report
Report: Task classification; References loaded; Source of truth; Tokens reused/created; Components created/reused; Responsive strategies; Accessibility checked; Anti-slop checked; Visual comparison completed; Known fidelity gaps.
If any mandatory reference was skipped: `NyxWork execution = INCOMPLETE`.

## Deviation Protocol
Explicit user requests win. Keep exceptions scoped and preserve unrelated system rules.

## Definition of Done
Primary user job clear; required references loaded; hierarchy/brand intentional; reusable patterns inspected; semantic tokens respected; responsive/accessibility intentional; anti-slop and rendered QA pass; technical checks pass; fidelity gaps disclosed.
