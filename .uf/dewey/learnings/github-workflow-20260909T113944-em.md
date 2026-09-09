---
tag: github-workflow
author: em
category: gotcha
created_at: 2026-09-09T11:39:44Z
identity: github-workflow-20260909T113944-em
tier: draft
---

When adding a new GitHub Actions workflow to a repository that already has workflows using concurrency groups based on `${{ github.workflow }}`, the workflow `name:` field MUST be unique across all workflow files. The `github.workflow` context variable resolves to the `name:` property, not the filename. If two workflows share the same name (e.g., both `name: CI`), their concurrency groups collide and `cancel-in-progress: true` causes them to cancel each other on every push. This was caught during code review of the adopt-org-infra-ci change where both ci.yml and ci_checks.yml initially used `name: CI`. The fix was renaming ci_checks.yml to `name: Standardized CI`. This mirrors the same class of issue documented in unbound-force/unbound-force PR #456 with release preflight concurrency groups.
