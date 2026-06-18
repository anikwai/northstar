# Dashboard Rules

Use this file when creating dashboards.

This file builds on `AGENTS.md` and does not repeat its global anti-patterns.

## Principle

Dashboards should answer:

1. What is happening?
2. What needs attention?
3. What should I do next?

## Avoid

Dashboard-specific failures (in addition to the global anti-patterns):

- unrelated widgets
- decorative analytics
- charts without decisions
- dense layouts

## Use KPI Cards Only When

The metric helps users:

- make a decision
- detect a problem
- track progress
- take action

## Layout

Recommended order:

1. Header
2. Summary
3. Attention needed
4. Primary operational area
5. Recent activity
6. Secondary actions

## Charts

Only include a chart when the visual pattern matters.

If a number is enough, use a number.

If a table is clearer, use a table.

If no action follows from the chart, remove it.

## Examples

Lead with attention and action, not a wall of cards.

Bad:

> Eight KPI cards in a grid: total users, active users, revenue, churn, sessions, signups, tickets, NPS.

Good:

> One summary line, then an "Attention needed" list (`3 overdue invoices · Send reminders`), then the main operational table.

Only chart when the pattern matters.

Bad:

> A donut chart showing "2 open / 1 closed".

Good:

> The sentence `2 open, 1 closed`. Reserve charts for trends and distributions a number cannot convey.
