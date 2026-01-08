# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.3] - 2025-01-08

### Changed
- Updated download badge to use pepy.tech for better download statistics

## [0.1.2] - 2025-01-08

### Added
- Complete publishing infrastructure with GitHub Actions
- Comprehensive documentation (PUBLISHING.md, CONTRIBUTING.md, QUICK_START.md)
- Pre-publish checklist for release management

## [0.1.1] - 2025-01-08

### Added
- Publishing infrastructure and documentation
- GitHub Actions workflows for CI/CD
- CHANGELOG.md, CONTRIBUTING.md, PUBLISHING.md
- Pre-publish checklist and quick start guide

## [0.1.0] - 2025-01-08

### Added
- Initial release
- Dataset catalog listing with pattern matching and pagination
- Binary and text dataset downloads with encoding conversion
- PDS member downloads with parallel support
- JCL job submission and monitoring
- JES job listing and spool output retrieval
- VSAM dataset information retrieval
- GDG (Generation Data Group) information retrieval
- Advanced text processing (encoding, line endings, trailing spaces)
- Write protection mode for safe production use
- Connection management via environment variables
- Comprehensive error handling and validation
- JESINTERFACELEVEL detection and handling

### Features
- Support for Python 3.10, 3.11, 3.12, and 3.13
- Cross-platform compatibility (Linux, macOS, Windows)
- MCP server integration
- Configurable via environment variables
- Pagination support for large result sets
- Parallel downloads for PDS members

[0.1.0]: https://github.com/arunkumars-mf/zos-ftp-mcp/releases/tag/v0.1.0
