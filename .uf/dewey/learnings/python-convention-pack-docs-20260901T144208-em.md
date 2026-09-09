---
tag: python-convention-pack-docs
author: em
category: gotcha
created_at: 2026-09-01T14:42:08Z
identity: python-convention-pack-docs-20260901T144208-em
tier: draft
---

When documenting Python convention pack doctor checks, the upstream design doc (D5) confirms the security scanner checks for `bandit` or `ruff`, NOT `safety`. Always cross-reference upstream design documents for exact tool binary names rather than assuming from the Python ecosystem.
