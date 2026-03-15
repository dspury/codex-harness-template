# Exec Plan 002 — Episode Log Writer

## Goal
Implement a minimal episode logging utility for the harness.

## Proposed Approach
1. follow the existing run log writer layout and patterns
2. create a small module for writing episode records
3. define the episode record naming inputs
4. write output to `.harness/episodes/`
5. add a basic test
6. verify file creation and JSON validity

## Expected Files
- source utility module
- test file
- task metadata
- docs update only if needed

## Validation
- run unit tests for the writer
- inspect generated JSON output
- confirm deterministic filename behavior

## Risks
- path handling issues
- unnecessary divergence from the run writer pattern
- overengineering a very small utility

## Completion Standard
Task is complete when an episode record can be written locally and verified by test.
