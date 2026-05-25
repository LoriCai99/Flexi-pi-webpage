# YAM paper — landing page

Minimal single-page template inspired by [pi.website/research/rlt](https://www.pi.website/research/rlt). Vanilla HTML + CSS, no build step.

## Preview locally

Any static server works. Easiest:

```bash
cd /Users/loricai/Desktop/YAM-paper
python3 -m http.server 8000
# then open http://localhost:8000
```

Or just open `index.html` directly in a browser (videos require a server to play).

## File layout

```
YAM-paper/
├── index.html         # all page content — edit here
├── styles.css         # design system / colors / typography
└── assets/
    ├── placeholder-*.svg   # swap these for your real media
    ├── hero.mp4            # (add) full-bleed hero video
    ├── method.svg|.png     # (add) architecture diagram
    ├── task1.mp4 … task4.mp4   # (add) experiment clips
    ├── before.mp4, after.mp4   # (add) comparison clips
    └── chart.svg|.png      # (add) headline plot
```

## Customizing

- **Title, authors, date, links** — top of `index.html`, inside `<section class="hero">`.
- **Abstract / intro / method / discussion** — each `<section class="container section">` block.
- **Videos** — drop files into `assets/` and update the `<source src="…">` paths. Each `<video>` is already set to `autoplay muted loop playsinline`, which is what browsers require for inline autoplay.
- **Posters** (the still image shown before a video loads / if it fails) — update each `poster="…"` attribute.
- **Table numbers** — under `<h2>Quantitative results</h2>`.
- **BibTeX** — under `<h2>Citation</h2>`.

## Design tokens

All colors, fonts, and spacing live as CSS variables at the top of `styles.css` (`:root { … }`). Dark mode is automatic via `prefers-color-scheme`.

Content width:
- `--container: 720px` — body text / single-column figures
- `--container-wide: 1040px` — full-bleed hero & nav

## Deploy

Drop the folder onto any static host:

- **GitHub Pages** — push to a repo, enable Pages on the `main` branch.
- **Netlify / Vercel** — drag the folder onto the dashboard, or point at the repo.
- **S3 / Cloudflare Pages** — upload as-is.
