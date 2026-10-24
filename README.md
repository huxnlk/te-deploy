# te-deploy

Phone-approved production deploys for TE apps. Public on purpose: on this account's GitHub plan,
the "required reviewer" approval gate only works on public repos.

1. There is no app code here and no secret in any file.
2. Each app has its own environment: `odoo-mcp`, `mission-control` and `aatuti-infra-mcp`. It has
   no required reviewer (a thread dispatches a deploy only on Robbie's own chat message) and only
   runs from `main`. Its deploy key, host and port live in that environment,
   and each app's key works only for that app.
3. The key on the target can only start a deploy of one commit, start a rollback, or read a
   run's status. The target refuses any commit that isn't on the app's private `main`.
4. Logs show step names and PASS or FAIL only.

Design and setup: huxnlk/ai-ops-2026 `11-remote-execution/PHONE-APPROVED-DEPLOYS-2026-10-23.md`
(private). Changes to this repo go through a pull request.
