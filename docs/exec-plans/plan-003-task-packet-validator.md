# Exec Plan 003 — Task Packet Validator

## Goal
Implement a minimal validator for task packet JSON files in `.harness/tasks/`.

## Proposed Approach
1. follow the existing utility and test patterns in `src/` and `tests/`
2. define the required task packet fields from the current task template
3. validate a task packet file path and JSON payload
4. return the parsed payload when validation succeeds
5. add focused tests for valid and invalid packets

## Expected Files
- source utility module
- test file
- task metadata
- docs update only if needed

## Validation
- run unit tests for the validator
- verify valid packets are accepted
- verify invalid packets raise clear errors

## Risks
- over-validating beyond the current template
- path handling issues
- accidental divergence from existing task packet shape

## Completion Standard
Task is complete when a task packet file can be validated locally and verified by test.
