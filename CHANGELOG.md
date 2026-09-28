# Changelog

Assets served at `https://healthdatasafe.github.io/assets-prod/` (GitHub Pages from `main`),
referenced by `hds.ngo` service-info → `assets.definitions`. The `version` field in
`apps/list.json` is the cache-buster consumers key on.

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
