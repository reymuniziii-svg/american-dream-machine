# The American Dream Machine

**Does your zip code determine your destiny?**

Interactive visualization exploring how childhood neighborhoods shape adult economic outcomes across 72,000 US neighborhoods.

## Live Demo

[View the visualization](https://reymuniziii-svg.github.io/american-dream-machine/scrollytelling.html)

## Features

- **Life River** — canvas animation of 5,000 lives flowing through the income ladder over 35 years, with live "rose from poverty / fell from wealth" counters
- **Scrollytelling Narrative** — 8-step guided story revealing mobility patterns
- **Interactive Choropleth** — native MapLibre GL map of 3,000+ US counties, hoverable and clickable throughout the story
- **Demographic Toggle** — see how outcomes differ by race/ethnicity
- **Find Your Neighborhood** — search with live autocomplete (county, city, state, or ZIP) plus geolocation lookup
- **County Report Card** — real metrics only: mobility percentile, incarceration rate, outcomes by race *and* gender, county outline mini-map
- **Best & Worst Leaderboards** — the 10 highest- and lowest-mobility counties, one click away
- **Keyboard Navigation** — arrow keys and number keys, scoped so they never hijack typing

## The Story

The visualization reveals:

1. **The Rural Advantage** — Highest mobility is in rural Great Plains
2. **The Urban Challenge** — Major cities show limited mobility
3. **The Hyperlocal Reality** — Outcomes vary dramatically within cities
4. **The Demographic Divide** — Same place, different outcomes by race

## Data Source

[Opportunity Atlas](https://opportunityinsights.org/data/) — Census Bureau + Opportunity Insights

- 20 million children tracked from birth (1978-1983) to age 35
- 72,000 Census tracts analyzed
- Outcomes: household income, college attendance, incarceration

## Tech Stack

- [MapLibre GL JS](https://maplibre.org) — the only runtime library, vendored in `vendor/` so the site has no CDN script dependencies
- Hand-rolled scroll stepper (IntersectionObserver), point-in-polygon geolocation, and SVG mini-map projection — no deck.gl, D3, Turf, or Scrollama needed
- CARTO dark basemap with an automatic offline fallback style

## Files

- `scrollytelling.html` — Main visualization (self-contained app)
- `index.html` — Redirect so the root URL works
- `county_mobility.json` — County-level mobility data
- `summary.json` — National statistics + top/bottom counties
- `us-counties.json` — US county boundaries (GeoJSON, quantized to ~110m precision)
- `particles_optimized.json` — Life River particle paths
- `vendor/` — MapLibre GL JS (pinned, local)

## Local Development

```bash
python3 -m http.server 8080
# Open http://localhost:8080/scrollytelling.html
```

## Credits

Created by Rey Muniz using data from Raj Chetty's Opportunity Insights project.

## License

MIT (visualization code). MapLibre GL JS is BSD-3-Clause, see `vendor/maplibre-gl-LICENSE.txt`.
