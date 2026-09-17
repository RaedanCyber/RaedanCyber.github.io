# Rae-I — Personal AI Orchestration Platform

**Status:** Ongoing development

Rae-I is my personal orchestration project built around a persistent Linux server. The goal is to give one control layer access to tools, devices and specialist agents without treating every component as an unrestricted autonomous system.

## Core design

The project is organised around:

- a persistent server-side backend
- controlled access to tools and devices
- private connectivity between systems
- audit and runtime state
- dedicated configuration and workspace areas
- specialist-agent delegation
- gradual permission expansion instead of default full access

## Current project structure

The live project currently includes dedicated areas for:

- `audit`
- `bin`
- `config`
- `data`
- `docs`
- `logs`
- `run`
- `skills`
- `workspace`
- cybersecurity lab integration

The current `bin` area contains **6 Python helper/orchestration scripts**, while the configuration tree contains **22 files** and the audit area currently contains **24 checkpoint/audit records**.

## Orchestration work

Current code includes job and step structures, goal-to-step planning and orchestration helpers. The wider system also includes model-routing configuration, rate-limit configuration, phone integration work, privileged-tool boundaries, media helpers and links to specialist tooling.

## Design principle

A core rule of the project is to start with read-only or limited capabilities and add execution permissions gradually. The aim is useful automation with a clear control path rather than giving every agent unrestricted system access.