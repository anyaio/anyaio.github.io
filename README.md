# anya.io

Anya's portfolio. Jekyll site, deployed to GitHub Pages by GitHub Actions.

## How it works

- `source` branch holds the site. Every push to `source` builds and deploys it
  (`.github/workflows/pages.yml`). Progress: the **Actions** tab on GitHub.
- `master` holds the built site that GitHub Pages serves. The workflow overwrites it; never edit it by hand.
- The whole page lives in `_layouts/default.html`. The **Works** grid and the
  pop-ups are generated from the files in `_posts/`, newest first.

## Add a new work (from the GitHub website)

1. Upload the picture to `img/portfolio/Uploads/`.
   Optional: a smaller square copy with the same name to `img/portfolio/Uploads/Thumbs/`.
2. In `_posts/`, click **Add file → Create new file**, name it
   `YYYY-MM-DD-short-name.markdown` (e.g. `2026-09-29-eco-room-1.markdown`), paste:

   ```yaml
   ---
   title: Eco Room Level Blockout
   layout: default
   date: 2026-09-29
   img: Uploads/eco-room-1.jpg
   thumbnail: Uploads/Thumbs/eco-room-1.jpg   # optional, img is used if missing
   alt: Eco Room Level Blockout
   category: 3D
   description: "Work-in-progress render"
   ---
   ```
3. Commit to `source`. The site updates in about a minute.

## Run locally

```sh
bundle install
bundle exec jekyll serve   # http://localhost:4000
```
