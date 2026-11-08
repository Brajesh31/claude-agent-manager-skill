# Parallel Agent Work Coordination

Use this guide before starting multiple local agents on related work.

## 1. Decompose the Work

Split the overall task into deliverables that can be completed and reviewed independently. Each task should have:

- One accountable agent.
- A clearly bounded scope.
- Explicit input and output.
- Acceptance criteria.
- Dependencies and handoff requirements.

Avoid assigning the same broad task to several agents. That creates duplicate work and conflicting edits.

## 2. Assign Ownership

| Workstream | Agent ID | Workspace / worktree | Owned files | Dependencies | Status |
|---|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

Give concurrent agents separate worktrees or isolated workspaces when they need to edit code. If files must be shared, nominate one owner and define a handoff sequence.

## 3. Define Interfaces First

Before parallel execution, agree on:

- File and folder ownership.
- API or schema contracts.
- Shared naming conventions.
- Expected data formats.
- Test commands and acceptance criteria.
- How conflicts and blockers are reported.

## 4. Monitor Work

For each agent, record:

- Session and agent identifier.
- Current task.
- Last meaningful output.
- Errors or blockers.
- Files modified.
- Whether the agent is waiting, running, or complete.

Do not infer progress from an open terminal or live tmux session. Inspect actual output and task artifacts.

## 5. Integrate Results

1. Collect each agent's completion report.
2. Review each change independently.
3. Run relevant tests after combining the work.
4. Resolve interface mismatches and overlapping changes.
5. Confirm that no unassigned files were modified.
6. Record accepted, rejected, and deferred work.

## 6. Conflict Handling

When two agents modify the same file:

- Pause further changes to that file.
- Compare the intent and evidence behind both changes.
- Select one integration owner.
- Reconcile the changes deliberately.
- Re-run validation after integration.

## Completion Gate

- [ ] Each workstream has a clear owner.
- [ ] Workspace and file boundaries are explicit.
- [ ] Shared interfaces were agreed in advance.
- [ ] Each agent reported outputs and tests.
- [ ] Combined changes were reviewed and validated.
