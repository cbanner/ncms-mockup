# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML/CSS mockup presentation for Nashua Community Music School (NCMS) board strategic planning. These mockups demonstrate a proposed digital presence refresh aligned with three strategic pillars: Boost Storytelling, Build Infrastructure, and Bridge Communities.

## Running the Project

No build system required. To view mockups:
- Open `index.html` or `index2.html` directly in a browser
- Or run a local server: `python3 -m http.server`

## Key Files

- **index.html** - Main homepage mockup with before/after comparison
- **index2.html** - Sub-page template mockups
- **Digital Presence Refresh - Strategic Recommendations.md** - Strategic guidance document
- **NCMS Schema Markup Implementation Guide.md** - SEO/structured data for Squarespace implementation

## Technology

- Vanilla HTML5 and CSS3 (all CSS is inline in `<style>` tags)
- Google Fonts: Fraunces (serif) for headings, Source Sans 3 (sans-serif) for body
- No JavaScript, no build tools, no dependencies

## Design System

NCMS brand colors defined as CSS custom properties:
- `--ncms-green: #1a7a4c` (primary)
- `--ncms-green-dark: #145f3b`
- `--ncms-green-light: #e8f5ee`
- `--warm-cream: #faf8f5`
- `--gold-accent: #c9a227`

## Target Platform

These mockups are designed for eventual implementation on Squarespace. The schema markup guide provides copy-paste JSON-LD for Squarespace's Code Injection feature.
