# Viewer Metrics

Viewer Metrics is a Manifest V3 Chrome extension for Twitch that tracks channel viewer data and highlights account-creation patterns that may indicate suspicious or automated accounts.

> **Important:** Account-age and account-creation patterns are heuristic signals, not proof that an account is a bot. Review the context before drawing conclusions.

## Features

- Viewer-count and viewer-list tracking on Twitch channel pages.
- Viewer profile details and account creation dates where available.
- Charts and summaries for account-creation patterns.
- Searchable viewer data and export tools.
- Adaptive polling intended to reduce unnecessary network requests.
- Local-first processing of tracking and analysis data.

## Privacy and network activity

- Requests are sent directly to Twitch endpoints, including `gql.twitch.tv`, to retrieve channel and profile data.
- The hardened 0.9.953 archive does not intercept OAuth tokens or authentication headers; it uses a Twitch Client ID.
- Most active tracking state is kept in memory. Some settings, viewer-page handoff data, and diagnostic logs may be stored in Chrome extension storage.
- Do not assume that data is never persisted: see [PRIVACY_POLICY.md](PRIVACY_POLICY.md) for the storage and retention details.

## Install from source

**The complete extension source is not yet published on the repository's default branch.** The current `main` branch only contains the license file, and this documentation branch does not include the extension runtime files. Do not try to load this repository as an extension until `manifest.json`, `background/`, `content/`, `pages/`, `shared/`, `lib/`, and the required assets are present.

To install a complete source distribution:

1. Unpack the extension archive into a directory.
2. Open `chrome://extensions/` in Chrome.
3. Enable **Developer mode**.
4. Select **Load unpacked** and choose the directory containing `manifest.json`.

Keep `manifest.json` at the extension root and preserve the relative paths used by the manifest.

## Security and validation

Before using a build, test the main Twitch channel page, viewer profile pages, API failure and rate-limit behavior, multiple tabs, and stopping/restarting tracking. Chrome may terminate Manifest V3 service workers; short-interval polling and state recovery need runtime validation in the target Chrome version.

See [AUDIT_FIXES.md](AUDIT_FIXES.md) for the hardening changes described for the 0.9.953 archive and [PRIVACY_POLICY.md](PRIVACY_POLICY.md) for privacy details. These documents should be verified against the exact source tree before publishing a release.

## Third-party libraries

The 0.9.953 distribution archive includes Chart.js and chartjs-adapter-date-fns. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md); preserve the upstream license headers when redistributing the bundled files.

## License

Project code is licensed under the [MIT License](LICENSE). Third-party libraries remain subject to their own license notices. The license does not imply endorsement by Twitch.
