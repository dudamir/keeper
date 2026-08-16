---
name: repo-work-planning
description: Use when scoping or planning work in this repository so planning starts from the repo's workflow, AGENTS.md, opencode.json, and .opencode state before implementation.
---

# Repo Work Planning

## Overview
Plan from the repo's real automation surface, not generic app assumptions.

For tracked feature work, the durable planning artifact is `docs/specs/<feature-name>.md` plus a PR that references the related GitHub issue.

## When to Use
- New repo work needs scope, a design path, or implementation handoff.
- The request touches workflows, OpenCode config, agents, skills, or repo automation.

## Implementation
1. Read `AGENTS.md`, `.github/workflows/opencode.yml`, `opencode.json`, and relevant `.opencode/` files first.
2. Treat this repo as automation/config-first unless the repo contents prove otherwise.
3. If the task changes behavior, invoke `brainstorming` before implementation.
4. For tracked work, write or update `docs/specs/<feature-name>.md` after approval.
5. Open a PR for the spec and reference the related GitHub issue in the PR body.
6. If the task is architectural, continue to `writing-plans` after the spec is approved.
7. If execution should be tracked in GitHub, hand off to `issue-planner` or use `github-issue-plan-sync` to keep the issue aligned with the spec and PR.
8. If the work spans UX and backend, approve `design.md` before UI implementation and sequence backend work in dependency order.

## Common Mistakes
- Assuming root `package.json` defines runnable app workflows.
- Planning from README prose without checking workflow/config files.
- Treating the GitHub issue as the only durable planning artifact.
- Starting implementation before repo-specific scope is clear.
