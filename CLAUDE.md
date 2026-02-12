# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static marketing/landing page for "IronPDF for C++ – Beta Software Program". No build tools, bundler, or package manager — just plain HTML/CSS served directly.

## Tech Stack

- **HTML5** — single `index.html` entry point
- **Bootstrap 5.3** — loaded via CDN (`cdn.jsdelivr.net`)
- **Google Fonts (Montserrat)** — used as Gotham fallback
- **Custom Gotham font files** — in `font/` (woff + woff2, weights: Black, Bold, Book, Medium)
- **CSS** — two custom stylesheets loaded in order:
  1. `css/style.css` — base/custom styles
  2. `css/queries.css` — responsive media-query overrides

## Development

No build step. Open `index.html` in a browser or use any static file server (e.g. `npx serve`, VS Code Live Server).

## Conventions

- Font files use spaces in names (e.g. `Gotham Book.woff2`) — quote paths when referencing them.
- CSS load order matters: Bootstrap first, then `style.css`, then `queries.css`.
