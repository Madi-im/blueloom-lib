
# Blueloom — ready-to-deploy static site

This package contains a simple static version of Blueloom Library suitable for GitHub Pages.

## What's included
- `index.html`
- `assets/styles.css`
- `assets/app.js`
- `favicon.svg`
- `404.html` (redirects to index.html)

## How to deploy (quick)
1. Unzip the archive.
2. On GitHub, open your repository and click **Add file → Upload files**.
3. Drag **all files and folders inside the unzipped folder** (index.html, assets, favicon.svg, 404.html).
   - Make sure `index.html` is at the repository root (not inside a `dist` folder).
4. Commit.
5. Settings → Pages → Branch: `main` (or `gh-pages`), Folder: `/root`.
6. Visit `https://your-username.github.io/your-repo-name/`.

If your repo will use client-side routing, the included `404.html` helps redirect to the SPA.

