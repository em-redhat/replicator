---
tag: github-workflow
author: em
category: gotcha
created_at: 2026-09-09T11:40:02Z
identity: github-workflow-20260909T114002-em
tier: draft
---

When adding a new required status check to GitHub branch protection via .github/settings.yml, be careful about task ordering: the branch protection update (settings.yml) should be committed LAST, after the workflow is verified working and any lint fixes are applied. If the branch protection requires a check that fails on pre-existing code issues, the repo enters a blocked state where no PRs can merge. The adopt-org-infra-ci spec review caught this as task ordering hazard and moved the settings.yml update to depend on the lint fix task completing first. The design also documented a 3-step rollback procedure: (1) remove from settings.yml required checks, (2) remove from release.yml ci_checks array, (3) optionally delete ci_checks.yml and .mega-linter.yml.
