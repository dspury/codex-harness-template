# Brief 001 — Run Log Writer

## Objective
Create a minimal utility that writes a structured JSON run record into `.harness/runs/`.

## Why
The harness needs lightweight run tracking for repeatability, debugging, and proof of execution.

## Scope
Implement a small utility that:
- accepts a run payload
- writes a JSON file to `.harness/runs/`
- uses a deterministic filename
- creates the target directory if missing

## Acceptance Criteria
- a run record can be created with a single function call or command
- output is valid JSON
- files are written to `.harness/runs/`
- filenames are predictable
- basic test coverage exists

## Constraints
- keep implementation simple
- no database
- no external service
- no unnecessary dependencies

## Out of Scope
- dashboards
- aggregation
- analytics
- multi-run indexing
- retries or queueing