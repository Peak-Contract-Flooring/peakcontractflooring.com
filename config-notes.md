# config.toml — edits to make

After copying the theme's exampleSite (which includes a working `config.toml`),
change these values. Don't replace the whole file — the example config has
theme-specific params worth keeping.

## Basics

```toml
baseURL = "https://www.peakcontractflooring.com/"
title   = "Peak Contract Flooring"
```

## Menu

The example config defines the main menu. Rename/reorder to:

```toml
[menu]
  [[menu.main]]
    name = "Our Work"
    url = "/work/"
    weight = 1
  [[menu.main]]
    name = "Services"
    url = "/services/"
    weight = 2
  [[menu.main]]
    name = "About"
    url = "/about/"
    weight = 3
  [[menu.main]]
    name = "Contact"
    url = "/contact/"
    weight = 4
```

"Our Work" goes first on purpose — it's the strongest asset and the reason
visitors are there. Contact is last, where eyes expect it.

## Colors / fonts

The Hero theme exposes theme colors in config params. Suggested palette for a
flooring brand (warm, wood-adjacent, not a template default):

- Primary accent: deep walnut `#5C4033` or brand color from his logo
- Keep backgrounds white/near-white — the job photos supply the color

## Two small template customizations worth doing (later, not blocking)

1. **Sticky phone + estimate button in the header** (the Signature Custom
   Flooring move). Override `layouts/partials/header.html` by copying it from
   the theme into your site's own `layouts/partials/` and adding a
   `tel:` link + a button to `/contact/`. Site-level layouts override theme
   layouts automatically in Hugo.

2. **PhotoSwipe lightbox on work pages** so gallery photos open full-screen.
   Add the PhotoSwipe CSS/JS include to the work single template. Optional —
   plain images work fine at launch.
