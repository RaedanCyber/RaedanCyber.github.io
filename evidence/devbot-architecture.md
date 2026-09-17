# DevBot — Architecture Notes

**Status:** Ongoing development

DevBot is a Python-based software-engineering control plane built to work across development projects with explicit boundaries around execution, validation, review and promotion.

## Current package

- `devbot-control-plane`
- Version **2.0.0**
- Python **3.11+**
- Bounded, resumable workflow design

## Workflow

```text
CLASSIFY -> PLAN -> PREPARE -> IMPLEMENT -> VALIDATE -> REVIEW -> DECIDE
                                                ^                    |
                                                +---- correction ----+
-> BUILD -> BUILD_REVIEW -> REPORT -> WAIT_USER
```

The system also includes stop handling, process locking, usage locking, budgets, protected paths, rollback, event/state persistence and no-progress detection.

## Execution model

- Normal work routes stay inside the configured development project area.
- Model responses are not passed directly to a shell.
- Trusted adapters create command specifications using argument arrays with `shell=False`.
- Subprocesses run with restricted environments, timeouts and capped output.
- Protected files and paths are guarded from normal model-driven changes.
- Structured writes are bounded, backed up and atomic.
- Promotion is a separate explicit action rather than part of normal development work.
- Multi-component promotion can roll back as one transaction when required.
- Provider usage and budget counters are kept under a cross-process lock.

## Project structure

The current project has dedicated modules for:

- CLI handling
- context and memory
- evidence collection
- project adapters
- command runners
- contracts
- orchestration loop
- usage accounting
- configuration
- release logic
- state and reporting
- providers
- workflow and safety controls

## Tests

The current test suite contains **7 Python test modules** covering foundations, workflow, loop logic, evidence/release behaviour, migration, project memory and model-usage display.

## Supported project families

The adapter layer documents support for Flutter, Maven/Java, Gradle/Java, Python, Node/frontend, static web, Tauri, .NET and Docker/Compose metadata.