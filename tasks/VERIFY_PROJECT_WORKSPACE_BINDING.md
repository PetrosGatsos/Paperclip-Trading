# Title
Verify project workspace binding and confirm repo-backed execution context

# Description
Your job is to verify whether this Paperclip run is actually operating inside the intended repo-backed project workspace, rather than a fallback workspace.

## Goal
Confirm the true execution context before any more hiring or delegation tasks are attempted.

## What to check
Determine whether the current run is using:
- the intended project workspace tied to the uploaded/imported repo
or
- a fallback workspace under `/paperclip/instances/default/workspaces/...`

## Required checks
1. Confirm the current workspace path being used for this run.
2. Confirm whether the repo-backed project files are actually visible from the current run context.
3. Confirm whether the project root `AGENTS.md` is being used, or whether the run is instead loading only the agent-local instruction file.
4. Confirm whether outputs written by this run land inside the intended project workspace.
5. Determine whether this run can safely use the repo as the canonical source of truth for downstream agent bootstrapping.

## Required outputs
Create or update these files inside the current writable workspace if possible:
- `docs/WORKSPACE_BINDING_REPORT.md`
- `docs/PROJECT_CONTEXT_REPORT.md`
- `docs/SMOKE_TEST.md`

## Final response requirements
At the end, clearly state one of these:
- `Project workspace binding confirmed. Safe to proceed with hire creation.`
or
- `Fallback workspace still active. Do not proceed with agent bootstrapping until workspace binding is fixed.`
