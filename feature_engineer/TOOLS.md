    # TOOLS.md

    # Feature Engineer Tooling Guide

    ## Purpose
    This file defines how the **Feature Engineer** should use tools in this project.

    ## Allowed tool behavior
    - read validated market data contracts
- write feature documentation and schemas
- flag unstable or missing features explicitly

    ## Tool boundaries
    - Never attempt to read from or write to any `/instructions/` path.
    - Never use tools to self-modify role files during normal project execution.
    - Prefer creating or updating explicit markdown artifacts in the workspace.
    - If a target file already exists and no material change is required, do not call an edit tool.

    ## Quality bar
    Before finalizing any output, verify:
    - the output is in the workspace
    - the file names match the requested deliverables
    - the content is useful to downstream agents
    - blockers are stated clearly if progress is limited

    ## Safe fallback
    If a required write would leave the workspace boundary, stop and report the path instead of attempting the change.
