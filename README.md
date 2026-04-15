# Artist Site

A minimal static artist site for Cloudflare Pages.

The current version is intentionally stripped down:

- Large centered logo
- Black background
- Centered text-only links in the logo color
- Optional embedded music player between the logo and links
- No build step, analytics, cookies, or external page-builder code

## Files

- `index.html`: layout, styles, and client-side rendering
- `site-config.js`: artist name, metadata, logo path, embed URL, and links
- `util_logo_orange_transparent.png`: current logo asset
- `_headers`: response headers for Cloudflare Pages

## Quick Start

1. Edit `site-config.js`.
2. Set your artist name, page title, description, and links.
3. Optionally add a music embed URL.
4. Push the repo to GitHub.
5. Connect the repo to Cloudflare Pages.

## Cloudflare Pages Setup

Use these settings:

- Framework preset: `None`
- Build command: leave blank
- Build output directory: `/`

This repo is plain static HTML, so Cloudflare Pages can deploy it directly from the repository root.

## Config

Everything artist-specific lives in `site-config.js`.

Available fields:

- `artistName`: used for the logo alt text and page identity
- `pageTitle`: browser title and social title
- `pageDescription`: meta description and social description
- `tagline`: optional line below the logo
- `siteUrl`: published site URL for social metadata
- `logoUrl`: logo image path or URL
- `musicEmbedUrl`: optional single iframe embed URL for a player
- `musicEmbeds`: optional ordered list of iframe embeds for stacked players
- `links`: ordered list of visible links

Each link object supports:

- `label`
- `url`

Only links with a non-empty `url` are rendered.

## Music Player

If both `musicEmbedUrl` and `musicEmbeds` are blank, the player section stays hidden.

If you add `musicEmbedUrl`, a single player appears between the logo and the links.

If you add `musicEmbeds`, each iframe in the list is rendered in order, which works well for stacked slim Bandcamp players.

## Local Preview

You can open `index.html` directly in a browser for a quick check, or run any static server if you prefer.

## Publishing Checklist

Before deploying:

- Set `siteUrl` to your real Pages URL or custom domain
- Confirm `logoUrl` points to the correct logo asset
- Add your live platform URLs
- Add `musicEmbedUrl` or `musicEmbeds` if you want the player enabled
- Double-check that no private URLs or sensitive data were added
