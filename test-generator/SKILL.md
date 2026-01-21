---
name: test-generator
description: Generate automated tests for frontend (Jest/RTL) and backend (Pytest/TestClient) in this multi-repo project. Use when asked to add tests, improve coverage, or implement QA/TDD for new features.
---

# Test Generator

## Overview
Write deterministic frontend and backend tests aligned with quality gates.

## Workflow
1. Read `references/tests.md` for scope rules and required test types.
2. Locate related code and requirements; add tests in the correct repo paths.
3. Cover happy, error, and edge cases; include auth and security scenarios.
4. Update `docs/development/quality-gates.md` only when explicitly needed.

## Output Requirements
- Tests must be complete with fixtures, clear assertions, and isolated state.
- Ask for minimal missing contract details if required to write tests.
- When presenting user choices, use a numbered list in the format `1. Option: description`.

## Example Choices
1. Add FE + BE tests: Cover happy, error, and edge cases.
2. Add backend-only tests: Focus on API and data layer.

## Resources
- `references/tests.md` is the authoritative prompt and deliverables.
