# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static marketing landing page for IronPDF for C++ beta program. The page is built with vanilla HTML, CSS, and Bootstrap 5, with no build process or JavaScript framework.

## Architecture

### HTML Structure (index.html)
- Single-page layout with navigation, hero section, features, and signup forms
- Bootstrap 5.3.2 used for grid system and navbar component
- Two signup forms (banner and bottom) for beta program registration
- Commented-out navigation code remains in lines 50-90 (legacy design)

### CSS Organization
1. **style.css** - Base styles with mobile-first approach
   - CSS custom properties (`:root`) define color palette and typography
   - Gotham font family (self-hosted woff/woff2 files in `/fonts`)
   - Montserrat (Google Fonts) as fallback
   - Key layout technique: `.hero-wrapper` contains nav + hero + banner with `.hero-image-wrap` positioned absolutely to span full height
   - Animation keyframes defined for entrance effects

2. **queries.css** - Responsive overrides only
   - Breakpoints align with Bootstrap 5: sm(576px), md(768px), lg(992px), xl(1200px), xxl(1400px)
   - Mobile-first approach: base styles work for mobile, queries adjust for larger screens
   - Handles reduced-motion preference

### Design System
Color scheme defined in css/style.css:38-59:
- Dark purple backgrounds (`--clr-bg-darkest`, `--clr-bg-dark`, `--clr-bg-mid`)
- Accent colors: pink (#e01a59), purple-light (#c6aac6), teal (#89d3df), gold (#fda509)

### Asset Structure
- `/fonts` - Gotham font files (Book, Medium, Bold, Black weights)
- `/images` - Page images and SVG graphics
- `/images/logos` - Logo assets

## Development Workflow

### Viewing the Page
Open `index.html` directly in a browser (no server required)

### Git Status
There are uncommitted changes:
- Modified: css/style.css, index.html
- Untracked: "css/style copy.css", "index copy.html"

The copy files appear to be backups and may be candidates for removal or `.gitignore`.

## Key Implementation Notes

### Hero Section Layout
The hero uses a wrapper pattern (css/style.css:211-323) where:
- `.hero-wrapper` contains navigation, hero content, and signup banner
- `.hero-image-wrap` is absolutely positioned (top:0, right:0, bottom:0) to span the entire wrapper height
- Navigation has `position: relative` (not absolute) so it flows naturally
- Image has `z-index: 3`, text content has `z-index: 5`

### Responsive Behavior
- Desktop (≥992px): Image visible on right side, two-column layouts
- Tablet/Mobile (<991px): Hero image hidden, single-column layout, signup forms stack vertically

### Typography
Prefer using Gotham font weights:
- 400 (Book) for body text
- 500 (Medium) for medium emphasis
- 700 (Bold) for headings and buttons
- 800 (Black) for hero titles and section headings

### Accessibility Features
- `visually-hidden` class for screen reader text (css/style.css:112-119)
- `:focus-visible` outline styling (css/style.css:121-124)
- ARIA labels on navigation and sections
- Semantic HTML5 elements
