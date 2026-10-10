# Relisted

A minimal Hugo theme for writing. The home page is a plain list of post titles and dates. Each post puts the text first, with readable typography and no JavaScript.

![Relisted screenshot](https://raw.githubusercontent.com/gyli/hugo-theme-relisted/master/images/screenshot.png)

Relisted started as a fork of [listed](https://github.com/ronv/listed) by Ronalds Vilciņš, and has been reworked since 2022 for the author's own blog, [guangyangli.com](https://guangyangli.com/posts/).

## Features

- A plain list of posts, newest first, with dotted leaders between title and date
- Responsive layout with larger text on phones
- Clear heading hierarchy, a styled table of contents, tables, blockquotes, and code blocks
- Syntax highlighting (Hugo's default Monokai style, or any style you set)
- Heading anchors, external links that open in a new tab, and lazy-loaded images with width and height set
- A `figure` shortcode that links each image to its full-size file, so readers can zoom in on diagrams
- Full-text RSS feed, without the table of contents, and with absolute image paths
- Tags and categories, with term pages
- Open Graph, Twitter cards, and JSON-LD structured data
- Google Analytics, only loaded when you set an ID
- Colors, fonts, and content width set in SCSS variables that your site can override
- Interface text in `i18n/` files, so it can be translated
- No JavaScript, except Google Analytics when you enable it

## How It Differs from Listed

Relisted is a separate theme, not a small restyle. Compared with listed at the time of the fork:

- **Configurable.** Listed hard-codes the site name, the menu links, the RSS author and the `posts` section. Relisted uses site config for all of them: menus, `mainSections`, author, favicon, and social images.
- **Responsive.** Listed has no mobile layout. Relisted has a phone layout with a collapsible menu and larger text.
- **New typography and styles.** Heading sizes, colors, links, code blocks, tables, blockquotes, and the table of contents are redesigned.
- **New templates.** Render hooks for headings, links, and images, a `figure` shortcode, a `table` shortcode, a footer menu, and a rewritten RSS feed.
- **Current Hugo.** Relisted removes APIs that newer Hugo versions dropped, and needs Hugo 0.158.0 or newer.

## Requirements

Hugo **extended** edition, version **0.158.0** or newer. The stylesheet is compiled from SCSS.

## Installation

As a Git submodule:

```sh
git submodule add https://github.com/gyli/hugo-theme-relisted.git themes/relisted
```

Then set the theme in your site config:

```toml
theme = "relisted"
```

Or as a Hugo module. Run `hugo mod init <your module path>` in your site first, then add:

```toml
[module]
  [[module.imports]]
    path = "github.com/gyli/hugo-theme-relisted"
```

## Configuration

A minimal `hugo.toml`:

```toml
baseURL = "https://example.org/"
locale = "en-us"
title = "My Blog"
theme = "relisted"

[params]
  author = "Jane Doe"
  description = "Notes on software and writing."
  favicon = "favicon.png"
  images = ["avatar.jpg"]

[menu]
  [[menu.main]]
    name = "About"
    url = "/about/"
    weight = 10

  [[menu.footer]]
    name = "RSS"
    url = "/index.xml"
    weight = 10
```

### Parameters

| Parameter | Description |
| --- | --- |
| `author` | Author name. Used in meta tags, structured data, and the footer. |
| `description` | Site description. Used when a page has no `description` of its own. |
| `favicon` | Path to the favicon under `static/`. PNG, SVG, and ICO are supported. |
| `logo` | Path to a logo under `static/`. Used as the publisher logo in structured data. |
| `images` | Fallback images for social previews, for pages without `images` in front matter. |
| `blogURL` | Where the site title in the header links to. Defaults to the first main section, or the home page. |
| `authorEmail` | Optional. Added to the RSS feed as the author and editor. |
| `copyright` | Optional. Added to the structured data on the home page. |

Other settings come from standard Hugo config:

- `mainSections`: the sections listed on the home page and in the RSS feed. Hugo picks the section with the most pages by default.
- `googleAnalytics`: a Google Analytics ID. Nothing is loaded when it is empty.
- `menu.main` and `menu.footer`: the header and footer links.
- `services.rss.limit`: the number of posts in the RSS feed.
- `markup.highlight.style`: the syntax highlighting style.

## Writing Posts

Front matter that the theme uses:

```yaml
---
title: "My First Post"
date: 2026-10-01
description: "Used for the meta description and social previews."
tags: ["Writing"]
categories: ["Notes"]
images: ["images/cover.png"]
---
```

### Shortcodes

- `{{< table_of_contents >}}` inserts the page's table of contents.
- `{{< figure src="images/diagram.png" alt="..." caption="..." >}}` inserts a lazy-loaded image that links to its full-size file. It also accepts `title`, `link`, `target`, `rel`, `class`, `width`, and `height`.
- `{{< table "table table-striped" >}}` wraps a Markdown table and adds CSS classes to it.
- `{{< tagcloud min=3 >}}` lists tags used at least `min` times, most used first.

## Customization

**Colors, fonts, and width.** Create `assets/scss/_custom.scss` in your site and set only the variables you want to change. The full list is in [`assets/scss/_variables.scss`](https://github.com/gyli/hugo-theme-relisted/blob/master/assets/scss/_variables.scss).

```scss
$color-accent: #b5442c;
$font-body: Charter, Georgia, serif;
$content-width: 72ch;
```

The link underline and text selection colors follow `$color-accent`.

**Templates.** Copy any file from `layouts/` into the same path in your site, and edit the copy. For example, add `layouts/index.html` to make your own home page.

**Translations.** Copy `i18n/en.toml` to your site as `i18n/<language>.toml`, and translate the values.

## Example Site

The `exampleSite` folder has a demo site with a Markdown guide. To run it, the theme folder must be named `relisted`:

```sh
git clone https://github.com/gyli/hugo-theme-relisted.git relisted
cd relisted/exampleSite
hugo server --themesDir ../..
```

## License

[MIT](https://github.com/gyli/hugo-theme-relisted/blob/master/LICENSE.md). Copyright © 2021 Ronalds Vilciņš, and © 2022-2026 Guangyang Li.

Listed was released under the MIT license in [September 2021](https://github.com/ronv/listed/blob/bc251c5683fdd40ebc3383233b60c9fee17cc3f9/LICENSE.md), and Relisted was forked from that version in May 2022. Listed later removed its license file, but that does not change the license of the copy Relisted is based on.
