# Relisted

Relisted is a minimalistic Hugo blogging theme, based on [Listed](https://github.com/ronv/listed).

### What's Changed

Relisted keeps the plain list of posts from Listed, and makes it easier to read and easier to reuse:

- **Better reading.** Clearer heading sizes, larger text on phones, softer colors, and styled code blocks, tables, quotes, and table of contents.
- **Nothing hard-coded.** The menus, author, favicon, and listed sections all come from your site config, so you do not need to edit the theme.
- **Easy to customize.** Change colors, fonts, and width in your site config. Translate the interface text in `i18n/`.
- **Works with current Hugo.** Uses Hugo's current template layout and `css.Build`, with no deprecated features. Works with the standard edition, no extended edition or Sass needed.

### Features

- Minimalistic, clean and simple design
- Responsive design
- Inline, minified CSS
- Anchor headings
- Table of contents
- Syntax highlighting
- Tags and categories
- Lazy-loaded images that link to the full-size file
- Full-text RSS feed
- 404 page
- SEO optimized (Twitter cards, Open Graph, Schema.org)
- No JavaScript, except Google Analytics when you enable it

### Installation

Relisted needs Hugo 0.160.0 or newer. Any edition works.

```sh
git submodule add https://github.com/gyli/hugo-theme-relisted.git themes/relisted
```

Then add `theme = "relisted"` to your site config. See [`exampleSite/hugo.toml`](https://github.com/gyli/hugo-theme-relisted/blob/master/exampleSite/hugo.toml) for the parameters and menus.

To run the example site:

```sh
cd themes/relisted/exampleSite
hugo server --themesDir ../..
```

### Customization

Set any of the theme's CSS variables under `[params.style]` in your site config. The full list with default values is in the theme's [`hugo.toml`](https://github.com/gyli/hugo-theme-relisted/blob/master/hugo.toml).

```toml
[params.style]
  color-accent = "#b5442c"
  font-body = "Charter, Georgia, serif"
  content-width = "72ch"
```

### Screenshot

![Screenshot](https://raw.githubusercontent.com/gyli/hugo-theme-relisted/master/images/preview.png)

### License

MIT. Listed is copyright © 2021 Ronalds Vilciņš, and was released under the [MIT license](https://github.com/ronv/listed/blob/bc251c5683fdd40ebc3383233b60c9fee17cc3f9/LICENSE.md) when Relisted was forked from it. Relisted changes are copyright © 2022-2026 Guangyang Li.
