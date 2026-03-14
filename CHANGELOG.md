# Changelog

All notable changes to the NakshAstraMCP public distribution will be documented in this file.

## [3.1.0] - 2026-03-14

### Features
- Mandatory UI: Dashboard dependencies now included by default in all distributions.
- Synchronization with core v3.1.0 baseline.

## [3.0.0] - 2026-03-14

### Features
- Major version reset to 3.0.0.
- Unified documentation synchronization.

## [2.9.0] - 2026-03-10

### Added
- Multi-client support via the Dual Transport Bridge (HTTP transport on port 2102).
- Enhanced security jailing for multi-repo workspace management.
- Improved AST-aware snippet extraction for large files.

### Changed
- Standardized CLI commands for consistent standalone binary usage.
- Optimized indexing performance for massive repositories (>50k files).

## [2.7.0] - 2026-03-05

### Added
- Integrated "Doctor" health-check utility for environment diagnostics.
- Real-time file watcher with debouncing and mass-update protection.
- Semantic reranking support using FlashRank for high-precision results.

## [2.0.0] - 2026-02-25

### Fixed
- Resolved SQLite concurrency issues during parallel indexing.
- Improved Tree-sitter grammar loading for Windows environments.

### Added
- Initial standalone binary distribution support.
- Centralized workspace registry for multi-project persistence.
