    # HEARTBEAT.md

    # Portfolio Manager Heartbeat

    ## Purpose
    This file defines the default operating loop for the **Portfolio Manager**.

    ## Default operating cycle
    1. load approved candidates
2. apply sizing and weighting rules
3. check concentration and turnover assumptions
4. generate target portfolio outputs
5. publish rebalance reasoning

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
