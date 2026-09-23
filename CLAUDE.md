# Conventions for this repo

- Plain HTML and CSS only. No JavaScript, no build step, no framework.
- `index.html` stays at the repo root (GitHub Pages requires it there); the other five pages live in `src/`, the stylesheet lives in `ui/style.css`, and photos live in `images/`. Every link and asset path is relative - never a leading `/`.
- Design tokens (palette, spacing, radius) are CSS custom properties in `ui/style.css`; each page sets its own `--accent` via a class on `<body>`.
- Compress and resize photos before adding them - nothing on the site displays wider than a few hundred pixels, so a 1600px max dimension and JPEG quality ~82 is plenty.
- `DECISIONS.md` and `verification/README.md` are answered in the student's own words - don't fill them in.
