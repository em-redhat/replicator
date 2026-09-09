---
tag: python-convention-pack-docs
author: em
category: gotcha
created_at: 2026-08-20T16:25:23Z
identity: python-convention-pack-docs-20260820T162523-em
tier: draft
---

When documenting Python convention pack doctor checks, the upstream design doc (D5) confirms the security scanner checks for `bandit` or `ruff`, NOT `safety`. The initial implementation incorrectly listed `safety` as a checked tool — this was caught during code review and corrected. Always cross-reference upstream design documents for exact tool binary names rather than assuming from the Python ecosystem.
