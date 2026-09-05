<!-- DERIVED from the structure genome `swift_toolkit` — DO NOT HAND-EDIT: edit the genome and regenerate -->
# The Astacinco Swift toolkit

A free, standalone SwiftUI toolkit for only what SwiftUI and Foundation do not give you: a token system, token-driven styles, test fixtures, a signpost sink, and the seams a paid tier plugs into. Everything the platform already does well — views, navigation, state, localization, networking, storage — stays the platform's, never wrapped. One module per concern, each with its own tests. The paid toolkit builds on this one; nothing here depends on it.

## The modules 🧱

Each module does one thing. The order is the order they land in: a module lands only after everything it needs. Every module on this page is proposed, for review.

**The free tier**

1. **fixtures** — What a test needs and the platform does not give: previews as fixtures, a fake network, a fake store. XCTest and the Testing framework stay the test runners. Needs nothing.
2. **tokens** — The design tokens as one typed value in the environment: colors, type scale, spacing, radii, motion, and the accessibility defaults. Every style reads it; dark mode and dynamic type stay the platform's. Needs nothing.
3. **styles** — Token-driven styles, not wrapper views: button, label, field and surface styles applied through modifiers, so SwiftUI's own views look right by default. Needs tokens.
4. **signposts** — A thin sink that turns signposts and MetricKit payloads into values with one place to send them. Instruments stays the profiler. Needs nothing.
5. **auth-provider** — The seam: the protocol a sign-in implementation satisfies, so a paid module can plug one in without the free tier knowing it exists. Needs nothing.
6. **analytics-sink** — The seam: the protocol an events sink satisfies. Needs nothing.
7. **notification-channel** — The seam: the protocol a notification channel satisfies. Needs nothing.
8. **security-policy** — The seam: the protocol a security policy satisfies; the protection product implements it. Needs nothing.

_Generated page — do not hand-edit; it regenerates from the declared genome._
