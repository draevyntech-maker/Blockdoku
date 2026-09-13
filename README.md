# Blockdoku

A block-puzzle / sudoku hybrid: drag pieces onto a 9x9 board, clear rows,
columns, or 3x3 boxes to score. No ads, no accounts, no tracking — it's
just files you own.

## Files

- `index.html` — the game
- `manifest.json` — makes it installable as an app icon
- `sw.js` — lets it work offline once loaded
- `icon-192.png`, `icon-512.png` — app icons

## How to play

Drag a piece from the tray onto the board. A green highlight means it
fits there; red means it doesn't. Clear a full row, column, or 3x3 box
to score points and trigger a combo. The game ends when none of your
three current pieces fit anywhere.

## Getting it on your phone

For "Add to Home Screen" to fully work (offline support, standalone
app window, no browser bar), the files need to be served over
`https://`, not opened directly from your Downloads folder. The
easiest free ways to do that:

### Option A — GitHub Pages (free, permanent link)

1. Create a free GitHub account if you don't have one.
2. Create a new repository, e.g. `blockdoku`.
3. Upload all 5 files from this folder into it (GitHub's web UI has an
   "Add file → Upload files" button — no command line needed).
4. Go to the repo's **Settings → Pages**, set the source to the `main`
   branch, root folder, and save.
5. GitHub gives you a URL like `https://yourname.github.io/blockdoku/`.
   Open that on your phone.

### Option B — Netlify Drop (free, fastest, no account needed)

1. On a computer, go to `app.netlify.com/drop`.
2. Drag this whole folder onto the page.
3. It gives you a live URL instantly. Open that on your phone.

### Installing on your phone once it's hosted

**iPhone (Safari):** open the URL → tap the Share icon → "Add to Home
Screen".

**Android (Chrome):** open the URL → tap the ⋮ menu → "Add to Home
screen" or "Install app".

It'll then behave like any other app: its own icon, opens without
browser chrome, and works with the screen off Wi-Fi/data since the
service worker caches it after the first load.

## Customizing

Everything is in `index.html` — one file, plain HTML/CSS/JS, no build
step. A few easy things to tweak near the top of the `<script>` block:

- `COLORS` — the palette used for pieces
- `SHAPES` — the set of piece shapes that can appear
- Scoring math is in `placePiece()` if you want harder/easier scoring
