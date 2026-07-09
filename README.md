# Pikachu — Pure CSS Mascot

A hand-coded recreation of Pikachu using **only** `<div>` / `<span>` elements
and CSS (`border-radius`, `transform`, `box-shadow`, absolute positioning).
No `<img>`, no SVG, no `background-image`, no art generators.

## What's in this repo

- `index.html` — the markup: every body part (head, ears, cheeks, eyes,
  tail, arms, feet, tail "lightning bolt" segments) is a plain `div`.
- `style.css` — all the styling and shape work, plus a few small idle
  animations (breathing, blinking, cheek pulse, swaying leaves).
- `README.md` — this file.

## Run it locally

No build step needed — it's static HTML/CSS.

```bash
# clone your repo, then just open it
open index.html      # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

Or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to `Deploy from a branch`,
   branch `main`, folder `/ (root)`.
4. Save — GitHub will give you a URL like
   `https://<your-username>.github.io/<repo-name>/`.

Use that URL as the "Live Demo URL" and the repo URL as the
"GitHub Repository URL" when submitting.

## Notes on the technique

- The tail is three rotated, bordered rectangles (`.bolt1/2/3`) layered to
  suggest Pikachu's jagged tail silhouette, plus a brown `.tail-base` patch.
- The ears are tapered rounded rectangles rotated outward from
  `transform-origin: bottom center`, with a black `.ear-tip` div nested
  inside so it rotates together with the ear.
- The face uses layered circles/ovals for the eyes, cheeks and eyebrows, a
  CSS border-triangle for the nose, and a `border-radius` "smile" (plus two
  smaller smiles via `::before`/`::after`) for the mouth.
- Everything responds to `prefers-reduced-motion` by disabling the idle
  animations.
