# Design

Built world, recorded from `_layouts/default.html` (updated 2026-11-05). Category standard: a dark portfolio where the renders carry all color.

## Tokens

- Ground `neutral-950`; image placeholders `neutral-900`; dividers `neutral-800` hairlines.
- Text: headings `neutral-50`, captions `neutral-100`, meta `neutral-400`. No accent color.
- Type: Schibsted Grotesk (Google Fonts), 400/500/600. Two sizes: `text-2xl` semibold for name and section headings, `text-sm` for everything else.
- Width `max-w-screen-2xl`, gutters `px-5` / `sm:px-8`.

## Components

- **Project:** a section with a full-width main image (up to 85vh), then a row with the `text-2xl` title left and `category · date` right, then a slideshow. Projects are split by a hairline.
- **Slideshow:** horizontal scroll-snap row of 16:9 crops with the description below each, 88% wide on mobile and 62% from `md`, so the next slide peeks in. Touch and trackpad scroll natively, a mouse drags, arrow keys and round prev/next buttons step; a `n / total` counter sits bottom-left.
- **Lightbox:** one shared native `<dialog>`, image `object-contain` up to 82dvh, caption with description and `n / total`, round prev/next at the sides and close top-right. Steps through the whole project and wraps; arrow keys and swipe work. Backdrop click or Esc closes. Fade 300ms ease-out via `@starting-style`.
- **Links:** underline with `neutral-600` decoration, brighten on hover. Focus: 2px `neutral-100` outline, offset.

## Rules

- Styling is Tailwind v4 from the CDN (`@tailwindcss/browser`), no build step. Theme tweaks live in the `<style type="text/tailwindcss">` block.
- Content comes only from `_data/works.yml`; no per-work HTML.
- No cards, eyebrows, gradients or accent color: the work is the color.
