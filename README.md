# Codex Skills Bundle

Monolithic repository containing Codex skills used in this environment.

## Contents
### Skills
- audit: Security and code quality audit for frontend and backend changes.
- codegen: Full-stack feature implementation (frontend + backend + DB/migrations).
- context-preflight: Context mapping and standardization across repos.
- discovery: Requirements discovery, scope definition, and acceptance criteria.
- docs-writer: Technical documentation updates and authoring.
- planner: Sprint planning and backlog organization.
- test-generator: Automated test generation for frontend and backend.

### Workflow
- workflow-engineer: Development workflow orchestration and sequencing across skills.

## Install (clone)
Clone into your Codex home and use it as the skills root:

```sh
git clone git@github.com:paulojalowyj/codex_skills.git "$CODEX_HOME/skills"
```

If you already have a skills directory, you can clone elsewhere and symlink:

```sh
git clone git@github.com:paulojalowyj/codex_skills.git ~/codex_skills
ln -s ~/codex_skills "$CODEX_HOME/skills"
```

## Notes
- Each skill lives in its own folder with a `SKILL.md` entrypoint.
 - Workflow references are in `workflow-engineer/references/workflows.md`.
