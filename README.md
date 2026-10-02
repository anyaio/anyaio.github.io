# anya.io

Anya's portfolio. Live at https://anya.io

Every change to the `source` branch publishes itself in about a minute.
Watch it in the **Actions** tab: green check means the site is updated.

## Add a new work in the browser (Windows, nothing to install)

1. Open https://github.com/anyaio/anyaio.github.io and check the branch says `source`.
2. Go to `img/portfolio/Uploads/` → **Add file → Upload files** → drop the picture → **Commit changes**.
   Name pictures in lowercase with dashes, no spaces: `eco-room-4.jpg`.
3. Optional: upload a smaller square copy with the same name to `img/portfolio/Uploads/Thumbs/`.
   Without it the grid uses the big picture.
4. Go to `_posts/` → **Add file → Create new file**.
   Name it `YYYY-MM-DD-short-name.markdown`, for example `2026-10-02-eco-room-4.markdown`.
5. Paste this and change the values:

   ```yaml
   ---
   title: Eco Room Level Blockout
   layout: default
   date: 2026-10-02
   img: Uploads/eco-room-4.jpg
   thumbnail: Uploads/Thumbs/eco-room-4.jpg
   alt: Eco Room Level Blockout
   category: 3D
   description: "Work-in-progress render"
   ---
   ```

6. **Commit changes**. Open the **Actions** tab, wait for the green check, refresh the site.

Delete the `thumbnail:` line when there is no small copy.
Keep the three dashes `---` at the top and bottom.
Put the description in quotes.

If the Actions run turns red, open it: the log names the file and line to fix.

## Edit a work

Open its file in `_posts/`, click the pencil, change, **Commit changes**.
To remove a work, open its file → `...` menu → **Delete file**.

## Edit the page itself

All the text (skills, story, contacts) lives in `_layouts/default.html`.
Edit it the same way: pencil → change → **Commit changes**.

## Preview on your own computer (optional)

1. Install Ruby from https://rubyinstaller.org (Ruby+Devkit 3.3, x64). Tick "Run ridk install" at the end, press Enter.
2. Install GitHub Desktop from https://desktop.github.com and clone `anyaio/anyaio.github.io`.
3. In GitHub Desktop: **Repository → Open in Command Prompt**, then run:

   ```
   bundle install
   bundle exec jekyll serve
   ```

4. Open http://localhost:4000. The page refreshes when you save a file.
5. Happy with it? In GitHub Desktop write a summary, **Commit to source**, then **Push origin**.

## How it works

- `source` holds the site: Jekyll 4. The Works grid and pop-ups come from `_posts/`, newest first.
- `.github/workflows/pages.yml` builds `source` and pushes the result to `master`.
- GitHub Pages serves `master`. The workflow overwrites it on every run, so edit `source` only.
