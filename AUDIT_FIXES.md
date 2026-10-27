# Viewer Metrics — hardening changes in 0.9.953

This document describes the changes made to the supplied source archive. It is not a claim that the source files have already been published to the default branch.

## Changes in the hardened archive

- Removed unused `scripting` permission and narrowed Twitch content-script matching; limited API host permission to `https://gql.twitch.tv/*`; restricted web-accessible resources to icons.
- Replaced selected unsafe viewer/profile HTML interpolation with DOM APIs or safe output handling and validated profile image URLs.
- Removed the 50-identical-query viewer-list fan-out; retained a compatibility method that makes one request.
- Switched viewer-count GraphQL construction to variables and validate channel logins.
- Added request timeouts, bounded user-info concurrency, request telemetry, and error handling.
- Prevented failed viewer-count calls from being recorded as a count of zero.
- Added validation of message objects/types and payloads, and corrected async message response handling.
- Bounded session history/error accumulation.
- Fixed force-stop ordering and tracked/cleared the initial delayed fetch timeout.
- Unified live interval recalculation with the shared timeout utility.
- Used a unique storage key per viewer-detail tab and removed the handoff key after reading it.
- Fixed `isAuthenticated: false` being coerced to `true`.
- Updated README and privacy-policy claims to reflect the intended request/storage implementation.

## Validation reported for the archive

- JavaScript syntax checks (`node --check`) on non-minified JavaScript source files.
- Manifest JSON parsing and structural checks.
- Static checks for duplicate viewer-list fan-out and selected unsafe rendering paths.

## Remaining limitations

The archive has not been runtime-tested in Chrome against the live Twitch API. Test the Twitch channel page, multiple viewer-detail tabs, offline/429 behavior, extension reloads, and service-worker termination before release. The short-interval polling architecture still depends on in-memory Manifest V3 service-worker state and `setInterval`; guaranteed continuity after worker termination requires further architectural work.
