# Changelog

Assets served at `https://healthdatasafe.github.io/assets-prod/` (GitHub Pages from `main`),
referenced by `hds.ngo` service-info → `assets.definitions`. The `version` field in
`apps/list.json` is the cache-buster consumers key on.

## Unreleased

- New `smart/brands.json`: SMART App Launch 2.2.0 User-access Brand Bundle for Health Data Safe, one brand with the
  Switzerland and USA FHIR R4 endpoints (`https://auth-{ch,us}.api.datasafe.dev/adapter/fhir/r4`), portal
  `https://account.hds.ngo`. Not referenced from `index.json`; `apps/list.json` unchanged.

## 2026-11-12.1

- `apps/list.json` drops the **`cycle-intelligence`** and **`cycle-intelligence-monitor`** `partnerApps` entries
  (added in 2026-11-05.1): Cycle Intelligence is offered on demo only (perki, 2026-11-12). Prod's Partner apps no
  longer list it, and its consent screens no longer name it as vouched for. assets-demo keeps both entries.

## 2026-11-06.1

- `apps/list.json` new `partnerApps` entry **`app-hds-support`**, the same as assets-demo 2026-11-06.1: the support
  console (`grant: access`) is named "HDS Support Console" on the account app's sign-in and consent screens, with no
  `urls`, so it never shows in a patient's Partner apps. (`_plans/BUGS.md` B-2026-11-02-17)

## 2026-11-05.1

- `apps/list.json` gains **`partnerApps`** (data-model APP-DESCRIPTION.md), the same three entries as assets-demo
  2026-11-05.1, each vouching for its implementer's manifest:
  - `cycle-intelligence` (`grant: access`), with `manifest` (its `hds-app-manifest.json`) and Open links;
  - `cycle-intelligence-monitor` (the practitioner app, `grant: access`), no `urls`, so it vouches on the
    practitioner's consent screen and Connected apps without appearing in a patient's Partner apps;
  - `dysnet-registry` (`grant: cmc`), `manifest` `registry.dysnet.org/publisher/hds-app.json`, `counterparty`
    `{ username: dysnet-registry, host: api.datasafe.dev }` (the account its invites come from, so only that
    account's relationships show as DysNet), Open links to `registry.dysnet.org`, `embedFrom` `https://app.hds.ngo`
    (allowed by its `frame-ancestors`).

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
