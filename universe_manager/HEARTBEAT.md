        # HEARTBEAT.md

        # Universe Manager Heartbeat

        ## Purpose
        This file defines the default operating loop for the **Universe Manager**.

        ## Default operating cycle
        1. load the current universe mandate
2. build the candidate set
3. apply eligibility rules
4. rank by market cap
5. publish the final universe and change log

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
