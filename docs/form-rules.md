# Form Rules

Use this file when creating forms.

## Principle

Forms are work.

Reduce effort.

## Layout

Prefer single-column forms.

Group related fields.

Avoid multi-column forms unless fields are short and strongly related.

## Required Fields

Ask only for necessary information.

Minimize required fields.

Use sensible defaults.

## Validation

Validation must be inline and helpful.

Bad:

> Invalid input

Good:

> Email address must contain a valid domain.

## States

Every form must include:

- default state
- focus state
- error state
- disabled state
- loading state
- success state

## Risk

Higher-risk submissions require stronger confirmation.

Examples:

- deleting records
- submitting payroll
- approving financial transactions
- medication workflows
- production deployments

## Examples

Single column, not multi-column.

Bad:

> A two-column grid placing `First name` next to `Email`, and `Phone` next to `Country`.

Good:

> One column, fields stacked top to bottom; only short, strongly related fields (e.g. `City` / `Postal code`) share a row.

Visible labels, not placeholders.

Bad:

> `<Input placeholder="Email address" />` with no label.

Good:

> A `Label` above the `Input`; use placeholder only for format hints (e.g. `name@company.com`).

Ask only for what you need.

Bad:

> A signup form requesting name, company, role, phone, and address.

Good:

> Email and password now; collect the rest later, in context, when it is actually used.
