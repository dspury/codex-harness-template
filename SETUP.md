# Easy Mode Setup

Paste the prompt below into your coding agent (Claude, Codex, or any LLM-based coding agent) after copying the harness files into your target repo.

Replace `[REPO_NAME]` with your actual repository name.

---

```text
Set up the agent harness in this repository so it matches the real project instead of generic boilerplate.

Context:
- This repo is: [REPO_NAME]
- The harness template files are already present (HARNESS.md, ARCHITECTURE.md, .harness/, docs/)
- The goal is a working harness tailored to this repo's actual structure and workflows

Steps:
1. Read HARNESS.md and ARCHITECTURE.md to understand the harness structure.
2. Scan the repository — identify the real code, docs, test, and tooling surfaces.
3. Rewrite HARNESS.md:
   - Set the heading to "# [REPO_NAME]-agent-harness"
   - Replace the TODO lines with real content
   - Fill in Purpose with what this repo actually does
   - Replace placeholder validation commands with real ones from this repo
   - Update Key Paths to reflect the actual project layout alongside the harness paths
   - Keep Working Rules and Priorities intact, adding repo-specific rules only if needed
4. Rewrite ARCHITECTURE.md:
   - Update the Structure diagram to show the real repo layout with harness directories included
   - Keep the Data Flow and Constraints sections, adjusting only if the repo demands it
5. Create one realistic example set:
   - One brief in docs/briefs/ for a small, safe task relevant to this repo
   - One plan in docs/plans/ matching that brief
   - One task packet in .harness/tasks/ linking the brief and plan
6. Set up the agent entry point:
   - If this agent uses CLAUDE.md: create or append to CLAUDE.md at root with "Read HARNESS.md for repo context and working rules."
   - If this agent uses AGENTS.md: create or append to AGENTS.md at root with "Read HARNESS.md for repo context and working rules."
   - If neither applies: skip this step; HARNESS.md is the entry point.
7. Append these lines to the repo's .gitignore if not already present:
   .harness/runs/*
   !.harness/runs/RUN_TEMPLATE.json
8. Run one real validation command from the repo and confirm it passes.
9. Delete SETUP.md — it has served its purpose and should not persist in the repo.

Constraints:
- Keep the diff focused — do not rewrite unrelated project files
- Prefer editing existing harness files over adding new ones
- Remove all placeholder/TODO lines after filling in real content
- Keep HARNESS.md under 50 lines
- Do not add services, databases, or orchestration
- Do not claim completion without running a real validation command

Deliverables:
- A working harness branded as [REPO_NAME]-agent-harness
- One example task path (brief + plan + task packet)
- The exact validation command you ran and its result
- A short summary of what you changed
```
