# UI Rules

Use this file when creating or redesigning screens and components.

This file builds on `AGENTS.md` (priority order, product thinking, global anti-patterns). It does not repeat those rules.

For concrete color, type, spacing, and motion values, see `tokens-rules.md`. For responsive behavior, see `responsive-rules.md`.

## Layout

Use calm, spacious layouts on desktop.

Avoid cramped layouts.

For spacing values, the desktop scale, and how to scale down on mobile, see `tokens-rules.md`.

## Content Width

Use readable widths:

- `max-w-3xl`
- `max-w-4xl`
- `max-w-5xl`
- `max-w-6xl`

Avoid stretching content across very wide screens.

## Visual Hierarchy

Hierarchy should be created through:

- layout
- spacing
- grouping
- weight
- placement

## shadcn/ui

Prefer shadcn/ui primitives before building custom ones (see `NORTHSTAR.md` for the full list).

Use `lucide-react` icons only when they clarify meaning.

## Anti-Patterns

In addition to the global anti-patterns in `AGENTS.md`, avoid these visual ones:

- decorative gradients
- too many icons
- excessive font sizes and colors
- generic SaaS templates

## Examples

Hierarchy through spacing and weight, not size and color.

Bad:

> `<h2 class="text-4xl text-blue-600">Customers</h2>`

Good:

> `<h2 class="text-xl font-semibold">Customers</h2>` with `space-y-6` separating the groups below it.

One primary action per view.

Bad:

> Three filled buttons side by side: `Save`, `Export`, `Delete`.

Good:

> One `Button` (`Save`), one `variant="outline"` (`Export`), and `Delete` in a `DropdownMenu` or as `variant="ghost"`.

Group with spacing, not nested cards.

Bad:

> A `Card` containing two more `Card`s to separate sections.

Good:

> One `Card` with `space-y-6` and a small heading per section.
