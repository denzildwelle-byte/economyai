# Homepage assets (Figma → site)

Place exported images in this folder so paths in `index.html` resolve correctly.

## Folder structure

```
assets/
├── hero/
│   ├── 0518(1) 4K.mp4       ← hero background video (right side, Figma fill)
│   ├── Ellipse 31.png       ← blue rim (CSS gradient used on site)
│   ├── Ellipse 32.png       ← gold arc reference export
│   ├── hero-visual.png      ← optional fallback still (not used when video present)
│   ├── icon-calendar.svg
│   ├── icon-arrow.svg
│   └── icon-spark.svg
├── services/
│   ├── icon-chatbot.png
│   ├── icon-workflow.png
│   ├── icon-document.png
│   ├── icon-crm.png
│   ├── icon-voice.png
│   └── icon-analytics.png
├── industries/
│   └── agriculture-panel.jpg   ← panel background (add more per industry if needed)
├── icons/
│   └── stars-gold.svg
├── fonts/
│   └── IntegralCF-Regular.woff2   ← display type (export from Figma / license)
└── footer/
    └── logo.svg
```

## Typography (must match Figma)

| Role | Font | Weights |
|------|------|---------|
| Headlines (hero, sections, modal title) | **Integral CF** | 400 (Regular) — self-hosted in `assets/fonts/` |
| UI (nav links, body, badges, buttons) | **Instrument Sans** | 400, 500, 600 — Google Fonts in `index.html` |

Do **not** use Bebas Neue, Inter, or Manrope on homepage content — those were placeholders.

If Integral CF looks wrong, re-export from Figma: select text → right panel → export font or use your licensed `.woff2` files in `assets/fonts/`.

## If automatic download fails (most common: hero image)

Figma MCP asset URLs expire after ~7 days and sometimes cannot be saved by scripts.

### Export from Figma (recommended)

1. Open [Economy-Ai-Agency homepage](https://www.figma.com/design/U1eQwzgAasuERC0CG9ziK5/Economy-Ai-Agency?node-id=200-12567).
2. Select the layer (e.g. hero 3D visual on the right).
3. In the right panel: **Export** → **PNG** @2x → **Export**.
4. Save into the matching folder above using the **exact filename** from this doc.

### Hero visual (important)

- Select node: hero background / 3D slabs (inside **Component 15**).
- Export as `assets/hero/hero-visual.png` (PNG, 2x, transparent or black background).
- Until this file exists, the hero uses a CSS gold gradient fallback.

### Industry panel images

- Default: `assets/industries/agriculture-panel.jpg` (already downloaded).
- For other tabs, export images from Figma and update `hp-ind-img` in JS or add per-tab images later.

## After adding files

1. Hard-refresh the browser (Ctrl+F5).
2. Confirm paths in DevTools → Network (no 404 on `assets/...`).

## Tell the agent

You can say: *“I added `assets/hero/hero-visual.png` from Figma — please wire it up.”* and share the file path if you used a different name.
