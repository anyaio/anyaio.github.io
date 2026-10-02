# anya.io

Anya's portfolio: https://anya.io

Every change on GitHub publishes itself in about a minute.
Green check in the **Actions** tab = the site is updated.

## Add a work (in the browser, works on Windows)

1. Open https://github.com/anyaio/anyaio.github.io
2. Open `img/portfolio/` → **Add file → Upload files** → drop the picture → **Commit changes**.
   Name it in lowercase with dashes, no spaces: `eco-room-4.jpg`.
3. Open `_posts/` → **Add file → Create new file**.
   Name: date + short name, e.g. `2026-10-02-eco-room-4.markdown`. Paste and edit:

   ```yaml
   ---
   title: Eco Room Level Blockout
   img: eco-room-4.jpg
   category: 3D
   description: Work-in-progress render
   ---
   ```

4. **Commit changes**. Wait for the green check in **Actions**, refresh https://anya.io

Newest works show first.
Optional small preview for the grid: upload it to `img/portfolio/thumbs/` and add `thumb: thumbs/eco-room-4.jpg`.
Red cross in **Actions**: open it, the log names the file to fix.

## Edit or remove

- A work: open its file in `_posts/` → pencil to edit, `...` → **Delete file** to remove.
- Page text (skills, story, contacts): `_layouts/default.html`, pencil → edit → **Commit changes**.

## How it works

Jekyll builds the site from `source` (`.github/workflows/pages.yml`) and pushes it to `master`, which GitHub Pages serves.
Edit `source` only: `master` is overwritten on every deploy.
Preview locally: `bundle install && bundle exec jekyll serve`, then open http://localhost:4000
