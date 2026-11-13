# anya.io

Anya's portfolio: https://anya.io

Everything is done in the browser on github.com. Nothing to install.

## Add a picture to a slideshow

1. Open https://github.com/anyaio/anyaio.github.io/tree/source/img/portfolio
   → **Add file → Upload files** → drop the picture → **Commit changes**.
   Name it in lowercase with dashes, no spaces: `doomsday-8.jpg`.
2. Open https://github.com/anyaio/anyaio.github.io/edit/source/_data/works.yml
   Under `slides` of the project, copy two lines and change them:

   ```yaml
       - img: doomsday-8.jpg
         description: Gameplay screenshot, the tower
   ```

3. **Commit changes**. In a minute the picture shows up on https://anya.io

## Add a project

In the same file, copy a whole block (from `- title` to its last slide) and change it.
`img` is the big main image; the order of blocks is the order on the page.
`slides` is optional. An optional `link` adds a link under the title ("Play the game" unless `link_label` says otherwise, e.g. "View on Steam"); games live in `games/`, outside links open in a new tab.

## Add a 3D model

The small images at the bottom of the page are in `_data/models.yml`. Upload the picture as above, then copy two lines and change them.
To make one rotatable in 3D, upload a `.glb` file to `models/` and add `model: <name>.glb` under it; it floats with no background, and the picture is used only where the model is not.
A picture without a model can get `effect: tilt` instead: it sways and tilts toward the mouse like a 3D card.
Optional `orbit` sets the starting view (e.g. `-40deg 65deg auto`) and `exposure` the brightness (1 = normal).

To edit or remove anything, change or delete its lines in the same file.
Name, role and the Instagram link are in `_layouts/default.html`.

## Something broke

Open the **Actions** tab. A red cross means the site didn't update: open it, the log names the line to fix.
In `works.yml`, keep the dashes and the indents exactly like the lines around them.

## How it works

On every commit to `source`, `.github/workflows/pages.yml` runs Jekyll and pushes the result to `master`, which GitHub Pages serves.
