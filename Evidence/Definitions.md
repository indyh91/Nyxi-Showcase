## Definitions
- POLICY_ALLOW / POLICY_DENY / POLICY_UNKNOWN are authorization-time decisions.
- Execution started (committed_started) means the irreversible sink began.
- Outcome is execution result: SUCCEEDED / TIMED_OUT / FAILED.
- POLICY_ALLOW does not imply SUCCEEDED (timeouts prove cap enforcement).
