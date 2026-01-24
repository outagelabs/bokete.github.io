# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static GitHub Pages website for **Bokete** - an iOS pothole detection and reporting app. The site serves as a marketing landing page with bilingual support (English/Spanish) and ASCII art-themed design.

## Architecture

### Content Structure
- **Landing pages**: `index.html` (English), `index-es.html` (Spanish)
- **Legal pages**: `tos.html`, `tos-es.html` (Terms of Service), `privacy.html`, `privacy-es.html` (Privacy Policy)
- **Markdown sources**: `Terms of Use.md`, `Privacy Policy.md` (source documents for legal pages)
- **Styling**: Single shared `style.css` with responsive breakpoints
- **Assets**: App screenshots, promotional images, audio samples, app icon

### Design System
- **Theme**: ASCII art / terminal aesthetic with monospace fonts (Courier New)
- **Color scheme**: Black on white with box-drawing characters for borders
- **Mobile-first**: Four responsive breakpoints (768px, 480px, 375px)
- **Typography**: All content uses monospace fonts for consistency

### Bilingual Support
Parallel page structure for English and Spanish:
- Navigation links between languages on each page
- Consistent URL patterns: `page.html` / `page-es.html`
- Translated meta tags for SEO and social sharing

## Development Commands

### Serving Locally
```bash
# Python 3 built-in server
python3 -m http.server 8000

# Open in browser
open http://localhost:8000
```

### Generating App Store Images
```bash
# Create promotional images with ASCII art overlays
python3 create_appstore_images.py
```

**Image generation script** (`create_appstore_images.py`):
- Creates 1242×2688px App Store screenshots
- Overlays ASCII art headings on preview images
- Generates both English and Spanish versions
- Requires PIL/Pillow library
- Hardcoded base path: `/Users/hector/code/bokete.github.io`

## File Conventions

### HTML Pages
- All pages include Open Graph and Twitter Card meta tags
- Navigation structure: HOME | TERMS OF SERVICE | PRIVACY POLICY
- Language switcher at top of each landing page
- Footer includes legal links and copyright notice

### CSS Responsive Breakpoints
- Desktop: default (max-width: 900px container)
- Tablet: `@media (max-width: 768px)`
- Mobile: `@media (max-width: 480px)`
- Small mobile: `@media (max-width: 375px)`

### ASCII Art
- Logo uses box-drawing characters (╔ ═ ╗ ║ ╚ ╝ █)
- Section headers formatted as: `┌─ TITLE ─────...─┐`
- List bullets use `▸` character
- Maintained in `create_appstore_images.py` for promotional images

## Important Notes

- **No build system**: Plain HTML/CSS served directly by GitHub Pages
- **No JavaScript**: Site is purely static content
- **Jekyll disabled**: `.nojekyll` file present to bypass Jekyll processing
- **Git workflow**: Main branch serves as deployment branch
- When updating legal pages, edit both the `.md` source and corresponding `.html` files
- App Store link placeholder (`href="#"`) needs updating when app is published
- Governing law: Delaware (per Terms of Service)

## Assets Location
- Screenshots: `preview-*.png`
- Promotional: `appstore-*.png`
- App icon: `app-icon.png` (1024×1024)
- Audio samples: `voice-*.wav`, `voice-*.aiff`
