<!--
  [P] marks tasks eligible for parallel execution.
  Add [P] when a task: (a) touches different files from
  other [P] tasks in the group, (b) has no dependency
  on prior tasks in the group, (c) can safely execute
  without ordering constraints.
  Do NOT add [P] when tasks modify the same file —
  parallel workers will cause merge conflicts.
  Tasks without [P] run sequentially first, then [P]
  tasks run in parallel.
-->

## 1. Add Build from Source subsection to README

- [x] 1.1 Add a "### Build from Source" subsection to `README.md`
  after the "### Binary Download" subsection (line ~40). Include:
  prerequisites line (Requires Go 1.25+ and `make`), clone command
  (`git clone https://github.com/unbound-force/replicator.git`),
  `cd replicator`, build command (`make build`), and verification
  (`bin/replicator version`). Follow the structural pattern from
  gaze and dewey READMEs.

## 2. Verification

- [x] 2.1 Run `make build` from repo root and verify
  `bin/replicator version` outputs version, commit, and date
  fields (not `dev`/`unknown`).
- [x] 2.2 Verify consistency: compare the new subsection structure
  against gaze (`README.md:44-50`) and dewey (`README.md:184-190`)
  build-from-source sections — same pattern: heading, code block
  with clone + build, prerequisites note.
- [x] 2.3 Verify Composability First alignment: the documented
  instructions allow building replicator independently without
  Homebrew, pre-built binaries, or any external distribution
  channel.
<!-- scaffolded by uf vdev -->
