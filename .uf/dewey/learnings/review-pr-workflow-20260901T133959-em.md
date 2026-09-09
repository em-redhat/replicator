---
tag: review-pr-workflow
author: em
category: pattern
created_at: 2026-09-01T13:39:59Z
identity: review-pr-workflow-20260901T133959-em
tier: draft
---

When /uf.review-pr posts a GitHub review, the PR and its linked issues should have their project board statuses updated to "In Review".

## Discovery Process
The PR's own `projectItems` GraphQL query does NOT show cross-org project items. To find all boards an item belongs to, you must query each project's items directly.

## Known Project Boards

### Compliance Automation Planning (org: complytime, project #14)
- Project ID: PVT_kwDOCtVpQc4Ber79
- Status field ID: PVTSSF_lADOCtVpQc4Ber79zhZESGk
- "In Review" option ID: ffeaa17d

### Unbound Force Planning (org: unbound-force, project #3)
- Project ID: PVT_kwDOD616js4BaE-9
- Status field ID: PVTSSF_lADOD616js4BaE-9zhU_Fcc
- "In Review" option ID: e43b292f

## Shared Status Columns
Both boards use: Backlog → Ready → In Progress → Blocked → Ready for Review → In Review → Done

## GraphQL Mutation Pattern
```graphql
mutation {
  updateProjectV2ItemFieldValue(input: {
    projectId: "PROJECT_ID"
    itemId: "ITEM_ID"
    fieldId: "STATUS_FIELD_ID"
    value: { singleSelectOptionId: "IN_REVIEW_OPTION_ID" }
  }) { projectV2Item { id } }
}
```

## Implementation Notes for uf.review-pr Step 8
1. After posting a review, discover which project boards the PR and its linked issues belong to
2. For each board, find the "In Review" status option
3. Update the status of the PR and all linked issues to "In Review"
4. This should be a best-effort step — failures should be logged but not block the review workflow
5. The step must work across orgs (complytime items on unbound-force boards and vice versa)
