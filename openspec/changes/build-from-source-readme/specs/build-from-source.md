## ADDED Requirements

### Requirement: Build from Source install subsection

The README `## Install` section MUST include a "Build from Source"
subsection positioned after the "Binary Download" subsection. The
subsection MUST document:

1. Prerequisites (Go 1.25+, make)
2. Clone command (`git clone`)
3. Build command (`make build`)
4. Output binary location (`bin/replicator`)
5. Verification step (`bin/replicator version`)

The subsection SHOULD follow the same structural pattern used by
gaze and dewey build-from-source documentation (clone, build,
verify).

#### Scenario: User builds replicator from source

- **GIVEN** a user has Go 1.25+ and make installed
- **WHEN** they follow the "Build from Source" README instructions
  (clone the repo, run `make build`)
- **THEN** a binary is produced at `bin/replicator` and
  `bin/replicator version` outputs version information including
  a git-derived version string, commit hash, and build date

#### Scenario: User without make reads the instructions

- **GIVEN** a user reads the "Build from Source" subsection
- **WHEN** they check the prerequisites
- **THEN** they see that both Go 1.25+ and make are required
  before attempting the build

## MODIFIED Requirements

None.

## REMOVED Requirements

None.
<!-- scaffolded by uf vdev -->
