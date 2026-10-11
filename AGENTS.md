# Maintaining Relisted

Notes for working on this theme repo. If you are working on a site that only uses the theme, ignore this file.

## Rules

- Keep the theme general: no hard-coded site names, links, or author details. Everything comes from site config or `i18n/`.
- Hugo 0.160.0 or newer, any edition. Use no deprecated features.
- A change must not change how existing sites look, unless that is the point of the change. Build a site before and after, and diff the output.
- `layouts/_markup/render-link.html` and `render-image.html` must not end with a newline. It adds a space before punctuation after links.
- Only `layouts`, `assets`, `i18n`, `archetypes`, `static`, `data`, and `content` reach a user's site. Keep repo tooling (this file, `CHANGELOG.md`, `.github/`, `exampleSite/`) outside those folders, and list tooling files in `.gitattributes` with `export-ignore`.

## Checks

From `exampleSite/`:

```sh
hugo --themesDir ../.. --logLevel info | grep -iE "warn|error|deprecat"
hugo server --themesDir ../..
```

## Changelog

Add an entry to `CHANGELOG.md` for each release: the version, the date (UTC), and one line per user-visible change. Leave out changes that only touch repo tooling, unless nothing else changed.

## Release

1. Update `CHANGELOG.md` and commit.
2. Tag and push: `git tag -a vX.Y.Z -m "Relisted vX.Y.Z" && git push origin master vX.Y.Z`.
3. Use a new patch version for fixes and a new minor version for features. A new major version needs a `/vN` suffix on the module path in `go.mod`.

themes.gohugo.io builds from the latest tag and rebuilds daily at 00:00 UTC. Never delete or move a published tag: Go modules cache each version's checksum.

## Demo Site

`.github/workflows/demo.yml` builds `exampleSite/` and publishes it to GitHub Pages (https://gyli.github.io/hugo-theme-relisted/) on every push to `master`. The site is served from a subpath, so links in `exampleSite/content` must use `relref` or relative paths, not `/path/`. The screenshots in `images/` should match the demo: `screenshot.png` (1500×1000) and `tn.png` (900×600) for themes.gohugo.io, `preview.png` for the README.
