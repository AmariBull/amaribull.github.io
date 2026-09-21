# Plan: pastel lifestyle blog (P1)

## Context
P1 is due Tue Sep 22. The site is a personal blog about food and restaurants, movies and TV, sports, and crochet/crafts, modeled on youngadventuress.com: a photo-card home page, a personal intro, and one dedicated page per interest. The template started as a one-page "Hello, world" (`index.html`, `style.css`, `.nojekyll`, `DECISIONS.md`, `RESOURCES.md`). Decisions made: plain HTML + CSS (no Jekyll), six pages, colored placeholders instead of photos for now, soft pastel and cozy look.

## Pages (all in repo root, relative links only)
- `index.html`: hero with site name and tagline, short "hi, I'm ..." intro with a link to About, a "fun facts" strip (3-4 stat tiles, like the reference's "100 countries"), a 4-card grid linking to each topic, a "latest picks" card row, footer.
- `about.html`: the story, a "currently into" list, a favorites grid.
- `food.html`: intro, "go-to spots" recommendation cards (name, cuisine, rating, one-line why), "what I'd order", a "want to try" list.
- `media.html`: Movies and TV as two labeled sections, poster-style cards (aspect-ratio 2/3), "watch this if you like ...", a currently-watching list.
- `sports.html`: teams I follow, favorite moments, a season or game-day calendar block.
- `crafts.html`: crochet projects as a gallery, a "pattern favorites" list, a materials list.
- Every page shares one header: site name plus nav (Home, About, Food, Movies & TV, Sports, Crafts), with the current page marked `aria-current="page"`. It also shares one footer. With no templating, the header and footer are copied into each page. That is the known cost of the plain-HTML choice.

## Design system (`style.css`, one file)
- Custom properties on `:root`: pastel palette (cream background, blush pink, butter yellow, sage, sky, lavender, and a dark plum text color), radius, shadow, spacing scale. Each topic page sets a `--accent` on `<body class="food">` and so on, so one stylesheet gives each page its own color.
- Type: a rounded, friendly Google Fonts pairing (handwritten display face for headings, clean rounded sans for body) with system-font fallbacks, so the page still reads if the fonts fail to load.
- HTML and CSS features: CSS Grid (`auto-fit, minmax()`) for card grids, flexbox nav, `aspect-ratio` for image blocks, `clamp()` for fluid type, sticky header, hover lift and tilt on cards, wavy SVG section dividers, `<details>/<summary>` accordions, `<figure>/<figcaption>`, and a `prefers-reduced-motion` guard.
- Placeholders: `.ph` blocks with a pastel gradient and a caption, so swapping in a real photo means replacing the `.ph` div with an `<img>` inside the same wrapper.
- Accessibility: one `<h1>` per page, a skip link, visible focus rings, alt text on every real image, dark plum text on light backgrounds for contrast.
- Mobile first: the nav wraps with no JavaScript. No JS anywhere unless something clearly needs it.
- Light theme only. The template's `color-scheme: light dark` is dropped because the pastel palette is not designed for dark mode.

## Content rules
- No invented personal facts. Placeholder copy is clearly marked (for example "[Your favorite ramen spot]") so real names, opinions and stats get filled in by the site's owner.
- The repo is public: no address, phone number, or other people's photos without permission. Image files go in `images/` only once supplied.

## Files
Create: `about.html`, `food.html`, `media.html`, `sports.html`, `crafts.html`, `images/.gitkeep`, this `PLAN.md`.
Rewrite: `index.html`, `style.css`.
Update: `README.md` (live Pages URL at the top).
Leave alone: `.nojekyll`, `.gitignore`, `RESOURCES.md`, and `DECISIONS.md` (the owner writes every answer, especially question 3).

## Build order (each step is checked before the next)
1. Design tokens, base styles, shared header and footer in `style.css`.
2. Build `index.html` and check it locally.
3. Copy the shell to the five other pages and fill in each page's layout.
4. Responsive pass at phone and desktop widths.
5. Commit in small steps and push to `main`.
6. Verify on the live URL.

## Verification
- Local: `python -m http.server 8000` in this folder, then open every page, click every nav link, and shrink the window to phone width.
- Browser console: no red 404s, CSS and font requests succeed, no link starts with `/`.
- After pushing, wait a few minutes, then `curl -s https://<username>.github.io/food.html` and confirm the new content, and open the URL in an incognito window.
- `verification/` holds `screenshot.png` (live URL bar visible), `fetch.txt`, and a three-line `README.md` (URL, time, what would have made the check fail).
- Still owed on Canvas: the 3-5 minute video and three classmate comments.

## Open items
- Confirm the repo is named `<username>.github.io` and Pages is on.
- Real names, opinions and photos for each page; they can be swapped in after the layout works.
