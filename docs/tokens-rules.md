# Tokens & Type Scale

Use this file when defining or applying design tokens: color, type, spacing, radius, elevation, and motion.

This file builds on `AGENTS.md`. It defines the concrete values that the other rule files refer to.

## Principle

Style with tokens, not raw values.

Reach for a semantic token before a literal color, size, or pixel value.

If a value is used twice, it should be a token.

## Color

Use semantic tokens, not raw colors.

Bad:

> `bg-[#0f172a]` `text-gray-500`

Good:

> `bg-background` `text-muted-foreground`

Follow the shadcn/ui CSS-variable convention. Define each as an HSL variable with a paired foreground:

| Token | Use |
|---|---|
| `background` / `foreground` | page surface and default text |
| `card` / `card-foreground` | raised surfaces |
| `popover` / `popover-foreground` | overlays, menus |
| `muted` / `muted-foreground` | secondary surfaces and text |
| `primary` / `primary-foreground` | primary action |
| `secondary` / `secondary-foreground` | secondary action |
| `accent` / `accent-foreground` | hover and subtle emphasis |
| `destructive` / `destructive-foreground` | dangerous actions, errors |
| `border` | dividers and outlines |
| `input` | form field borders |
| `ring` | focus indicator |
| `chart-1` … `chart-5` | data visualization |

Rules:

- Every foreground token must hit the contrast ratios in `accessibility-checklist.md` against its paired surface.
- Color communicates meaning, not decoration. Use `destructive` for danger, not for emphasis.
- Define every token for both light and dark mode.
- Add status tokens (`success`, `warning`, `info`) only if the product needs them, and give each a foreground pair.

## Type Scale

Use a fixed scale. Do not use arbitrary font sizes.

| Token | Size | Line height | Role |
|---|---|---|---|
| `text-xs` | 12px | 16px | captions, metadata |
| `text-sm` | 14px | 20px | secondary text, labels, table cells |
| `text-base` | 16px | 24px | body text (default) |
| `text-lg` | 18px | 28px | lead text, card titles |
| `text-xl` | 20px | 28px | section headings |
| `text-2xl` | 24px | 32px | page subheadings |
| `text-3xl` | 30px | 36px | page titles |
| `text-4xl` | 36px | 40px | rare hero / marketing only |

Rules:

- Body text is `text-base` (16px). Never set body below 16px (avoids mobile zoom — see `responsive-rules.md`).
- One `text-3xl`/`text-4xl` per screen at most. Hierarchy comes from spacing and weight, not size inflation.
- Weights: `font-normal` for body, `font-medium` for labels and emphasis, `font-semibold` for headings. Avoid `font-bold` outside marketing.
- Constrain measure to roughly 60–75 characters for readable body text.

## Spacing

Use the Tailwind 4px-based scale. Do not use arbitrary pixel values.

| Step | Value | Typical use |
|---|---|---|
| `1` | 4px | icon gaps, tight inline spacing |
| `2` | 8px | between label and control |
| `3` | 12px | compact internal padding |
| `4` | 16px | default gap, mobile padding |
| `6` | 24px | card padding, section gaps |
| `8` | 32px | desktop section padding |
| `10`–`12` | 40–48px | major section separation |

Rules:

- Compose layouts from this scale only.
- Spacious is a desktop default; scale down on mobile (see `responsive-rules.md`).
- Prefer `gap` and `space-y` over per-child margins.

Desktop layout defaults:

- Container and card padding: `p-6` to `p-8`, up to `p-10` for major sections.
- Gaps between groups: `gap-6` / `gap-8`.
- Vertical rhythm between sections: `space-y-6` / `space-y-8`.

Avoid cramped layouts; avoid forcing these desktop values onto small screens.

## Radius

Drive radius from a single `--radius` variable.

- `rounded-sm` — inputs, badges
- `rounded-md` — buttons, cards (default)
- `rounded-lg` — modals, large surfaces
- `rounded-full` — avatars, pills, icon buttons

Keep radius consistent within a component family.

## Elevation

Use shadow sparingly to signal layering, not decoration.

- flat (`shadow-none`) — most surfaces
- `shadow-sm` — cards, raised rows
- `shadow-md` — dropdowns, popovers
- `shadow-lg` — modals, sheets

Prefer borders over shadows for separation on dense screens.

## Motion

Motion clarifies state change. It is the lowest priority and must never block a task.

| Duration | Use |
|---|---|
| 150ms | hover, focus, small state changes |
| 200ms | dropdowns, tooltips, toggles |
| 300ms | dialogs, sheets, larger transitions |

Rules:

- Use ease-out for entrances, ease-in for exits.
- No purely decorative animation (see global anti-patterns in `AGENTS.md`).
- Respect `prefers-reduced-motion`: reduce or remove non-essential motion.

## Anti-Patterns

Avoid:

- raw hex/rgb values instead of tokens
- arbitrary font sizes (`text-[15px]`)
- arbitrary spacing (`p-[18px]`)
- mixing radius scales within one component
- shadows used for decoration
- defining tokens for light mode only

## Examples

Use the type scale, not arbitrary sizes.

Bad:

> `<p class="text-[15px]">` and `<h1 class="text-[44px]">`

Good:

> `<p class="text-base">` and `<h1 class="text-3xl font-semibold">`

Use the spacing scale, not arbitrary values.

Bad:

> `<div class="p-[18px] gap-[10px]">`

Good:

> `<div class="p-6 gap-4">`

Use semantic color tokens, not raw colors.

Bad:

> `<span class="text-red-500">Overdue</span>`

Good:

> `<span class="text-destructive">Overdue</span>`
