# Repo Readiness Check

This repo is ready to adopt as a harness template when:

- the root docs match the actual repo structure
- the harness artifact directories exist and are writable
- the task, run, and episode templates match the current file conventions
- the sample tasks document at least one complete task flow
- the local utilities cover the current artifact workflow
- the automated tests pass locally
- no step in the documented workflow requires a service, database, or orchestration layer

Current status:
- ready for local adoption
- ready for repo-to-repo copying
- not yet optimized for CLI-driven operation
- not yet enforcing referenced file existence inside task packets
