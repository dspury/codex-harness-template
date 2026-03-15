# Architecture

## Overview

This template keeps planning, execution, and review context inside the repository. It favors deterministic file-based artifacts and small local utilities over services or orchestration layers.

## Core Components

- `AGENTS.md` acts as the short Codex-facing map into the repo.
- `docs/briefs/` stores feature briefs that define objective, scope, and acceptance criteria.
- `docs/exec-plans/` stores execution plans that turn a brief into concrete implementation steps.
- `docs/reference/` stores reusable setup prompts and release-facing reference notes.
- `.harness/tasks/` stores task metadata that points at the active brief and plan.
- `.harness/runs/` stores structured run records for implementations and validations.
- `.harness/episodes/` stores compact summaries of completed work and lessons learned.
- `src/` contains lightweight harness utilities; today that includes `src/run_log_writer.py`.
- `tests/` contains unit tests for repo-local utilities.

## Data Flow

The normal task loop is:
1. define the task in a brief
2. create an execution plan
3. register the task in `.harness/tasks/`
4. implement the change in `src/` and related files
5. validate the change with the smallest meaningful command
6. persist the execution result in `.harness/runs/`
7. record a short completion summary in `.harness/episodes/`

For run logging specifically, callers construct a payload, `src/run_log_writer.py` derives a stable base filename from payload fields, allocates a numeric suffix on collision, and persists the record as JSON under `.harness/runs/`.

## Dependencies

The current implementation uses Python standard library modules only. There is no external database, service, or queue.

## Constraints

- File-based state only
- Deterministic local behavior
- No external service dependencies for harness tracking
- Repo-first workflow: briefs, plans, tasks, runs, and episodes live with the code they describe
- Minimal formats: JSON for machine-readable artifacts, Markdown for human-authored docs
- Append-safe audit trail: repeated run or episode identifiers create suffixed files instead of overwriting prior records

## Future Work

Add more small utilities only when they simplify the local task loop without introducing orchestration overhead.
