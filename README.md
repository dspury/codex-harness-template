# Codex Harness Template

A local-first, file-based harness for structured Codex work.

It keeps planning, execution, validation, and review state inside the repository instead of hidden chat history or external orchestration. The template is optimized for Codex's `AGENTS.md` workflow and a docs-first repository map.

## Easy Mode

If you want the fastest path, do this:

1. Copy this template into your working project.
2. Open `docs/reference/EASY_MODE_SETUP_PROMPT.md`.
3. Paste the prompt into Codex.
4. Let Codex adapt the harness to your real repo structure, docs, and test commands.

This is the intended quick-start path for most people. Manual setup is still documented below for teams that want tighter control.

## What You Get

- `AGENTS.md` as the primary Codex repo map
- `ARCHITECTURE.md` for stable structure and constraints
- `docs/briefs/` for task briefs
- `docs/exec-plans/` for execution plans
- `docs/generated/` for the small set of durable operator docs worth keeping in the public template
- `.harness/tasks/` for active task packets
- `.harness/runs/` for run records
- `.harness/episodes/` for completion summaries
- `src/` for small harness utilities
- `tests/` for local validation
- `LICENSE` with MIT terms

## Manual Setup

1. Copy this folder to your new project location.
2. Ensure Python 3 is installed.
3. Read `AGENTS.md`, `ARCHITECTURE.md`, `README.md`, and the generated docs in `docs/generated/`.
4. Run the baseline validation:

```sh
python3 -m unittest discover -s tests -p 'test_*.py'
```

## Task Loop

### 1. Create the brief

Copy `docs/briefs/BRIEF_TEMPLATE.md` to a task-specific brief.

The brief should capture:
- the target outcome
- why it matters
- scope and non-scope
- acceptance criteria

### 2. Create the execution plan

Copy `docs/exec-plans/EXEC_PLAN_TEMPLATE.md` to a task-specific plan.

The plan should capture:
- the implementation approach
- likely files to change
- validation commands
- key risks
- completion criteria

### 3. Create the task packet

Copy `.harness/tasks/TASK_TEMPLATE.json` to a task-specific packet in `.harness/tasks/`.

The packet ties together the task ID, brief, and plan so the work can be picked up reproducibly.

### 4. Execute the task

Ask Codex to read:
- `AGENTS.md`
- `ARCHITECTURE.md`
- the task packet
- the referenced brief
- the referenced plan

Then implement the smallest viable change that satisfies the task.

### 5. Validate locally

Start with the smallest meaningful command. For the harness itself, use:

```sh
python3 -m unittest discover -s tests -p 'test_*.py'
```

If you copy this template into a larger project, prefer the narrowest repo-defined command that proves the change.

### 6. Record the run

After a meaningful validation attempt, write a run record:

```sh
python3 -c "from src.run_log_writer import write_run_record; write_run_record({'run_id': 'run-example', 'task_id': 'task-000', 'status': 'passed', 'tests_run': ['python3 -m unittest discover -s tests -p test_*.py'], 'files_changed': ['README.md'], 'summary': 'Release readiness validation'})"
```

Run records are append-safe. If `run-task-000.json` already exists, the writer creates `run-task-000-2.json`, `run-task-000-3.json`, and so on.

### 7. Record completion

When the task is complete and verified, write an episode record:

```sh
python3 -c "from src.episode_log_writer import write_episode_record; write_episode_record({'episode_id': 'episode-example', 'task_id': 'task-000', 'result': 'completed', 'lesson': 'Keep AGENTS.md short and push durable detail into docs.'})"
```

Episode records use the same append-safe naming rule.

## Key Files

- `AGENTS.md`: primary Codex repo map
- `ARCHITECTURE.md`: stable repo structure and constraints
- `docs/reference/EASY_MODE_SETUP_PROMPT.md`: copy-paste prompt for adapting the harness inside a real repo
- `docs/generated/BOOTSTRAP_STEPS.md`: technical startup notes
- `docs/generated/ADOPTION_CHECKLIST.md`: adoption checklist
- `.harness/tasks/TASK_TEMPLATE.json`: task packet template

## Repository Layout

```text
.
|-- .codex/SKILLS.md
|-- .harness/
|   |-- tasks/
|   |-- runs/
|   `-- episodes/
|-- AGENTS.md
|-- ARCHITECTURE.md
|-- README.md
|-- LICENSE
|-- docs/
|   |-- briefs/
|   |-- design/
|   |-- exec-plans/
|   |-- generated/
|   `-- reference/
|-- src/
`-- tests/
```

## Codex Notes

- OpenAI's published harness guidance recommends treating `AGENTS.md` as a short table of contents rather than a monolithic manual.
- The durable system of record should live in repository docs, plans, code, and tests.
- Generated docs in `docs/generated/` are part of the template's onboarding path, but `AGENTS.md` should stay concise.

## Supporting Docs

- bootstrap: `docs/generated/BOOTSTRAP_STEPS.md`
- adoption checklist: `docs/generated/ADOPTION_CHECKLIST.md`
- readiness check: `docs/generated/REPO_READINESS_CHECK.md`

## Release Notes

- The harness utilities use Python standard library modules only.
- The project is released under the MIT License.
- Historical migration notes and placeholder generated files have been removed from the public OSS surface.
