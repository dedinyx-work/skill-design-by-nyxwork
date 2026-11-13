# Responsive and Accessible by Design

Adapt structure to task and content. Choose Preserve / Reflow / Wrap / Collapse / Scroll / Hide / Reorder per major region. Use project breakpoints or content-driven thresholds; do not automatically invent a mobile drawer or turn every table into cards.

## Responsive checks
- Preserve primary tasks, critical information, navigation access, and understandable action order.
- Check gutters, readable typography, image crop, long labels, large numbers, and missing data.
- Avoid accidental page-level horizontal overflow; intentional table/region scrolling needs clear boundaries.
- Check fixed/sticky controls, zoom, safe areas, and dialog content scrolling.
- Inspect a representative wide and narrow viewport for material layout changes; add intermediate sizes where the layout transitions or fails.

## Accessibility baseline
Use semantic controls, meaningful headings/landmarks, accessible names, persistent form labels, logical reading/focus order, visible unobscured focus, and keyboard-operable interactions.
Use WCAG AA contrast targets where applicable: 4.5:1 for normal text, 3:1 for large text and required non-text control/state indicators. Distinguish status beyond color. Do not claim a full WCAG audit from a partial check.
Prefer touch-friendly targets around 44×44 CSS px. WCAG 2.2 AA target-size criteria have a 24×24 CSS px baseline with spacing and other exceptions; verify the actual design rather than declaring every smaller target a failure.
Dialogs manage initial focus, containment where appropriate, dismissal, and return focus. Forms retain recoverable input and expose actionable errors. Essential actions cannot depend on hover alone.
Respect reduced motion when motion exists; avoid unnecessary vestibular or flashing effects. Test relevant states and content resilience, not every theoretical state on every edit.

If brand constraints create an accessibility conflict, use `brand-guideline-analysis.md`; do not silently modify official values or certify unresolved issues.
