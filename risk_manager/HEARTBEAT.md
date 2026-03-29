        # HEARTBEAT.md

        # Risk Manager Heartbeat

        ## Purpose
        This file defines the default operating loop for the **Risk Manager**.

        ## Default operating cycle
        1. load ranked candidates
2. apply trade-level checks
3. apply portfolio-level checks
4. evaluate kill-switch conditions
5. publish approvals, rejections, and active risk state

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
