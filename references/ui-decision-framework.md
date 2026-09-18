# UI Decision Framework

## Objective
Choose UI structures from user intent and information behavior instead of default AI patterns.

## Start With the Job
Before choosing components identify: primary user, primary job, primary decision, primary action, critical information, frequency of use, and consequence of mistakes.

## Information Architecture
Order information by task importance, not visual novelty. Prefer: task-critical information, primary action, current state, supporting context, secondary actions, optional detail.

## Pattern Selection
Use a table when users compare structured records across consistent attributes. Use a list when items are heterogeneous or scanning the item identity matters more than column comparison. Use cards for independent grouped objects or summaries, not as the default container. Use tabs for sibling views of the same context. Use page navigation for distinct destinations. Use a drawer for contextual secondary work that benefits from preserving the parent context. Use a modal for short, focused, interruptive decisions. Use a full page for complex, persistent, multi-section, or multi-step work. Use a popover/dropdown for compact transient choices.

## Actions
A screen should normally have one visually dominant primary action per task context. Secondary and tertiary actions must be quieter. Do not make every action filled or brand-colored.

## Forms
Group fields by user mental model and task sequence. Do not create sections solely to make the form look designed. Use persistent labels when ambiguity or validation matters. Helper text only when useful.

## Data-Dense Products
For ERP, CRM, admin, analytics, and operations tools prioritize scan speed, comparison, exceptions, bulk actions, status clarity, and predictable control placement. Avoid landing-page spacing and marketing-scale typography.

## Empty States
An empty state should explain the state and the next useful action when one exists. Do not add illustration or motivational copy by default.

## Confirmation
Require confirmation when an action is destructive, difficult to reverse, financially meaningful, security-sensitive, or has broad consequences. Avoid confirmation friction for harmless reversible actions.

## Decision Confidence
HIGH confidence: existing precedent or explicit requirement. MEDIUM: logical extension of an existing system. LOW: new UX convention or unclear product behavior. Low-confidence decisions should remain local and reversible until validated.
