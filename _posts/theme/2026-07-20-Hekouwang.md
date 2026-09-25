---
layout: theme
title: "Hekouwang"
category: theme
author: "huiyonghkw"
thumbnail: hekouwang.png
homepage: "https://github.com/huiyonghkw/hekouwang-typora-theme"
download: "https://github.com/huiyonghkw/hekouwang-typora-theme/archive/refs/heads/main.zip"
description: "A warm off-white theme (light + dark) reproducing the reading experience of Claude's desktop app. Generated from a token file, zero !important, 100 KB of bundled fonts, and CJK/Latin mixing that follows what the app actually does."
tags: [light, dark, clean, cjk, minimal, reading]
typora-root-url: ../../
---

# Hekouwang for Typora

A warm off-white theme (light **and** dark) built for long reading sessions, reproducing the reading
experience of Claude's desktop app.

The CSS is **generated from a token file** rather than hand-written — every color, size and
spacing value lives in `scripts/tokens.json`, and `scripts/build.py` emits the stylesheet.

## Design principles

Built for people who stare at a Markdown editor for hours:

- **No high-saturation accent colors.** Inline code uses a low-saturation warm brown, not a
  bright red. A paragraph with eight inline code spans should still read as text, not as a
  rash of colored blocks.
- **Hierarchy from size, weight and spacing — not color.** No colored accent bars, no heavy
  borders, no decorative rules.
- **Borders are ink at low alpha**, never flat gray. A flat `#ccc` on a warm background reads
  as a dead, muddy line.
- **Tighter tracking as size grows.** `h1` at `-0.022em`, body at `0`.
- **Compact but not cramped.** Line height `1.62`, paragraph gap `0.78rem`.

## CJK / Latin mixing

Anthropic Sans contains **581 glyphs and zero CJK characters** — not even the ideographic
comma. So Chinese text necessarily falls back to the system face. That is not a compromise;
it is exactly what the desktop app does. This theme therefore pairs a Latin face with the
system CJK face and **bundles no CJK font at all**.

The font stack degrades in three tiers: Anthropic Sans (only if already present on your
system — proprietary, never bundled) → **Inter** (SIL OFL, Latin subset, 100 KB, shipped) →
system UI font. Tier 2 is what almost everyone sees.

## Customization

Don't edit the CSS; it's generated. Edit `scripts/tokens.json` and rebuild:

```bash
python3 scripts/build.py
```

The build refuses to emit CSS that violates two Typora rules, so a bad edit fails loudly
instead of silently breaking the editor:

- **zero `!important`** — `#write` specificity is sufficient
- **zero `px` font sizes except the root** — otherwise Typora's font-size preference stops
  working

## Relationship to the existing "Claude Theme"

There is already a [Claude Theme](https://theme.typora.io/theme/Claude-Theme/) in the gallery
with a similar goal. **This is an independent implementation, not a fork** — no CSS was
copied, and the stylesheet is machine-generated from a token file. Both themes reference
Anthropic's published brand colors, which is where any color overlap comes from.

Measurable differences, reproducible from both repositories:

| | Existing Claude Theme | Hekouwang |
|---|---|---|
| Authoring | 3,158 hand-written lines | generated from a token file |
| `!important` declarations | 397 | **0** (enforced at build time) |
| Font sizes | some `px` | all `rem` except root |
| Bundled fonts | ~24 MB (full Noto Serif SC variable) | **100 KB** (Inter, Latin subset) |
| Anthropic fonts | bundled and redistributed | **not bundled**; `local()` + Inter fallback |
| Body CJK | Noto Serif SC (serif) | system sans-serif |
| Latin weights | single 400 → synthetic bold | true variable **300–800** + `opsz` axis |
| Page background | `#faf9f5` | `#fdfdfc` |
| UI coverage | mainly the editor pane | sidebar, file tree, outline, search panel, focus mode |

Two of these are worth explaining:

**Body CJK.** The existing theme sets `#write { font-family: var(--font-serif) }`, rendering
Chinese in Noto Serif SC — a serif. The desktop app renders Chinese in the system sans-serif
(it has no choice, given the glyph coverage above). Matching the app means *not* bundling a
CJK serif, which is also why this theme is 100 KB instead of 24 MB.

**Page background.** `#faf9f5` is Anthropic's cream, but it is the *window/sidebar* color.
Sampling the app's conversation pane gives `#fdfdfc`. This theme uses `#fdfdfc` for the editor
pane and `#f5f4ed` for the sidebar, preserving the app's two-level relationship.

## Licensing note

This theme does **not** bundle, redistribute or include any Anthropic font. Anthropic Sans and
Anthropic Serif are proprietary to Anthropic PBC with no open license. Only Inter (SIL OFL
1.1) is shipped. The theme is an independent work inspired by the app's reading experience,
not affiliated with or endorsed by Anthropic PBC.

## Installation

1. Download and unzip the theme.
2. Copy `theme/hekouwang.css`, `theme/hekouwang-dark.css` and the `theme/hekouwang/` folder
   into Typora's theme folder.
3. **Quit Typora completely and relaunch** (switching themes does not reload a modified CSS
   file), then select **Hekouwang** from the Themes menu.

## Platform support

Designed and tested on **macOS**. Not fully tested, but should work for Windows/Linux.
This theme does not include styles for the Windows "unibody" style.

## Dark variant

`hekouwang-dark.css` is **sampled** from the app's dark mode, not derived by inverting the
light theme — which matters, because the light theme's relationships do not survive inversion:

- In dark mode the **sidebar (`#262626`) is lighter than the editor pane (`#1f1f1e`)** — the
  reverse of the light theme. Inverting would have gotten this backwards.
- Inline code sits on a **neutral white overlay** in dark (solving for alpha gives a consistent
  0.036/0.040/0.031 across channels), rather than the brand-orange wash used in light (which
  would solve inconsistently: 0.043/0.10/0.12).
- Border and shadow base colors swap: ink-at-low-alpha in light, white-at-low-alpha in dark.

Both variants are generated from the same token file; the `dark` block overrides only the
`color` and `alpha` groups.
