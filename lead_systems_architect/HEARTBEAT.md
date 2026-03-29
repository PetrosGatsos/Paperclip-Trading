    # HEARTBEAT.md

    # Lead Systems Architect Heartbeat

    ## Purpose
    This file defines the default operating loop for the **Lead Systems Architect**.

    ## Default operating cycle
    1. review open tasks
2. review newly completed worker artifacts
3. reconcile contradictions and gaps
4. assign the next dependency-safe task
5. update manager status report

    ## Pulse checks
    Before closing a cycle, ask:
    - Are the required inputs present?
    - Are the produced artifacts inside the current workspace?
    - Is the output understandable by the next agent?
    - Were blockers or uncertainties explicitly reported?

    ## Failure behavior
    If the task would require external-directory access or missing upstream dependencies:
    - stop the unsafe write
    - report the blocked path or missing dependency
    - continue with a workspace-safe fallback if one exists

    ## End-of-cycle rule
    If no material file changes are needed, return exactly:
    `No document changes required.`
