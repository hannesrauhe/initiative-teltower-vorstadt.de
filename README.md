# initiative-teltower-vorstadt.de

Read-only static mirror of the WordPress blog at https://initiative-teltower-vorstadt.de/blog/,
crawled with wget and post-processed for GitHub Pages. All `/blog/...` URLs are preserved
exactly; nothing redirects. Hosted via custom domain (see `CNAME`).

## Layout

- `blog/` — the mirrored site (posts, pages, tags, categories, uploads, theme assets)
- `index.html` — root page, meta-refresh to `/blog/`
- `404.html` — GitHub Pages 404
- `Offener_Brief_Initiative_Teltower_Vorstadt.pdf` — linked from the 2019 post, lives at the domain root
- `blog/wp-sitemap*.xml` — WordPress sitemaps, kept for search engines
- `tools/` — the scripts that produced this tree

## What was removed (WordPress-only, cannot work statically)

Search widget, comment forms/JS, RSS/Atom/oEmbed discovery, REST/pingback/RSD/shortlink
head tags, emoji CDN loader, IE conditional blocks, `?ver=` cache busters (stripped from
URLs and file names), and the redundant "Blog" entry in the Seiten sidebar widget.
Same-origin URLs were made root-relative and links restored to the original clean form
(`/blog/…/`, no trailing `index.html`).

## Known faithful quirks

- `blog/wp-content/uploads/2022/05/Girlande.jpg` 404s — broken on the live site too
- Gallery links to attachment pages (`?attachment_id=`, `screenshot_*/`) 404 — broken upstream too
- 18 `wp-admin/post.php` editorial links inside post content — kept as authored
- One link in the `buendnis-90-die-gruenen` tag page has a German quote as its href — as authored
