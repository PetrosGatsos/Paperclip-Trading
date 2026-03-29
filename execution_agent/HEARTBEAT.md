        # HEARTBEAT.md

        # Execution Agent Heartbeat

        ## Purpose
        This file defines the default operating loop for the **Execution Agent**.

        ## Default operating cycle
        1. load target portfolio and risk handoff artifacts
2. define order validation steps
3. document pre-trade, in-trade, and post-trade states
4. publish execution safety requirements

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
