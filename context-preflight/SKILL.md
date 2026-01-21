---
name: context-preflight
description: Map and standardize context for multi-repo frontend/backend/docs projects. Use when asked to perform a context pre-flight, generate a context pack in docs/, audit structure/dependencies/routes/endpoints/models/migrations/tests/CI, assess security posture and quality gates, check drift between OpenAPI and code or SDK, or build shadcn LLM index artifacts.
---

# Context Preflight

## Overview
Generate a verified context pack for a multi-repo full-stack workspace and document risks, drift, and gaps with file-cited evidence.

## Workflow
1. Load the project-specific prompt if provided; otherwise read `references/context-preflight.md` for the exact checklist and outputs.
2. Discover structure and configs with `rg` and directory listings; record evidence with file paths and short snippets.
3. Map frontend routing and data fetching plus backend endpoints, models, and migrations; mark items as "not found" when evidence is missing.
4. Diagnose risks (security, config, drift, missing tests, missing `.env.example`, logger and correlation-id).
5. Produce or update every required file under `docs/` with tables and concise summaries.
6. If network access is needed (pip-audit, npm audit, shadcn llms.txt), request approval and record blockers in `docs/Action_Items.md`.

## Output Requirements
- Always create or update the full context pack listed in `references/context-preflight.md`.
- Cite evidence in each doc with explicit file paths.
- Put cross-repo impacts in `docs/Action_Items.md` with severity and owner.
- When presenting user choices, use a numbered list in the format `1. Option: description`.

## Example Choices
1. Full preflight: Frontend + backend + docs pack.
2. Backend-only preflight: Skip frontend routing and UI checks.

## Resources
- `references/context-preflight.md` contains the authoritative checklist and deliverables.
