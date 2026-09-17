# AI Development Automation — Architecture Evidence

**Project status:** Ongoing development  
**Evidence source:** Live read-only inspection of the development automation project on the self-hosted server.

## What the project is

The project is a Python-based software-engineering control plane designed to inspect development projects, collect bounded evidence, plan work, validate results, review changes and stop for human review within explicit safety limits.

The current package identifies itself as:

- **Name:** `devbot-control-plane`
- **Version:** `2.0.0`
- **Python requirement:** Python 3.11+
- **Description:** "Bounded, resumable software-engineering control plane"

## Current architecture

The documented execution model is:

```text
CLI and explicit approvals
  -> exact development-project path policy
  -> component detection and trusted project adapters
  -> bounded evidence/context preparation
  -> CLASSIFY -> PLAN -> PREPARE -> IMPLEMENT -> VALIDATE -> REVIEW -> DECIDE
                                              ^                    |
                                              +---- correction ----+
  -> BUILD -> BUILD_REVIEW -> REPORT -> WAIT_USER
```

Cross-cutting controls include stop handling, process locking, usage locking, budgets, protected paths, rollback, event/state persistence and no-progress detection.

## Safety design verified in the project documentation

The project documentation currently specifies that:

- Normal development routes do not write to the production project tree.
- Model output is not directly executed as shell commands.
- Trusted adapters build `CommandSpec` objects using argument arrays with `shell=False`.
- Subprocesses receive sanitised environments, timeout limits and bounded output.
- `.env`, credential/key files and reserved evidence locations are protected.
- Structured writes are bounded, backed up and atomic.
- Production promotion is exposed through an explicit non-AI promotion command rather than through normal AI work routes.
- Multi-component promotion supports transactional rollback behaviour.
- Provider usage and budget counters are updated under a cross-process lock.

## Project structure observed

The current project contains dedicated modules for areas including:

- CLI handling
- context preparation
- memory
- evidence collection
- adapters
- command runners
- contracts
- orchestration loop
- usage accounting
- configuration
- release logic
- state
- reporting
- providers
- workflow
- safety controls

It also includes documentation for architecture, configuration, migration, implementation, user guidance, acceptance criteria and local testing.

## Test evidence

The current `tests/` directory contains **7 Python test modules** covering areas such as:

- foundations
- workflow
- loop logic
- evidence and release behaviour
- migration
- project memory
- model-usage display

This count refers to test modules, not individual test cases.

## Supported project families documented by the control plane

The adapter design currently documents support for detecting and validating multiple project families, including:

- Flutter
- Maven/Java
- Gradle/Java
- Python/CLI
- Node/frontend/Electron/CLI
- static web
- Tauri
- .NET desktop
- Docker/Compose metadata

## Publication note

This public document describes architecture and verified structure only. It intentionally excludes `.env` contents, provider keys, prompts, run history, private logs, usage records, copied project content and other sensitive runtime material.
