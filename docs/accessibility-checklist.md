# Accessibility Checklist

Accessibility is mandatory.

## Structure

- Use semantic HTML.
- Use one `h1` per page.
- Keep heading order logical.
- Use landmarks where helpful.

## Keyboard

- All actions must be keyboard accessible.
- Focus order must match visual order.
- Focus indicators must be visible.

## Screen Readers

- Add labels for icon-only buttons.
- Avoid meaningless ARIA.
- Use descriptive button text.
- Announce important async state changes where appropriate.

## Forms

- Every input must have a label.
- Error messages must be associated with fields.
- Required fields must be clear.

## Color

- Do not communicate meaning by color alone.
- Meet WCAG 2.1 AA contrast as a minimum:
  - Normal text (under 18px, or under 14px bold): at least `4.5:1`.
  - Large text (18px+, or 14px+ bold): at least `3:1`.
  - UI components and graphical objects (borders, icons, focus rings, chart segments): at least `3:1` against adjacent colors.
- Focus indicators must meet `3:1` against both the focused element and the background.
- Disabled elements are exempt, but do not rely on a disabled-looking control to convey required information.
- Aim for AAA (`7:1` normal, `4.5:1` large) for long-form body text where practical.

See `tokens-rules.md` for the semantic color tokens these ratios apply to.

## Examples

Label icon-only buttons.

Bad:

> `<button><Trash2 /></button>`

Good:

> `<button aria-label="Delete invoice"><Trash2 /></button>`

Never rely on color alone for meaning.

Bad:

> A red dot to mean "failed", a green dot to mean "passed".

Good:

> An icon plus text — `✕ Failed` / `✓ Passed` — using `destructive` and `success` tokens for emphasis, not as the only signal.

Associate errors with their field.

Bad:

> A standalone `Invalid input` message above the form.

Good:

> `<Input aria-invalid aria-describedby="email-error" />` with the message in `#email-error`.
