---
tag: file-specific
author: em
category: pattern
created_at: 2026-08-20T13:28:14Z
identity: file-specific-20260820T132814-em
tier: draft
---

When adding a new installation method section between existing methods on a documentation page, always check whether the existing transition text needs updating. During sync-dewey-rpm-docs implementation, inserting an RPM section before the existing "On Linux, install from source:" text on dewey.md required changing it to "Or install from source:" because RPM is also a Linux method. The spec review caught this as a MEDIUM finding and it was added to the tasks before implementation. On knowledge.md, the fallback text "If the Homebrew formula is not yet available, install from source:" at line 82 was not updated because it is separated by 45 lines of embedding model configuration content — the code review flagged this as a LOW informational finding suitable for a follow-up change. Pattern: when inserting content between two existing sections, review the transitional text of both the preceding and following sections for accuracy.
