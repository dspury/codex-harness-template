# Bootstrap Steps

1. Read `AGENTS.md`.
2. Read `ARCHITECTURE.md`.
3. Read `README.md` for the operator path.
4. Confirm these folders exist: `docs/briefs/`, `docs/exec-plans/`, `docs/generated/`, `.harness/tasks/`, `.harness/runs/`, `.harness/episodes/`, `src/`, `tests/`.
5. Confirm the template files exist in `docs/briefs/`, `docs/exec-plans/`, and `.harness/`.
6. Run `python3 -m unittest discover -s tests -p 'test_*.py'`.
7. Use `docs/generated/ADOPTION_CHECKLIST.md` to confirm the template is complete.
8. Use `docs/generated/REPO_READINESS_CHECK.md` before treating the repo as ready for reuse.
