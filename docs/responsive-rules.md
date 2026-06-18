# Responsive Rules

Use this file when a screen, component, or layout must adapt across screen sizes.

This file builds on `AGENTS.md`. It does not repeat global rules.

## Principle

Design mobile-first.

Start with the smallest screen.

Add complexity only as space allows.

The primary action must be reachable on every screen size.

## Breakpoints

Use the standard Tailwind breakpoints. Do not invent new ones.

| Prefix | Min width | Typical device |
|---|---|---|
| (none) | 0 | phones |
| `sm` | 640px | large phones |
| `md` | 768px | tablets |
| `lg` | 1024px | small laptops |
| `xl` | 1280px | desktops |
| `2xl` | 1536px | large desktops |

Write base styles for mobile.

Use `sm:`, `md:`, `lg:` to scale up.

Avoid `max-*` prefixes unless removing something on larger screens.

## Layout

Stack first.

Use `flex-col` then `lg:flex-row`.

Use `grid-cols-1` then `sm:grid-cols-2` then `lg:grid-cols-3`.

Never hardcode column counts that overflow small screens.

Use fluid spacing:

- `p-4` on mobile
- `md:p-6`
- `lg:p-8`

Reduce generous desktop spacing on mobile.

Spacious is a desktop default, not a mobile mandate.

## Touch Targets

Interactive targets must be at least 44×44px.

Use `min-h-11` and adequate padding for buttons, links, and rows.

Space adjacent targets to prevent mis-taps.

Hover-only interactions must have a tap or focus equivalent.

## Navigation

Collapse primary navigation on mobile.

Prefer:

- `Sheet` for menus
- bottom navigation for frequent actions
- visible back affordance

Never hide the primary action inside a collapsed menu.

## Tables

Tables rarely fit on phones.

On small screens, prefer one of:

- a card or list view per record
- horizontal scroll for the full table, with the key column pinned

Show only essential columns on mobile.

Reveal secondary columns at `md:` and above.

See `table-rules.md` for table structure.

## Forms

Always single-column on mobile.

Inputs should be full-width.

Use `inputMode` and `type` to trigger the correct mobile keyboard.

Keep labels visible above inputs, not as placeholders.

See `form-rules.md` for form structure.

## Dialogs

On mobile, prefer `Sheet` over centered `Dialog`.

Sheets respect small viewports and thumb reach.

Reserve centered dialogs for short confirmations.

## Typography

Keep body text at least 16px to avoid mobile zoom.

Scale headings up at larger breakpoints, not down on mobile.

Maintain readable line length at every width.

## Media

Use responsive, lazy-loaded images.

Constrain with `max-w-full` and intrinsic aspect ratios.

Avoid fixed pixel widths that cause horizontal scroll.

## Anti-Patterns

Avoid:

- horizontal scroll on the whole page
- fixed-width containers wider than the viewport
- desktop spacing forced onto phones
- hover-only actions with no tap equivalent
- multi-column forms on small screens
- tables that overflow without a mobile alternative

## Review

Before approving responsive work, check:

- Does it work at 360px width?
- Is the primary action visible without scrolling on mobile?
- Are touch targets large enough?
- Does anything cause horizontal scroll?
- Are tables usable on phones?
- Does text avoid forced zoom?

## Examples

Stack first, then scale up.

Bad:

> `<div class="grid grid-cols-3 gap-8">` — three columns at every width.

Good:

> `<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 md:gap-6">`

Give tables a mobile alternative.

Bad:

> A 10-column `Table` that overflows the viewport on a phone.

Good:

> A card/list view per record below `md:`, switching to the full `Table` at `md:` and up.

Reach the primary action without a menu.

Bad:

> The only `Save` button hidden inside a collapsed hamburger menu on mobile.

Good:

> `Save` pinned in a visible bottom bar; secondary actions live in the menu.
