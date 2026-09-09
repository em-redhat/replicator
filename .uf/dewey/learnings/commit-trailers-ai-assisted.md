---
type: learning
category: reference
tag: process
created: 2026-08-20
source: complytime/community STYLE_GUIDE.md §3
---

# Commit Trailers for AI-Assisted Work

## Required Trailers

All commits that were authored or substantially assisted by an AI tool MUST include an `Assisted-by` trailer identifying the tool and model:

```
Assisted-by: OpenCode (claude-opus-4-6)
```

All commits MUST include a `Signed-off-by` trailer (use `git commit -s`):

```
Signed-off-by: Your Name <your.email@example.com>
```

## AI-Assisted Submissions

- AI-assisted issues and PRs MUST be validated by the author before submission
- The `ai_assisted` or `llm_assisted` label MUST be applied to the issue/PR
- Authors retain full ownership and responsibility for the submission
- Authors SHOULD provide supporting evidence when applicable (reproducible steps, logs, permalinks, screenshots)

## Commit Message Format

All commit messages MUST follow the Conventional Commits specification:
`<type>: <description>` (e.g., `feat: implement validation logic`)
