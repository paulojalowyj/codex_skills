# Codex Skills Bundle

Monolithic repository containing Codex skills used in this environment.

## Contents
- audit
- codegen
- context-preflight
- discovery
- docs-writer
- engineer
- planner
- test-generator

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
- Workflow references are in `engineer/references/workflows.md`.
