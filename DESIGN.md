# Design

Built world, recorded from `_layouts/default.html` (updated 2026-11-05). Category standard: a dark portfolio where the renders carry all color.

## Tokens

- Ground `neutral-950`; image placeholders `neutral-900`; dividers `neutral-800` hairlines.
- Text: headings `neutral-50`, captions `neutral-100`, meta `neutral-400`. No accent color.
- Type: Schibsted Grotesk (Google Fonts), 400/500/600. Two sizes: `text-2xl` semibold for name and section headings, `text-sm` for everything else.
- Width `max-w-screen-2xl`, gutters `px-5` / `sm:px-8`.

## Components

- **Project:** a section with a full-width main image (up to 85vh), then a row with the `text-2xl` title left and `category · date` right, then an optional link ("Play the game" or `link_label`) and an optional slideshow. Projects are split by a hairline.
- **Slideshow:** horizontal scroll-snap row of 16:9 crops with the description below each, 88% wide on mobile and 62% from `md`, so the next slide peeks in. Touch and trackpad scroll natively, a mouse drags, arrow keys and round prev/next buttons step; a `n / total` counter sits bottom-left.
- **3D Models:** last section, `text-2xl` heading and a row of three small square tiles (pictures cropped to 800×800) with the title below, no dates. Width capped at `max-w-3xl`; stays 3 columns on mobile. A model with a `.glb` shows as a `<model-viewer>` (Google model-viewer 3.5.0 from jsDelivr, loaded only when one exists) with no background or shadow, so it floats on the page ground; auto-rotating, drag to orbit, no zoom, vertical page scroll kept on touch; no poster, a small "3D" label sits top-left. Per-model `orbit` and `exposure` set the start view and brightness (Bolgarka: -40deg 65deg, 1.3). A picture with `cutout` + `depth` (Bathroom, whose model is lost) is drawn by a small WebGL depth-parallax shader: background cut out, near parts shift more than far ones, gentle sway by itself, follows the mouse on hover, still for reduced motion, plain cutout picture without WebGL; no "3D" label, opens the original render in the lightbox. It opens no lightbox.
- **Lightbox:** one shared native `<dialog>`, image `object-contain` up to 82dvh, caption with description and `n / total`, round prev/next at the sides and close top-right. Steps through the whole project and wraps; arrow keys and swipe work. Backdrop click or Esc closes. Fade 300ms ease-out via `@starting-style`.
- **Links:** underline with `neutral-600` decoration, brighten on hover. Focus: 2px `neutral-100` outline, offset.

## Rules

- Styling is Tailwind v4 from the CDN (`@tailwindcss/browser`), no build step. Theme tweaks live in the `<style type="text/tailwindcss">` block.
- Content comes only from `_data/works.yml` and `_data/models.yml`; no per-work HTML.
- No cards, eyebrows, gradients or accent color: the work is the color.
