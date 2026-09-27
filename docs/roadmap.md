## Phase 0: Foundations (before writing feature code)

Pick the map/places API (price out Mapbox/OSM vs Google Places at expected scale)
Decide the account model (phone/email/Google sign-in — this affects the "account suggestion based on phone nb" feature later)
Legal pass: privacy policy, data retention, age gate (13+ or 16+ depending on target market)
Decide backend approach for location data specifically — it needs stricter handling than the rest of your data (encryption at rest, short retention, no third-party analytics on it)

## Phase 1: MVP: solo trip tool, no social yet

_Goal: prove the core loop (search place → save it → see it on a map → build a trip) works before layering people on top._
Add-place flow: search, details popup, "add to list / add to trip"
Personal trip/map tab: fullscreen map, colored pins by type, the three list views (premade trips, liked places, want-to-go)
Basic filters (type, price)
Account tab basics: settings, privacy, logout, bug report
Manual check-in (photo + geotag at time of posting) instead of continuous GPS tracking — solves your rating-gating problem without the battery/permission cost of background tracking
This phase alone is a usable, shippable app (personal trip planner) — good for early testing and feedback before social complexity.

## Phase 2: Social layer

_Goal: friends can see each other's stuff, safely, by default privately._
Friend system (request/accept, no following)
Privacy-by-default publishing, with per-trip and per-photo visibility toggles
Public trip viewing, ratings, pics/moments
Blocking + reporting
Home tab: friend updates, notifications, place recommendations based on ratings + friends
Friend suggestions (start simple — mutual friends only; save phone/contact matching for later, it's a bigger privacy lift)

## Phase 3: Group trips

_Goal: trips become collaborative, not just personal._
Invite-to-trip with accept/decline
Group trip roles (driver, DJ, snack supplier, etc.)
Trip-scoped notes section
Trip chat (decide now: ephemeral or persistent, moderated how)

## Phase 4: Live/real-time features

_Goal: the highest-risk, highest-complexity features, built last and with the most safety scaffolding._
Live location sharing during active trips — opt-in per trip, auto-expires at trip end, clear always-visible stop button
Real-time "who's near who" grouping on the trip map
Reconsider GPS-verified ratings here if manual check-in from Phase 1 turns out to feel weak

## Phase 5: Monetization + polish

Subscription or affiliate-based monetization (decide based on what Phase 1–4 usage data shows people value)
Account suggestions via phone/Google contacts (opt-in, clearly disclosed)
Accessibility pass (pin shapes, not just colors)
Offline map caching for active trips
