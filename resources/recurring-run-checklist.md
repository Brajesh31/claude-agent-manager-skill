# Recurring Agent Run Checklist

Use this checklist when scheduling an agent task to run repeatedly through a cron-compatible workflow.

## Schedule Definition

- **Job name:**
- **Agent ID:**
- **Task owner:**
- **Schedule / cron expression:**
- **Time zone:**
- **Expected run duration:**
- **Start date:**
- **End date or stop condition:**

## Safe Repeatability

- [ ] The task is safe to run more than once.
- [ ] Duplicate execution will not create harmful side effects.
- [ ] The task checks whether a previous run is still active.
- [ ] Inputs and outputs are stored in known locations.
- [ ] Output filenames or records are uniquely identifiable.
- [ ] External actions require appropriate approval.
- [ ] Retries will not repeat irreversible work unexpectedly.

## Observability

- [ ] Each run records a start time and completion status.
- [ ] Logs include a run identifier.
- [ ] Errors and timeouts are visible to the owner.
- [ ] Output is checked, not merely process status.
- [ ] Resource use is monitored.
- [ ] A missed or overlapping run can be identified.

## Recovery and Stop Conditions

- [ ] Retry policy is defined.
- [ ] Maximum retry count is defined.
- [ ] Overlap behavior is defined.
- [ ] The job can be paused or disabled.
- [ ] A clear stop condition exists.
- [ ] Ownership transfers are documented.

## Run Record

| Run ID | Start time | End time | Status | Output reference | Notes |
|---|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

Do not schedule recurring work until ownership, overlap handling, logging, retry behavior, and stop conditions are understood.
