# Exec Plan 001 — Run Log Writer

## Goal
Implement a minimal run logging utility for the harness.

## Proposed Approach
1. inspect repo structure and determine where utility code should live
2. create a small module for writing run records
3. define the run record shape
4. write output to `.harness/runs/`
5. add a basic test
6. verify file creation and JSON validity

## Expected Files
- source utility module
- test file
- optional small fixture or helper
- docs update only if needed

## Validation
- run unit test for the writer
- inspect generated JSON output
- confirm deterministic filename behavior

## Risks
- unclear source layout
- path handling issues
- overengineering a very small utility

## Completion Standard
Task is complete when a run record can be written locally and verified by test.