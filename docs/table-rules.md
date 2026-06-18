# Table Rules

Use this file when displaying records.

## Principle

Tables are for scanning, comparing, and acting.

## Use Tables For

- records
- logs
- invoices
- customers
- transactions
- audit trails
- inventory

## Requirements

Tables should include, when relevant:

- search
- sorting
- filtering
- pagination
- loading state
- empty state
- row actions

## Empty State

Never say only:

> No data

Explain why and provide an action.

Example:

> No invoices yet. Create your first invoice to begin tracking customer payments.

## Actions

Common row actions should be easy to access.

Dangerous actions should be visually secondary and protected.

## Examples

Show essential columns, not every column.

Bad:

> A customer table with 14 columns including internal IDs, timestamps, and raw flags.

Good:

> Name, status, last activity, and amount; everything else moves to the row's detail view.

Dangerous actions stay secondary.

Bad:

> A red `Delete` button in every row, next to `Edit`.

Good:

> A `⋯` `DropdownMenu` per row; `Delete` sits inside it, styled `destructive`, behind a confirm.
