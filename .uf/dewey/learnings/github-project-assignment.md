---
type: learning
category: pattern
tag: process
created: 2026-08-20
source: team process, observed workflow
---

# GitHub Project Assignment Requirements

When creating PRs for issues that are tracked in GitHub Projects, the PR MUST be added to the same project(s) as the originating issue. This ensures visibility in project boards and sprint tracking.

## For the unbound-force org

- Check the issue's project assignments using `gh issue view N --json projectItems`
- Add the PR to the same projects using `gh pr edit N --add-project "Project Name"`
- Common projects: "Unbound Force", "Compliance Automation Planning"
- Note: the `gh` CLI requires `read:project` scope — run `gh auth refresh -s read:project` if missing

When an issue specifies a milestone (e.g., "release v0.16.0"), set the same milestone on the PR.

## For the complytime org

- Same pattern applies — mirror project assignments from issue to PR
- Use issue templates from each repo (revised templates available)
