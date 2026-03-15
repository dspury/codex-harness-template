# Repo 2 Migration Plan

## Goal

Copy this harness into a second repository without introducing cross-repo dependencies.

## Steps

1. Copy `AGENTS.md`, `README.md`, and `ARCHITECTURE.md`.
2. Copy `docs/briefs/BRIEF_TEMPLATE.md` and `docs/exec-plans/EXEC_PLAN_TEMPLATE.md`.
3. Copy `.harness/tasks/TASK_TEMPLATE.json`, `.harness/runs/RUN_TEMPLATE.json`, and `.harness/episodes/EPISODE_TEMPLATE.json`.
4. Copy the current local utilities under `src/` and their tests under `tests/`.
5. Copy the generated operator docs from `docs/generated/` that are still repo-agnostic.
6. Run `python3 -m unittest discover -s tests -p 'test_*.py'` in the destination repo.
7. Create the first destination-repo brief, plan, and task packet before implementing anything else.

## Scope Guard

- do not add network calls
- do not add external packages unless the destination repo already requires them
- do not move harness state outside the destination repo
- do not introduce background services or orchestration layers
