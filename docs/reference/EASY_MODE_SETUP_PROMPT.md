# Easy Mode Setup Prompt

Paste this into Codex after copying this template into your target project.

Replace `[PROJECT_NAME]` with the real repository name if you want a more specific setup result.

```text
Set up this repository to use the Codex Harness Template in a way that matches the existing project instead of blindly copying boilerplate.

Context:
- This repo is the working project: [PROJECT_NAME]
- The Codex harness files are already present in the repository
- The goal is to make the harness usable immediately for future tasks

What I want you to do:
1. Read `AGENTS.md`, `ARCHITECTURE.md`, and `README.md`.
2. Inspect the real repository structure and identify the actual code, docs, test, and tooling surfaces.
3. Adapt the harness so it matches this repo's real workflows and constraints.
4. Keep the harness file-based and local-first.
5. Preserve existing project conventions. Do not rewrite unrelated project docs or rename files unless needed.

Set up the harness by doing the following:
- update `AGENTS.md` so it acts as a short map into the real repo
- update `ARCHITECTURE.md` so it describes the actual repository structure and where the harness fits
- keep `docs/briefs/`, `docs/exec-plans/`, `.harness/tasks/`, `.harness/runs/`, and `.harness/episodes/`
- create or adjust one example brief, one example execution plan, and one example task packet that are realistic for this repo
- keep the example task narrow and safe
- verify the smallest meaningful validation command and name it explicitly
- avoid adding services, databases, or orchestration layers

Constraints:
- keep the diff focused
- prefer editing the existing harness files over adding lots of new files
- keep the root guidance short and push durable detail into `docs/`
- do not claim completion without running at least one real validation command

Deliverables:
- a working Codex harness setup aligned to this repo
- one example task path that demonstrates how to use it
- a short summary of what you changed
- the exact validation command you ran
```

## Notes

- This prompt is meant to bootstrap the harness inside a real project quickly.
- It works best after the template files are already copied into the target repo.
- The official OpenAI harness guidance emphasizes keeping `AGENTS.md` short and using the docs tree as the deeper system of record.
