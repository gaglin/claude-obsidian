---
type: entity
title: "Opus 4.8"
created: 2026-07-16
entity_type: model
related:
  - "[[Multi-Model Development Workflow]]"
  - "[[systematic-debugging]]"
  - "[[brainstorming]]"
  - "[[writing-plans]]"
status: developing
tags:
  - model
  - anthropic
  - reasoning
---

# Opus 4.8

Anthropic's reasoning model used for planning and diagnosis tasks.

## Role in Workflow

Assigned to high-reasoning tasks:
- Bug diagnosis (with systematic-debugging)
- Feature brainstorming
- Plan writing
- Adversarial verification

## Why Opus for Planning

- Deep reasoning capabilities
- Handles complex analysis well
- Excels at structured output
- Good at adversarial thinking

## Why Not for Implementation

- More expensive than alternatives
- Slower for repetitive coding tasks
- Sonnet/GPT-5.4 handle implementation adequately

## Related

- [[Multi-Model Development Workflow]] — model assignment rationale
- [[Development Workflow Pattern]] — the workflow that uses Opus
