# Agent Harness Template

A minimal, agent-agnostic harness for structured AI-assisted development.

It keeps planning, execution, and validation artifacts inside the repository as file-based state — no chat history dependency, no external services, no orchestration layers. Works with Claude, Codex, or any LLM-based coding agent.

## Why

Coding agents work better when tasks are structured. A brief defines *what*, a plan defines *how*, and a run record proves *it worked*. This template gives you that structure in ~10 files with zero dependencies.

## Quick Start

1. Copy the harness files into your repo root: `HARNESS.md`, `ARCHITECTURE.md`, `SETUP.md`, `.harness/`, and `docs/`
2. Open `SETUP.md` and paste the prompt into your coding agent
3. The agent adapts the harness to your repo's real structure and workflows

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
- **Minimal surface** — ~10 files, zero dependencies
- **Starting point, not framework** — adapt the templates to fit how you work

## License

MIT
