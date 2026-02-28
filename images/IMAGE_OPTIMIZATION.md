# Image optimization guide

The portfolio uses **lazy loading** and **preload** so the page loads and scrolls better. For the biggest gain, **compress your image files** so they are smaller in size.

## Quick wins (no code)

1. **Compress JPG/PNG**
   - [TinyPNG](https://tinypng.com/) or [Squoosh](https://squoosh.app/) — drag and drop images; often 50–70% smaller with little visible loss.
   - Do this for all images in `images/` and `images/work/` (replace originals or keep backups).

2. **Resize to max needed size**
   - Gallery thumbnails don’t need 2000px width. Resize to about **800–1200px** on the long edge for gallery images, and **600–800px** for the hero (pic01) and about (radhika) images.
   - Use Photoshop “Save for Web”, Canva export, or [Squoosh](https://squoosh.app/) (Resize tab).

3. **Use WebP for smaller files (optional)**
   - WebP is supported in all modern browsers and is much smaller than JPG/PNG.
   - Convert with [Squoosh](https://squoosh.app/) (output format: WebP) or a batch tool, then you can switch the site to use `.webp` where available (e.g. with a small script or duplicate `<picture>` elements).

## What’s already done in this repo

- **Preload** of the hero image (`pic01.jpg`) so it appears faster.
- **Lazy loading** (`loading="lazy"`) on About and all Gallery images so they load as you scroll.
- **Async decoding** (`decoding="async"`) so image decode doesn’t block the main thread.
- **CSS containment** on the gallery and panels so the browser can optimize layout and paint.

## Suggested workflow

1. Keep original high‑res files in a separate folder (e.g. `images/originals/`).
2. Export **resized + compressed** versions into `images/` and `images/work/`.
3. Re-run compression (TinyPNG/Squoosh) on the exported files.
4. Reload the site and check quality; adjust resize/quality if needed.

After compressing and resizing, the page should load faster and scroll more smoothly.
