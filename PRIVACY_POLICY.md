# Privacy Policy — Viewer Metrics

**Last updated: October 27, 2026**

This policy describes the source snapshot currently being published to this repository: Viewer Metrics 0.9.951, based on the public upstream project. Verify these statements against the exact release artifact before distribution.

## Data the extension processes

While tracking is active, the extension may process viewer usernames, timestamps, account creation dates, publicly available profile details, viewer metrics, following-related information, and user-configured preferences. This information is used to display viewer analytics, charts, and account-creation-pattern heuristics. Such heuristics can produce false positives and are not proof that an account is automated.

## Network requests

The extension makes requests directly to Twitch endpoints, including `gql.twitch.tv`, to retrieve viewer and profile information. Twitch receives the request details needed to serve those requests and handles them under its own privacy notice and terms.

The reviewed 0.9.951 source uses a public Twitch Client ID and does not implement OAuth token interception. This policy does not claim that no data leaves the device: requests to Twitch are part of the extension's functionality.

## Local storage and retention

Configuration preferences are stored using Chrome extension storage. Active tracking state is held primarily in memory, but the code also contains paths for temporarily storing viewer-page handoff data and diagnostic logs. Values written to extension storage may persist until overwritten or cleared; do not assume every value expires automatically after 24 hours.

You can stop tracking, clear extension data through Chrome, or uninstall the extension. Clearing storage or uninstalling may remove locally retained data.

## Permissions

The 0.9.951 upstream manifest requests `storage`, `tabs`, and `scripting`, and broad Twitch host access. Content scripts run on Twitch pages; extension pages and bundled resources are declared as web-accessible resources for Twitch page contexts. Review the permission prompt before enabling the extension. These permissions should be narrowed only after confirming that the affected features continue to work.

## Third-party service

Viewer Metrics relies on Twitch. Please review the [Twitch Privacy Notice](https://www.twitch.tv/p/legal/privacy-notice/) to understand how Twitch handles requests sent to its services.

## Policy changes and contact

This policy may be revised as source code and data flows change. Questions can be raised via the [GitHub repository](https://github.com/vibecoderqin/viewermetrics/issues).

This policy is a summary of intended behavior, not a legal compliance certification. The publisher is responsible for verifying the published build, Chrome Web Store declarations, and applicable legal requirements.
