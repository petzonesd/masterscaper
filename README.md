# Masterscaper — launch checklist

## 1. Publish (matches flowerhornhobby.com / freshwaterguides.com)
- Create repo `petzonesd/masterscaper` (public) on GitHub Pages
- Push `index.html` as-is (fonts load from Google Fonts CDN, no build step)
- Point masterscaper.com DNS at GitHub Pages (same as the other two — DNS is at GoDaddy)
- This session has no GitHub auth, so the push itself needs to happen from a
  session with the petzonesd GitHub account (Claude Code / Cowork), or by hand

## 2. Reciprocal edits on the other sites (agreed plan)

**petzonesd.com `/aquascaping/` category (BigCommerce)**
Add below the existing Hakkai link:
> Want to learn the techniques yourself? Visit **Masterscaper** for style guides,
> hardscape placement, and planting technique.
> Link: https://masterscaper.com

**Six-site footer cross-link block** (Script Manager entry, currently on
petzonesd, Hakkai, Arowana, Flowerhorn, Betta Believe, Aquascape Supply)
Add a "Masterscaper — learn to aquascape" row to that block so it goes out to
all six sites in the next push, rather than as a separate rollout.

**Hakkai.com workshop/class pages**
Add an outbound line pointing to the relevant Masterscaper technique page
(e.g. Iwagumi class → `/styles/iwagumi/`) as supporting reading. Needs
whoever edits Hakkai's Shopify pages — flagging so it isn't dropped.

**Organization schema (my call, per your go-ahead)**
Added `sameAs` on Masterscaper pointing to petzonesd's Organization @id,
Hakkai, and Aquascape Supply (see JSON-LD in index.html). Also queue a small
addition to petzonesd's existing sitewide Organization schema: add
`"sameAs": ["https://masterscaper.com"]` alongside whatever's already there.
Low-risk, reversible, fits the "schema blocks can ship directly" autonomy rule.

## 3. Content — built (this session)
- `/index.html` — homepage
- `/styles/index.html` — Iwagumi, Dutch, jungle/nature, biotope, paludarium, each with a full breakdown section
- `/techniques/index.html` — hardscape placement, planting order, trim schedule, CO2/light basics
- `/progression/index.html` — beginner → intermediate → master tracks
- `/glossary/index.html` — 13 core terms
- `/styles.css` — shared stylesheet used by all sub-pages (homepage keeps its styles inline)

Still to build: `/gallery/` or `/showcase/` — needs real photos to be worth building, so
holding until the image pass below is done.

## 4. Photo pass — needs a session with site/browser access
This session has no network path to petzonesd.com, hakkai.com, or aquascapesupply.co,
so every image slot on the site is a placeholder `<div class="img-slot">` with a plain-text
note describing exactly what shot is needed and which of your properties is the likely
source. Search each page for `img-slot` to find all of them (14 total across styles,
techniques, and progression). A Cowork session with browser access to those three sites
should be able to pull matching photos you already own and swap each placeholder for a
real `<img src="...">` — either hotlinked to the existing URL on your site, or downloaded
and committed into an `/assets/` folder in this repo (safer long-term — a hotlink breaks
if you ever reorganize the source site's image paths).
