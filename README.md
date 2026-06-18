# Northstar

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/anikwai/northstar/releases/tag/v1.0.0)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A reusable product-design constitution for AI-assisted product development.

Northstar helps LLM coding agents make better product, UX, UI, and engineering decisions by prioritizing:

1. User outcomes
2. Usability
3. Information architecture
4. Accessibility
5. Performance
6. Visual design
7. Animation

It is designed for projects using:

- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- lucide-react
- Cursor
- Claude Code
- Codex
- GitHub Copilot

## What Northstar Is

Northstar is not just a design system.

It is a decision-making framework for building useful software.

A design system answers:

> How should we build it?

Northstar asks:

> Should we build it?
> Why should we build it?
> What is the simplest version?
> How do users succeed?

## How to Use

Northstar is a set of Markdown instruction files you give to your AI coding agent. You do not run it. You drop it into a project and the agent reads it as context.

### 1. Add the files to your project

Copy these into your project root:

- `AGENTS.md`
- `NORTHSTAR.md`
- `CLAUDE.md`
- `.cursorrules`
- the `docs/` folder

### 2. The wiring is already done

Each tool reads its own entry file, which points to `AGENTS.md`:

- Claude Code reads `CLAUDE.md`.
- Cursor reads `.cursorrules`.
- Codex, GitHub Copilot, and most other agents read `AGENTS.md` directly.

`AGENTS.md` is the always-loaded baseline. Everything else loads on demand.

### 3. Work normally

Prompt as usual ("build a customers table", "add a settings form"). A configured agent applies the rules automatically.

To be explicit, point the agent at the relevant file:

> Follow `docs/form-rules.md`.

> Review this screen against `docs/review-checklist.md`.

Load only what the task needs (see Context Strategy below). Do not paste everything into every prompt.

### Note

These files are advisory, not enforced. Nothing lints against them, so adherence depends on the agent loading and following them. For important work, explicitly reference the relevant document.

## Recommended Usage

Use the short rules file for everyday AI context:

- `AGENTS.md`

Keep the full constitution as reference:

- `NORTHSTAR.md`

Use task-specific files only when needed:

- `docs/ui-rules.md`
- `docs/tokens-rules.md`
- `docs/responsive-rules.md`
- `docs/form-rules.md`
- `docs/table-rules.md`
- `docs/dashboard-rules.md`
- `docs/accessibility-checklist.md`
- `docs/review-checklist.md`

## Context Strategy

Do not paste the full constitution into every prompt.

Use this rule:

| Task Type | Context To Load |
|---|---|
| Small bug fix | `AGENTS.md` only |
| New component | `AGENTS.md` + relevant rule file |
| New screen | `AGENTS.md` + `docs/ui-rules.md` |
| Tokens / theming | `AGENTS.md` + `docs/tokens-rules.md` |
| Responsive / mobile work | `AGENTS.md` + `docs/responsive-rules.md` |
| New form | `AGENTS.md` + `docs/form-rules.md` |
| New table | `AGENTS.md` + `docs/table-rules.md` |
| Dashboard | `AGENTS.md` + `docs/dashboard-rules.md` |
| Accessibility audit | `AGENTS.md` + `docs/accessibility-checklist.md` |
| Major feature | `AGENTS.md` + `NORTHSTAR.md` |
| UX review | `NORTHSTAR.md` + `docs/review-checklist.md` |

## Maintainer

Maintained by [@anikwai](https://github.com/anikwai).

## GitHub Setup

```bash
git init
git add .
git commit -m "Add Northstar product constitution"
git branch -M main
git remote add origin git@github.com:YOUR_USERNAME/northstar.git
git push -u origin main
```
