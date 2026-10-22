# Changelog

All notable changes to this project are documented in this file. The format is based on
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- The README leads with a narrated scan-to-rollout demo: identify a broken rule pattern,
  verify a reviewed fix, publish it to a selected team and inspect delivery status.

### Security

- Builds use Go 1.26.10 and `tetriz-py` locks certifi 2026.10.19, both of which distrust the
  compromised eMudhra (emSign) intermediate CA keys. The server image now runs on
  `distroless/static-debian13`, and the `tetriz-py` image installs uv 0.13.5.

## [0.1.0] - 2026-10-15

### Added

- Initial source release.
- Harness Recommendations: scan committed harness files in the context of a repository, persist
  evidence-backed findings, and tune detectors through public Go configuration.
- A DERIVED engine for recommending new artifacts from populated coding-signal tables, backed by
  the bundled `tetriz-py` service and the operator's model credentials.
- Confined, bounded regular-file reads for repository scans, atomic inventory seeding after the
  run guard, and explicit errors when an on-disk scan fails.
- An Agent Desk pairing guide for adapting harness inventories, invocation records and session
  signals into the recommendations engine.
- Harness Control Plane: a Go server library, reference host, admin UI and Node agent for distributing
  selected artifacts to people, teams and repository checkouts, with manual test/control targeting.
- Agent file ownership checks, anchored filesystem operations, hook lifecycle reconciliation and
  HTTPS enforcement outside loopback. Agent source builds bundle a native helper and its notices.
- Runnable Go examples, offline component tests, disposable-Postgres integration tests, Compose
  acceptance, isolated protobuf drift checks, vulnerability checks and built-image notice verification.
- Project and third-party notices for the source, linked Go modules, bundled UI dependencies and
  Python image, including bundled OpenSSL and libuv components.

[Unreleased]: https://github.com/tetriz-ai/tetriz-harness/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/tetriz-ai/tetriz-harness/releases/tag/v0.1.0
