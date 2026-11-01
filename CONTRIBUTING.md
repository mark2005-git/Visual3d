# Contributing to Visual3d

Thanks for your interest in Visual3d. The project is at an early foundation stage, so clarity and small, verifiable changes matter more than adding features quickly.

## Before starting

1. Read the [README](README.md), [roadmap](docs/ROADMAP.md), and [architecture notes](docs/ARCHITECTURE.md).
2. Check existing issues before starting substantial work.
3. For a new feature or architectural change, open an issue first so its scope and acceptance criteria can be agreed.

## Development principles

- Keep the first milestone focused on an editable 3D scene.
- Prefer small modules with clear responsibilities.
- Keep scene data separate from rendering and UI state.
- Validate structured commands before applying them.
- Do not commit API keys, credentials, personal data, or local environment files.
- Add or update tests when behavior changes.
- Document meaningful architectural decisions.

## Pull requests

A pull request should explain:

- What changed and why
- How to run or verify the change
- Any known limitations
- Screenshots or a short recording for visible UI changes, where useful

Keep pull requests focused. Avoid bundling unrelated formatting, refactoring, and feature work.

## Code quality

The implementation stack and exact lint/test commands will be documented as the applications are introduced. Until then, do not add tooling without explaining its purpose and maintenance cost.
