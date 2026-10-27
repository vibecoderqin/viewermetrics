# Changelog

All notable changes to Viewer Metrics are documented here.

## [0.9.953] — Security and performance hardening

- Replaced unsafe viewer/profile HTML interpolation with escaped output or DOM APIs and validated avatar URLs.
- Reduced identical viewer-list requests to one per polling cycle.
- Set adaptive polling targets of 5/10/15 seconds for small, medium, and large streams.
- Added request timeouts, bounded user-info concurrency, retry/backoff handling, and cancellation on stop.
- Prevented failed viewer-count calls from being recorded as real zeros.
- Validated background message payloads and normalized tracking configuration values.
- Fixed initial timeout cleanup, force-stop ordering, and the `isAuthenticated: false` default.
- Used per-tab keys for viewer-detail handoff data to avoid cross-tab overwrite races.
- Narrowed manifest permissions and updated privacy documentation.

## [0.9.952] — Multi-tab

- Allowed multiple tracking tabs, with each tab monitoring its own channel.
- Removed the global tracking-page lock.
- Made background sessions per tab and cleaned them up when tabs close.

## [0.9.951] — 2025-12-12

- Fixed event listener cleanup.

## [0.9.95] — 2025-12-11

- Refactored the viewer details popup.
- Added preliminary follower analysis.

## [0.9.94] — 2025-12-10

- Performance improvements and minor fixes.

## [0.9.93] — 2025-12-09

- Added CSV, XML, SQL, and JSON exports for viewer tracking and graph history.
- Added session save/load and analysis mode.

## [0.9.92] — 2025-12-03

- Fixed an issue with bot calculation.

## [0.9.91] — 2025-12-03

- Added concurrent batch processing for user information.
- Removed request interception in favor of a public Client ID.
- Adjusted bot detection baselines to reduce false positives and use 2020 as a base year.

## Older versions

See the Git history and release notes for changes in earlier versions.
