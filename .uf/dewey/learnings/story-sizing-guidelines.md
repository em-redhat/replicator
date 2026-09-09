---
type: learning
category: reference
tag: process
created: 2026-08-20
source: beatrizmcouto/roadmap docs/story-sizing-guidelines branch (private repo, fetched via gh CLI)
---

# Story Sizing Guidelines

T-shirt sizes for Step 6 (Story Sizing). Size once per release/milestone for a credible timeline — not sprint-by-sprint precision.

**Rule:** If a story is XL, break it before committing it to a sprint.

## Size Definitions

| Size | Effort | What It Looks Like |
|------|--------|-------------------|
| XS | Hours | Clear, tiny change; almost no unknowns. Touches one file/area; no new infra or contracts. No cross-team dependency; trivial test. |
| S | ~1-2 days | Well-understood scope; solution path is obvious. Mostly local to one service/component. Limited edge cases; existing patterns to follow. |
| M | ~3-5 days | Clear goal, but non-trivial implementation. Multiple components or IaC + app glue. Some research or config decisions — not open-ended discovery. |
| L | ~1-2 weeks | Significant complexity, unknowns, or integration surface. New subsystem, prod infra, or multi-service behavior. Ownership/design questions still open. |
| XL | Multi-week / needs split | Ambiguous problem or multiple independent deliverables. Cross-org coordination, greenfield architecture. Break it before sprint commit. |

## Quick Discriminators

| Question | Smaller (XS-S) | Larger (L-XL) |
|----------|----------------|---------------|
| Do we know how? | Yes | Spike / research first |
| How many systems? | 1 | 3+ |
| New contract / infra? | No | Yes |
| Failure / ops story? | Minimal | Central to DoD |
| Can one person finish in a week? | Yes | No / maybe with risk |
| Still blocked on ownership / design? | No | Yes → size up or split |

## Rules of Thumb

1. Size the uncertainty, not just the code volume
2. Dependencies inflate size — blocked work counts
3. If acceptance criteria span unrelated outcomes, split rather than XL
4. Infra + app + observability in one story usually lands M+; all three deep → L
5. Compare to a known baseline on your team

## Process Fit

- Applied in Step 6: Story Sizing after kickoff locks release scope
- Stories are sized once and not resized; material scope change is an escalation, not a re-size
- Per-story task breakdown stays just-in-time in execution (OpenSpec), not in this step
