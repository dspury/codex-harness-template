# Repo 2 First Task Guide

Use this sequence for the first task in the destination repo.

1. Copy `docs/briefs/BRIEF_TEMPLATE.md` to a new task brief.
2. Copy `docs/exec-plans/EXEC_PLAN_TEMPLATE.md` to a new execution plan.
3. Copy `.harness/tasks/TASK_TEMPLATE.json` to a new task packet.
4. Read the destination repo’s `AGENTS.md`, `README.md`, and `ARCHITECTURE.md`.
5. Map only the files relevant to the first task.
6. Implement the smallest viable change.
7. Run `python3 -m unittest discover -s tests -p 'test_*.py'` or the destination repo’s smaller task-specific validation command if one exists.
8. Write a run artifact in `.harness/runs/`.
9. Write an episode artifact in `.harness/episodes/`.
10. Review the patch against the task brief and plan before merge.

Recommended first task shape:
- small file-based utility or validator
- no external integration
- easy to verify with local unit tests
- narrow enough to produce a clean example run and episode artifact
