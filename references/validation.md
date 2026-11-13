# Evidence-Based UI Validation
Technical correctness is necessary but insufficient.
Reference loop: IMPLEMENT → RENDER → COMPARE → IDENTIFY DELTAS → FIX → RENDER AGAIN. Never stop after first render.
Compare composition, alignment, density, whitespace, typography personality/scale, color roles, image crop/proportions, component proportions, hierarchy, asset language, responsive behavior.
Test relevant states only when in scope. Run project typecheck/lint/tests/build as appropriate.
Record viewports, deltas corrected, remaining fidelity gaps, accessibility, anti-slop, token compliance, technical results. Never claim pixel-perfect when distinctive assets/fonts are unavailable.
