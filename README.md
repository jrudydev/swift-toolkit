<!-- DERIVED from the structure genome `swift_toolkit` — DO NOT HAND-EDIT: edit the genome and regenerate -->
# The Astacinco Swift toolkit

A free, standalone SwiftUI toolkit for only what SwiftUI and Foundation do not give you: a token system, token-driven styles, test fixtures, a signpost sink, and the seams a paid tier plugs into. Everything the platform already does well — views, navigation, state, localization, networking, storage — stays the platform's, never wrapped. One module per concern, each with its own tests. The paid toolkit builds on this one; nothing here depends on it.

## The modules 🧱

Each module does one thing. The order is the order they land in: a module lands only after everything it needs. A proposed module is on the table for review; approved means it is decided; built means its code and its tests are here.

**The free tier.** Every module here is approved.

1. **fixtures** — What a test needs and the platform does not give: previews as fixtures, a fake network, a fake store. XCTest and the Testing framework stay the test runners. Needs nothing.
2. **tokens** — The design tokens as one typed value in the environment: colors, type scale, spacing, radii, motion, and the accessibility defaults. Every style reads it; dark mode and dynamic type stay the platform's. Needs nothing.
3. **styles** — Token-driven styles, not wrapper views: button, label, field and surface styles applied through modifiers, so SwiftUI's own views look right by default. Needs tokens.
4. **signposts** — A thin sink that turns signposts and MetricKit payloads into values with one place to send them. Instruments stays the profiler. Needs nothing.
5. **auth-provider** — The seam: the protocol a sign-in implementation satisfies, so a paid module can plug one in without the free tier knowing it exists. Needs nothing.
6. **analytics-sink** — The seam: the protocol an events sink satisfies. Needs nothing.
7. **notification-channel** — The seam: the protocol a notification channel satisfies. Needs nothing.
8. **security-policy** — The seam: the protocol a security policy satisfies; the protection product implements it. Needs nothing.

**The paid tier — behind a paywall.** Each module implements one seam of the free tier or builds on it; it imports the free tier, never the reverse. Every module here is proposed, for review.

1. **sdui** — Screens described by the server: a schema, a registry of view builders, a renderer over the styles. The heart of the paid tier, and the one thing the platform gives nothing for. Needs tokens, styles.
2. **auth** — The sign-in flow over AuthenticationServices and the Keychain, filling the auth-provider seam. Needs auth-provider.
3. **analytics** — Sessions and actions as values: the session lifecycle as the app goes foreground and back, screen views, named actions with properties, user properties, an offline queue that batches and flushes, one adapter per vendor behind the sink. The pattern the founder shipped at Vessel.io, filling the analytics-sink seam. Needs analytics-sink, signposts.
4. **deep-linking** — Deferred and campaign links over the app's own universal links. Needs nothing.
5. **notifications** — The full-screen experience and the plumbing that gets a user to it: a takeover presenter an event can raise over anything, routing from a tapped notification straight into it, the interruption levels including the critical-alert path, the push token lifecycle, named channels. The pattern the founder shipped at Vessel.io, filling the notification-channel seam. Needs notification-channel, styles.
6. **security** — Pinning, device checks and the protection product behind the security-policy seam. Needs security-policy.
7. **testing-dsl** — A readable layer over the fixtures. Needs fixtures.

## How it is built

One module does one thing and ships with its own tests. A module lands only after everything it needs has landed, so the order on this page is the build order. The free tier never imports the paid tier: where the paid tier plugs in, the free tier declares a protocol, the seam, and a paid module implements it. Nothing the platform already does well is wrapped: views, navigation, state, localization, networking and storage stay SwiftUI's and Foundation's.

## The two tiers

The free tier is this repository: public, MIT, standalone. The paid tier is a second package, private and commercial, that imports this one and fills its seams: server-driven screens, sign-in, sessions and actions, deferred links, the full-screen notification experience, security, and a readable test language. It is listed below behind the paywall so the whole shape is visible in one place.

## What is not here, and why

A first draft carried the React Native toolkit's module list across; the second pass asked what SwiftUI and Foundation already give and kept only what is left. Cut: primitives (SwiftUI's views are the primitives), layout, state, navigation, networking, persistence, forms, lists, feedback, and localization (string catalogs and formatters). A module that wraps what the platform does well is a shallow module, and none ships here.

## How each module lands

A module is proposed until it is approved, then built once its code and its tests are in this repository. Each one is one package target with one public entry, reviewed against a structure audit that names any second concern or defect before it lands. This page regenerates from the declared structure; it is never edited by hand.

## License

MIT for this repository. The paid package carries a commercial license; access to its repository is what enforces it.

_Generated page — do not hand-edit; it regenerates from the declared genome._
