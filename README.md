# Agent Harness Template

A self-optimizing, agent-agnostic harness for structured AI-assisted development.

Use the Quick Start prompt to have your coding agent adapt this template to the target repository's real structure, tooling, and workflows.

It keeps planning, execution, and validation artifacts inside the repository as file-based state: no chat-history dependency, no external services, and no orchestration layer. Works with Claude, Codex, or any LLM-based coding agent.

## Purpose

Most agent failures come from weak repo context and inconsistent execution structure. This template fixes that by bootstrapping a repeatable task loop, then having the agent self-optimize the harness for each target repo.

A brief defines *what*, a plan defines *how*, and a run record proves *it worked*.

## Quick Start

1. Copy the harness files into your repo root: `HARNESS.md`, `ARCHITECTURE.md`, `SETUP.md`, `.harness/`, and `docs/`
2. Open `SETUP.md` and paste the prompt into your coding agent
3. The agent self-optimizes the harness to your repo's real structure and workflows

That's it. After setup, follow the Task Loop in `HARNESS.md`.

## What's Inside

| Path | Purpose |
|---|---|
| `HARNESS.md` | Agent entry point — repo map, working rules, task loop |
| `ARCHITECTURE.md` | Structure, data flow, and constraints |
| `SETUP.md` | Easy Mode bootstrap prompt (deleted after setup) |
| `docs/briefs/` | Task brief template |
| `docs/plans/` | Implementation plan template |
| `.harness/tasks/` | Task packet template (JSON) |
| `.harness/runs/` | Run record template (JSON) |

## Manual Setup

If you prefer to configure the harness by hand instead of using Easy Mode:

1. Copy the harness files listed above into your repo root
2. Read `HARNESS.md` and `ARCHITECTURE.md`
3. Edit `HARNESS.md` to map your real repo (replace all TODO lines)
4. Edit `ARCHITECTURE.md` to describe your actual structure
5. Create or append to your agent's config file (CLAUDE.md, AGENTS.md) with a pointer to HARNESS.md
6. Delete `SETUP.md`
7. Start using the Task Loop

## Design Principles

- **File-based state** — everything lives in the repo, versioned with git
- **Agent-agnostic** — no agent-specific files; works with any LLM coding tool
- **Self-optimizing setup** — Quick Start prompt adapts templates to the target repo
- **Minimal surface** — small set of templates, zero dependencies
- **Starting point, not framework** — adapt the templates to fit how you work

## License

MIT
