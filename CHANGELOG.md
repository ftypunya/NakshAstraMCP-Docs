# Changelog

All notable changes to the NakshAstraMCP public distribution will be documented in this file.

## [3.7.0] - 2026-03-22

### Features
- **Enhanced Kotlin Support**: Correctly identify `import` statements and `property` declarations in Kotlin files.
- **Nebula Graph Persistence**: Symbol graph edges are now saved to the database, enabling full file connectivity in the visual dashboard.

### Improvements
- **Multi-Workspace Fallback**: Search tools now automatically search across all registered workspaces if no specific path is provided.

## [3.7.0] - 2026-03-22

### Features
- **Multi-Workspace Search**: Results from all registered repositories are merged and sorted by relevance score.

## [3.6.1] - 2026-03-20

### Bug Fixes
- Resolved database locking issues during intensive UI search operations.
- Fixed language-agnostic graph resolutions for improved visualization accuracy.

## [3.6.0] - 2026-03-19

### Features
- **Runtime Language Addons**: Support for provisioning any Tree-sitter grammar at runtime (e.g., Go, Rust, Ruby).
- **Operational Resilience**: Hardened environment checks and concurrency management for enterprise-scale deployments.

## [3.5.0] - 2026-03-15

### Features
- Secure binary wheel build process for streamlined distribution.
- Comprehensive CLI documentation and distribution guides integrated.
- Automated release pipeline with GitHub Actions.

### Improvements
- Optimized build process for smaller binary sizes.
- Version synchronization across all project assets.

## [3.4.0] - 2026-03-15

### Features
- Comprehensive user and distribution documentation overhaul.
- New Typer-based CLI with `start`, `status`, `gc`, and `doctor` subcommands.
- Multi-language AST support finalized for Python, JavaScript, TypeScript, Java, and Kotlin.

## [3.3.0] - 2026-03-14

### Features
- Dynamic multi-language node coloring in the Visual Dashboard (graph visualization).
- Grid layout for disconnected nodes in the dependency graph.

## [3.2.0] - 2026-03-14

### Features
- New Typer-based CLI for streamlined server management.
- Comprehensive user and distribution documentation added.

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
- Semantic reranking support for high-precision results.

## [2.0.0] - 2026-02-25

### Fixed
- Resolved database concurrency issues during parallel indexing.
- Improved grammar loading for Windows environments.

### Added
- Initial standalone binary distribution support.
- Centralized workspace registry for multi-project persistence.
