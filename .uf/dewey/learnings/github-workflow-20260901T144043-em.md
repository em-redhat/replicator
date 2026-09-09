---
tag: github-workflow
author: em
category: pattern
created_at: 2026-09-01T14:40:43Z
identity: github-workflow-20260901T144043-em
tier: draft
---

## GitHub Project Board Assignment for PRs

When submitting a PR, it MUST be added to ALL project boards that its linked issue(s) belong to. Use the GitHub GraphQL API `addProjectV2ItemById` mutation.

Key gotcha: `gh project item-add` CLI command silently fails for cross-org projects. Always use the GraphQL API directly with `gh api graphql`.

PRs should inherit Priority and Size fields from their linked issues on each board. Query the issue's item fields first, then set the same values on the PR item using `updateProjectV2ItemFieldValue`.
