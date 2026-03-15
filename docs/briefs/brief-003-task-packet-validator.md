# Brief 003 — Task Packet Validator

## Objective
Create a minimal utility that validates task packet JSON files in `.harness/tasks/`.

## Why
The harness needs lightweight validation so task packets stay consistent with the local task workflow and template.

## Scope
Implement a small utility that:
- reads a task packet JSON file
- validates the required task fields
- rejects invalid packet paths or malformed payloads
- returns the validated payload for valid packets

## Acceptance Criteria
- a task packet can be validated with a single function call or command
- invalid JSON or missing required fields are rejected
- `.harness/tasks/*.json` packets can be validated locally
- validation rules are predictable and documented in code
- basic test coverage exists

## Constraints
- keep implementation simple
- no database
- no external service
- no unnecessary dependencies

## Out of Scope
- task scheduling
- task execution
- batch reporting
- schema versioning
- auto-fixing invalid packets
