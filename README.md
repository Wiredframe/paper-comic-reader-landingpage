# Paper Comic Reader — Landing Page

Marketing landing page for **Paper Comic Reader**, a lean, native iPhone & iPad comic reader that
makes pages read like ink on paper. Single static page, light "apple.com" look with the app's
yellow accent, no framework.

## Stack

- One hand-written `index.html` — markup + inline `<style>` design system + small vanilla-JS blocks.
- **Tailwind CSS v3** compiled ahead of time to `assets/tailwind.css` (committed, so GitHub Pages needs
  no build step). The `<link>` sits after the inline `<style>` so utilities win cascade ties.
- System font stack (SF Pro on Apple devices) — zero web-font files.
- No analytics, no external requests: fully self-contained.

## Develop

```bash
npm install          # once
npm run watch:css    # rebuild assets/tailwind.css on change
python3 -m http.server 8732   # serve, then open http://localhost:8732
```

Before committing markup/class changes, regenerate the CSS:

```bash
npm run build:css
```

## Deploy

GitHub Pages from the repo root (branch `main`, folder `/`). Because `assets/tailwind.css` is committed,
no CI build is required.

## To do before launch

- Fill in the **App Store URL**: edit the single `APPSTORE_URL` constant near the bottom of `index.html`.
  Until it is set, the "App Store" buttons show **Coming soon** and don't navigate.
- The `.ipa` / source buttons point at `github.com/Wiredframe/paper-comic-reader` (releases).

## Assets

- `assets/appicon.png` — app icon (from the app repo).
- `assets/img/1-recents.png … 6-folder.png` — iPhone screenshots, web-optimized.

App © Wiredframe · Ulf Schuster. App source & releases: <https://github.com/Wiredframe/paper-comic-reader>
