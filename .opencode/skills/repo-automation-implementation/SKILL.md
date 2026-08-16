---
name: repo-automation-implementation
description: Use when changing this repository's workflows, OpenCode config, agents, skills, or other automation/config files so implementation follows the repo's actual control points.
---

# Repo Automation Implementation

## Overview
This repo's main execution surface is configuration and automation, not application code.

## When to Use
- Editing `.github/workflows/`, `opencode.json`, `.opencode/`, or other repo-level automation files.
- Adding or changing OpenCode agents, skills, or local tooling behavior.

## Implementation
1. Inspect `.github/workflows/opencode.yml` first when behavior may involve automation triggers.
2. Prefer minimal edits to tracked config over adding new layers.
3. Treat root `package.json` as non-authoritative for scripts unless it changes from `{}`.
4. Treat `.opencode/` carefully: distinguish tracked repo config from local tooling state.
5. Verify the relevant config loads after edits using an OpenCode command when possible.

## Common Mistakes
- Assuming missing root scripts exist.
- Tracking local `.opencode` dependency state without an explicit reason.
- Editing unrelated files when the workflow or config file is the real source of truth.
