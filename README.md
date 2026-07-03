# Cosmos — a scroll-morphing particle landing page

A single-file futuristic landing page ("Technology that redefines interaction") built with React 18, Tailwind CSS v4, and an HTML5 Canvas particle engine — no build step, everything lives in [`index.html`](index.html).

## The particle engine

One fixed canvas renders ~2,800 particles that morph between four shapes as you scroll, with light mouse parallax:

1. **Hero** — a glowing energy orb with banded cosmic colors (orange → violet → blue)
2. **Stats** — a twisting double-helix / wormhole column
3. **Growth** — a 3D-perspective terrain wave with a glowing horizon
4. **Ecosystem** — a spinning galaxy whose particles get pulled into the core as you reach the bottom of the page

Plus a drifting, twinkling starfield behind everything. Rendering uses pre-baked radial-gradient glow sprites with additive compositing, and all animation damping is time-based so it feels identical at any frame rate.

## Run it

Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 4173
# → http://localhost:4173
```

Requires internet access (React, Babel, and Tailwind load from unpkg).

## Notes

- Uses `@tailwindcss/browser@4` (the old `cdn.tailwindcss.com` Play CDN no longer resolves)
- Pins `@babel/standalone@7` — Babel 8's React preset emits `import` statements that break with UMD React
