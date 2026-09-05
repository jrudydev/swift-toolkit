<!-- DERIVED from the structure genome `swift_toolkit` — DO NOT HAND-EDIT: edit the genome and regenerate -->
# The Astacinco Swift toolkit

A free, standalone SwiftUI toolkit: the pieces an app needs to look right, move right and stay simple, one module per concern, each with its own tests. The paid toolkit builds on it; nothing here depends on the paid toolkit. This page is the plan for review: every module below is proposed until it is approved, and built once its code and tests land.

## The modules 🧱

Each module does one thing. The order is the order they land in: a module lands only after everything it needs. A proposed module is on the table for review; approved means it is decided; built means its code and its tests are here.

**The free tier**

1. **testing** — The helpers every test in the toolkit uses: previews as fixtures, snapshot helpers, a fake network and a fake store. Needs nothing. _proposed, for review_
2. **tokens** — The design tokens: colors, type scale, spacing, radii, motion, plus the accessibility defaults. One source every view reads. Needs nothing. _proposed, for review_
3. **theme** — A theme is a set of tokens: light, dark, brand. Switch it with one call. Needs tokens. _proposed, for review_
4. **primitives** — The atoms you build screens from: text, button, image, field, surface. Themed and accessible by default. Needs tokens, theme. _proposed, for review_
5. **layout** — How things sit on screen: stacks with weights, grids, anchors, safe areas. No hand-placed coordinates. Needs tokens. _proposed, for review_
6. **i18n** — Strings, plurals, formats and text direction for other languages. Needs nothing. _proposed, for review_
7. **state** — The one way app state is held and bound to views, as a thin convention over SwiftUI's own observation and environment. Needs nothing. _proposed, for review_
8. **navigation** — Routes as values over SwiftUI's own stack: tabs, modals, and links from outside the app resolving to a route. Needs state. _proposed, for review_
9. **networking** — Requests as values: one session, decoding, retries, cancellation. Needs nothing. _proposed, for review_
10. **persistence** — One way to store locally: key-value, files, a database adapter. Needs nothing. _proposed, for review_
11. **perf** — Render and network timing as values, with one place to send them. Needs networking. _proposed, for review_
12. **feedback** — Toasts, alerts, sheets and progress, through one presenter. Needs primitives, layout, state. _proposed, for review_
13. **forms** — Fields, validation and submission state. Needs primitives, state. _proposed, for review_
14. **lists** — Sections, loading, empty and error states. Needs primitives, layout, state. _proposed, for review_
15. **auth-provider** — The seam: the protocol a sign-in implementation satisfies, so a paid module can plug one in. Needs networking. _proposed, for review_
16. **analytics-sink** — The seam: the protocol an events sink satisfies. Needs perf. _proposed, for review_
17. **flag-source** — The seam: the protocol a feature-flag source satisfies. Needs networking. _proposed, for review_
18. **media-loader** — The seam: the protocol a media loader satisfies. Needs persistence. _proposed, for review_
19. **notification-channel** — The seam: the protocol a notification channel satisfies. Needs nothing. _proposed, for review_
20. **security-policy** — The seam: the protocol a security policy satisfies. Needs networking, persistence. _proposed, for review_

_Generated page — do not hand-edit; it regenerates from the declared genome._
