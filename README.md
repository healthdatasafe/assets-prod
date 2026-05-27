# HDS Production Visual Assets

This repository hosts the **production** visual assets for the [Health Data Safe](https://www.healthdatasafe.org) platform. Content is served as static GitHub Pages from this repo's `main` branch.

The file [`index.json`](index.json) is exposed via the [Service Information](https://api.pryv.com/reference/#service-info) API call under the `assets.definitions` property, referenced by the prod open-pryv.io platform config.

- **Prod service-info:** <https://reg.api.datasafe.dev/service/info>
- **Published URL:** <https://healthdatasafe.github.io/assets-prod/index.json>
- **Demo equivalent:** [`healthdatasafe/assets-demo`](https://github.com/healthdatasafe/assets-demo) — same structure, served from <https://healthdatasafe.github.io/assets-demo/index.json>.

## Structure

### `index.json`

- `baseUrl` resolves relative resource paths. `null` means "resolve against `index.json`'s own location" (HTML `<base href>` semantics).
- `favicon.default` — `.ico` file path.
- `css.default` — `.css` file path.
- `{app-name}` — custom assets per consumer app (see `app-web-auth3/`, `lib-js/`).

```json
{
  "baseUrl": null,
  "favicon": { "default": "favicon.ico" },
  "css": { "default": "default.css" },
  "lib-js": {
    "buttonSignIn": {
      "css": "lib-js/buttonSignIn.css",
      "html": "lib-js/buttonSignIn.html",
      "messages": "lib-js/buttonSignInMessages.json"
    }
  }
}
```

## Editing

1. Edit files on `main`.
2. Commit + push — GitHub Pages publishes the root of `main` automatically.
3. Verify the change at <https://healthdatasafe.github.io/assets-prod/index.json> after build (~1 minute).

Service-info caches mean clients may see the old version for several minutes after a content change. Verify with a fresh browser session or `curl --no-keepalive`.
