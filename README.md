# The American Dream Machine

A scrollytelling map of where children grow up to out-earn their parents, and where they do not. [View the live visualization](https://reymuniziii-svg.github.io/american-dream-machine/scrollytelling.html). It runs entirely in the browser on data from the Opportunity Atlas, covering 72,014 Census tracts and 3,171 counties.

The premise: does your zip code determine your destiny? The map lets you scroll the answer county by county, then look up your own.

## What it does

- An 8-step scrollytelling narrative that walks through the major mobility patterns.
- A deck.gl choropleth of every US county, colored by upward-mobility rate.
- A demographic toggle that re-colors outcomes by race and ethnicity.
- A "find your neighborhood" lookup driven by browser geolocation.
- A particle animation ("Life River") that flows over the map between story steps.
- Keyboard navigation: arrow keys to move between steps, number keys to jump.

## Stack

Single self-contained HTML page. No build step, no framework, no package manager. Libraries load from the unpkg CDN at the pinned versions below:

- [MapLibre GL JS](https://maplibre.org) 3.6.2, base map rendering.
- [deck.gl](https://deck.gl) 8.9.33, WebGL choropleth and particle layers.
- [D3.js](https://d3js.org) v7, scales, color, and data shaping.
- [Scrollama](https://github.com/russellgoldenberg/scrollama) 3.2.0, scroll-triggered story steps.
- [Turf.js](https://turfjs.org) v6, geospatial point-in-polygon for the neighborhood lookup.

Fonts: EB Garamond and IBM Plex (Sans and Mono), loaded from Google Fonts.

## Run it locally

No install. Clone, serve the directory over HTTP (a file:// open will not work because the page fetches local JSON), and open the page:

```bash
git clone https://github.com/reymuniziii-svg/american-dream-machine.git
cd american-dream-machine
python3 -m http.server 8080
# then open http://localhost:8080/scrollytelling.html
```

Any static server works; Python is just the one with no dependencies.

## Files

- `scrollytelling.html` The full app: markup, styles, and logic in one file.
- `county_mobility.json` County-level mobility values that drive the choropleth.
- `us-counties.json` County boundary polygons (GeoJSON).
- `particles_optimized.json` Precomputed particle paths for the Life River animation.
- `summary.json` National statistics shown in the narrative (tract and county counts, percentiles).

The raw tract-level CSVs and the Python scripts that produced these JSON files are not tracked (see `.gitignore`); the committed files are the processed output the page consumes.

## Data

Source: the [Opportunity Atlas](https://opportunityinsights.org/data/) from Opportunity Insights and the US Census Bureau, the research program led by Raj Chetty. It tracks roughly 20 million children from birth (cohorts born 1978 to 1983) to age 35 and measures adult outcomes including household income, college attendance, and incarceration, linked back to the neighborhood where each child grew up.

This project visualizes that data and is not affiliated with or endorsed by Opportunity Insights.

## License

MIT. See [LICENSE](LICENSE).

Built by Rey Muniz.
