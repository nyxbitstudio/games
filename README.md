# nyxbit games

The public arcade for [nyxbit studio](https://github.com/nyxbitstudio) games, served with GitHub Pages at <https://nyxbitstudio.github.io/games/>. This repo contains published builds only — game sources live in private repos. All rights reserved.

## How to add a game

1. Bundle and minify the game's entry module into a new subfolder named after its id:
   `npx esbuild path\to\src\shell\main.js --bundle --minify --format=iife --outfile=<id>\game.min.js`
2. Copy the game's `index.html` into the same subfolder and point its script tag at the bundle: `<script src="game.min.js"></script>` (drop `type="module"` — the bundle is an IIFE).
3. Add an entry to the manifest in `games.js` (`id`, `title`, `tagline`, `accent`).
4. Make sure the game's save-data keys are game-prefixed (e.g. `smi.station.v1`) — every game here shares the `nyxbitstudio.github.io` localStorage origin.
5. Commit and push. Pages redeploys automatically.
