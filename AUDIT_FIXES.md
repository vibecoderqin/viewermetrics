# Audit status and release scope

The static audit identified areas for further hardening, including dynamic HTML rendering, message validation, API error semantics, polling behavior, cleanup, service-worker lifetime, permission minimization, and privacy documentation.

**Release scope:** the complete source snapshot being published to the repository is upstream Viewer Metrics 0.9.951. A separate local archive labelled 0.9.953 was prepared in the conversation, but its modified JavaScript files are not part of this GitHub source snapshot. The earlier local hardening summary must therefore not be read as evidence that those code changes have shipped here.

Before promoting any later hardened version, compare the changed files with this source tree and run runtime tests in Chrome against live Twitch behavior. In particular, repeated CommunityTab requests may return different viewer samples; eliminating all duplicate-looking requests without confirming the API semantics could reduce coverage.
