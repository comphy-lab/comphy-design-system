# CoMPhy Lab Design System — SKILL.md

Use this when producing ANY artifact (web page, microsite, slide deck, figure card) for the CoMPhy Lab.

## Start every file

1. Load the self-hosted webfont pack (canonical SoT in this repo’s `fonts/`):

```html
<link rel="stylesheet" href="fonts/fonts.css">
```

Copy or symlink the whole `fonts/` directory (css + woff2 + `OFL.txt`). Do **not** load Google Fonts, Bunny, or other third-party font CDNs.

2. Link `tokens.css`. Do not redefine tokens locally — reference the CSS variables.

3. On `<html>` add `data-theme="light"` (default) or `data-theme="dark"`. The token file handles the rest.

## The non-negotiables

- **Paper, not white.** `background: var(--c-paper)` on body. Never `#fff`.
- **Teal is the only interactive accent.** Buttons, focus rings, hover states all resolve to `--c-accent-teal`. Do not introduce new hues.
- **Hero gradient is for the hero only.** The four-stop gradient clips into Cormorant Garamond on the lab name / page title and nowhere else. Never on chrome, body text, or UI.
- **Four font roles:** Cormorant Garamond = hero / display. Fraunces = headings. IBM Plex Sans = body / UI. IBM Plex Mono = code / DOI / email. Do not rename these families or fall back to system-ui for body.
- **Panel radius stays at 28 px** (`--r-lg`). Do not shrink it to fit more content.
- **Eyebrows are always purple + uppercase + tracked.** Use `<span class="eyebrow">…</span>`.

## Composition rules

- Lead a section with an eyebrow, then an h2 in Fraunces, then a `.lede` paragraph. Body paragraphs sit max `--maxw-read` (68ch) wide.
- Use `<strong>` sparingly — it resolves to coral and is meant to mark the *one* noun that matters in a sentence (author last name, key term).
- Put DOIs, emails, numbers, and equation references in `<code class="copyable">…</code>` so they're clickable-to-copy.
- Wrap large content sections in `.panel` (translucent, blurred) and nest `.card` inside for inner items.

## Voice

Plain words, specific nouns. Write like a methods section, not a press release.

- ✅ "Bubble bursting seeds jet instability above Oh ≈ 0.03."
- ❌ "Discover the fascinating world of bursting bubbles."

## When in doubt

Open `CoMPhy Design System.html` and copy the closest pattern. The guide has: buttons, chips, inputs, paper cards (featured paper), news rows, team tiles, metric cards, bento hero, and header/nav chrome — all rendered from `tokens.css`.
