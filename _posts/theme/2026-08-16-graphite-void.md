---
layout: theme
title: "Graphite Void"
category: theme
author: "Vojtech Foukal"
thumbnail: "graphite-void.png"
preview: "graphite-void.png"
homepage: "https://github.com/vofo/typora-theme-graphite-void"
download: "https://github.com/vofo/typora-theme-graphite-void/archive/refs/heads/main.zip"
description: "Near-black theme for long writing and coding sessions — WCAG + APCA verified contrast, centered ~80-character column, serif prose with sans headings."
tags: [dark, focus, writing, serif, night]
---

# Graphite Void

A neutral near-black theme (`#111112`) tuned for long editing sessions on high-contrast displays. Every foreground/background pair is verified against both WCAG 2.x and APCA — bright enough to read fluently, never bright enough to glow.

## Features

- **Near-black, never pure black**: `#111112` (L\*≈5) avoids the halation and mini-LED blooming that pure `#000` causes, while staying darker than typical dark modes.
- **Halation-safe text**: dimmed gray `#CFCFCC` at 12.1:1 / APCA Lc 77 — the fluent-reading band, below the glow zone.
- **Centered readable column**: 40–42 rem ≈ 75–85 characters per line instead of full-window lines.
- **Serif prose · sans structure · mono code**: Charter body, SF Pro headings, JetBrains Mono fences — all with graceful fallbacks (all-sans fallback is one section-delete away).
- **Built on Night's skeleton**: uses Typora's built-in dark code-block and source-mode styles, so nothing extra is required.

## Installation

1. Download and unzip this theme.
2. Open Typora **Settings/Preferences → Appearance → Open Theme Folder**.
3. Copy `graphite-void.css` into the theme folder.
4. Restart Typora and select **Graphite Void** from the Themes menu.

Fonts are macOS-first; on Windows/Linux the theme falls back to your system serif/sans — colors and layout are unaffected.
