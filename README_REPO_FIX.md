# Complete Repo Bootstrap Pack

This pack includes:
- repo-root configuration files
- all agent definition folders
- helper task templates
- a runtime workspace note

## What this pack solves
- puts all agent role files into the repo
- adds a repo-root `AGENTS.md`
- adds `opencode.json`
- gives you task templates for workspace verification and actual hire approvals

## Important limitation
These files make the repo complete, but they do **not** by themselves guarantee that the `external_directory` error disappears.

That error happens when the agent is launched outside the repo workspace and the repo path is treated as external.

For this to work normally, the agent runtime should start in the repo checkout directory.

## Recommended next order
1. Commit these files to the repo.
2. Re-run the workspace verification task from `tasks/VERIFY_PROJECT_WORKSPACE_BINDING.md`.
3. Only after workspace binding is confirmed, run the hire-approval task from `tasks/CREATE_ACTUAL_HIRE_APPROVALS.md`.
