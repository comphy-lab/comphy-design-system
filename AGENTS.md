# comphy-design-system

Core CoMPhy Lab design system: tokens, the living style guide, and the website v2 redesign.

Mirror of the Claude Design project **CoMPhy Lab Design System** (`2cdc2831-a1e8-4e99-977c-ff55c6a1baa1`). Claude Design is upstream for authored design work; this repository is the durable, reviewable record.

## Layout

| Path | Role |
|---|---|
| `tokens.css` | Single source of truth for colour, type roles, spacing, radius and shadow. |
| `fonts/` | Canonical self-hosted webfont pack (`fonts.css`, `*.woff2`, `OFL.txt`). |
| `CoMPhy Design System.html` | Living style guide. Open this first; light/dark toggle top-right. |
| `CoMPhy Website v2.html` | Website redesign answering the red-team audit. |
| `Red Team Audit.html` | 12 findings against comphy-lab.org, with a priority matrix. |
| `CoMPhy Design System (standalone).html` | Self-contained build with assets inlined. Generated — do not hand-edit. |
| `SKILL.md` | Prompt to hand an agent working inside this system. |
| `_ds_manifest.json`, `_ds_bundle.js`, `_adherence.oxlintrc.json` | Claude Design build products. Generated — re-import, do not hand-edit. |
| `assets/`, `uploads/` | Logos, imagery, and source uploads. |

## Rules

- Never redefine a token locally. Reference the CSS variable from `tokens.css`.
- Paper (`--c-paper`), not `#fff`. Teal (`--c-accent-teal`) is the only interactive accent.
- The four-stop brand gradient clips into type on the hero only — never on chrome, body text or UI.
- Changing a core colour here is a cross-repo decision. Check the sibling theme and design-system repos in the `comphy-themes` project before you do it.
- Pull with the `DesignSync` read methods; push with `/design-sync`, one component at a time. Never wholesale-replace the remote project.

See `IMPORT-STATUS.md` for exactly which files came from the live project and which are still outstanding.
