# Agent Manager Skill

A Claude Code skill for coordinating multiple local command-line agents through isolated tmux sessions. It covers agent discovery, session startup and monitoring, task assignment, output review, and cron-friendly recurring work.

The repository's skill instructions use the agent-manager project as the runtime. Installing this Claude Code skill does not install or configure that runtime.

## What It Covers

- Diagnose the local agent-manager environment.
- List configured local agents.
- Start agents in separate tmux sessions.
- Monitor an agent's output and follow its logs.
- Assign bounded tasks to individual agents.
- Coordinate parallel work with clear ownership.
- Plan recurring work using cron-compatible scheduling.

## Prerequisites

- tmux installed and available in the shell.
- Python 3 installed and available as python3.
- The agent-manager runtime cloned and configured in the intended workspace.
- Agent configuration files and workspace paths prepared.
- Appropriate permissions for any files or commands the agents will use.

## Installation

Clone this skill into the Claude Code skills directory:

~~~bash
git clone https://github.com/Brajesh31/claude-agent-manager-skill.git ~/.claude/skills/agent-manager
~~~

Clone the agent-manager runtime separately, as described by the skill instructions:

~~~bash
git clone https://github.com/fractalmind-ai/agent-manager-skill.git
~~~

Follow the runtime project's current setup instructions before invoking its scripts.

## Usage

Invoke the skill in Claude Code:

~~~text
/agent-manager
~~~

Provide the agent identifier, workspace, task, expected output, and whether the work is one-time or recurring.

## Runtime Commands

These command patterns are included in SKILL.md. Run the diagnostic before starting work and confirm the runtime's current usage instructions if its interface has changed.

~~~bash
python3 agent-manager/scripts/main.py doctor
python3 agent-manager/scripts/main.py list
python3 agent-manager/scripts/main.py start EMP_0001
python3 agent-manager/scripts/main.py monitor EMP_0001 --follow
python3 agent-manager/scripts/main.py assign EMP_0002 <<'EOF'
Follow teams/fractalmind-ai-maintenance.md Workflow
EOF
~~~

Use actual agent identifiers and task instructions from your own runtime configuration. The example identifiers above are illustrative.

## Recommended Workflow

1. Run the environment diagnostic.
2. List available agent configurations.
3. Confirm the agent identifier and workspace.
4. Start the required tmux session.
5. Assign one bounded task with explicit inputs and acceptance criteria.
6. Monitor output and inspect the logs.
7. Validate generated files and results independently.
8. Review the changes before integrating them.
9. Stop sessions that no longer need to run.
10. Schedule recurring tasks only when the cadence, owner, and stop condition are explicit.

## Parallel Work Principles

- Split work by deliverable, not vague topic.
- Give each agent a distinct file or workspace boundary.
- Prefer separate worktrees or workspaces for concurrent code changes.
- Define shared interfaces and file ownership before starting.
- Avoid simultaneous edits to the same files.
- Require each agent to report changed files, test results, and unresolved issues.
- Integrate work through review rather than assuming parallel outputs are compatible.

## Included Resources

- [Agent task brief template](resources/agent-task-brief-template.md): specify ownership, scope, inputs, acceptance criteria, and outputs.
- [Parallel work coordination guide](resources/parallel-work-coordination.md): plan independent tasks and integrate agent results safely.
- [Recurring run checklist](resources/recurring-run-checklist.md): prevent overlapping jobs and make scheduled runs observable and stoppable.

## Repository Structure

~~~text
claude-agent-manager-skill/
├── SKILL.md
├── README.md
├── LICENSE
└── resources/
    ├── agent-task-brief-template.md
    ├── parallel-work-coordination.md
    └── recurring-run-checklist.md
~~~

## Operational Safety

- A running tmux session does not prove that the agent completed its task.
- Check output and logs for errors, stalled work, or incomplete results.
- Do not allow concurrent agents to modify shared files without an ownership plan.
- Review generated code and commands before running or merging them.
- Keep credentials and sensitive data out of prompts, logs, and task templates.
- For recurring jobs, define overlap handling, retry behavior, and a stop condition.

## Upstream Runtime

- [agent-manager-skill runtime](https://github.com/fractalmind-ai/agent-manager-skill)

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root LICENSE file for the complete terms.
