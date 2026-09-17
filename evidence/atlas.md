# Atlas — Cybersecurity Orchestration Service

**Status:** Ongoing development

Atlas is a local cybersecurity orchestration service built for authorised lab and bug-bounty work. Models can reason and propose actions, while Atlas Core owns scope, policy, evidence handling, rate limits and approvals.

## Current architecture

The live project currently includes:

- **33 Python modules** in the main Atlas package
- **16 top-level Python test modules**
- dedicated `docs`, `tests`, `bin`, `atlas`, `client`, `config`, `tools` and `worker` areas
- local model integration and optional cloud-model profiles
- scope and policy validation
- evidence and audit handling
- worker transport and capability execution
- investigation and iterative-analysis workflows
- bug-bounty engagement and finding workflows

## Security workflow

Current components cover areas including:

- engagement and target scope
- request validation
- evidence collection
- findings and report preparation
- policy enforcement
- approval handling
- local API authentication
- worker management
- tool discovery and execution

Atlas also separates local and paid model modes. Paid cloud use requires an explicit launch mode and operator confirmation, while switching back to local mode disables billed use immediately.

## Bug-bounty workflow

The current interface supports recording program rules, reviewing targets, creating bounded requests, inspecting saved evidence, preparing findings and exporting reports for manual submission.

The current release is intentionally narrower than the long-term design: browser automation, authenticated session handling, mobile testing and automatic platform submission are not treated as completed features.