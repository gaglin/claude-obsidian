---
type: entity
title: "OpenCode Plan Manager"
created: 2026-06-22
updated: 2026-06-22
tags:
  - entity
  - opencode
  - plugin
  - planning
status: developing
related:
  - "[[OpenCode]]"
  - "[[Planner-Executor Workflow Pattern]]"
  - "[[OpenCode Game Studios]]"
---

# OpenCode Plan Manager

An OpenCode plugin by yurihbm that provides structured plan management for agentic workflows. Implements the Planner-to-Builder pattern with Zod-validated schemas, filesystem Kanban, and cross-session continuity.

## Architecture

- Two-agent hierarchy: Plan Agent (architect) and Build Agent (executor)
- Plan Agent follows 4-step process: Analysis -> Deduplication -> Context Decision -> Plan Creation
- Filesystem layout: `.opencode/plans/{pending,in_progress,done}/`
- Selective context loading: summary (stats), spec (requirements), plan (task list), full

## Key Features

- Selective context loading prevents hallucination from oversized context windows
- Zero-hallucination schemas via strict Zod validation
- Atomic folder moves for state transitions (no database)
- Cross-session continuity — plans survive chat boundaries
- Escalation path: Build Agent escalates to Plan Agent when tasks need more design

## Tools

| Tool | Purpose |
|------|---------|
| `plan_create` | Create new plan with full Zod validation |
| `plan_list` | List plans by status/type (reads only metadata.json) |
| `plan_read` | Read plan with summary/spec/plan/full views |
| `plan_update` | Update status or tasks with atomic folder moves |

## Status

Active development. 25 releases as of June 2026. MIT license. Built with TypeScript + Bun. npm package: `opencode-plan-manager`.
