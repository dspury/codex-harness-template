# Architecture

## Overview

This harness keeps planning, execution, and validation artifacts inside the repository as file-based state. No services, databases, or orchestration layers. Everything is local-first and deterministic.

## Structure

```
.
├── HARNESS.md              # Agent entry point — repo map and working rules
├── ARCHITECTURE.md         # This file — structure and constraints
├── .harness/
│   ├── tasks/              # Task packets linking briefs to plans (JSON)
│   └── runs/               # Execution records (JSON)
└── docs/
    ├── briefs/             # Task briefs — what to do and why (Markdown)
    └── plans/              # Implementation plans — how to do it (Markdown)
```

## Data Flow

1. Define the task in a **brief**
2. Write an implementation **plan**
3. **Implement** the change
4. **Record** the execution result

Briefs and plans are human-authored Markdown. Task packets and run records are machine-readable JSON.

## Constraints

- File-based state only — no databases, no services
- Deterministic local behavior — reproducible offline
- Minimal formats — JSON for structured data, Markdown for human-authored docs
- Unique identifiers — use distinct IDs for task packets and run records to preserve history
- Repo-first — all artifacts live with the code they describe
