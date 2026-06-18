# NORTHSTAR.md

Version: 1.0

Northstar is the product-design constitution for this project.

It defines how products, features, workflows, interfaces, and AI-generated code should be designed and evaluated.

Its purpose is to keep every product decision aligned with user success.

This file is the canonical source of truth. `AGENTS.md` is a condensed, always-loaded subset; the `docs/` files add task-specific depth. Where any file disagrees with this one, this one wins.

---

## Core Idea

Software should help users succeed.

Everything else is secondary.

The goal is not to create beautiful screens.

The goal is to help users complete real tasks with minimum effort, minimum confusion, and maximum confidence.

---

## Priority Order

Always optimize in this order:

1. User goals
2. Usability
3. Information architecture
4. Accessibility
5. Performance
6. Visual design
7. Animation

Never sacrifice a higher priority for a lower priority.

A beautiful interface that is difficult to use is a failed interface.

A simple interface that helps users complete their work is successful.

---

## First Principles

### 1. User Success Is The Goal

Users do not want software.

Users want outcomes.

Users do not want:

- CRM systems
- inventory systems
- hospital systems
- billing systems

Users want:

- customer visibility
- accurate stock levels
- better patient care
- faster payments

Design for outcomes, not screens.

---

### 2. The Best Interface Is No Interface

Before adding anything, ask:

Can users succeed without this?

If yes, do not build it.

Every page, card, field, chart, button, workflow, tab, filter, and setting must justify its existence.

Complexity requires permission.

---

### 3. Simplicity Wins

Simple is not the absence of capability.

Simple is the absence of unnecessary capability.

Users should understand a screen within five seconds.

If explanation is required, simplify.

---

### 4. Optimize For Time-To-Value

Users should achieve meaningful success as quickly as possible.

Reduce:

- clicks
- navigation
- form fields
- decisions
- waiting
- repeated actions

Every unnecessary step is a design failure.

---

## Before Creating Any Feature

Identify:

### User

Who is using this?

Examples:

- Nurse
- Doctor
- Customer
- Accountant
- Administrator
- Support Agent
- Manager
- Developer

### Goal

What are they trying to accomplish?

### Frequency

How often does this happen?

- Constantly
- Daily
- Weekly
- Rarely

Higher-frequency actions deserve simpler interfaces.

### Risk

What happens if they make a mistake?

- Low risk
- Medium risk
- High risk
- Critical

Higher-risk actions require stronger safeguards.

### Primary Action

What action matters most?

Every screen should have one clearly identifiable primary action.

### Success State

How does the user know they succeeded?

The interface must communicate success clearly.

---

## Product Thinking

### Actions Over Information

Information alone rarely creates value.

Information should enable action.

Bad:

> 15 invoices overdue

Good:

> 15 invoices overdue  
> Send reminders

Whenever presenting information, identify the next logical action.

---

### Information Must Earn Visibility

Do not display information merely because it exists.

Show information only if it helps users:

- decide
- act
- prevent mistakes
- understand status

Hide everything else.

---

### Progressive Disclosure

Do not reveal complexity immediately.

Show:

- essentials first
- details when needed
- advanced options on demand

Use:

- drawers
- sheets
- accordions
- expandable sections
- advanced settings areas

Complexity should unfold gradually.

---

## Information Architecture

Information architecture is more important than visual design.

Organize information according to how users think, not how the database is structured.

Every element belongs in one category:

### Essential

Required immediately.

Must be visible.

### Important

Useful but not required immediately.

Visible but secondary.

### Advanced

Rarely used.

Hidden until needed.

---

## User Intent Hierarchy

Every screen must identify:

### Primary Intent

The main reason users are here.

### Secondary Intent

Supporting activity.

### Rare Intent

Occasional or dangerous actions.

Primary intent should dominate the interface.

Rare actions should not compete visually.

---

## Cognitive Load

The user should not need to think about the interface.

They should think about their work.

Reduce:

- choices
- navigation
- decisions
- competing actions
- visual clutter
- unclear labels

Clarity beats cleverness.

Always.

---

## Trust

Every interface should increase confidence.

Users must always know:

- where they are
- what happened
- what is happening
- what happens next

Confusion is a design defect.

---

## Safety & Risk

Friction should match risk.

### Low Risk

Examples:

- rename item
- update note
- change view

Use minimal friction.

### Medium Risk

Examples:

- modify permissions
- edit financial data
- change billing details

Confirmation may be appropriate.

### High Risk

Examples:

- delete customer
- submit payroll
- discharge patient
- revoke access

Use additional safeguards.

### Critical Risk

Examples:

- medication administration
- production deployment
- financial settlement

Require explicit review and confirmation.

---

## Domain Awareness

Different domains require different priorities.

| Domain | Priority |
|---|---|
| Healthcare | Safety → Accuracy → Speed |
| Finance | Accuracy → Auditability → Speed |
| Telecommunications | Reliability → Operational efficiency → Visibility |
| Government | Compliance → Transparency → Accessibility |
| Education | Clarity → Guidance → Simplicity |
| CRM | Visibility → Relationships → Productivity |
| Inventory | Accuracy → Speed → Traceability |

Never apply generic SaaS patterns blindly.

The interface must adapt to the domain.

---

## User Experience Principles

Design for the most frequent task.

Minimize navigation.

Make next steps obvious.

Respect user attention.

Avoid:

- excessive notifications
- unnecessary animations
- decorative content
- visual noise

---

## Accessibility

Accessibility is mandatory.

Every feature must support:

- keyboard navigation
- screen readers
- focus visibility
- semantic HTML
- sufficient contrast
- meaningful labels
- logical heading order

Accessibility is quality, not an enhancement.

---

## Performance

Performance is a feature.

Users experience latency as friction.

Prefer:

- lazy loading
- code splitting
- optimistic updates where safe
- efficient rendering
- skeleton states
- predictable layout

Fast systems feel easier to use.

---

## Design System

The design system serves usability.

Usability does not serve the design system.

Interfaces should feel:

- calm
- spacious
- trustworthy
- professional
- modern

Use whitespace generously.

Create hierarchy through:

- spacing
- placement
- grouping
- weight

Use color to communicate meaning, not decoration.

Prefer neutral surfaces and semantic colors.

---

## UI Engineering Standards

Use:

- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- lucide-react
- `cn()` utility

Prefer shadcn/ui primitives before creating custom primitives.

Common primitives:

- Card
- Button
- Input
- Form
- Dialog
- DropdownMenu
- Sheet
- Tabs
- Table
- Skeleton
- Alert

Prefer composition.

Build small reusable components.

Avoid monolithic files.

---

## Component Architecture

Use feature-based organization.

Example:

```text
features/
  billing/
    components/
    hooks/
    types/
    actions/
    services/
    pages/
```

Each component should:

- have one responsibility
- accept typed props
- be reusable where appropriate
- remain visually isolated
- be easy to understand later

---

## AI Generation Rules

AI must not default to:

- KPI cards
- dashboards
- charts
- tabs
- filters
- forms

Each UI element must justify itself.

Choose structures intentionally:

| Need | Pattern |
|---|---|
| Metrics | KPI cards |
| Records | Tables |
| Processes | Timelines |
| Relationships | Graphs |
| Actions | Menus |
| Navigation | Lists |
| Detailed editing | Forms |
| Contextual task | Dialog or sheet |

Do not use a pattern simply because it is common.

---

## AI Anti-Patterns

Avoid:

- dashboard card explosions
- cards inside cards
- giant hero sections in admin tools
- multiple competing primary actions
- excessive borders
- excessive icons
- excessive gradients
- unnecessary charts
- decorative animations
- generic SaaS templates

Prefer clarity.

---

## Review Checklist

Before approving any feature, ask:

- Who is the user?
- What is the user's goal?
- What is the fastest path to success?
- Is every element necessary?
- Can anything be removed?
- Is the primary action obvious?
- Is information prioritized correctly?
- Are mistakes prevented?
- Is accessibility supported?
- Is mobile-first considered?
- Is cognitive load minimized?
- Does the interface increase confidence?
- Would a first-time user understand it within five seconds?

If not, redesign.

---

## Final Rule

When forced to choose between beauty and clarity, choose clarity.

When forced to choose between flexibility and simplicity, choose simplicity.

When forced to choose between features and usability, choose usability.

The purpose of software is not to impress users.

The purpose of software is to help users succeed.
