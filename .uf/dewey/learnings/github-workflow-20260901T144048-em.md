---
tag: github-workflow
author: em
category: reference
created_at: 2026-09-01T14:40:48Z
identity: github-workflow-20260901T144048-em
tier: draft
---

## PR and Issue Labeling Requirements (unbound-force org)

### Required Labels
- `llm_assisted` — MUST be applied to ALL PRs/issues created with AI assistance
- Carry over labels from linked issues (e.g., `docs`, `next-release`, `enhancement`)

### PR Assignment
- PRs MUST be assigned to the same user(s) as their linked issue
- Use `gh pr edit --add-assignee` after PR creation

### Milestone Inheritance
- If the linked issue has a milestone, the PR should inherit it
- Use `gh pr edit --milestone` after PR creation

### Label Validation
Before submitting a PR, verify:
1. `llm_assisted` label exists (create it if not: `gh label create llm_assisted --color ededed`)
2. All issue labels are carried over
3. Assignment matches the linked issue
