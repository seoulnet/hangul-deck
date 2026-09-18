# 한글 연습 — Hangul Study Deck

A self-contained Korean flashcard + spelling-practice web app. No build step,
no dependencies, no backend. Works offline once installed.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The whole app (HTML + CSS + JS in one file) |
| `sw.js` | Service worker — offline caching + installable PWA |
| `manifest.webmanifest` | App name, colours, icons for "Install app" |
| `icons/` | App icons (192, 512, Apple touch) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |

## Publish on GitHub Pages

### Option A — no command line

1. Sign in at <https://github.com> and click **New repository**.
   Name it `hangul-deck`, set it **Public**, and create it.
2. On the repo page click **Add file ▸ Upload files**.
3. Drag in **the contents of this folder** — `index.html`, `sw.js`,
   `manifest.webmanifest`, `.nojekyll`, and the whole `icons` folder.
4. Click **Commit changes**.
5. Go to **Settings ▸ Pages**. Under *Build and deployment* set
   **Source: Deploy from a branch**, branch **main**, folder **/ (root)**,
   then **Save**.
6. Wait ~1 minute. Your app is at
   `https://<your-username>.github.io/hangul-deck/`.

### Option B — git command line

```bash
cd hangul-pages
git init -b main
git add .
git commit -m "Hangul Study Deck"
git remote add origin https://github.com/<your-username>/hangul-deck.git
git push -u origin main
```

Then do step 5 above (Settings ▸ Pages).

## Install it as an app

Open the Pages URL on each device:

- **iPhone / iPad (Safari):** Share ▸ **Add to Home Screen**
- **Android (Chrome):** ⋮ ▸ **Install app** (or *Add to Home screen*)
- **Desktop Chrome / Edge:** the **Install** icon in the address bar

After installing it runs full-screen and works with no internet.

## Updating later

Edit `index.html` (or the icons), then **bump the cache version in `sw.js`**
— change `hangul-deck-v1` to `v2`, etc. — and re-upload. Installed copies
pick up the new version the next time they're opened online.

## Moving your deck between devices

Each device stores its own deck and progress in the browser. In
**Manage deck** use **Save to file** / **Load from file** to copy your
cards from one device to another (duplicates are skipped on load).
