# UI/UX Hierarchy and Decision Framework

Inherit source authority from `SKILL.md`. Apply principles to the actual task, not as rigid layout recipes.

## 1. Identify the task
Determine primary user, job, critical information, primary action, frequency, and cost of mistakes. Infer from the brief and existing product; ask only for material ambiguity.
Choose a screen model: task completion, browsing/discovery, comparison, monitoring, editorial/storytelling, or conversion. A marketing page and an operations screen need different density and pacing.

## 2. Order information
Put task-critical information and current state near the action they support. Group related content by proximity and common alignment; separate unrelated groups with space, headings, or dividers before adding containers.
Use progressive disclosure for secondary complexity while keeping essential information discoverable. Preserve predictable navigation, orientation, and back/exit paths.

## 3. Choose the right structure
| User need | Starting pattern | Avoid |
| --- | --- | --- |
| Compare records across attributes | Table with clear columns | Turning every row into a large card |
| Scan heterogeneous items | List or editorial feed | Forced columns that obscure identity |
| Browse independent visual objects | Grid/cards | Wrapping every paragraph in a card |
| Switch sibling views of one context | Tabs | Tabs for unrelated destinations |
| Complete complex or persistent work | Full page or staged flow | Overloaded modal |
| Make a short focused decision | Dialog | Interruptions for harmless reversible actions |
| Edit secondary contextual details | Drawer/panel where appropriate | Losing parent context unnecessarily |

These are defaults, not mandates. Existing accessible patterns and approved direction can justify alternatives.

## 4. Establish visual priority
- Use document order, position, type scale/weight, whitespace, grouping, and contrast together. Color alone must not carry importance or state.
- Give the main action clear emphasis within its task context. Keep competing actions quieter; destructive actions need distinct meaning, not dominant decoration.
- Titles orient; section headings organize; body copy explains; metadata stays readable. Avoid oversized titles that push the real task out of view.
- Align repeated elements and numeric data consistently. Set density for scanning needs and content volume.
- Use recognizable controls and affordances. A unique art direction does not require unfamiliar interaction.

## 5. Support completion and recovery
Forms use persistent labels, logical grouping, suitable input types, clear required/optional meaning, and actionable field-level errors. Preserve input on recoverable errors.
Show timely feedback for actions. Plan relevant loading, empty, error, success, permission, and partial-data states. Confirm actions when consequences justify interruption; offer undo when suitable.
Dialogs need focus management and return focus. Hidden or hover-only controls must not make essential tasks inaccessible.

## 6. Check the hierarchy
At a glance, can a user identify where they are, what matters, and what to do next? Does reading order match visual order? Does the primary task remain clear on mobile, with long content, and without decorative effects?
Fix workflow and comprehension before cosmetic polish. Do not describe a heuristic review as user research or usability testing.
