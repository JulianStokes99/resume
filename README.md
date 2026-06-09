# Resume

Julian Stokes — portfolio site, deployed to GitHub Pages.

The site is built by the reusable [`ahzs645/portfolioThemes`](https://github.com/ahzs645/portfolioThemes)
engine. This repo only holds the content (`CV.yaml`) and a thin workflow that calls the engine.

## How it works

- `CV.yaml` — all portfolio content. Edit this to update the site.
- `.github/workflows/deploy.yml` — calls the reusable `deploy-portfolio.yml` workflow on every
  push to `main`, builds the site, and deploys it to GitHub Pages.

The deploy uses `build-mode: random-static`. Internally the engine writes these env vars into
`.env.production` before building:

```
VITE_THEME_SELECTION_MODE=random   # random theme on every fresh load
VITE_SHOW_THEME_BAR=false          # no top bar
```

## Setup (one time)

In the repo on GitHub: **Settings → Pages → Build and deployment → Source = GitHub Actions.**

After that, every push to `main` redeploys. You can also trigger it manually from the
**Actions** tab (Deploy Portfolio → Run workflow).

## Updating content

Edit `CV.yaml`, commit, and push to `main`
