# Project Design System

> Generated from Skill Design by NyxWork.
> Replace placeholders with project-specific decisions.

## 1. Product Context

Product:
Audience:
Primary workflows:
Platform:
Primary device target:

## 2. Visual Direction

Describe the intended visual language in 2–4 sentences.

Example structure:

- Density:
- Surface model:
- Border model:
- Radius behavior:
- Typography feel:
- Brand accent behavior:
- Interaction feel:

## 3. Design Principles

1.
2.
3.
4.
5.

## 4. Source of Truth

Priority:

1. Explicit product requirements
2. Existing approved design assets
3. This design system
4. Shared components
5. Design tokens
6. Local implementation judgment

## 5. Color Roles

| Role | Token | Value | Usage |
| --- | --- | --- | --- |
| App background | `--color-bg-app` |  |  |
| Surface | `--color-bg-surface` |  |  |
| Surface subtle | `--color-bg-subtle` |  |  |
| Selected | `--color-bg-selected` |  |  |
| Border | `--color-border-default` |  |  |
| Border strong | `--color-border-strong` |  |  |
| Text primary | `--color-text-primary` |  |  |
| Text secondary | `--color-text-secondary` |  |  |
| Text muted | `--color-text-muted` |  |  |
| Brand primary | `--color-brand-primary` |  |  |
| Brand hover | `--color-brand-primary-hover` |  |  |
| Success | `--color-status-success` |  |  |
| Warning | `--color-status-warning` |  |  |
| Error | `--color-status-error` |  |  |
| Info | `--color-status-info` |  |  |
| Focus | `--color-focus` |  |  |

## 6. Typography

Font family:
Heading family:
Numeric behavior:

| Role | Size | Weight | Line Height |
| --- | ---: | ---: | ---: |
| Page title |  |  |  |
| Section title |  |  |  |
| Card title |  |  |  |
| Body |  |  |  |
| Label |  |  |  |
| Metadata |  |  |  |
| Metric |  |  |  |

## 7. Spacing

Base unit:

Approved spacing scale:

- `--space-1`:
- `--space-2`:
- `--space-3`:
- `--space-4`:
- `--space-5`:
- `--space-6`:
- `--space-8`:
- `--space-10`:
- `--space-12`:

## 8. Sizing

Control height small:
Control height default:
Control height large:
Icon size small:
Icon size default:
Sidebar width:
Header height:
Content max-width:
Minimum interactive target:

## 9. Radius

- `--radius-xs`:
- `--radius-sm`:
- `--radius-md`:
- `--radius-lg`:
- `--radius-pill`:
- `--radius-circle`:

Component usage:

- Buttons:
- Inputs:
- Cards:
- Panels:
- Badges:
- Avatars:

## 10. Borders

Default border:
Subtle divider:
Strong border:
Focus border:

## 11. Elevation

Standard surface:
Raised surface:
Overlay:
Modal:

## 12. Iconography

Icon family:
Style:
Stroke:
Default size:
Icon-only accessibility rule:

## 13. Component Rules

### Button

Primary:
Secondary:
Ghost:
Destructive:
Sizes:
Radius:
States:
Avoid:

### Input

Height:
Surface:
Border:
Focus:
Error:
Disabled:

### Card

Purpose:
Surface:
Border:
Radius:
Shadow:
Padding:
Avoid:

### Table

Density:
Header:
Row height:
Borders:
Hover:
Numeric alignment:
Responsive behavior:

### Badge

Purpose:
Size:
Radius:
Semantic color behavior:
Avoid:

### Tabs

Active state:
Inactive state:
Overflow behavior:

### Navigation

Active state:
Hover:
Density:
Responsive behavior:

### Dropdown / Popover

Surface:
Border:
Radius:
Shadow:
Keyboard behavior:

### Modal / Dialog

Width:
Padding:
Elevation:
Focus behavior:
When to use:
When not to use:

## 14. Interaction States

Define:

- Hover
- Focus
- Active
- Selected
- Disabled
- Loading
- Error
- Success

## 15. Responsive Rules

Large desktop:
Desktop:
Tablet:
Mobile:

Structural rules:

- Grid:
- Sidebar:
- Filters:
- Tables:
- Dialogs:

## 16. Accessibility Baseline

- Focus:
- Contrast:
- Labels:
- Icon buttons:
- Keyboard:
- Status communication:
- Motion:

## 17. Anti-Patterns

Do not use:

-
-
-
-
-

## 18. Implementation Rules

- Reuse existing components before creating new ones
- Use semantic tokens
- Avoid arbitrary styling
- Keep local exceptions scoped
- Validate responsive behavior and accessibility
