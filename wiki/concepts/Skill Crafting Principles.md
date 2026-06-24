---
type: concept
title: "Skill Crafting Principles"
created: 2026-06-24
updated: 2026-06-24
tags:
  - concept
  - skills
  - agent-skills
  - best-practices
status: current
related:
  - "[[Thariq Tips — Agent Skills Guide]]"
  - "[[Agent Skill Categories]]"
  - "[[Thariq]]"
  - "[[Agent Skills Ecosystem]]"
sources:
  - "[[Thariq Tips — Agent Skills Guide]]"
---

# Skill Crafting Principles

9 best practices for writing effective agent skills, documented by Anthropic's Thariq from actual usage across hundreds of skills.

## The 9 Principles

### 1. Don't State the Obvious
Focus on information that pushes Claude out of its normal way of thinking. Avoid documenting what the model already knows.

### 2. Build a Gotchas Section
This is the highest-signal content in any skill. Build from common failure points Claude hits when using the skill. Update iteratively as new edge cases emerge.

### 3. Use the File System & Progressive Disclosure
A skill is a folder, not a markdown file. Split detailed reference material into `references/api.md`. Point to sub-files; the model reads them at appropriate times.

### 4. Avoid Railroading Claude
Give goals and constraints, not prescriptive step-by-step instructions. Claude will try to follow instructions literally — leave room for adaptation.

### 5. Think Through the Setup
Store configuration in `config.json`. If unconfigured, ask the user structured multiple-choice questions to gather context.

### 6. The Description Is for the Model
Claude scans all skill descriptions at session start. The description must describe **when to trigger** this skill — not summarize what it is. Write trigger patterns, not abstracts.

### 7. Memory & Storing Data
Use append-only logs, JSON, or SQLite within the skill's data directory (`$CLAUDE_PLUGIN_DATA` for persistence across upgrades).

### 8. Store Scripts & Generate Code
Ship scripts alongside instructions. Lets the model compose rather than reconstruct. Most powerful tool you can give an agent.

### 9. On-Demand Hooks
Activate hooks only when the skill is called, lasting the session duration. Use for opinionated guardrails (e.g., `/careful` blocks destructive commands).

## Distribution Patterns

- **Repo-checked** (`.claude/skills`): works for small teams with few repos
- **Plugin marketplace**: best at scale; let teams decide what to install
- **Composition**: reference other skills by name; the model resolves at runtime
- **Measurement**: PreToolUse hooks log skill usage for popularity/undertriggering analysis
