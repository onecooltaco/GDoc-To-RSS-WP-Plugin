=== Google Doc to RSS ===
Contributors: onecooltaco
Tags: google docs, rss, feed, syndication
Requires at least: 4.5
Tested up to: 6.3
Requires PHP: 7.0
Stable tag: 2.0.0
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Turns the lines of a shared Google Doc into items in a custom WordPress RSS feed.

== Description ==

Google Doc to RSS retrieves the plain-text export of a configured Google Doc and publishes each line as an item in a custom RSS 2.0 feed.

The document must be shared so the WordPress server can retrieve it without an interactive Google login. Do not use this workflow for confidential content.

== Installation ==

1. Upload the plugin files to `/wp-content/plugins/gdoc2rss`.
2. Activate Google Doc to RSS.
3. Open Settings > Google Doc to RSS.
4. Configure a feed name.
5. Enter the Google Doc ID, found between `/d/` and `/edit` in the document URL.
6. Visit `/feed/ticker`, replacing `ticker` with the configured feed name.

If the feed initially returns a 404, save Settings > Permalinks once to refresh rewrite rules.

== Frequently Asked Questions ==

= Does the document need to be public? =

It must allow the WordPress server to retrieve its plain-text export without signing in. Review the document's sharing settings and do not include sensitive information.

= How are feed items separated? =

Each line of document text becomes one RSS item.

= Does the plugin use the Google Drive API? =

No. It requests the document's standard plain-text export URL.

== Changelog ==

= 2.0.0 =

* Restructured the plugin using WordPress Plugin Boilerplate conventions.

= 1.0 =

* Renamed the plugin and made class functions public.

= 0.6 =

* Disabled page caching for the RSS template.

= 0.5 =

* Added the first working custom RSS feed.
