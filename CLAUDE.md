# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A collection of self-contained browser games, each built as a single HTML file with embedded CSS and JS. No build tools, no dependencies, no package manager — just open any `.html` file directly in a browser.

## Architecture

Each game is a standalone `.html` file containing all markup, styles, and logic inline. There is no shared code between files.

- **wildlife-watcher.html** — "David's Wildlife Expedition": a wildlife photography game with 30 real species across 5 habitats. Fetches species/habitat photographs from the Wikipedia REST API (`en.wikipedia.org/api/rest_v1/page/summary/{title}`) at load time. Uses `localStorage` key `wildlifeWatcher` for persistence.
- **tictactoe.html** — Simple two-player tic-tac-toe. No external calls or persistence.

## Development

No build or install step. To test changes, open the file in a browser:
```
open wildlife-watcher.html
```

Wildlife Watcher requires an internet connection on first load (Wikipedia API image fetch). After images load, gameplay works offline for that session.

## Conventions

- All games must remain single-file (HTML + inline CSS + inline JS) with zero external dependencies.
- Wildlife Watcher species data includes a `wiki` field (Wikipedia article title) used for image lookups — keep this accurate when adding/editing species.
- Game state is persisted via `localStorage`. Clearing storage resets progress.

## GitHub

- Remote: `origin` on github.com (ediamond64/CCtest)
- Branch: `main`
