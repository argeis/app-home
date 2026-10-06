# App Home

One home screen icon for all of the score pads on this GitHub Pages site. Install **App Home** as the app on your phone, then tap through to May I, Putt Card or Yahtzee. Each one opens full-screen inside the same window, and your phone's back gesture brings you back to the menu.

Why: phone Chrome treats every app on `argeis.github.io` as the same site, so installing each one separately does not work well. App Home sets its scope to the whole site (`"scope": "/"` in `manifest.webmanifest`), so every app lives inside the one installed window.

It is a single HTML page with no build step. Published at:

**https://argeis.github.io/app-home/**

## Install on a phone

- Android (Chrome): open the link, menu, then **Install app** or **Add to Home screen**.
- iPhone (Safari): open the link, share button, then **Add to Home Screen**.

## Adding an app

Edit the `APPS` list at the bottom of `index.html` (name, description, link, colour, icon). Links are relative to `/app-home/`, so `../my-app/` points at `https://argeis.github.io/my-app/`. Then bump `VERSION` at the top of `sw.js` so phones pick up the new copy.

## Deploying

The workflow in `.github/workflows/pages.yml` deploys on every push to `main`. Pages must be enabled once in the repo: Settings → Pages → Source: *GitHub Actions*.

## Files

- `index.html` – the launcher
- `manifest.webmanifest` – PWA name, colours, icons and the site-wide scope
- `sw.js` – service worker that caches the launcher for offline use
- `icons/` – app icons
