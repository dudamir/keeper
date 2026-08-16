---
name: github-issue-plan-sync
description: Use when a GitHub issue should act as the living plan for repository work and needs to stay aligned with approved scope and actual execution status.
---

# GitHub Issue Plan Sync

## Overview
Keep issue plans synchronized with the approved spec, its PR, and current repo state.

## When to Use
- Creating a new planning issue.
- Updating an issue after scope approval, spec PR creation, implementation progress, or blockers.

## Implementation
1. Copy only approved scope, acceptance criteria, and checklist items.
2. Link the issue to `docs/specs/<feature-name>.md` and the spec PR.
3. Keep issue content compact: summary, spec link, PR link, acceptance criteria, checklist, status, blockers.
4. Use `gh issue create`, `gh issue edit`, or `gh issue comment` to reflect the current state.
5. If the repo state changed, update the issue to match reality instead of restating intent.
6. Report GitHub auth or permission blockers exactly.

## Common Mistakes
- Inventing scope or acceptance criteria in the issue.
- Letting the issue drift away from the current spec or spec PR.
- Letting issue status drift from the actual worktree or completed verification.
