---
type: source
source_type: article
title: "Why Separating Planning From Execution Changed My AI Coding Workflow"
author: Damilare Protocol Arikeusola
url: https://medium.com/@mrprotocoll/why-separating-planning-from-execution-changed-my-ai-coding-workflow-aeb377c3136f
date_published: 2026-06-02
confidence: high
key_claims:
  - ChatGPT for PRD/FRD generation, then OpenCode Plan Mode for architecture, then Build Mode for execution
  - Different models excel at different stack layers (Codex for backend, Claude for frontend)
  - Self-review prompt after every implementation improves correctness and safety
  - Battle-tested boilerplates with conventions, rules, and AI guidance docs reduce drift
  - AI coding quality is limited by process, not model capability
related:
  - "[[Planner-Executor Workflow Pattern]]"
  - "[[OpenCode]]"
  - "[[AI Game Dev Pipeline]]"
---

# Source: Separating Planning From Execution in AI Coding Workflows

A concise but high-signal article documenting a structured AI coding workflow: ChatGPT handles the planning/design phase (PRD, FRD, implementation phases), then OpenCode's Plan Mode generates the architecture, then Build Mode executes.

## Key Contributions

- Explicit ChatGPT-as-planner pattern with OpenCode-as-executor
- OpenCode's Plan Mode as the bridge between external planning and internal execution
- Self-review prompt template for post-implementation quality gate
- Boilerplate-first development reduces context dependency

## Confidence

**High** — published 2026-06-02, directly describes the ChatGPT+OpenCode workflow without promotional framing. Methodology matches patterns observed across multiple independent sources.
