---
tag: review-insight
author: em
category: gotcha
created_at: 2026-09-01T14:41:53Z
identity: review-insight-20260901T144153-em
tier: draft
---

When the spec review council checks upstream repo content for factual accuracy, stale local clones can cause false CRITICAL findings. During the sync-dewey-rpm-docs review (August 2026), 8 of 11 reviewers flagged the upstream Dewey README as missing RPM documentation because the local clone was behind upstream/main. After rebasing, the RPM section was confirmed present. Pattern: always rebase sibling repos before running spec review when the spec references upstream content.
