# Import status

Imported from Claude Design project `2cdc2831-a1e8-4e99-977c-ff55c6a1baa1` ("CoMPhy Lab Design System") on **2026-08-09**.

## Provenance

Two sources were used, because the DesignSync read path caps a single file at 256 KiB and returns content through the agent context:

- **live** — pulled fresh from the Claude Design project today.
- **april-export** — copied byte-for-byte from the 2026-04-24 export at
  `comphy-lab.github.io/comphy-lab-design-system/project/`.

`tokens.css` and `README.md` were pulled live **and** diffed against the April export: both were byte-identical. That parity is the evidence for trusting the April export for the remaining shared files.

| File | Source |
|---|---|
| `tokens.css` | live |
| `README.md` | live |
| `_ds_manifest.json` | live |
| `_adherence.oxlintrc.json` | live |
| `SKILL.md` | april-export |
| `CoMPhy Design System.html` | april-export |
| `CoMPhy Website v2.html` | april-export |
| `Red Team Audit.html` | april-export |
| `CoMPhy Design System (standalone).html` | april-export (5.2 MB — over the 256 KiB read cap) |
| `assets/**`, `uploads/**` | april-export |

## Outstanding

| File | Why | Fix |
|---|---|---|
| `_ds_bundle.js` | Not yet pulled | Re-run a DesignSync `get_file`, or let the Claude Design self-check regenerate it |
| `CoMPhy Design System (standalone).html` | Generated build with prior Google Fonts inlined | Re-generate from the living guide after DesignSync; do not hand-edit |

`_ds_manifest.json` was re-serialised through `jq -c`, so it is semantically identical to the remote but not necessarily byte-identical. It is a generated file; the next self-check will normalise it.

## Webfont pack (added in-repo SoT)

Canonical self-host tree (not from Claude Design):

| Path | Source |
|---|---|
| `fonts/fonts.css` + `fonts/*.woff2` (14 faces) | `comphy-lab/club` `assets/css/fonts.css` + `assets/fonts/` (urls rewritten to `url(./…)` for co-located layout) |
| `fonts/OFL.txt` | `comphy-lab/qr-codes` `site/assets/fonts/OFL.txt` |

Demos load `fonts/fonts.css` locally. Google Fonts CDN is no longer the documented install path.
