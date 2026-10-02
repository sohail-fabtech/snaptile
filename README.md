# Floor Designer

Design an interlocking tile floor in the browser, see exact tile and edge quantities, and download the plan as an image.

No build step, no dependencies — plain HTML, CSS and ES modules.

## Features

- **Room shapes** — rectangle, square, L, U, T, double leg, notched corner, plus; drag walls or type dimensions to resize.
- **Obstacles** — mark areas that don't get tiles.
- **15 tile surfaces** — vented, smooth rib, coin top, diamond plate, vinyl wood, rubber fleck, grass, court grid and more.
- **Patterns & colours** — solid, checker, stripes, argyle, etc.
- **Edges & ramps** — finish the perimeter.
- **Quantities** — full tiles, cut tiles, edges, with a waste allowance (0–15%).
- **Export** — download the design as a PNG.
- Undo/redo, autosave to `localStorage`.

## Run

ES modules need a web server (opening `index.html` from disk won't work):

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

Or use the VS Code Live Server extension.

## Shortcuts

| Key | Action |
| --- | --- |
| `Ctrl/⌘ + Z` | Undo |
| `Ctrl/⌘ + Y` | Redo |
| `+` / `-` | Zoom in / out |
| `0` | Fit to view |
| `Delete` / `Backspace` | Remove selected obstacle |
| `Esc` | Cancel / deselect |

Scroll to zoom, drag empty space to pan.

## Project layout

```
index.html
css/            tokens, layout, sidebar, canvas, summary styles
js/
  main.js       bootstrap: store → renderer → interaction → UI
  config.js     tunable defaults (coverage thresholds, zoom, export size)
  data/         tiles, patterns, layouts, colours, edges
  geometry/     polygons, clipping, tiling, walls, obstacles
  state/        store, actions, history, derived quantities
  render/       camera, scene, tile surfaces, thumbnails
  interaction/  pointer + canvas tools
  ui/           sidebar panels, summary, toolbar, dimension editor
  export/       PNG export
```

## License

[MIT](LICENSE)
