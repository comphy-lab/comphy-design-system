# CoMPhy Lab Design System — SKILL.md

Use this when producing ANY artifact (web page, microsite, slide deck, figure card) for the CoMPhy Lab.

## Start every file

1. Load the three Google fonts in one call:

```html
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@600&family=IBM+Plex+Sans:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400&family=Source+Serif+4:opsz,wght@8..60,400;8..60,600&display=swap" rel="stylesheet">
```

2. Link `tokens.css`. Do not redefine tokens locally — reference the CSS variables.

3. On `<html>` add `data-theme="light"` (default) or `data-theme="dark"`. The token file handles the rest.

## The non-negotiables

- **Paper, not white.** `background: var(--c-paper)` on body. Never `#fff`.
- **Teal is the only interactive accent.** Buttons, focus rings, hover states all resolve to `--c-accent-teal`. Do not introduce new hues.
- **Hero gradient is for the hero only.** The four-stop gradient clips into Cormorant Garamond on the lab name / page title and nowhere else. Never on chrome, body text, or UI.
- **Three font roles:** Cormorant = hero. Source Serif 4 = all other headings. IBM Plex Sans = everything else. Plex Mono for code/DOI/email.
- **Panel radius stays at 28 px** (`--r-lg`). Do not shrink it to fit more content.
- **Eyebrows are always purple + uppercase + tracked.** Use `<span class="eyebrow">…</span>`.

## Composition rules

- Lead a section with an eyebrow, then an h2 in Source Serif, then a `.lede` paragraph. Body paragraphs sit max `--maxw-read` (68ch) wide.
- Use `<strong>` sparingly — it resolves to coral and is meant to mark the *one* noun that matters in a sentence (author last name, key term).
- Put DOIs, emails, numbers, and equation references in `<code class="copyable">…</code>` so they're clickable-to-copy.
- Wrap large content sections in `.panel` (translucent, blurred) and nest `.card` inside for inner items.

## Voice

Plain words, specific nouns. Write like a methods section, not a press release.

- ✅ "Bubble bursting seeds jet instability above Oh ≈ 0.03."
- ❌ "Discover the fascinating world of bursting bubbles."

## When in doubt

Open `CoMPhy Design System.html` and copy the closest pattern. The guide has: buttons, chips, inputs, paper cards (featured paper), news rows, team tiles, metric cards, bento hero, and header/nav chrome — all rendered from `tokens.css`.
