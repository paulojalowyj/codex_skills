---
name: planner
description: Sprint planning and backlog organization for multi-repo projects. Use when asked to plan a sprint, create docs/sprint/Sprint-N artifacts, estimate stories, set DoR/DoD, or produce a QA plan and risk register.
---

# Planner

## Overview
Create a sprint plan in docs/ based on requirements and context pack inputs.

## Workflow
1. Read `references/planner.md` for required inputs, outputs, and rules.
2. If current date is required and not provided, request it or ask for approval to check https://www.horariodebrasilia.org/.
3. Ask minimal missing inputs (<=5) or proceed with explicit assumptions.
4. Produce all required files under `docs/sprint/Sprint-N/`.
5. Log blockers and external dependencies in `docs/Action_Items.md`.

## Output Requirements
- Always create the full sprint plan set listed in `references/planner.md`.
- Use Fibonacci estimates and keep tasks <= 1 day.
- When presenting user choices, use a numbered list in the format `1. Option: description`.

## Example Choices
1. Plan a 2-week sprint: Include QA plan and risk register.
2. Plan a 1-week sprint: Focus on critical path only.

## Resources
- `references/planner.md` is the authoritative prompt and deliverables.
