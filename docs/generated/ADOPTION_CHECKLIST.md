# Adoption Checklist

Use this checklist before treating the repo as an active Codex harness.

- `AGENTS.md`, `README.md`, and `ARCHITECTURE.md` are present and describe the current workflow
- `docs/briefs/BRIEF_TEMPLATE.md` exists
- `docs/exec-plans/EXEC_PLAN_TEMPLATE.md` exists
- `.harness/tasks/TASK_TEMPLATE.json` exists
- `.harness/runs/RUN_TEMPLATE.json` exists
- `.harness/episodes/EPISODE_TEMPLATE.json` exists
- `src/` contains the current local utilities
- `tests/` contains the current unit test coverage
- `python3 -m unittest discover -s tests -p 'test_*.py'` passes locally
- at least one sample brief, plan, task packet, run artifact, and episode artifact are available as references

Adoption is ready when every line above is true without relying on external services or repo-external state.
