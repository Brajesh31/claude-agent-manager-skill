# Agent Manager Skill

A Claude skill for coordinating multiple local command-line agents through separate tmux sessions. It provides a concise workflow for starting and stopping agents, assigning tasks, monitoring their output, and scheduling recurring work.

## What This Skill Covers

- Running several CLI agents in parallel using independent tmux sessions.
- Starting and stopping agents by their configured identifiers.
- Monitoring agent output and following logs during execution.
- Assigning tasks to individual agents.
- Scheduling recurring agent work with cron-friendly commands.
- Checking the local setup and listing configured agents.

## Repository Structure

- `SKILL.md`: Skill instructions, prerequisites, common commands, and operational notes.
- `LICENSE`: MIT License for this repository.

## Prerequisites

The workflow requires tmux and Python 3. The upstream project is installed in the workspace using the setup command documented in `SKILL.md`. Check its own installation instructions and configuration requirements before running agent commands.

## Typical Workflow

1. Install the agent manager in the intended workspace.
2. Run its diagnostic command to confirm that the environment is ready.
3. List configured agents and identify the agent to operate.
4. Start the required agent and assign a clearly scoped task.
5. Monitor the agent's output, using follow mode when active observation is needed.
6. Use cron or another scheduler for recurring tasks where appropriate.

## Usage

Add this skill to a Claude-compatible skills environment. Invoke it when you need help operating multiple local CLI agents or managing their task execution through tmux.

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
