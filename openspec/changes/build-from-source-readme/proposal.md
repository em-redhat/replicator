## Why

The README install section lists Homebrew, `go install`, and binary
download but omits "Build from Source" instructions. Other UF
components ([gaze](https://github.com/unbound-force/gaze#build-from-source),
[dewey](https://github.com/unbound-force/dewey#build-from-source))
document this path, creating an inconsistency across the organization.
Contributors, users on unsupported platforms, and users who prefer
building from source have no documented path despite `make build` and
`make install` targets already existing.

Tracked by [#90](https://github.com/unbound-force/replicator/issues/90).

## What Changes

Add a "Build from Source" subsection to the README `## Install`
section, positioned after the existing "Binary Download" subsection.
The subsection documents prerequisites, clone + build commands, and
a verification step.

## Capabilities

### New Capabilities
- `Build from Source docs`: README subsection with prerequisites
  (Go 1.25+, make), clone + build commands (`git clone`,
  `make build`), output location (`bin/replicator`), and
  verification (`bin/replicator version`).

### Modified Capabilities
- None

### Removed Capabilities
- None

## Impact

- **Files**: `README.md` (add ~15 lines to the Install section)
- **Behavior**: No code changes. Documentation only.
- **Risk**: None. Additive content with no effect on build, tests,
  or CI.

## Constitution Alignment

Assessed against the Unbound Force org constitution.

### I. Autonomous Collaboration

**Assessment**: N/A

Documentation-only change. No artifact interfaces, MCP tools, or
inter-agent communication affected.

### II. Composability First

**Assessment**: PASS

Documenting how to build from source directly supports standalone
installability -- users can build replicator independently without
relying on Homebrew or pre-built binaries.

### III. Observable Quality

**Assessment**: N/A

No output formats, provenance metadata, or machine-parseable
interfaces affected.

### IV. Testability

**Assessment**: N/A

No code changes. No testable components introduced or modified.
<!-- scaffolded by uf vdev -->
