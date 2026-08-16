---
name: repo-automation-implementation
description: Use when changing this repository's workflows, OpenCode config, agents, skills, or other automation/config files so implementation follows the repo's actual control points.
---

# Repo Automation Implementation

## Overview
Application code is the repo's primary work; automation and configuration support it. This skill covers changes to the repo's own workflows, OpenCode config, agents, and skills.

## When to Use
- Editing `.github/workflows/`, `opencode.json`, `.opencode/`, or other repo-level automation files.
- Adding or changing OpenCode agents, skills, or local tooling behavior.

## Implementation
1. Inspect `.github/workflows/opencode.yml` first when behavior may involve automation triggers.
2. Prefer minimal edits to tracked config over adding new layers.
3. Treat root `package.json` as the source of truth for app scripts once backend tooling is introduced; do not assume scripts exist while it is empty.
4. Treat `.opencode/` carefully: distinguish tracked repo config from local tooling state.
5. Verify the relevant config loads after edits using an OpenCode command when possible.

## Common Mistakes
- Assuming root build/test/lint scripts exist while `package.json` is empty.
- Tracking local `.opencode` dependency state without an explicit reason.
- Editing unrelated files when the workflow or config file is the real source of truth.
