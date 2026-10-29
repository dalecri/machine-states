# Machine States

A family of small isometric machine animations for product states: loading, compressing, exporting, importing, cleaning. One component API, one set of state names, interchangeable machines.

**Live:** heycristobal.com/machine-states/ (once Pages is enabled on this repo: Settings, Pages, deploy from `main`, root)

## The family rules

- **One API for every machine:** `mountMachine(el, options)`, `setProgress(0..1)`, `setState(name)`, `play()`. A host app swaps machines without changing its own code.
- **Six states, always the same names:** `idle`, plus working phases, `done`, `error`. Each state sets machine motion, caption, subline, and optional button as one unit. Captions and file details are data, never hard-coded in the artwork.
- **Motion:** easing curves, never linear, for anything mechanical; moving parts leave a 2-frame fade trail instead of hard cuts; `prefers-reduced-motion` collapses a machine to a static done-state pose.
- **Build:** single HTML files, vanilla JS and inline SVG, no frameworks, no CDN, no images. Palette travels as CSS variables (`--machine-dark`, `--machine-light`, `--plate`, `--paper`, `--accent`, `--ground`, `--ink`, `--muted`) so a host app can re-theme every machine at once.

## Machines

| # | Machine | Job it does | Status |
|---|---|---|---|
| 1 | The Press | Compressing, squeezing a file down (pitch-deck.pdf, 4.2 MB to 1.1 MB) | Built, in `index.html` |
| 2 | Conveyor Scanner | Imports, batch processing, organizing, one item at a time | Prompt written, build pending |
| 3 | Washing Machine | Cleaning up, deduping, tidying a library | Prompt written, build pending |

## The page

`index.html` is the family demo: the Press live at the top, the state grid, a progress slider wired to `setProgress`, and stub frames for the machines still to come. Open it with `?demo=1` for the full harness.

Prompts for the family live in Cris's files (`isometric-machine-animations-prompt`, `conveyor-scanner-animation-prompt`, `washing-machine-animation-prompt`, all Oct 29, 2026) and are candidates for the vault's Prompts shelf.
