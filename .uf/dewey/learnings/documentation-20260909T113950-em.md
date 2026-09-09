---
tag: documentation
author: em
category: pattern
created_at: 2026-09-09T11:39:50Z
identity: documentation-20260909T113950-em
tier: draft
---

When documenting CI linter configurations in AGENTS.md or workflow header comments, reference the config file (e.g., `.mega-linter.yml`) as the source of truth rather than enumerating specific linter names inline. Inline lists inevitably go stale — the adopt-org-infra-ci change initially listed 7 of 12 linters in AGENTS.md and 8 of 12 in the workflow header, both missing linters and misnamting betterleaks as gitleaks. The Scribe divisor caught this as an FA-001 factual accuracy violation. The fix was changing both to reference `.mega-linter.yml` configuration file. This follows the same pattern already used in AGENTS.md for CI commands: "Read `.github/workflows/` for the exact commands -- do not rely on memory."
