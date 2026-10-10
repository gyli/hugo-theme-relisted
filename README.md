# Relisted

A minimalistic Hugo blogging theme: a plain list of posts, and pages that put the text first. Relisted is a reworked version of [Listed](https://github.com/ronv/listed).

![Screenshot](https://raw.githubusercontent.com/gyli/hugo-theme-relisted/master/images/preview.png)

### What's Changed from Listed

- **Redesigned for reading.** New typography, softer colors, a layout tuned for phones, and styled code, tables, quotes, figures, and table of contents.
- **Ready for any site.** Nothing is hard-coded. Menus, author, sections, colors, fonts, and width come from your site config, and the interface text can be translated.
- **Built for current Hugo.** Rewritten for Hugo's current template system and CSS pipeline, with no deprecated features and no Sass or extended edition needed.

### Features

- Responsive layout, no JavaScript (except optional Google Analytics)
- Table of contents, heading anchors, and syntax highlighting
- Tags and categories
- Lazy-loaded images that link to the full-size file
- Full-text RSS feed
- Open Graph, Twitter cards, and Schema.org data

### Installation

Needs Hugo 0.160.0 or newer.

```sh
git submodule add https://github.com/gyli/hugo-theme-relisted.git themes/relisted
```

Add `theme = "relisted"` to your site config. [`exampleSite/hugo.toml`](https://github.com/gyli/hugo-theme-relisted/blob/master/exampleSite/hugo.toml) shows the available settings.

To change colors, fonts, or width, set CSS variables under `[params.style]`. The defaults are in the theme's [`hugo.toml`](https://github.com/gyli/hugo-theme-relisted/blob/master/hugo.toml).

```toml
[params.style]
  color-accent = "#b5442c"
  content-width = "72ch"
```

### License

MIT. Listed is copyright © 2021 Ronalds Vilciņš, and was under the [MIT license](https://github.com/ronv/listed/blob/bc251c5683fdd40ebc3383233b60c9fee17cc3f9/LICENSE.md) when Relisted was forked from it. Relisted changes are copyright © 2022-2026 Guangyang Li.
