# CoMPhy Lab — Design System

A shared visual language for the Computational Multiphase Physics Lab: the group site, per-paper microsites, seminar pages, and internal tools.

## Files

| File | Purpose |
|---|---|
| `CoMPhy Design System.html` | Living style guide — open this first. Light/dark toggle top-right. |
| `tokens.css` | **The single source of truth.** Drop this into any project + load the three Google fonts and you have the system. |
| `SKILL.md` | Prompt to hand to Claude when working inside this system. |

## Direction at a glance

- **Paper before pixels.** Body surface is warm off-white `#f3efe8`, never pure white. Screens should feel like good editorial print.
- **One accent, not four.** Deep teal `#254c4a` is the interactive accent (buttons, focus, hover). The brand purple / blue / coral stay for content emphasis.
- **Three type families, one job each.**
  - **Cormorant Garamond** — hero headline only, clipped against the four-stop brand gradient.
  - **Source Serif 4** — every other heading.
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
- `sl25` (Science Line 2025 deck) — warm paper surface, deep teal accent, Source Serif 4, soft grid, 28-px panel radius.
- `app/YatraDeck` — component patterns (paper cards, news rows, team tiles).

— Maintained by V. Sanjay · Durham University
