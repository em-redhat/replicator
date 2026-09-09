---
tag: review-pr-workflow
author: em
category: pattern
created_at: 2026-09-01T11:41:19Z
identity: review-pr-workflow-20260901T114119-em
tier: draft
---

When posting a PR review via /uf.review-pr, the agent must also update the status of linked issues and the PR itself to "In Review 🏁" on two GitHub project boards:

1. **Unbound Force Planning** (org: unbound-force, project #3, project ID: PVT_kwDOD616js4BaE-9)
   - Status field ID: PVTSSF_lADOD616js4BaE-9zhU_Fcc
   - "In Review 🏁" option ID: e43b292f

2. **Compliance Automation planning** (org: complytime, project #14, project ID: PVT_kwDOCtVpQc4Ber79)
   - Status field ID: PVTSSF_lADOCtVpQc4Ber79zhZESGk
   - "In Review 🏁" option ID: ffeaa17d
   - View #10 ("PRs in review") shows items filtered to this status

Cross-org items (e.g., unbound-force/replicator PRs on the complytime board) may not appear in the PR's own `projectItems` GraphQL query but ARE visible when querying the project's items directly.

The update should happen immediately after the review is successfully posted via `gh api repos/{owner}/{repo}/pulls/{number}/reviews`. Use the GraphQL `updateProjectV2ItemFieldValue` mutation to set the status field.

Both boards share the same status column names: Backlog → Ready 🚀 → In Progress 📋 → Blocked 🚧 → Ready for Review 👀 → In Review 🏁 → Done ✔️
