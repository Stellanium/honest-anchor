# Changelog

All notable changes to Honest Anchor will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.1] - 2025-12-24

### Security (HARDENING RELEASE)
- **TOCTOU fix**: Atomic file rename with symlink rejection
- **Path validation**: Safe `relative_to()` handling prevents ValueError crashes
- **Glob limits**: Max 10,000 files to prevent DoS from huge directories
- **Symlink protection**: Rejects symlinks in OTS file moves
- Post-move verification ensures destination is not a symlink

### Changed
- Requires `honest-chain >= 2.14.0` (post-quantum signatures)

## [0.2.0] - 2025-12-24

### Added
- `honest-chain >= 2.14.0` as dependency for post-quantum signature support
- Combined timestamping (Bitcoin) + signing (Dilithium) capability

### Changed
- Updated README with honest-chain integration notice

## [0.1.2] - 2025-12-19

### Fixed
- Minor bug fixes

## [0.1.1] - 2025-12-15

### Added
- `--staged` / `-s` flag for `anchor commit` command
- Git pre-commit hook integration
- `get_staged_files()` function to detect git staged files
- 6 new tests for staged functionality (20 total)
- GitHub Actions CI workflow (Python 3.8-3.12)
- CI, PyPI, Python version, and license badges in README

### Changed
- Expanded Git Integration section in README with setup instructions

## [0.1.0] - 2025-12-15

### Added
- Initial release
- `anchor init` - Initialize `.anchor/` directory
- `anchor commit <file>` - Timestamp files to Bitcoin via OpenTimestamps
- `anchor commit --all` - Anchor all files matching config patterns
- `anchor status` - Show pending/confirmed anchors
- `anchor verify <file>` - Verify file hasn't changed since anchoring
- `anchor history` - Show timeline of anchored files
- `anchor info <file>` - Show details about a specific anchor
- `anchor upgrade` - Check and upgrade pending anchors to confirmed
- YAML configuration support (`.anchor/config.yml`)
- Auto-anchor patterns with glob support
- Dual licensing (AGPL-3.0 + Commercial)
- 14 unit tests

[0.1.1]: https://github.com/Stellanium/honest-anchor/releases/tag/v0.1.1
[0.1.0]: https://github.com/Stellanium/honest-anchor/releases/tag/v0.1.0
