# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Jianwei Zheng's personal academic site, built on the **academicpages** template (fork of **Minimal Mistakes** Jekyll theme), served as a GitHub Pages site at `https://jwzheng96.github.io`. There is no application code — Jekyll renders Markdown + Liquid templates into static HTML.

## Local development

```bash
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

`_config.dev.yml` overrides production config (URL → `localhost:4000`, expanded SCSS). **Jekyll does not auto-reload `_config*.yml`** — restart the server after editing config.

## Where content lives

All real, edited content is in `_pages/`. There is no separate `_posts`/`_publications`/`_talks` content — those template collections were removed; the publications and talks lists are hand-written in `_pages/`.

| URL | Source file | Notes |
|---|---|---|
| `/` | `_pages/about.md` | Home page. Has `permalink: /`. Contains bio, News, Selected Publications, Honors, Teaching, Academic Service. |
| `/publications/` | `_pages/publications.md` | Full publications list, hand-written Markdown. |
| `/teaching/` | `_pages/teaching.html` | Iterates `site.teaching` collection (renders `_teaching/*.md`). |
| `/cv/` | `_pages/cv.md` | Education + work experience; links to PDFs in `static/cv/`. |
| `/collections/` | `_pages/collections.md` | Curated reading list of papers/articles. |
| 404 | `_pages/404.md` | Error page. |

The **only active collection** is `_teaching/` (configured in `_config.yml` under `collections:`). To add a teaching entry, drop a Markdown file into `_teaching/` following the existing entries' front-matter shape (`title`, `collection: teaching`, `type`, `permalink`, `venue`, `date`, `location`).

## Theme infrastructure (don't touch unless intentional)

Comes from upstream Minimal Mistakes:

- `_layouts/` — `default`, `single`, `archive`, `archive-taxonomy`, `compress`, `splash`, `talk`
- `_includes/` — partials (head, footer, sidebar, navigation, etc.)
- `_sass/` — theme SCSS
- `assets/` — compiled JS (`main.min.js`) and entry SCSS

Site-author metadata: `_config.yml` under `author:` (uses `images/jianweizheng.jpeg` as avatar). `_data/authors.yml` is **empty** — only needed if a page sets `author: "Name"` in front-matter, which nothing currently does.

Navigation links: `_data/navigation.yml`. UI strings: `_data/ui-text.yml` (theme-supplied).

## Real content assets

- `static/` — real PDFs (papers, CVs in EN/中文), figures. Linked from `_pages/about.md`, `_pages/publications.md`, `_pages/cv.md`, `_pages/collections.md`. Treat as untouchable.
- `images/jianweizheng.jpeg` — avatar referenced from `_config.yml`. Other `images/` entries (`manifest.json`, `browserconfig.xml`, `mstile-*.png`, `safari-pinned-tab.svg`) are favicon/PWA assets referenced from `_includes/head/custom.html`.

## Dormant tooling

- `markdown_generator/` — Python scripts (`publications.py`, `talks.py`, `pubsFromBib.py`) that generate per-item Markdown into `_publications/` and `_talks/` from TSV/BibTeX. **Currently inert** — the target collections were removed (`_config.yml` only declares `teaching`). To use them again, recreate the collection in `_config.yml`, recreate the `_publications/`/`_talks/` dirs, and a matching `_pages/publications.html` / `_pages/talks.html` that iterates `site.publications` / `site.talks`. The current hand-written `_pages/publications.md` doesn't need them.
- `talkmap.py` — generates a leaflet cluster map of talk venues by scraping `location:` front-matter from `_talks/*.md`. Inert for the same reason; `talkmap_link: false` in `_config.yml`.

## Gotchas

- **GitHub Pages plugin whitelist**: only [whitelisted plugins](https://pages.github.com/versions/) build in production. The `whitelist:` block in `_config.yml` reflects this — adding a plugin to `plugins:` alone is not enough.
- **`permalink` rules**: site default is `permalink: /:categories/:title/`, but every active content page sets an explicit `permalink:` in its front-matter, so the default only matters if blog posts are ever added.
- **Avatar path**: `_config.yml` author block uses `avatar: "jianweizheng.jpeg"` (resolved against `images/`). If renamed, update both the file and `_config.yml`.
