---
name: repo-ux-to-ui-handoff
description: Use when UX direction must be turned into implementation-ready UI guidance so UI work does not invent missing flow, copy, or interaction decisions.
---

# Repo UX To UI Handoff

## Overview
UI work should start from explicit UX direction, not guessed intent.

`ux-designer` owns `design.md`; `ui-implementer` consumes it.

## When to Use
- UX work is finished and UI implementation needs a clear handoff.
- A UI task is blocked on missing flow, copy, or behavior details.

## Implementation
1. Ensure `design.md` includes flow, structure, layout intent, user-visible behavior, copy, responsive requirements, accessibility requirements, constraints, and unresolved questions.
2. Mark what is approved versus still undecided.
3. Specify when existing shared components must be reused and when a new shared component is justified; leave component composition and APIs to the UI implementer.
4. Hand off only implementation-ready decisions to the UI implementer.
5. If key UX details are missing, stop and return to UX definition instead of guessing.

## Common Mistakes
- Starting UI work from a vague concept only.
- Leaving copy or behavior implicit.
- Letting the implementer invent missing design decisions.
