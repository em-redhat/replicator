---
tag: github-workflow
author: em
category: reference
created_at: 2026-09-09T11:39:57Z
identity: github-workflow-20260909T113957-em
tier: draft
---

The complytime/org-infra reusable CI workflow (reusable_ci.yml) at SHA 0c784711 (v0.7.1) takes zero inputs via workflow_call. It includes a fallback mechanism that checks for 5 local config files (.mega-linter.yml, .golangci.yml, .yamllint.yml, commitlint.config.js, ruff.toml) and fetches missing ones from org-infra at the pinned SHA. The canonical consumer pattern is a thin ci_checks.yml with no `with:` block, SHA-pinned, with job-level permissions for contents:read, issues:read, pull-requests:read. The expected GitHub check name follows the nested job naming convention: if the consumer job name is "Standardized CI" and the reusable workflow's internal job name is "Run linters", the check appears as "Standardized CI / Run linters". When adding this check to release preflight and branch protection, use the exact string "Standardized CI / Run linters".
