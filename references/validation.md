# Proportional, Evidence-Based Validation

Validate outcomes, not completion rituals. Technical success alone does not prove good UI; a screenshot alone does not prove working interactions.

## Depth by impact
- Tiny copy/token/local styling edit: inspect the affected region and relevant technical checks; avoid unrelated full-product audits.
- Material screen or layout change: inspect actual render at representative wide/narrow viewports, relevant states, and the main task path.
- Brand/reference-heavy work: compare the defining anchors against source material, using matching viewport/region where appropriate.
- Design-system migration: inspect representative consumers and shared-component regressions before expanding.

## Inspection order
1. Workflow, missing essential content, keyboard/accessibility, broken controls.
2. Composition, reading order, hierarchy, alignment, density.
3. Actual typography, assets, brand rules, reference anchors.
4. Component/image proportions, spacing, responsive transformations.
5. Color roles, borders, effects, interaction polish.

Fix material deltas and inspect again after changes. Stop when the requested scope meets the quality bar and remaining gaps are explicit; do not demand pointless extra renders or endless polish.

## Evidence
For substantial work keep concise notes, using `templates/validation-notes.md` only if helpful:
`Check | Viewport/state | Evidence/tool result | Observed issue | Correction/result`.
Evidence may be a screenshot, browser observation, computed font/style inspection, keyboard interaction, or named technical command result. Distinguish observed, inferred, and unverified. Never fabricate file paths, tool results, usability studies, or a passing audit.
Screenshots compare appearance; test actual interactions separately. Inspect loaded fonts rather than assuming a declared CSS family was used. Run lint/typecheck/tests/build according to implementation risk and project conventions.

## Completion and fallback
Blockers are broken core tasks, material mandatory-brand violations, major reference-anchor mismatches in faithful mode, or serious accessibility/layout failures. Fix feasible blockers before claiming completion.
If tools, fonts, assets, or runtime are unavailable, deliver feasible changes and identify exact checks/gaps still unresolved. Do not require the user to configure extra tooling for every small task.
Final summary: meaningful changes, checks actually performed, and remaining limitations. Add source mode, brand deviations, or evidence detail when relevant; a long compliance report is not mandatory.
