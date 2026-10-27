# Privacy Policy for Viewer Metrics

**Last updated: October 27, 2026**

## Overview

Viewer Metrics is a Chrome extension for Twitch viewer analytics. This policy describes the intended behavior of the 0.9.953 hardened distribution. The publisher must verify it against the exact source and build shipped to users.

## Data the extension processes

When you start tracking a channel, the extension may process:
- Twitch viewer usernames and observed first/last-seen times;
- account creation dates and publicly available profile fields, including avatars and descriptions;
- public profile/following information requested for the extension's analytics;
- tracking preferences and diagnostic information.

These fields are used to show metrics, charts, viewer profiles, and heuristic account-creation analysis. Bot indicators are estimates, not proof of automated behavior.

## Network requests

The extension sends requests directly to Twitch endpoints, including `https://gql.twitch.tv/gql`, using a public Twitch Client ID.

- The 0.9.953 source archive does not implement OAuth token interception.
- Twitch receives the request data needed to answer these requests, such as channel/login identifiers, and processes it under Twitch's own terms and privacy notice.
- The extension is not intended to send viewer datasets to a server operated by the Viewer Metrics publisher.
- The extension does not intentionally use advertising analytics, tracking pixels, or a separate telemetry backend.

## Storage and retention

- Configuration preferences may be stored in Chrome extension storage.
- Active tracking sessions and analysis data are held primarily in memory.
- Temporary viewer-page handoff data and bounded diagnostic logs may be written to Chrome local storage.
- The extension removes inactive viewers from the active session according to the configured timeout. This does **not** mean every locally stored value automatically expires after 24 hours.
- Values may remain until overwritten or the extension's data is cleared. Users can clear extension data through Chrome's extension settings or uninstall the extension.

## Permissions

The hardened manifest uses:
- **storage** — to save preferences and limited handoff/diagnostic data;
- **tabs** — to coordinate tracking and viewer-detail tabs;
- **Host access to `https://gql.twitch.tv/*`** — to make HTTPS requests to Twitch's GraphQL endpoint;
- **Content script matching on Twitch channel pages** — to display the extension UI.

The source must continue to be reviewed whenever permissions or data flows change.

## Security

The extension is designed to communicate with Twitch over HTTPS and not to capture OAuth tokens. Users should install the extension only from a source they trust and should review the code and permission prompts before enabling it.

## Your choices

You can stop tracking at any time, change extension preferences, clear extension storage, or uninstall the extension. Uninstalling or clearing storage may remove locally retained data.

## Third-party service

Viewer Metrics relies on Twitch. Please review the [Twitch Privacy Notice](https://www.twitch.tv/p/legal/privacy-notice/) and Twitch's terms to understand how Twitch handles requests sent to its services.

## Children

The extension is not intended for children under 13. The publisher must ensure that the product and its disclosures comply with applicable laws in the jurisdictions where it is offered.

## Policy updates and contact

This policy may change as the extension evolves. For questions, open an issue in the [vibecoderqin/viewermetrics repository](https://github.com/vibecoderqin/viewermetrics).

## Summary

**The extension does:** process viewer and profile data for local analytics; store preferences and some limited temporary data locally; make requests directly to Twitch.

**The extension is not intended to:** intercept OAuth tokens, sell viewer data, or send tracking datasets to a publisher-operated analytics backend.

This policy describes intended data practices and is not a legal compliance certification. The publisher is responsible for verifying the published build, Chrome Web Store data declarations, and applicable legal requirements.
