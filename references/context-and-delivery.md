# Context and Delivery Contract

Inherit all authority, established-system boundaries, and reuse rules from `SKILL.md`. This contract makes design work inspectable without requiring the user to prepare a brief or approve routine steps.

## 1. Assemble context
Read existing direction (`DESIGN.md` or equivalent), brand sources, architecture, tokens/components, references, and relevant product content. A filename is not mandatory; use the project's actual source of truth.
For substantial work, give a compact context snapshot before building:

```text
Task: [user job, screen, scope]
Authority: [brand/system sources and the dimensions they control]
Direction: [composition, type/imagery character, density]
Reuse: [canonical components/layouts and verified gaps]
Reference: [mode and defining anchors, or none]
Assumptions: [material inference or missing assets only]
```

Use a few sentences rather than six headings when that is clearer. For incomplete briefs, infer a coherent reversible direction; do not label all work without a brand document as unusable. Persist context only when it will help future screens or sessions. Never overwrite user direction with inferred rules.

Distinguish direction from filtering: context establishes the intended visual character; anti-slop checks test whether choices serve it. Neither decorative excess nor a sterile neutral default is automatically good design.

## 2. Apply stable governance checks
These IDs summarize obligations defined by the controller and detailed references; they do not create an alternative authority hierarchy.

| ID | Check | Evidence to inspect |
| --- | --- | --- |
| NW-01 | Architecture and canonical sources inspected | Relevant paths, public exports, representative consumers. |
| NW-02 | Equivalent components reused | Imports/variants/compositions; verified reason for any new component. |
| NW-03 | Established-system and brand boundaries respected | Source rules, token use, scoped authorized departures. |
| NW-04 | Hierarchy supports the user job | Reading order, grouping, primary action, appropriate structure. |
| NW-05 | Visual character fits the context | Composition, typography, imagery, density; purposeful expression. |
| NW-06 | Reference fidelity matches the chosen mode | Anchor comparison; material substitutions and inferred behavior. |
| NW-07 | Content and interactions are honest | Source claims, real destinations, implemented behavior or clear prototype limitations. |
| NW-08 | Responsive and accessibility checks fit the scope | Relevant viewports, keyboard/focus, labels, contrast, content resilience. |
| NW-09 | Outcome validation is evidence-based | Render observations, interaction checks, actual technical results. |

Rules that protect reuse, mandatory constraints, truthfulness, and core usability are requirements. Visual techniques are purpose-based choices, not universal bans. Optional polish must not be reported as a blocker without a material impact.

## 3. Report actual status
- **PASS**: an applicable check was performed and supported by stated evidence.
- **FAIL**: an observed issue remains; state impact and next action.
- **UNVERIFIED**: applicable, but tools/evidence are unavailable or the check was not performed.
- **N/A**: genuinely outside scope, with a short reason when unclear.

Do not turn a declaration into evidence. Code inspection can support reuse/token checks but cannot by itself prove visual fidelity or keyboard behavior. Do not claim an overall PASS while material applicable checks fail or remain unverified.

For substantial delivery, use a compact format:

```text
Implemented: [what changed]
Decisions: [important context-led choices and reuse/gap decisions]
Checks: [ID/status with concise evidence, grouped when appropriate]
Remaining: [unverified checks, material gaps, approved exceptions]
```

Use `templates/delivery-report.md` only when a table helps. No mandatory document creation, numerical design score, or full checklist for a tiny edit. A serious blocker must be fixed where feasible, or the result explicitly described as partial.

## 4. Audit-only output
Inspect without changing files when the user asks only for a review. Give numbered findings:
`Priority | NW-ID | Location | Observed evidence | User impact | Suggested correction`.
Prioritize by actual impact: high for broken tasks, equivalent duplicates or material system/brand violations; medium for hierarchy/fidelity problems; low for localized polish. Never assert a violation from a fashionable technique alone.
If the user has already requested fixes, act within that scope without a second approval ritual. Findings do not authorize unrelated refactors.
