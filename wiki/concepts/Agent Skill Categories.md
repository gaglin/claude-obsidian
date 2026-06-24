---
type: concept
title: "Agent Skill Categories"
created: 2026-06-24
updated: 2026-06-24
tags:
  - concept
  - skills
  - agent-skills
  - taxonomy
status: current
related:
  - "[[Thariq Tips — Agent Skills Guide]]"
  - "[[Skill Crafting Principles]]"
  - "[[Thariq]]"
  - "[[Agent Skills Ecosystem]]"
sources:
  - "[[Thariq Tips — Agent Skills Guide]]"
---

# Agent Skill Categories

A 9-type taxonomy of agent skills cataloged by Anthropic's Thariq from hundreds of skills in active use across the company. Published March 17, 2026.

## The 9 Categories

| # | Category | Purpose | Examples |
|---|----------|---------|---------|
| 1 | **Library & API Reference** | Explain correct library/CLI/SDK usage with gotchas | billing-lib, internal-platform-cli, frontend-design |
| 2 | **Product Verification** | Test/verify code using external tools | signup-flow-driver, checkout-verifier, tmux-cli-driver |
| 3 | **Data Fetching & Analysis** | Connect to data/monitoring stacks | funnel-query, cohort-compare, grafana |
| 4 | **Business Process & Team Automation** | Automate repetitive workflows | standup-post, create-ticket, weekly-recap |
| 5 | **Code Scaffolding & Templates** | Generate framework boilerplate | new-workflow, new-migration, create-app |
| 6 | **Code Quality & Review** | Enforce quality and review code | adversarial-review, code-style, testing-practices |
| 7 | **CI/CD & Deployment** | Fetch, push, deploy code | babysit-pr, deploy-service, cherry-pick-prod |
| 8 | **Runbooks** | Symptom → investigation → structured report | service-debugging, oncall-runner, log-correlator |
| 9 | **Infrastructure Operations** | Routine maintenance with guardrails | resource-orphans, dependency-management, cost-investigation |

## Key Insight

The best skills fit cleanly into one category. Confusing skills straddle multiple. Use this taxonomy when designing new skills to keep scope focused.
