# Mika's Adorable Playhouse

A collection of educational games for toddlers and kids, all in one cozy place.

This repo is a set of small, self-contained HTML games plus a single-file dashboard (`index.html`) that finds them automatically and lets kids pick one to play. Add a game, push it, and it shows up. No build step, no config file, no list to maintain.

**[Live site](https://kungpowunicorn.github.io/map/)** or **[Download](https://github.com/KungPowUnicorn/map/archive/refs/heads/main.zip)**

## Features

- **Automatic discovery.** Every `.html` file in the repo, including subfolders, becomes a card.
- **Play inside the dashboard.** Games open in an embedded player with back, previous/next, restart, and fullscreen buttons. Each game has its own URL (`#/folder/game.html`), so links and the browser back button work.
- **Cards show the game's own icon and title**, read from each file's `<title>` and `<link rel="icon">`. Games without an icon get a pastel emoji tile.
- **Sort A–Z or by folder.**
- **Search, favorites, and a random-game button** for quick picking.
- **7 color themes** (5 light, 2 dark), 3 card sizes, and optional sound effects.
- **Keyboard shortcuts:** `/` focuses search, `←` / `→` switch games while playing, `Esc` returns to the grid.
- **Works on desktop and phones.**

## Adding a game

1. Put a self-contained `.html` file anywhere in the repo (root or a subfolder).
2. Give it a `<title>`. That becomes the card's name. Without one, the filename is used.
3. Optionally add an icon: `<link rel="icon" href="...">`. A data URI works well and keeps the game to one file.
4. Push to `main`.

The dashboard refreshes its file list every 10 minutes. Use the ↻ button to rescan immediately.

## Known limitations

- **Repo and branch are hardcoded** to `KungPowUnicorn/map` and `main` in `index.html`. If you fork this, change the `REPO` constant and the branch in the tree URL.
- **Very large repos:** GitHub can truncate the file tree response. The dashboard notes when the list may be incomplete.
- **Embedded games share the same origin**, so two games using the same `localStorage` key can overwrite each other's saved data. Use unique keys per game.
- **Games that redirect the top window** (`window.top.location`) won't behave inside the embedded player. Turn off *Play inside dashboard* in Settings to open games in a new tab instead.
- **New files can appear before Pages has deployed them.** If a card opens a blank page, wait a minute and try again.

## Support

If the Playhouse made someone's day, you can say thanks on [Ko-fi](https://ko-fi.com/kungpowunicorn).

Made with ❤️ by [KungPowUnicorn](https://ko-fi.com/kungpowunicorn).
