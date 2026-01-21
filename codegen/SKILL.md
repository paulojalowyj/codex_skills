---
name: codegen-full-stack
description: Implement full-stack features across React/TanStack Router/Query/Tailwind/shadcn/ui and FastAPI/SQLAlchemy/Alembic/Pydantic/Celery/PostgreSQL. Use when asked to generate frontend and backend code together, coordinate cross-stack changes, or when a task references docs/prompts/04-codegen.md.
---

# Codegen Full Stack

## Workflow
1. Read `references/codegen.md` for authoritative full-stack codegen rules.
2. Read current sprint tasks and requirements in `docs/sprint/` and `docs/requirements/`.
3. Implement frontend changes in `front-end/` and backend changes in `back-end/` as needed, plus required docs updates.
4. Update `docs/sprint/<Sprint-N>/Tasks.md` with the final status.

## Output Requirements
- Provide complete, production-ready code with no TODOs.
- Follow UUIDv7, enum/status, contract, and PSC rules from `references/codegen.md`.
- Regenerate API artifacts and client code when contracts change.
- When presenting user choices, use a numbered list in the format `1. Option: description`.

## Example Choices
1. Implement full stack: FE + BE + migrations as required.
2. Implement backend only: Leave frontend untouched.

## Resources
- `references/codegen.md` is the authoritative prompt and deliverables.
