# Brand Pages

<p align="center"><b>Motion</b> &nbsp;·&nbsp; <b>Scroll</b> &nbsp;·&nbsp; <b>Visuals</b> &nbsp;·&nbsp; <b>Story</b></p>

> Brand experiences you scroll *through*, not past.

A collection of contemporary, sleekly technical brand and landing pages. Each one treats the product as the hero of a short film you direct with the scroll wheel: a living WebGL backdrop, a product that travels between scenes, and copy that arrives, holds and leaves on cue.

**Live:** [Draconis · No. 113](https://afrinhaque19-beep.github.io/brand-pages/draconis/)

Every page is a self-contained static site in its own folder. There is no build step and no framework; open a folder, serve it, and it runs.

---

## The pages

| Page | Brand | What it is | Live | Folder |
| --- | --- | --- | --- | --- |
| **Draconis** | Draconis · No. 113 and No. 114 | A men's eau de parfum launched against the Flying Dragon Nebula (Sh 2-113). The bottle drifts through a live nebula, the fog parts under your cursor, and the sky shifts colour with each chapter, from hydrogen red to cobalt and violet. | [**View live →**](https://afrinhaque19-beep.github.io/brand-pages/draconis/) | [`/draconis`](./draconis) |

<p align="center">
  <img src="draconis/b113.webp" alt="Draconis No. 113 bottle" height="220">
  &nbsp;&nbsp;
  <img src="draconis/b114c.webp" alt="Draconis No. 114 Cobalt bottle" height="190">
  &nbsp;&nbsp;
  <img src="draconis/b114v.webp" alt="Draconis No. 114 Violet bottle" height="190">
</p>

---

## What the pages have in common

- **A living backdrop.** The background is a real photograph rendered through a WebGL shader: drifting gas, twinkling stars, colour grading per chapter, and fog that reacts to the pointer and the scroll.
- **Choreographed scroll.** One GSAP ScrollTrigger timeline moves the camera, the sky and the product between hand-set poses. Each scene arrives, holds while you read, then hands over to the next.
- **Product as the main character.** The product image is a single fixed element that travels through every scene, so the page feels like one continuous shot rather than a stack of sections.
- **Built for every screen.** Desktop gets side-by-side compositions. Phones and portrait tablets get a layout of their own, with copy pinned low and the product sized to fit the space left above it.
- **Considerate by default.** Respects `prefers-reduced-motion`, works with touch, keeps type readable at every width, and falls back to a still image when WebGL isn't available.

## Tech

- Plain HTML, CSS and JavaScript, one `index.html` per page
- WebGL 1 shaders (no Three.js)
- [GSAP 3](https://gsap.com) with ScrollTrigger, loaded from cdnjs
- [Lenis](https://github.com/darkroomengineering/lenis) for smooth wheel scrolling on desktop
- Google Fonts

## Running a page locally

The pages read their images into WebGL, which browsers block on `file://` URLs. Serve the folder over HTTP instead:

```bash
cd draconis
python3 -m http.server 8000
# then open http://localhost:8000
```

Any static server works (`npx serve`, VS Code Live Server, and so on).

## Publishing

Each folder can be deployed as-is to any static host: GitHub Pages, Netlify, Vercel, Cloudflare Pages or an S3 bucket. This repository is published with GitHub Pages, so each folder is served at `https://afrinhaque19-beep.github.io/brand-pages/<folder>/`.

## Adding a new brand page

1. Create a folder named after the brand, in lowercase (for example `/aurelia`).
2. Put the page's `index.html` and every asset it uses inside that folder, using relative paths.
3. Add a `README.md` in the folder describing the concept, the scenes and how to customise it.
4. Add a row to the table above.

## Notes

The brands, prices and product details on these pages are concept work, written to show the experience. Product photography and background imagery belong to their respective owners; see each page's README for credits.
