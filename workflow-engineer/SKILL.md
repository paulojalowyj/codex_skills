---
name: workflow-engineer
description: Development workflow orchestration for this multi-repo project. Use when asked to design, follow, or standardize workflows (review, codegen, release readiness, hotfix, migration, performance tuning, documentation-only) and when a task requires sequencing multiple skills.
---

# Workflow Guides

## Overview
Provide repeatable workflow sequences that chain skills and document required outputs.

## How to Use
1. Read `references/workflows.md` and select the workflow that matches the request.
2. Confirm scope (frontend/backend/docs) and required artifacts before starting.
3. Execute each step in order; log cross-repo impacts in `docs/Action_Items.md`.

## Output Requirements
- Use the exact workflow definitions from `references/workflows.md`.
- When presenting workflow options, show a numbered list in the format `1. Option: description` so the user can select.
- If a step is blocked, record the blocker and continue with what is possible.

## Example Choices
1. Review Workflow: Validate scope before implementation.
2. Codegen Workflow: Implement new feature end-to-end.

## Resources
- `references/workflows.md` contains the authoritative workflow definitions.
