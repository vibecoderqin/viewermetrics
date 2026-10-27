# Viewer Metrics

Viewer Metrics is a Manifest V3 Chrome extension for Twitch that tracks channel viewers and analyzes account-creation patterns that may indicate suspicious or automated accounts.

> **Important:** account age and creation-date patterns are heuristic signals, not proof that an account is a bot.

## Features

- Track viewer counts and lists on Twitch channel pages.
- Show public viewer profile details where available.
- Visualize account-creation patterns and viewer history.
- Search viewer data and export reports.
- Adjust request frequency based on stream conditions.

## Install

1. Download the ZIP from [GitHub Releases](https://github.com/vibecoderqin/viewermetrics/releases).
2. Extract it into a folder.
3. Open `chrome://extensions/` in Chrome.
4. Enable **Developer mode**.
5. Click **Load unpacked** and select the extracted folder containing `manifest.json`.

Alternatively, clone the repository and load the project root.

## Version and source

The first complete source snapshot published to this repository is the upstream Viewer Metrics source at version **0.9.951**, synced from [viewermetrics/viewermetrics](https://github.com/viewermetrics/viewermetrics). This is an authentic source baseline; it is **not** the separate locally prepared 0.9.953 hardened archive mentioned in earlier chat messages. That 0.9.953 archive has not been uploaded to this repository.

## Network activity and privacy

The extension sends requests directly to Twitch, including its GraphQL endpoint, to retrieve channel and profile information. The source uses a public Twitch Client ID and does not implement OAuth-token interception. Viewer data is processed primarily in the browser; preferences and some temporary or diagnostic values may be stored in Chrome extension storage. See [PRIVACY_POLICY.md](PRIVACY_POLICY.md) and verify it against the exact build you use.

## Development and validation

The extension uses a Manifest V3 service worker, content scripts, extension pages, and bundled Chart.js libraries. Before relying on it, test live Twitch tracking, API rate limiting, multiple tabs, and stop/restart behavior in your target Chrome version. Service-worker lifetime behavior can vary with Chrome's MV3 implementation.

## License

Project code is distributed under the [MIT License](LICENSE). Third-party libraries are subject to their own license notices. This project is not endorsed by Twitch.
