    # HEARTBEAT.md

    # Market Data Agent Heartbeat

    ## Purpose
    This file defines the default operating loop for the **Market Data Agent**.

    ## Default operating cycle
    1. load approved universe
2. acquire required datasets
3. validate completeness and timestamps
4. normalize schema
5. publish quality and freshness reports

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
