# AGENTS.md

This is the short, always-loaded instruction file for AI coding agents.

It is a condensed subset of `NORTHSTAR.md`, which is canonical. The `docs/` rule files are always loaded alongside this file, so they do not repeat the rules below — they only add task-specific depth.

For deeper product and UX decisions, consult `NORTHSTAR.md`.

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

## Before Building UI

Identify:

- User
- Goal
- Primary action
- Frequency of use
- Risk of mistake
- Success state

## Core Rules

Do not add UI elements unless they help the user:

- decide
- act
- avoid mistakes
- understand status

Every page, card, field, chart, button, and workflow must justify its existence.

If users can succeed without it, remove it.

## Product Thinking

Prefer:

- simple workflows
- obvious primary actions
- fewer choices
- progressive disclosure
- clear feedback
- safe defaults

Avoid:

- dashboard card explosions
- unnecessary charts
- cards inside cards
- multiple primary actions
- decorative UI that does not help the task
- giant hero sections in admin tools

## UI Stack

Use:

- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- lucide-react
- `cn()` utility

Reuse existing shadcn/ui primitives before creating custom primitives.

## Review Before Final Output

Before final output, check:

- Is the user goal clear?
- Is the primary action obvious?
- Can anything be removed?
- Is the interface accessible?
- Is mobile considered?
- Are loading, empty, error, and success states handled?
