# Workflows

## Workflow Selector
Use this quick guide to pick the right flow.

| Need | Workflow |
| --- | --- |
| Validate scope before implementation or review a change set | Review Workflow |
| Implement new feature end-to-end | Codegen Workflow |
| Prepare for release or major deploy | Release Readiness Workflow |
| Urgent production fix | Hotfix / Incident Workflow |
| Schema or data change | Migration / Schema Change Workflow |
| Improve performance or cost | Performance Tuning Workflow |
| Docs work only | Documentation-Only Workflow |

## Skill ID Legend
Use these IDs in workflow steps to reference the corresponding skills.

| Skill | ID |
| --- | --- |
| Audit | `audit` |
| Codegen Full Stack | `codegen-full-stack` |
| Context Preflight | `context-preflight` |
| Discovery | `discovery` |
| Docs Writer | `docs-writer` |
| Planner | `planner` |
| Test Generator | `test-generator` |

## Review Workflow (requires `discovery` + `planner`)
**Use when**: reviewing a feature, change set, or PR scope before implementation.
**Sequence**:
1. `discovery`: capture requirements, constraints, and acceptance criteria in `docs/requirements/<feature-name>/`.
2. `planner`: create a sprint plan in `docs/sprint/<Sprint-N>/` using the discovery pack.
3. `audit`: review current code/plan risks and record findings in `docs/security/posture.md` + `docs/Action_Items.md`.
4. `test-generator`: outline or add missing tests as needed.
5. `docs-writer`: update docs impacted by review (routes, API index, runbooks).
**Exit criteria**:
- `docs/requirements/<feature-name>/` complete.
- `docs/sprint/<Sprint-N>/` complete.
- Findings and action items logged.

## Codegen Workflow (requires `discovery` + `planner`)
**Use when**: implementing features with code changes.
**Sequence**:
1. `discovery`: produce requirements pack.
2. `planner`: produce sprint plan and tasks.
3. `codegen-full-stack`: implement tasks per owner.
4. `test-generator`: add tests for new/changed behavior.
5. `docs-writer`: update docs and indexes; add docstring insertion notes if needed.
6. `audit` (release-bound): run a quick audit pass if the change is release-critical.
**Exit criteria**:
- Code implemented in target repo(s) with tasks updated.
- Tests added or documented gaps.
- Docs updated and action items logged.

## Release Readiness Workflow
**Use when**: preparing a release or major deploy.
**Sequence**:
1. `context-preflight`: rebuild context pack.
2. `planner`: confirm scope, risk register, and release timeline.
3. `audit`: security + quality + compliance checks.
4. `test-generator`: ensure coverage for high-risk paths.
5. `docs-writer`: update runbooks, ADRs, and release notes.
**Exit criteria**:
- Context pack refreshed.
- Security posture updated with findings.
- Release notes and runbooks updated.
- Action items logged.

## Hotfix / Incident Workflow
**Use when**: urgent production issues.
**Sequence**:
1. `discovery` (rapid): capture the incident scope and immediate constraints.
2. `planner` (micro): define a narrow, time-boxed plan and rollback steps.
3. `codegen-full-stack`: implement the fix.
4. `test-generator`: add focused regression tests.
5. `docs-writer`: update runbook with incident learnings.
**Exit criteria**:
- Fix deployed or ready.
- Regression tests added.
- Runbook updated.
- Action items logged.

## Migration / Schema Change Workflow
**Use when**: database schema changes or data migrations.
**Sequence**:
1. `discovery`: document data contracts and risks.
2. `planner`: schedule migration steps and downtime/rollback.
3. `codegen-full-stack`: implement Alembic migration and model changes.
4. `audit`: validate data risks and security implications.
5. `docs-writer`: update schema docs, ADRs, and runbooks.
**Exit criteria**:
- Migration scripts added and documented.
- Rollback plan captured.
- Action items logged for dependent teams.

## Performance Tuning Workflow
**Use when**: improving performance or cost.
**Sequence**:
1. `discovery`: capture perf targets and baseline metrics.
2. `planner`: define experiments and measurement plan.
3. `audit`: identify bottlenecks and risks.
4. `codegen-full-stack`: implement optimizations.
5. `test-generator`: add perf or regression tests.
6. `docs-writer`: update performance notes and SLOs.
**Exit criteria**:
- Metrics recorded and improvements measured.
- Docs updated with new targets or guidance.
- Action items logged.

## Documentation-Only Workflow
**Use when**: documentation work without code changes.
**Sequence**:
1. `discovery`: define scope and audience.
2. `planner`: outline doc tasks and ownership.
3. `docs-writer`: produce or update docs.
4. `audit` (optional): validate consistency and completeness.
**Exit criteria**:
- Required docs updated.
- Action items logged for any dependencies.
