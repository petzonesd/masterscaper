# Masterscaper

Masterscaper.com is a live, static GitHub Pages site (served from `main`, root,
via the `CNAME` file) — the aquascaping technique and style "field manual" for
Pet Zone Tropical Fish / Hakkai (San Diego). No build step: plain HTML/CSS/JS,
fonts from Google Fonts CDN.

## Site structure

- `/` — homepage
- `/styles/` — Iwagumi, Dutch, jungle/nature, biotope, paludarium
- `/techniques/` — hardscape materials & placement, planting order, trim
  schedule, CO2/lighting & nutrients
- `/progression/` — beginner → intermediate → master stages
- `/gallery/` — curated layouts by style, cross-linked to the style pages
- `/glossary/` — A–Z plain-language term definitions
- `/about/` — who writes it, relationship to Hakkai / Pet Zone SD
- `404.html`, `sitemap.xml`, `robots.txt`, `llms.txt` — standard site plumbing
- `styles.css` — shared stylesheet for all sub-pages; `assets/nav.js` drives
  the mobile nav toggle
- `assets/` — icons and shared JS; page photos are hotlinked from the Hakkai
  Shopify CDN and Aquascape Supply CDN rather than stored in this repo

## Design system

Current tokens (see `:root` in `styles.css`): `--slate`, `--granite`,
`--moss`/`--moss-ink`, `--lichen`, `--paper`, `--plumb`, with `--ink`/`--sand`/
`--deepwater`/`--driftwood` kept as aliases onto those for backward
compatibility. Display font is Epilogue, body/serif text is Newsreader
(both via Google Fonts). The site went through a full visual redesign around
2026-10-07 (see the `pre-redesign-20261007` branch for the prior look) —
don't assume older references to a different palette or font pair still
apply; this file and `styles.css` are the source of truth.

Visual language: full-bleed photo heroes (`.page-hero.has-photo`) with a dark
gradient overlay, `.img-slot.photo` image wrappers, and a `.grid-3` card
layout for galleries/index pages. SEO schema (BreadcrumbList, FAQPage,
Organization, WebSite, DefinedTermSet, HowTo, ImageGallery) is already in
place site-wide via JSON-LD `@graph` blocks — extend it, don't duplicate it.

## Maintenance

This repo is maintained day-to-day by a scheduled Claude session (small,
reversible SEO/content/UI improvements, pushed straight to `main`) and
periodically by Roger directly or via other tooling (e.g. a ChatGPT-based
workflow) — same-day pushes from more than one source are expected, so any
session working on this repo should `git fetch`/merge before and after
making changes rather than assuming its local clone is current.

Template-wide CSS changes, `robots.txt`, redirects, and DNS/account settings
are flagged for Roger's review rather than shipped directly.
