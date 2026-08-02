# Changelog

All notable changes to **Aqly Production Readiness** are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- **Licence — added a free-use grant.** Personal use, internal business use, modification for your own
  use, and producing work product for yourself, your business, or your clients are now permitted at
  no charge. Redistribution, resale, sublicensing, repackaging, and building a competing product for
  distribution remain prohibited, and now apply to free users and purchasers alike. Work product you
  create with the skill is yours and is not restricted. The grant may be withdrawn for future
  versions but cannot be revoked for a version already obtained under it.
- **Install instructions** now point at the skill folder (`.../tree/main/production-readiness`) rather than the
  repository root, which contains no `SKILL.md` and cannot be imported.

> These changes are live on `main`, so they already reach anyone importing from it, but they are not
> yet covered by a version tag.

## [1.0.0] — 2026-08-01

### Added

- Initial public release.
- A 20-item MUST-HAVE launch-blocker checklist across security, reliability, data and recovery, observability, release safety, and docs and legal.
- 9 items marked *(always)* that cannot be waived at any size; the rest scale to the artifact.
- A SHOULD-HAVE maturity list recorded as follow-ups rather than blockers.
- Evidence discipline: an item claimed met without evidence is not met, and an unverifiable item is reported rather than assumed.

[Unreleased]: https://github.com/tohir-dev/aqly-production-readiness/compare/v1.0.0...main
[1.0.0]: https://github.com/tohir-dev/aqly-production-readiness/releases/tag/v1.0.0
