# anya.io

Anya's portfolio: https://anya.io

Everything is done in the browser on github.com. Nothing to install.

## Add a work

1. Open https://github.com/anyaio/anyaio.github.io/tree/source/img/portfolio
   → **Add file → Upload files** → drop the picture → **Commit changes**.
   Name it in lowercase with dashes, no spaces: `eco-room-4.jpg`.
2. Open https://github.com/anyaio/anyaio.github.io/edit/source/_data/works.yml
   Copy the top block, paste it above, change the text:

   ```yaml
   - title: Eco Room Level Blockout
     img: eco-room-4.jpg
     date: Oct 2, 2026
     category: 3D
     description: Work-in-progress render
   ```

3. **Commit changes**. In a minute the work shows up on https://anya.io

To edit or remove a work, change or delete its block in the same file.
Page text (skills, story, contacts) is in `_layouts/default.html`.

## Something broke

Open the **Actions** tab. A red cross means the site didn't update: open it, the log names the line to fix.
In `works.yml`, keep the dash and the two-space indent exactly like the blocks around it.

## How it works

On every commit to `source`, `.github/workflows/pages.yml` runs Jekyll and pushes the result to `master`, which GitHub Pages serves.
