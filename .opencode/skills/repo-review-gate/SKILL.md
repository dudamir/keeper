---
name: repo-review-gate
description: Use before claiming repository work is complete to review workflow triggers, config discovery, tracked versus local state, and verification coverage.
---

# Repo Review Gate

## Overview
Review this repo for automation and configuration risks, not just code style.

## When to Use
- Before claiming completion on workflow, config, agent, or skill changes.
- When reviewing diffs that affect repo automation or OpenCode behavior.

## Implementation
1. Check whether `.github/workflows/opencode.yml` trigger behavior still matches intent.
2. Check whether new OpenCode config is discoverable from the repository itself.
3. Check whether `.opencode` changes belong in tracked config or local tooling state.
4. Confirm verification actually exercised the changed config or workflow path.
5. Report findings with file references and explicit risks.

## Common Mistakes
- Reviewing only syntax and missing behavior changes.
- Claiming completion without verifying config discovery.
- Mixing local plugin state with tracked repo configuration.
