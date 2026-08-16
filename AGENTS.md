# Repository Notes

- This is an application repo. The project implements a web server, HTTP APIs, background services, and an event hub (pub/sub). The root `package.json` is currently empty and `package-lock.json` has no packages, so there are no root `build`, `test`, `lint`, or `typecheck` commands to run yet; app tooling will be introduced with the backend.
- The only tracked automation is `.github/workflows/opencode.yml`. It runs `anomalyco/opencode/github@latest` on `issue_comment` and `pull_request_review_comment` events, but only when the comment body starts with or contains `/oc` or `/opencode`.
- The workflow uses model `opencode/big-pickle` and expects `OPENCODE_API_KEY` from GitHub secrets. If automation behavior changes, start by editing `.github/workflows/opencode.yml`.
- `.opencode/` mixes tracked repo config and local tooling state. Tracked: `.opencode/agents/` (repo-local agents) and `.opencode/skills/` (repo-local skills). Local state (ignored via `.opencode/.gitignore`): `.opencode/package.json`, `.opencode/package-lock.json`, and `node_modules/`, used only for the local plugin dependency `@opencode-ai/plugin@1.18.18`.
- Use `npm --prefix .opencode install` if the local plugin environment needs to be recreated or refreshed.
- Repo-local agents: `planner`, `issue-planner`, `backend-implementer`, `ux-designer`, `ui-implementer`, `code-reviewer`. Repo-local skills: `repo-work-planning`, `github-issue-plan-sync`, `repo-automation-implementation`, `repo-ux-to-ui-handoff`, `repo-review-gate`.
- Tracked feature planning uses `docs/specs/<feature-name>.md` plus a PR referencing the related GitHub issue. The planner owns the spec; `issue-planner` keeps the GitHub issue aligned with the spec, PR, and actual state.
