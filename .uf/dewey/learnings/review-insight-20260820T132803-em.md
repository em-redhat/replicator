---
tag: review-insight
author: em
category: gotcha
created_at: 2026-08-20T13:28:03Z
identity: review-insight-20260820T132803-em
tier: draft
---

When the spec review council checks upstream repo content for factual accuracy, stale local clones can cause false CRITICAL findings. During the sync-dewey-rpm-docs review (August 2026), 8 of 11 reviewers flagged the upstream Dewey README as missing RPM documentation because the local clone at /home/elyons/Projects/dewey/ was behind upstream/main. After rebasing the local Dewey repo, the RPM section was confirmed present at lines 166-174. Pattern: always rebase sibling repos before running spec review when the spec references upstream content. This avoids wasting an entire review cycle on a false positive that requires re-running all 11 agents.
