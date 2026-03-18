# {repo-name}-agent-harness

> TODO: Run the Easy Mode prompt in SETUP.md to configure this harness for your repo.

## Purpose

> TODO: One line describing what this repo does.

## Priorities

- Keep structure simple and navigable
- Prefer deterministic, local-first workflows
- Avoid unnecessary dependencies
- Use file-based state over services or databases
- Make every artifact traceable and auditable

## Working Rules

- Read `ARCHITECTURE.md` before making structural changes
- Keep task scope narrow — one logical change per task
- Use the templates in `docs/briefs/`, `docs/plans/`, and `.harness/`
- Place structured artifacts only in approved directories
- Update this file and `ARCHITECTURE.md` when workflows change
- Do not introduce orchestration layers, services, or queues
- Prefer editing existing files over creating new ones

## Validation

> TODO: Replace with your repo's real validation commands.
```sh
# example: npm test
```

## Task Loop

1. **Brief** — Write a task brief in `docs/briefs/` using `BRIEF_TEMPLATE.md`
2. **Plan** — Write an implementation plan in `docs/plans/` using `PLAN_TEMPLATE.md`
3. **Implement** — Make the change, keeping scope to what the brief defines
4. **Record** — Log the result in `.harness/runs/` using `RUN_TEMPLATE.json`

For multi-task tracking, optionally create a task packet in `.harness/tasks/` linking the brief and plan.

## Key Paths

| Path | Purpose |
|---|---|
| `HARNESS.md` | Agent entry point and repo map |
| `ARCHITECTURE.md` | Structure, data flow, and constraints |
| `docs/briefs/` | Task briefs |
| `docs/plans/` | Implementation plans |
| `.harness/tasks/` | Task packets (structured tracking) |
| `.harness/runs/` | Run records (execution audit trail) |
