# Runtime Workspace Fix Note

These repo files help only if the agent is actually launched in the repo workspace.

## The runtime should use this repo checkout as the working directory
`/paperclip/instances/default/projects/b35e4c8e-f9d3-4114-b4aa-2d45a693e7d3/0182605d-301c-4393-9d66-5b3519153c07/Paperclip-Trading`

## The Lead Systems Architect instructions path should ideally point to
`/paperclip/instances/default/projects/b35e4c8e-f9d3-4114-b4aa-2d45a693e7d3/0182605d-301c-4393-9d66-5b3519153c07/Paperclip-Trading/lead_systems_architect/AGENTS.md`

## Why the error happens
If the agent starts in:
`/paperclip/instances/default/workspaces/...`
then the repo path is treated as an external directory and OpenCode permission rules can block it.

## Practical consequence
- Repo files can be present and correct
- but the run can still fail with `external_directory`
- unless the runtime or project binding starts the agent inside the repo workspace
