# Changelog

Assets served at `https://healthdatasafe.github.io/assets-prod/` (GitHub Pages from `main`),
referenced by `hds.ngo` service-info → `assets.definitions`. The `version` field in
`apps/list.json` is the cache-buster consumers key on.

## 2026-10-28.1

- `apps/list.json` **bridge-cyclefeminin and bridge-femm grant the streams bridge-cycles-files
  writes**: `app-cyclefeminin` + its 5 sub-streams (was `cyclefeminin-custom*`), `app-femm` + its 3
  sub-streams (was `bridge-femm*`). Without them the importer stops at "Preview changes" with `Stream
  provisioning failed … app-cyclefeminin`. Item grants aligned too: Cyclefeminin `symptom-pain-pelvic`
  replaces `symptom-gastrointestinal-cramps`; FEMM no longer asks for `fertility-cycles-average-length` /
  `-period`, which it does not write. `lastSync.streamId` follows the base streams. Same change as
  assets-demo 2026-10-28.1. (`_plans/BUGS.md` B-2026-10-26-5)
- `apps/list.json` connector entries may carry **`deviceName`** (the device the connector reads, used
  to label the values it writes) and **`deviceItems`** (item keys the device measures; absent means
  every value the connector writes). bridge-tempdrop: `Tempdrop`; bridge-mira: `Mira`, the five
  urine-hormone items.

## 2026-10-01.1

- `apps/list.json`: **bridge-mira `resync.initiate` now sends `{returnUrl}`** (and declares
  `openUrlField`), as assets-demo does. Without the body, the bridge's `/mira/resync` answered 400
  `Invalid or missing returnUrl`, so "Reconnect Mira" failed in prod.

## 2026-09-28.1

- `apps/list.json`: **bridge-femm and bridge-ryb icons** are now 128px PNG base64 data URIs
  (`type: "base64"`), rasterized from their previous SVG tiles, which were `type: "url"` SVG data URLs.
  app-web-user-account (upstream v0.5.0+, deployed 2026-09-25) accepts only absolute http(s) `url` icons
  and raster `base64` images (SVG is script-capable), so both apps showed no icon on the consent screen.
  (`_plans/BUGS.md` B-2026-09-25-4)

## 2026-06-12.1

- `apps/list.json`: **bridge-healthkit icon** — replaced the ❤️ emoji placeholder
  with the Apple Health app icon (128px PNG, base64 data URI, sourced from
  Wikimedia Commons `Icon_-_Apple_Health.png`).

## 2026-06-11.1

- `apps/list.json`: added **bridge-healthkit** (plan 38) — Apple Health
  connector, byte-identical port from assets-demo v2026-06-11.1.

(Changelog created 2026-06-12; for earlier history see `git log`.)
