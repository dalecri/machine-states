# Machine States

A family of small isometric machine animations for product states: loading, compressing, exporting, importing, cleaning. One component API, one set of state names, interchangeable machines.

**Live:** heycristobal.com/machine-states/ (once Pages is enabled on this repo: Settings, Pages, deploy from `main`, root)

## The family rules

- **One API for every machine:** `mountMachine(el, options)`, `setProgress(0..1)`, `setState(name)`, `play()`. A host app swaps machines without changing its own code.
- **Six states, always the same names:** `idle`, plus working phases, `done`, `error`. Each state sets machine motion, caption, subline, and optional button as one unit. Captions and file details are data, never hard-coded in the artwork.
- **Motion:** easing curves, never linear, for anything mechanical; moving parts leave a 2-frame fade trail instead of hard cuts; `prefers-reduced-motion` collapses a machine to a static done-state pose.
- **Build:** single HTML files, vanilla JS and inline SVG, no frameworks, no CDN, no images. Palette travels as CSS variables (`--machine-dark`, `--machine-light`, `--plate`, `--paper`, `--accent`, `--ground`, `--ink`, `--muted`) so a host app can re-theme every machine at once.

## Machines

| Machine | Job it does | Where it lives |
|---|---|---|
| The Press | Compressing, squeezing a file down (pitch-deck.pdf, 4.2 MB to 1.1 MB) | In `index.html` |
| Conveyor Scanner | Imports, batch processing, organizing, one item at a time | In `index.html`; standalone Grok build at `conveyor/` |
| Washing Machine | Cleaning up, deduping, tidying a library | In `index.html` (as `washer`) |
| Envelope Sealer | Sealing, sending, submitting | In `index.html` (as `sealer`) |
| Printer | Printing, rendering, exporting to paper | In `index.html` (as `printer`) |
| Typewriter | Writing, drafting, retyping | In `index.html` (as `typewriter`) |
| Distiller | Summarizing, condensing, extracting | In `index.html` (as `distiller`) |
| Coffee Machine | Waiting states, brewing, warming up | In `index.html` (as `coffee`) |
| Claw Sorter | Picking, sorting, retrieving one item from many | Standalone Grok build at `claw/` |
| Vending Machine | Checkout, credits, claiming a reward | Built, standalone at `vending/` |
| Subway | Data arriving and being sent: the train arriving is receiving, departing is sending, doors open is the exchange | Built, standalone at `subway/` |

## The page

`index.html` is the family demo: eight machines registered in one file (press, conveyor, sealer, washer, printer, typewriter, distiller, coffee), a machine picker, a progress slider wired to `setProgress`, and a per-machine state grid. Open it with `?demo=1` for the full harness. Four machines also exist as standalone builds with their own state labs: `conveyor/` and `claw/` (Grok builds), `vending/`, and `subway/`. Every page carries a small Pages nav linking the five. Prompts for the family live in Cris's files (press, conveyor, washer, vending; Oct 29, 2026) and are candidates for the vault's Prompts shelf.
