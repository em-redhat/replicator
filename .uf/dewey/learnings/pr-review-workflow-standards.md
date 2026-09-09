---
type: learning
category: reference
tag: process
created: 2026-08-20
source: complytime/community STYLE_GUIDE.md §3
---

# PR Review and Workflow Standards

## PR Requirements

1. **Atomic Changes**: PRs MUST address a single concern and be small enough for focused review
2. **No Merge Commits**: PR branches MUST NOT contain merge commits — rebase onto target branch
3. **Review Requirement**: All PRs REQUIRE review from at least two Maintainers
4. **PR Title Format**: `<type>: <description>` (e.g., `feat: implement validation logic`)
5. **Commit Messages**: MUST follow Conventional Commits specification
6. **Signed-off-by**: All commits MUST include `Signed-off-by` trailer (use `git commit -s`)
7. **Assisted-by**: AI-assisted commits MUST include `Assisted-by` trailer

## Fast-Track Small Fixes

For simple bugs or improvements fixable in a couple of hours or less, contributors SHOULD open a PR directly with the fix instead of creating a tracking issue first. The PR description MUST still explain the problem and the fix.

## Review Etiquette

- Focus on functionality, security, performance, test coverage, architectural alignment
- Data-driven findings (broken behavior, missing tests, security issues) MUST be reported
- Preference-based suggestions with no negative technical impact SHOULD be avoided
- Lead with curiosity, not judgment — ask for clarification rather than assuming incorrect
- PR author MAY accept or decline preference-based suggestions
