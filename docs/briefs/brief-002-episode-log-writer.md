# Brief 002 — Episode Log Writer

## Objective
Create a minimal utility that writes a structured JSON episode record into `.harness/episodes/`.

## Why
The harness needs lightweight episode tracking for completed work summaries and reusable lessons.

## Scope
Implement a small utility that:
- accepts an episode payload
- writes a JSON file to `.harness/episodes/`
- uses a deterministic filename
- creates the target directory if missing

## Acceptance Criteria
- an episode record can be created with a single function call or command
- output is valid JSON
- files are written to `.harness/episodes/`
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
- multi-episode indexing
- retries or queueing
