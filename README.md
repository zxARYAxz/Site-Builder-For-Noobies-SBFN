# Site-Builder-For-Noobies-SBFN
# Site Builder

A step-by-step, no-code website builder with a Persian (RTL) interface. Users answer simple questions ("Do you want a navbar?", "Do you want an ad popup?"), customize each part, watch a live preview, and download a clean, ready-to-use website as a ZIP.

## Features

- **Guided wizard**: one question per screen, with sensible defaults so the site always looks good
- **Live preview** with desktop and mobile views
- **Customization**: accent color (presets or custom), light/dark theme, font, corner style, section order
- **Navigation**: top bar or side drawer (the bar collapses into the drawer on mobile), dark-mode toggle
- **Sections**: hero (with image and button), about, products/services, photo gallery, contact form, footer
- **Products/services**: each item can have a title, price (auto-formatted with thousands separators), description, multiple images, image position (top / side / bottom) and an optional button with a link
- **Ads**: inline banners, closable corner boxes, or popups, with text, image, button, link and delay
- **Images**: uploaded from the device and resized in the browser
- **Clean export**: a ZIP with plain HTML, CSS and a small JS file only when needed

## Exported site structure

```
my-site/
├── index.html
├── css/style.css      # colors and look are controlled by CSS variables at the top
├── js/main.js         # only included if the site needs it (drawer, theme toggle, ads)
├── images/            # uploaded images, replaceable by file name
└── README.txt
```

The exported site has no dependencies and works by opening `index.html`.

## How it works

1. The wizard edits a single configuration object (the user's answers).
2. A generator function turns that object into HTML, CSS and JS strings.
3. The live preview renders those strings in a sandboxed iframe.
4. Export packs the same output (and the images) into a ZIP using [JSZip](https://stuk.github.io/jszip/).

## Run locally

Open `index.html` in a browser. No build step is needed.

## Tech

HTML, CSS and vanilla JavaScript in a single file, plus JSZip (loaded from a CDN).

## Limitations

- Exported fonts use system fonts (e.g. Tahoma) so the output has no external dependencies
- The contact form uses `mailto:` (it opens the visitor's email app)
- Content-heavy sites (blogs with many articles and pagination) are not supported yet

## Roadmap

- Port to SvelteKit + TypeScript
- Sidebar ad column and more section types
- More templates and design presets
- Automated tests for the generator

## License

MIT
