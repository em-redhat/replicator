## Context

The replicator README `## Install` section has three installation
methods (Homebrew, `go install`, Binary Download) but no "Build from
Source" option. Gaze and dewey both include this subsection. The
project already has `make build` and `make install` Makefile targets
that handle building, including version/commit/date injection via
ldflags.

## Goals / Non-Goals

### Goals
- Add a "Build from Source" subsection to the README install area
- Match the structure used by gaze and dewey (clone, build, verify)
- Document the correct build command for replicator specifically

### Non-Goals
- Adding Makefiles to dewey or gaze (separate concern)
- Unifying build approaches across all UF repos
- Documenting cross-compilation or GoReleaser usage
- Modifying the Makefile or build system

## Decisions

### D1: Use `make build` instead of bare `go build`

Replicator's Makefile injects version, commit, and date via
`-ldflags` at build time. A bare `go build ./cmd/replicator` would
produce a binary that reports `version=dev, commit=unknown` for
`replicator version`. Using `make build` gives users a binary with
meaningful version output. This differs from gaze and dewey where
bare `go build` is sufficient because they do not inject version
info at dev time.

### D2: Place subsection after "Binary Download"

Following the same ordering as gaze and dewey: package manager
first (easiest), then `go install`, then binary download, then
build from source (most effort). Build from source is the last
resort for users who need full control.

### D3: Include `make` as a prerequisite

Unlike gaze and dewey which use bare `go build`, replicator
requires `make`. This must be called out explicitly so users on
systems without make (e.g., some minimal containers) know upfront.

### D4: Verification step uses `bin/replicator version`

The Makefile places the binary at `bin/replicator`, not in the
working directory or on `$PATH`. The verification command must
reference this path. This differs from gaze (`./gaze --version`)
and dewey (`./dewey --version`) which place binaries in the
project root.

## Risks / Trade-offs

- **Low risk**: Documentation-only change. No code, tests, or CI
  affected.
- **Make dependency**: Documenting `make build` introduces a soft
  dependency on `make` being installed. This is standard on
  macOS and Linux but may not be present on all systems. The
  subsection lists it as a prerequisite to set expectations.
- **Composability First alignment**: Documenting build-from-source
  strengthens this constitutional principle by ensuring users
  can build replicator without any external distribution channel.
<!-- scaffolded by uf vdev -->
