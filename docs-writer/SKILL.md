---
name: docs-writer
description: Produce and update technical documentation in docs/ for this multi-repo project. Use when asked to write docs, update API indexes, document routes, generate ADRs/runbooks, or produce docstring insertion notes.
---

# Docs Writer

## Overview
Create clear, actionable documentation based on code changes and context pack inputs.

## Workflow
1. Read `references/docs.md` for scope rules and required outputs.
2. Update only `docs/` files; reference code paths without editing them.
3. Ensure API indexes, frontend routes, and data fetching docs are updated when relevant.
4. Add Action Items for inconsistencies or cross-repo impacts.

## Output Requirements
- Provide docs updates and docstring insertion notes as specified in the reference.
- Use tables and examples where needed for clarity.
- When presenting user choices, use a numbered list in the format `1. Option: description`.

## Example Choices
1. Update API index and routes: Touch only `docs/`.
2. Add runbook updates: Include ops notes and ADRs.

## Resources
- `references/docs.md` is the authoritative prompt and deliverables.
