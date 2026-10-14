# Google Doc to RSS

A WordPress plugin that converts the non-empty lines of a shared Google Doc into items in a custom RSS feed.

It is useful for simple editorial feeds where nontechnical contributors maintain a short list in Google Docs and WordPress publishes the list at a stable RSS URL.

## How it works

1. WordPress requests the document's plain-text export from Google Docs.
2. The plugin splits the returned text into lines.
3. Each line is rendered as an item in a custom RSS 2.0 feed.

The document must be shared so the WordPress server can retrieve it without an interactive Google login. Do not use this workflow for confidential content.

## Requirements

- WordPress 4.5 or newer
- PHP 7.0 or newer
- Outbound HTTPS access from WordPress to `docs.google.com`
- A Google Doc with link-sharing permissions that allow unauthenticated export

## Installation and configuration

1. Copy the repository to `wp-content/plugins/gdoc2rss`.
2. Activate **Google Doc to RSS**.
3. Open **Settings → Google Doc to RSS**.
4. Enter a feed name such as `ticker`.
5. Enter the Google Doc ID—the value between `/d/` and `/edit` in its URL.
6. Visit the resulting feed:

   ```text
   https://example.com/feed/ticker
   ```

If the feed initially returns a 404, save **Settings → Permalinks** once to refresh WordPress rewrite rules.

## Authoring guidelines

- Put one feed item on each line.
- Keep lines short enough for the applications consuming the feed.
- Avoid private or sensitive information; link-shared document text may be retrievable by anyone with the document URL or ID.
- Expect changes to appear when the feed is requested again; downstream feed readers may apply their own caching.

## Development

Install the PHP development dependencies with Composer:

```bash
composer install
```

The WordPress.org-style [`readme.txt`](readme.txt) contains release metadata. Keep its stable tag and compatibility fields aligned with the plugin header.

## License

GPL-2.0-or-later.
