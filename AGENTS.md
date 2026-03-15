# Repo AGENTS.md

## Purpose
This repo is a reusable local-first Codex harness template.

## Repo Priorities
- keep the structure simple
- prefer deterministic local workflows
- avoid unnecessary dependencies
- favor file-based state over services
- make the harness easy to copy into other repos

## Working Rules
- read `ARCHITECTURE.md` before major edits
- keep features narrowly scoped
- place generated outputs only in approved folders
- update docs when workflow changes
- do not introduce orchestration complexity into the template
- keep `AGENTS.md` short and use `docs/` as the deeper system of record
- keep task metadata in `.harness/tasks/`
- keep run records in `.harness/runs/`
- keep episode summaries in `.harness/episodes/`
- prefer the templates in `docs/briefs/`, `docs/exec-plans/`, and `.harness/` over inventing new formats

## Validation
- run the smallest meaningful test first
- prefer simple local validation over broad automation
- do not claim success without naming exact commands run

## Commands
- tests: `python3 -m unittest discover -s tests -p 'test_*.py'`
- run writer smoke check: `python3 -c "from src.run_log_writer import write_run_record; write_run_record({'run_id': 'example-run', 'task_id': 'task-000', 'status': 'running'})"`
- easy mode setup prompt: `docs/reference/EASY_MODE_SETUP_PROMPT.md`

## Current Focus
The current goal is to keep the harness template accurate, reusable, and aligned with repo-local artifacts.
