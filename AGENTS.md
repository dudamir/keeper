# Repository Notes

- Treat this as an automation/config repo, not an app repo. `package.json` at the root is empty and `package-lock.json` has no packages, so there are currently no root `build`, `test`, `lint`, or `typecheck` commands to run.
- The only tracked automation is `.github/workflows/opencode.yml`. It runs `anomalyco/opencode/github@latest` on `issue_comment` and `pull_request_review_comment` events, but only when the comment body starts with or contains `/oc` or `/opencode`.
- The workflow uses model `opencode/big-pickle` and expects `OPENCODE_API_KEY` from GitHub secrets. If automation behavior changes, start by editing `.github/workflows/opencode.yml`.
- `.opencode/` is a separate npm project used only for the local OpenCode plugin dependency `@opencode-ai/plugin@1.18.18`.
- Use `npm --prefix .opencode install` if the local plugin environment needs to be recreated or refreshed.
- `.opencode/.gitignore` ignores `.opencode/package.json`, `.opencode/package-lock.json`, and `node_modules/`. Treat `.opencode` as local tooling state unless the user explicitly wants those files tracked or changed.
