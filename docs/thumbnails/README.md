# ECIS data explorer — card thumbnails

Ten SVG thumbnails, one per chart type used on the data-explorer cards.
Each file is a standalone SVG (opens in a browser, Illustrator, Figma, Inkscape).

| File | Used by (cards) | Notes |
|---|---|---|
| line-chart.svg | 20 | two series, gridlines, year ticks |
| horizontal-bar-chart.svg | 24 | five ranked bars + faint second series |
| stacked-bar-chart.svg | 1 | 100 % stacked, 3 segments, legend |
| data-table.svg | 21 | coloured header row, zebra rows |
| map.svg | 5 | real Europe outlines (Highcharts map collection, simplified) |
| pie-chart.svg | 3 | donut, 4 slices, legend |
| dumbbell-chart.svg | 3 | Highcharts dumbbell: hollow start / filled end markers |
| big-numbers.svg | 3 | headline figure + sparkline bars |
| people-icons.svg | 1 | pictogram grid, 24 icons |
| pyramid.svg | 1 | women / men population pyramid |

## Specs

* **Canvas** 300 × 200 (3 : 2) — the ECL card image ratio. Everything is drawn in
  this coordinate space and scales with the card width; no raster.
* **Colours** one accent colour only, EC blue `#0E47CB`, with opacity steps
  (1 / .55 / .35 / .25) for secondary series and choropleth shading.
  Background `#F5F7FB`. Greys: axes `#D5DBE5` / `#E3E8EF`, text `#6B7686` / `#9AA5B5`.
* **Typography** Inter (falls back to Arial); sizes 8.5–10 px for labels, 52 px bold
  for the big number. Text in the SVGs is decorative sample text, not data.
* **Size** 1–3 KB each; the map is 18 KB because it carries country outlines.
* **In the app** the same drawings are inlined by Vue (`v-html`) with the accent
  colour as a CSS variable (`--sc`), so a single change recolours all ten.
  The exported files have that variable resolved to `#0E47CB`.
* **Accessibility** thumbnails are `aria-hidden` on the cards — the card title
  carries the meaning. The exports have `role="img"` + `aria-label` so they are
  self-describing when used elsewhere.

## Open questions for the designer

* Sample labels: keep cancer-site names (Breast, Lung…) or go abstract (bars only)?
* Should chart type be visible at all, given the card label now shows study + scenario?
* The map: keep the choropleth look, or a simpler outline to match the flat style of the others?
* One accent colour vs. the scenario colours (coral / blue / purple / green / yellow / pink) — the app can do either.
