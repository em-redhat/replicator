---
tag: review-insight
author: em
category: pattern
created_at: 2026-09-01T14:42:01Z
identity: review-insight-20260901T144201-em
tier: draft
---

For small documentation-only changes (2 files, under 20 lines of diff), dispatching all 11 Divisor agents for code review is wasteful. Pattern: for docs-only changes, dispatch a focused subset of reviewers (adversary, guard, techwriter, scribe, architect) rather than the full council. This saves significant time and token cost while maintaining review quality. The curator, envoy, herald, PR, SRE, and testing agents have minimal relevance for pure Markdown content additions with no code, CI, or architectural changes.
