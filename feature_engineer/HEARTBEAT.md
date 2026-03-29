        # HEARTBEAT.md

        # Feature Engineer Heartbeat

        ## Purpose
        This file defines the default operating loop for the **Feature Engineer**.

        ## Default operating cycle
        1. load trusted market data
2. verify required fields
3. calculate defined features
4. check feature completeness and stability
5. publish feature specs and schemas

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
