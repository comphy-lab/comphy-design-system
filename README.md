# CoMPhy Lab — Design System

A shared visual language for the Computational Multiphase Physics Lab: the group site, per-paper microsites, seminar pages, and internal tools.

## Files

| File | Purpose |
|---|---|
| `CoMPhy Design System.html` | Living style guide — open this first. Light/dark toggle top-right. |
| `tokens.css` | **The single source of truth for colour, type roles, spacing, radius, shadow.** |
| `fonts/` | **Canonical self-hosted webfont pack.** Copy/link this directory + `tokens.css`. |
| `fonts/fonts.css` | `@font-face` sheet (latin + latin-ext, `font-display: swap`). |
| `fonts/OFL.txt` | SIL Open Font License texts for the shipped faces. |
| `SKILL.md` | Prompt to hand to an agent when working inside this system. |

## Install (consumers)

```html
<link rel="stylesheet" href="fonts/fonts.css">
<link rel="stylesheet" href="tokens.css">
```

Do **not** use `fonts.googleapis.com`, `fonts.gstatic.com`, Bunny, or other font CDNs. Vendor from this repo’s `fonts/` pack.

### Faces shipped

| Family | Role | Weights / styles |
|---|---|---|
| Cormorant Garamond | Hero / display | italic 500, normal 600 |
| Fraunces | Headings | normal 600 |
| IBM Plex Sans | Body / UI | normal 400, 500, 600 |
| IBM Plex Mono | Code | normal 400 |

Each face includes latin + latin-ext woff2. Provenance: fuller pack from `comphy-lab/club`; licence text from `comphy-lab/qr-codes`.

## Direction at a glance

- **Paper before pixels.** Body surface is warm off-white `#f3efe8`, never pure white. Screens should feel like good editorial print.
- **One accent, not four.** Deep teal `#254c4a` is the interactive accent (buttons, focus, hover). The brand purple / blue / coral stay for content emphasis.
- **Four type families, one job each.**
  - **Cormorant Garamond** — hero headline only, clipped against the four-stop brand gradient.
  - **Fraunces** — every other heading.
  - **IBM Plex Sans** — body, UI, captions. Plex Mono for code, DOIs, emails.
- **Restraint beats density.** 28-px panel radius + 32-px background grid overlay give air. Do not fill it.

## Tokens to know

```css
/* The five you'll use every day */
--c-paper          /* #f3efe8 — body */
--c-surface-strong /* #fffdf9 — cards */
--c-accent-teal    /* #254c4a — CTAs, focus */
--c-brand-purple   /* #68236d — H1, logo */
--fg-strong        /* #0f0c08 — headings */
```

Flipping `<html data-theme="dark">` rewires paper/ink without touching components. Brand hues stay intact.

### Coral as text

`--c-accent-coral` (`#cf4900`) is the fill: swatches, chip grounds, avatar gradients. It is not body text. On 13 Oct 2026 it measured 3.97:1 on `#f3efe8` and 4.48:1 on `#fffdf9` (WebAIM, WCAG 2). Both fail AA for normal text. `#f3efe8` is `--c-paper`, and it is the panel colour named in that audit. This system's `.panel` is glass; its rendered light ground is `#fcfaf5`, which is a separate, lighter surface.

Text on those surfaces uses `--c-accent-coral-text`. In light mode that is `#c04400`, the same hue (about 21°) darkened until it clears 4.5:1. `<strong>` and other coral text, including thesis links, use this token. Dark mode sets the text token back to `#cf4900`. The fill does not change in either theme.

The coral chip keeps the 10% fill tint. That tint renders darker than the surface under it (`#efddd0` on paper, `#f7e7db` on the light panel), so the light label is `#b03c00` (same hue). Dark chip text stays `#ff9966`.

| Pair | Before `#cf4900` | After (light) |
|---|---|---|
| On `#f3efe8` paper, the audited panel | 3.97:1 fail | `#c04400` 4.50:1 pass |
| On rendered light `.panel` `#fcfaf5` | — | `#c04400` 4.94:1 pass |
| On `#fffdf9` | 4.48:1 fail | `#c04400` 5.08:1 pass |
| Chip label on rendered tint `#efddd0` (over paper) | — | `#b03c00` 4.55:1 pass |
| Chip label on rendered tint `#f7e7db` (over the light panel) | — | `#b03c00` 4.98:1 pass |

## The three class names you need

```html
<section class="panel">          <!-- translucent scholarly surface, r-lg -->
  <span class="eyebrow">…</span>  <!-- uppercase tracked, purple -->
  <h2>…</h2>
  <p class="lede">…</p>
  <a class="btn" href="…">Read the paper</a>
  <a class="btn-ghost" href="…">PDF</a>
  <span class="chip chip--brand">Soft Matter · 2026</span>
</section>
```

Everything else in the guide (`paper-card`, `news-row`, `team-tile`, `bento-hero`) is a composition of these.

## Voice

Plain words, specific nouns, no marketing verbs. Write like a good methods section.

- ✅ *"We investigate non-Newtonian free-surface flows."*
- ❌ *"Unlocking the secrets of fluids."*

## Assets

- `assets/logos/` — primary mark, favicon, partner logos (Basilisk, Physics of Fluids, Durham). Partner marks are monochrome/white only.
- `assets/images/` — hero photography + figure placeholders.

## Source material

This system is a fusion of:
- `comphy-lab.github.io` — brand colors, gradient, Cormorant hero treatment.
- `sl25` (Science Line 2025 deck) — warm paper surface, deep teal accent, soft grid, 28-px panel radius.
- `app/YatraDeck` — component patterns (paper cards, news rows, team tiles).
- `comphy-lab/club` — self-hosted webfont pack adopted as SoT here.

— Maintained by V. Sanjay · Durham University
