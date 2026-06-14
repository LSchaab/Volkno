# VolKno Landing Page

A fully responsive landing page built in **plain HTML + CSS** — no build tools, no npm, no frameworks. Just open it in a browser.

## How to open it

Double-click `index.html`, or from a terminal:

```bash
open index.html        # macOS
```

That's it. Nothing to install or compile.

> Tip: if you edit a file and the browser doesn't update, just refresh the page (⌘R).

## Project structure

```
Volkno/
├── index.html          The whole page (all sections, top to bottom)
├── css/
│   ├── tokens.css      Design tokens: colors, fonts, spacing (change values here)
│   ├── base.css        Reset, typography, buttons, layout helpers
│   ├── gradients.css   The hero mesh gradient + section backgrounds
│   └── sections.css    Layout for nav, hero, cards, footer, etc.
├── assets/
│   ├── logo/           VolKno logo
│   ├── icons/          Inline-ready SVG icons
│   └── images/         ← drop dashboard/chart screenshots here (see below)
└── Resources/          Original design exports (charts, personas, dashboard)
```

## The hero gradient

The hero background is a **mesh/blob gradient** recreated in pure CSS (not an image), so it stays crisp at any size. It lives in `css/gradients.css` under `.hero-bg`.

To fine-tune it, open the page next to the Figma hero and nudge each `radial-gradient`'s position (`at X% Y%`), size, and color. Each one is commented (purple, magenta, red, coral, orange, glow).

Want a subtle animated drift? Add the class `hero-bg--animated` to the hero section. It automatically turns off for visitors who prefer reduced motion.

## Adding the remaining images

A couple of sections use **labelled placeholders** until you supply the real image. To fill one in:

1. Export the image from Figma (PNG or WebP).
2. Save it in `assets/images/` using the filename shown in the placeholder.
3. In `index.html`, replace the `<div class="media media--placeholder">…</div>` with:

   ```html
   <div class="media">
     <img src="assets/images/your-file.png" alt="Describe the image" loading="lazy" />
   </div>
   ```

**Naming convention:** `assets/images/<section>-<description>.png`
Currently expected:

| File | Used in section |
|------|-----------------|
| `dashboard-summary.png` | "Custom-tailored, fully integrated summaries" |
| `sdk-preview.png` | "Our software development kit" |

## Changing colors, fonts, or spacing

Everything is driven by tokens in `css/tokens.css`. For example, to change the
hero's purple blob, edit `--color-blob-purple`. To change body spacing rhythm,
edit the `--space-*` scale. Change once, updates everywhere.

## Notes / not yet wired

- The **contact form** is markup + styling only. Connecting it to email or a
  backend (e.g. a form service) is a separate step.
- Section copy is placeholder-quality where the final wording wasn't in the
  design — refine the text directly in `index.html`.
