# Contributing Guide

Thanks for contributing! This guide explains how to report issues, propose changes, and get a PR merged.

## Quick links

- Code of Conduct: `CODE_OF_CONDUCT.md`
- Security policy (for vulnerabilities): `SECURITY.md`
- Support: `SUPPORT.md`

## Ground rules

- Be respectful and constructive (see Code of Conduct).
- Keep PRs small and reviewable when possible.
- Prefer discussing non-trivial changes before implementing them.

## What counts as a good contribution

- Bug fixes, improvements, refactors that reduce complexity
- Documentation improvements (including examples and troubleshooting)
- Tests and CI reliability improvements
- Performance improvements with evidence (benchmarks/profiling)
- Issue triage: reproductions, minimal examples, labeling suggestions

## Before you open an issue

1. Search existing issues/discussions (including closed).
2. Confirm you're on a supported version.
3. Collect minimal reproduction steps (or a small repo/snippet if feasible).

**Do not file security vulnerabilities publicly.** Use `SECURITY.md`.

## Before you open a pull request

### 1) Align on approach

For anything beyond small fixes:

- Open an issue or discussion first (or comment on an existing one).
- Explain the problem, constraints, and proposed approach.

### 2) Development setup

Each repository may have repo-specific setup steps in its README. In general:

- Fork the repository (or use a branch if you have access)
- Create a feature branch from the default branch
- Run formatting, lint, and tests locally before pushing

Suggested commands (check repo-specific README):

- Install: `npm ci` / `pip install -r requirements.txt` / `go mod download`
- Test: `npm test` / `pytest` / `go test ./...`
- Lint: `npm run lint` / `ruff check` / `golangci-lint run`
- Format: `prettier --write .` / `ruff format` / `gofmt -w .`

## PR requirements (org standard)

- PR title uses **Conventional Commits** style (e.g., `feat: add X`, `fix: handle Y`).
- PR description includes:
  - What changed and why
  - How to test
  - Risk/rollout notes for impactful changes
- Add or update tests when behavior changes.
- Update docs if user-facing behavior changes.
- Avoid mixing unrelated changes in one PR.

## Code style & quality

- Prefer clarity over cleverness.
- Keep public API changes explicit; document migrations for breaking changes.
- Add logging/telemetry only where appropriate and avoid sensitive data.

## Reviews

- Maintainers may request changes, re-scoping, or splitting PRs.
- If you disagree with feedback, explain tradeoffs and propose alternatives.

## Licensing

By contributing, you agree that your contributions are licensed under the repository's existing license.

## Contributor attribution

We appreciate attribution in release notes and changelogs where applicable.
