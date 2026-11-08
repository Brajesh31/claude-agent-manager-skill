# claude-agent-manager-skill

A Claude Code skill for coordinating multiple local command-line agents through tmux sessions.

## Overview

This skill helps operate several CLI agents on one machine. It covers agent discovery, session creation, task assignment, output monitoring, process control, and recurring task scheduling.

Each agent should have a clear workspace and responsibility. Running multiple agents without isolation or coordination can create file conflicts and inconsistent changes.

## Main Capabilities

- Start and stop configured agents.
- Run agents in separate tmux sessions.
- Assign tasks to individual agents.
- Monitor output and follow logs.
- List configured agents and inspect local setup.
- Schedule recurring tasks with cron-compatible workflows.
- Coordinate parallel work across independent workspaces.

## Prerequisites

The documented workflow requires:

- tmux.
- Python 3.
- The agent manager project installed and configured in the intended workspace.
- CLI access to the agents being managed.

Review the setup instructions in `SKILL.md` before running commands.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-agent-manager-skill.git ~/.claude/skills/agent-manager
```

Install and configure the required agent-manager runtime separately.

## Usage

Invoke the skill for local agent operations:

```text
/agent-manager
```

Provide the agent identifier, workspace, intended task, and whether the operation is one-time or recurring.

## Typical Workflow

1. Run the environment diagnostic.
2. List available agent configurations.
3. Confirm the correct workspace and agent identifier.
4. Start the required tmux session.
5. Assign a bounded task with a clear expected output.
6. Monitor logs and process status.
7. Review generated changes before integrating them.
8. Stop or hibernate agents when work is complete.
9. Schedule recurring tasks only when the cadence and ownership are clear.

## Parallel Work Guidelines

- Give each agent a distinct task boundary.
- Prefer separate worktrees or workspaces for concurrent code changes.
- Define shared interfaces before parallel implementation.
- Avoid multiple agents editing the same files simultaneously.
- Review all outputs before merging work.
- Keep a record of task ownership and session identifiers.

## Repository Contents

- `SKILL.md`: Main agent management instructions.
- `README.md`: Prerequisites, operating workflow, and coordination guidance.

## Operational Checklist

- tmux sessions are named consistently.
- Agent workspaces are isolated where needed.
- Task instructions include acceptance criteria.
- Logs are checked for errors and incomplete work.
- Resource usage is monitored.
- Recurring tasks have a clear schedule and stop condition.
- Changes are reviewed before being integrated.

## Safety Note

A running process is not proof of successful work. Inspect the output, validate artifacts, and confirm the intended result before reporting an agent task as complete.
