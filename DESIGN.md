# Design

Built world, recorded from `_layouts/default.html` (2026-10-03). Category standard: a dark portfolio where the renders carry all color.

## Tokens

- Ground `neutral-950`; image placeholders `neutral-900`; dividers `neutral-800` hairlines.
- Text: headings `neutral-50`, captions `neutral-100`, meta `neutral-400`. No accent color.
- Type: Schibsted Grotesk (Google Fonts), 400/500/600. Two sizes: `text-2xl` semibold for name and section headings, `text-sm` for everything else.
- Width `max-w-screen-2xl`, gutters `px-5` / `sm:px-8`.

## Components

- **Work tile:** a `<button>` wrapping the image and a caption row (title left, `category · date` right). The newest work spans both columns at up to 78vh; the rest are 16:10 crops in a 2-column grid (1 column on mobile).
- **Lightbox:** native `<dialog>` per work, image `object-contain` up to 82dvh, caption with description, round close button top-right. Backdrop click or Esc closes. Fade/scale 300ms ease-out via `@starting-style`.
- **Early work:** square tiles, 3/5/8 columns, slightly desaturated until hover; same lightbox.
- **Links:** underline with `neutral-600` decoration, brighten on hover. Focus: 2px `neutral-100` outline, offset.

## Rules

- Styling is Tailwind v4 from the CDN (`@tailwindcss/browser`), no build step. Theme tweaks live in the `<style type="text/tailwindcss">` block.
- Content comes only from `_data/works.yml` and `_data/early.yml`; no per-work HTML.
- No cards, eyebrows, gradients or accent color: the work is the color.
