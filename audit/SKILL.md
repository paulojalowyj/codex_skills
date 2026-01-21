---
name: audit
description: Security and code quality audit for frontend and backend changes. Use when asked to review code, run audits, produce findings, or update docs/security/posture.md and docs/Action_Items.md.
---

# Audit

## Overview
Perform a structured security and quality audit, then report findings in docs.

## Workflow
1. Read `references/audit.md` for scope and required checks.
2. Inspect code and configs; cite evidence with file paths and snippets.
3. If audits require external tools or network access, request approval first.
4. Record findings in `docs/security/posture.md` and action items in `docs/Action_Items.md`.

## Output Requirements
- Each finding includes title, severity, location, evidence, recommendation, and owner.
- Include positives (good practices) where applicable.
- When presenting user choices, use a numbered list in the format `1. Option: description`.

## Example Choices
1. Run a full audit now: Review FE/BE scope and produce findings.
2. Focus only on backend risks: Skip frontend checks.

## Resources
- `references/audit.md` is the authoritative prompt and deliverables.
