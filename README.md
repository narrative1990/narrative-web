# NARRATiVE — narrative-studio.ai

Website source for [narrative-studio.ai](https://narrative-studio.ai), hosted on Vercel.

## Structure

```
narrative-web/
├── index.html          — Main single-page site
├── vercel.json         — Vercel deployment config
└── assets/
    └── partners/       — Partner logo PNGs (luma-mono.png, kling-mono.png, etc.)
```

## Media Assets

All videos and images are stored as GitHub Release assets in:
👉 [narrative1990/narrative-media-assets](https://github.com/narrative1990/narrative-media-assets/releases/tag/v1)

To update a video: upload new file to a new release, then update the URL in `index.html`.

## Deploy

Push to `main` → Vercel auto-deploys to narrative-studio.ai.

## Missing Assets (TODO)

- [ ] `assets/partners/luma-mono.png`
- [ ] `assets/partners/seedance-mono.png`
- [ ] `assets/partners/kling-mono.png`
- [ ] `assets/partners/runway-mono.png`
- [ ] `assets/partners/higgsfield-mono.png`
- [ ] `assets/partners/artlist-mono.png`
- [ ] `assets/partners/magnific-mono.png`
- [ ] Hero poster image (replace `YOUR_HERO_POSTER_URL` in index.html)
- [ ] Scrub section poster image (replace `YOUR_SCRUB_POSTER_URL` in index.html)
