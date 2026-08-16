---
name: repo-review-gate
description: Use before claiming repository automation/config work is complete to review workflow triggers, config discovery, tracked versus local state, and verification coverage. Invoked by the code-reviewer agent and by anyone completing workflow, config, agent, or skill changes.
---

# Repo Review Gate

## Overview
Review repo changes for automation and configuration risks in addition to code review: workflow triggers, config discovery, tracked versus local state, and verification coverage (including the app's tests and build once they exist). This is the repo-specific review checklist for `code-reviewer` and for anyone claiming completion on workflow, config, agent, or skill changes.

## When to Use
- Before claiming completion on workflow, config, agent, or skill changes.
- When reviewing diffs that affect repo automation, OpenCode behavior, or the app's build/test/verification paths.

## Implementation
1. Check whether `.github/workflows/opencode.yml` trigger behavior still matches intent.
2. Check whether new OpenCode config is discoverable from the repository itself.
3. Check whether `.opencode` changes belong in tracked config or local tooling state.
4. Confirm verification actually exercised the changed config, workflow, or app code path.
5. Report findings with file references and explicit risks.

## Common Mistakes
- Reviewing only syntax and missing behavior changes.
- Claiming completion without verifying config discovery.
- Mixing local plugin state with tracked repo configuration.
